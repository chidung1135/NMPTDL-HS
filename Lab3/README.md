# LAB 3: Làm Sạch Dữ Liệu Cơ Bản (Data Cleaning)

## Giới thiệu

Dự án này thực hiện các bước làm sạch và xử lý dữ liệu bệnh nhân từ tập dữ liệu `patient_heart_rate.csv`. Các vấn đề về chất lượng dữ liệu được xác định và giải quyết một cách có hệ thống.

## Tập dữ liệu

**Tệp gốc:** `patient_heart_rate.csv`

**Các cột:**
- `Id`: Mã định danh bệnh nhân
- `Age`: Tuổi
- `Weight`: Cân nặng
- `m0006, m0612, m1218`: Huyết áp nam giới (00-06, 06-12, 12-18 giờ)
- `f0006, f0612, f1218`: Huyết áp nữ giới (00-06, 06-12, 12-18 giờ)
- `Firstname`, `Lastname`: Tên người bệnh
- `Sex`: Giới tính
- `Time`: Khoảng thời gian đo

## Các Vấn Đề Xử Lý

### 1. **Missing Header** 
   - Giải pháp: Thêm tên cột thủ công khi đọc tệp CSV

### 2. **Dòng dữ liệu rỗng toàn bộ**
   - Giải pháp: Sử dụng `df.dropna(how='all', inplace=True)`

### 3. **Dữ liệu thiếu (Missing Values)** 
   - Các cột: `Age`, `Weight`, `PulseRate`
   - Giải pháp áp dụng (theo độ ưu tiên):
     - Thay bằng trung bình cộng giữa giá trị liền trước và liền sau
     - Thay bằng trung bình 2 giá trị liền trước
     - Thay bằng trung bình 2 giá trị liền sau
     - Thay bằng trung bình của người đó
     - Thay bằng trung bình theo giới tính
     - Thay bằng giá trị mức ổn định

### 4. **Dữ liệu không hợp lệ**
   - Cân nặng: Chuyển đổi từ `lbs` → `kgs`
   - Thay thế ký hiệu `-` bằng `NaN`

### 5. **Một cột chứa quá nhiều thông tin**
   - Phân rã cột `m0006` thành: `Sex` (m/f) và `Time` (00-06)
   - Kết quả: `PulseRate` (huyết áp)

### 6. **Tên người bệnh cần phân tách**
   - Từ: `Name` → Thành: `Firstname`, `Lastname`

## Kết Quả

**Tệp đầu ra:** `patient_heart_rate_clean.csv`

- **Số dòng:** 71 dòng dữ liệu sạch
- **Số cột:** 8 cột (Id, Firstname, Lastname, Age, Weight, Sex, Time, PulseRate)
- **Cải thiện:** 100% dữ liệu hợp lệ sau xử lý

## Các Bước Thực Hiện

```python
# 1. Tải dữ liệu
df = pd.read_csv("patient_heart_rate.csv", names=column_names)

# 2. Xóa dòng rỗng
df.dropna(how="all", inplace=True)

# 3. Xử lý dữ liệu thiếu
# - Chuyển đổi đơn vị cân nặng
# - Thay thế ký hiệu không hợp lệ

# 4. Xử lý giá trị thiếu trong PulseRate
# - Sử dụng nhiều phương pháp thay thế

# 5. Sắp xếp và chuẩn hóa dữ liệu
df = df[['Id', 'Firstname', 'Lastname', 'Age', 'Weight', 'Sex', 'Time', 'PulseRate']]
df = df.sort_values(by=['Id', 'Time']).reset_index(drop=True)

# 6. Lưu dữ liệu sạch
df.to_csv("patient_heart_rate_clean.csv", index=False)
```

## Công Nghệ Sử Dụng

- **Python 3.x**
- **Pandas**: Xử lý và phân tích dữ liệu
- **NumPy**: Các phép toán số học
- **Google Colab**: Môi trường thực thi