# Lab 2: BÀI THỰC HÀNH TRÌNH BÀY DỮ LIỆU

Dự án này là bài thực hành Lab 2 thuộc môn Phân tích dữ liệu, tập trung vào việc sử dụng các thư viện Python để xử lý, thống kê và trực quan hóa dữ liệu xét tuyển đại học.

## Công nghệ sử dụng

Các thư viện và công cụ chính được sử dụng trong dự án:

* **Python**: Ngôn ngữ lập trình chính.
* **Pandas**: Dùng để đọc file CSV, xử lý khung dữ liệu (DataFrame), sắp xếp và tạo bảng tổng hợp (Pivot Table).
* **NumPy**: Hỗ trợ các phép toán số học và xử lý mảng.
* **Matplotlib** (tích hợp trong Pandas): Dùng để vẽ các biểu đồ trực quan hóa dữ liệu.
* **Jupyter Notebook / Google Colab**: Môi trường thực thi mã nguồn.

## Cách hoạt động

Quy trình xử lý dữ liệu trong file bao gồm:

1.  **Khởi tạo dữ liệu**:
    * Nhập các thư viện cần thiết (`pandas`, `numpy`).
    * Đọc dữ liệu từ file `processed_dulieuxettuyendaihoc.csv`.

2.  **Sắp xếp dữ liệu**:
    * Sắp xếp danh sách sinh viên theo điểm `DH1` tăng dần.
    * Sắp xếp dữ liệu theo nhóm giới tính (`GT`) và điểm `DH2` tăng dần.

3.  **Thống kê mô tả**:
    * Tạo các hàm tính tứ phân vị (Q1, Q2, Q3).
    * Sử dụng `pivot_table` để thống kê các chỉ số quan trọng (count, sum, mean, median, min, max, std, Q1, Q2, Q3) của điểm `DH1`.
    * Phân tích thống kê điểm `DH1` theo các nhóm phân loại:
        * Theo khối thi (`KT`).
        * Theo khối thi (`KT`) và khu vực (`KV`).
        * Theo khối thi (`KT`), khu vực (`KV`) và đối tượng (`DT`).

4.  **Trực quan hóa dữ liệu (Visualization)**:
    * Thống kê số lượng sinh viên theo giới tính (`GT`) bằng hàm `groupby` và `agg`.
    * Vẽ biểu đồ để trình bày phân bố giới tính:
        * Biểu đồ cột (Bar chart).
        * Biểu đồ tròn (Pie chart).
        * Biểu đồ vùng (Area chart).

## Kết quả

Sau khi chạy, dự án sẽ tạo ra các kết quả chính sau:

* **Bảng dữ liệu đã sắp xếp**: Giúp dễ dàng tra cứu thí sinh theo thứ hạng điểm số hoặc nhóm giới tính.
* **Bảng thống kê chi tiết**: Cung cấp cái nhìn tổng quan về phổ điểm `DH1` dựa trên các yếu tố nhân khẩu học và khu vực (ví dụ: điểm trung bình của từng khối thi, độ lệch chuẩn điểm số giữa các khu vực).
* **Biểu đồ trực quan**:
    * Hiển thị tỷ lệ nam/nữ trong tập dữ liệu giúp đánh giá sự cân bằng giới tính của các thí sinh xét tuyển.
    * Các biểu đồ `bar`, `pie`, và `area` minh họa trực quan số lượng thí sinh theo giới tính.