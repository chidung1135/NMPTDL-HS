# LAB 2: Phân tích dữ liệu

## Công nghệ và thư viện sử dụng

Bài lab được thực hiện bằng các công nghệ và thư viện sau:

- Python: Ngôn ngữ lập trình chính, dễ học và mạnh mẽ trong phân tích dữ liệu.

- NumPy: Hỗ trợ xử lý mảng số, phép toán vector và tính toán số học nhanh.

- Pandas: Thư viện cốt lõi để làm việc với dữ liệu dạng bảng (DataFrame), hỗ trợ đọc file, lọc, thống kê và biến đổi dữ liệu.

- Matplotlib / Seaborn (nếu có): Dùng để trực quan hóa dữ liệu thông qua các biểu đồ.

- Jupyter Notebook: Môi trường làm việc tương tác, thuận tiện cho việc viết code, chạy thử và giải thích kết quả.
## Cách hoạt động
### Import thư viện
* Khởi tạo môi trường làm việc.
* Import các thư viện cần thiết như `numpy`, `pandas`, `matplotlib`.
=> chuẩn bị công cụ để xử lý và phân tích dữ liệu.

### Đọc và khảo sát dữ liệu
* Đọc dữ liệu từ file processed_dulieuxettuyendaihoc.csv
* Hiển thị một vài dòng đầu `head()` để xem cấu trúc dữ liệu.
* Kiểm tra kích thước dữ liệu, tên cột và kiểu dữ liệu.
=> Hiểu dữ liệu ban đầu trước khi xử lý.

### Làm sạch và xử lý dữ liệu
* Kiểm tra và xử lý giá trị thiếu.
* Chuyển đổi kiểu dữ liệu khi cần.
* Chuẩn hóa hoặc hiệu chỉnh dữ liệu điểm số.
=> Đảm bảo dữ liệu nhất quán và sẵn sàng cho phân tích.

### Thống kê mô tả
* Tính các đại lượng thống kê: `count`, `mean`, `min`, `max`, `std`.
* Sử dụng 'groupby' và 'pivot table' để thống kê theo nhóm (giới tính, khu vực, khối thi, …).
=> Nắm bắt đặc điểm phân bố và xu hướng của dữ liệu.

### Phân tích và biến đổi dữ liệu
* Tạo các biến mới (ví dụ: kết quả xét tuyển – đậu/rớt).
* Áp dụng công thức tính toán trên các cột dữ liệu.
* So sánh và phân tích kết quả giữa các nhóm.
=> Rút ra thông tin có ý nghĩa từ dữ liệu thô.

### Trực quan hóa dữ liệu
* Vẽ biểu đồ cột, biểu đồ histogram hoặc boxplot.
* Quan sát sự phân bố và so sánh dữ liệu giữa các nhóm.
=> Giúp việc phân tích trở nên trực quan và dễ hiểu hơn.
