# DATATHON-VINUNI-2026_AI2104
FILE README.md tổng quan cấu trúc.  
Github repository for our project (Cấu trúc của github repository).  
Trong từng thư mục sẽ có các file README.md hướng dẫn riêng.      

```
├── data/
│   └── README.md           # File này sẽ chứa link hướng dẫn tải dữ liệu từ Kaggle
├── notebooks/              # Chứa các file chạy chính của 3 phần
│   ├── 01_mcq.ipynb
│   └── 02_eda.ipynb
|   └── 03_forecasting.ipynb
|   └── README.md           # Hướng dẫn tải các thư viện bổ sung
├── outputs/                    # Chứa các bảng và biểu đồ được tạo ra từ bảng
│   ├── charts/                     
|       ├── 01_category_diagnostic.png
|       └── 02_segment_margin_comparison.png
|       └── 03_top_10_products.png
|       └── 04_correlation_discount_quantity.png
|       └── 05_time_seasonality.png
|       └── 06_customer_behavior.png
|       └── 07_anomaly_detection.png
|       └── README.md
│   └── tables/                     
|       ├── 01_category_margin.csv
|       └── 02_segment_diagnostic.csv
|       └── 03_top_10_products.csv
|       └── 04_correlation_matrix.csv
|       └── 05_monthly_seasonality.csv
|       └── 06_customer_frequency.csv
|       └── 07_sales_anomalies.csv
|       └── README.md         
│   └── README.md                 # Phân tích sơ lược
├── submission/                   # Chứa file kết quả cuối cùng để BTC đối chiếu (Phần 3)
│   └── submission.csv
├── reports/                      # Thư mục chứa báo cáo PDF(LaTex) nộp cho BTC
│   └── Bao_cao_Vong1_AI2104.pdf
├── .gitignore                    # Quan trọng: Để chặn các file csv nặng bị đẩy lên nhầm
├── README.md                     # Tổng quan dự án, link Kaggle và hướng dẫn chạy code
└── requirements.txt              # Danh sách thư viện (pandas, numpy, scikit-learn...)
```
