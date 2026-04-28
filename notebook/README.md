📂 Hướng dẫn Chạy mã nguồn (Notebooks):  
- Thư mục này chứa toàn bộ quy trình xử lý dữ liệu, phân tích trực quan (EDA) và xây dựng mô hình dự báo doanh thu cho dự án Datathon 2026: The Gridbreaker.  

🏗️ Cấu trúc Môi trường & Thư mục:  
- Để code chạy chính xác mà không cần sửa đổi đường dẫn, vui lòng bố trí các thư mục theo sơ đồ sau:  
Plaintext:  
```
├── data/
│   └── raw/                <-- Tải 15 file CSV từ Kaggle vào đây
├── notebooks/
│   └── [CÁC_FILE_NOTEBOOK].ipynb
└── outputs/                <-- Tự động khởi tạo khi chạy code
    ├── charts/             <-- Lưu biểu đồ (Phần 2)
    └── tables/             <-- Lưu bảng phân tích (Phần 2)
```

🛠️ Cài đặt Môi trường (Environment Setup):  
Để đảm bảo code chạy ổn định và tương thích hoàn toàn với kết quả của nhóm, vui lòng sử dụng cấu hình sau:  
+ Python Version: 3.13.x  

Các thư viện chính:  

+ pandas: Xử lý và biến đổi 15 bảng dữ liệu.  
+ numpy: Tính toán số học và xử lý mảng.  
+ matplotlib & seaborn: Trực quan hóa dữ liệu và vẽ biểu đồ phân tích.  

Hướng dẫn cài đặt nhanh:  
+ Sử dụng pip (Khuyên dùng):  
+ Mở terminal (hoặc Command Prompt) tại thư mục gốc của dự án và chạy lệnh sau để cài đặt tất cả thư viện cần thiết:  
```
Bash
pip install pandas numpy matplotlib seaborn
```
  
📝 Thứ tự Thực hiện (Pipeline):  
- Nhóm đã chia quy trình thành các bước logic để đảm bảo tính minh bạch và dễ theo dõi:  

(01_mcq.ipynb)  
+ Mục tiêu: Thực hiện các bước tính toán để trả lời cho 10 câu hỏi trắc nghiệm của Phần 1.  
+ Phương pháp: Sử dụng thư viện Pandas để thực hiện các thao tác Join bảng, GroupBy và tính toán thống kê để đưa ra con số chính xác nhất cho từng câu hỏi: Q1 - Q10.  
+ VD: Các câu hỏi từ tính toán trung vị khoảng cách đơn hàng (Gap analysis), tỷ suất lợi nhuận gộp theo phân khúc, đến phân tích hành vi trả hàng theo kích thước sản phẩm.   

(02_eda.ipynb)  
+ Mục tiêu: Thực hiện Phân tích Khám phá Dữ liệu (EDA) để giải quyết Phần 2 của đề thi.  
+ Nội dung: Trực quan hóa xu hướng doanh thu, hành vi khách hàng, và hiệu quả khuyến mãi.  
+ Đầu ra: Các insight kinh doanh (Descriptive, Diagnostic, Predictive, Prescriptive) và tệp biểu đồ trong /outputs/charts/.  

(03_forecasting.ipynb)  
+ Mục tiêu: Xây dựng mô hình dự báo cho Phần 3.  
+ Nội dung: Tiền xử lý dữ liệu từ 15 bảng, kỹ thuật đặc trưng (Feature Engineering), huấn luyện mô hình, và đánh giá qua các chỉ số MAE, RMSE, $R^{2}$.  
+ Giải thích: Bao gồm phần giải thích tầm quan trọng của tính năng (Feature Importance/SHAP) theo ngôn ngữ kinh doanh.  

⚙️ Cấu hình Đường dẫn (Paths):  
Trong code, các đường dẫn được thiết lập theo dạng tương đối để đảm bảo tính linh động:  
+ RAW_PATH = "../data/raw/": Đường dẫn đến bộ dữ liệu gốc (15 file CSV).  
+ TABLE_OUTPUT = "../outputs/tables/": Nơi lưu trữ các bảng thống kê kết quả.  
+ CHART_OUTPUT = "../outputs/charts/": Nơi lưu trữ các hình ảnh biểu đồ để đưa vào báo cáo NeurIPS. Lưu ý: Lệnh os.makedirs(..., exist_ok=True) đã được tích hợp để tự động tạo các thư mục đầu ra nếu chúng chưa tồn tại trên máy của bạn.  

⚠️ Lưu ý Quan trọng về Tính Tái lập:  
+ Random Seed: Nhóm đã cố định random_state trong các bước chia dữ liệu và huấn luyện mô hình để đảm bảo kết quả không thay đổi giữa các lần chạy.  
+ Dữ liệu ngoài: Tuyệt đối không sử dụng dữ liệu ngoài; tất cả đặc trưng đều được tạo từ 15 file dữ liệu do BTC cung cấp.  
+ Xử lý Leakage: Chúng tôi đã thực hiện Cross-validation theo đúng trình tự thời gian (Time-series Split), không sử dụng dữ liệu tương lai để dự báo quá khứ.  
