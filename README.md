# Khám Phá Dữ Liệu Sức Khỏe Tâm Thần (Exploring Mental Health Data)

## Danh Sách Thành Viên Nhóm

Thành viên nhóm dự án gồm các sinh viên:

| STT | Họ và Tên | MSSV |
| :---: | :--- | :--- |
| 1 | Nguyễn Kim Quốc | 23120347 |
| 2 | Nguyễn Đức Tiến | 23120368 |
| 3 | Nguyễn Lê Tân Tiến | 23120369 |
| 4 | Kiều Đỗ Song Tinh | 23120373 |
| 5 | Mai Đình Trí | 23120377 |
| 6 | Đào Quốc Tuấn | 23120392 |

---

## 1. Thông Tin & Mô Tả Đồ Án

Đồ án này lấy cảm hứng từ cuộc thi **[Exploring Mental Health Data](https://www.kaggle.com/competitions/exploring-mental-health-data)** trên Kaggle thuộc môn Phân tích Dữ liệu Thông minh.

Mục tiêu chính của cuộc thi là sử dụng dữ liệu từ khảo sát sức khỏe tâm thần để khám phá các yếu tố có thể dẫn đến trầm cảm. Dựa trên các đặc điểm được cung cấp trong bộ dữ liệu, nhóm đã xây dựng và phát triển các mô hình học máy (Machine Learning) để dự đoán xem một cá nhân có mắc phải triệu chứng trầm cảm (biến mục tiêu `Depression`) hay không.

**Các bước thực hiện chính:**
1. **Khám phá và Tiền xử lý dữ liệu (EDA & Data Preprocessing):** Thực hiện phân tích sự phân bố của dữ liệu, làm sạch (xử lý dữ liệu ngoại lai, lấp đầy dữ liệu bị thiếu), chuyển đổi dữ liệu và rút trích các đặc trưng (Feature Engineering) quan trọng nhất giúp tăng độ chính xác dự đoán.  
2. **Xây dựng Mô hình (Model Development):** Áp dụng các thuật toán Machine Learning (Baseline, Boosting, Neural Network...) trên nền tảng dữ liệu đã xử lý.  
3. **Đánh giá, Tối ưu và Dự báo (Experiments and Results):** Lựa chọn mô hình tốt nhất căn cứ theo các thuộc tính đánh giá, tinh chỉnh siêu tham số, sau đó tiến hành dự đoán trên tập test từ Kaggle.

---

## 2. Cấu Trúc Thư Mục

Dự án được cấu trúc theo định dạng chuẩn để dễ theo dõi tiến trình thực thi, cụ thể như sau:

```text
Exploring-Mental-Health-Data/
+-- data/                     # Thư mục đặt dữ liệu thô từ Kaggle (.csv) và dữ liệu đã qua tiền xử lý
+-- notebooks/                # Các mã nguồn Jupyter Notebook được đánh số theo từng luồng công việc
|   +-- 01_eda.ipynb              # Khám phá dữ liệu, vẽ biểu đồ (EDA)
|   +-- 02_preprocessing_fe.ipynb # Tiền xử lý dữ liệu và Feature Engineering
|   +-- 03_baseline_models.ipynb  # Triển khai huấn luyện các mô hình cơ sở
|   +-- 04_boosting_models.ipynb  # Triển khai các mô hình Boosting nâng cao (XGBoost, LightGBM,...)
|   +-- 05_neural_network.ipynb   # Triển khai mạng nơ-ron (Neural Network)
+-- outputs/                  # Thư mục lưu file submission (.csv), file mô hình (model object) hoặc báo cáo
+-- .gitignore
+-- README.md
+-- requirements.txt          # Tiêu chuẩn thư viện Python cần thiết cho đồ án
```

---

## 3. Hướng Dẫn Cài Đặt và Chạy Chương Trình

Để chạy các notebook mà không gặp trục trặc, môi trường Python của bạn cần có phiên bản >= 3.8 và các thư viện như Pandas, Numpy, Scikit-learn, XGBoost, Matplotlib, Seaborn,... Bạn có thể thiết lập theo các bước dưới đây.

### Bước 1: Clone repository
Mở Terminal / Command Prompt và tải project về máy nội bộ:

```bash
git clone https://github.com/s4lt1f0l/Exploring-Mental-Health-Data.git
cd Exploring-Mental-Health-Data
```

### Bước 2: (Khuyên dùng) Tạo và kích hoạt Virtual Environment
Khuyến nghị sử dụng môi trường ảo để không gây ảnh hưởng đến hệ thống máy tính.

- Trên Windows:
```bash
python -m venv venv
venv\Scripts\activate
```

- Trên macOS/Linux:
```bash
python -m venv venv
source venv/bin/activate
```

### Bước 3: Cài đặt các Package
```bash
pip install -r requirements.txt
```

### Bước 4: Thiết lập Dữ Liệu Kaggle
Đảm bảo bạn đã tải bộ dữ liệu `train.csv` và `test.csv` (và cả `sample_submission.csv` nếu có) từ trang web Kaggle và đặt toàn bộ chúng vào thư mục `data/` của đồ án.

> Gợi ý: Có thể thêm script tự động sử dụng Kaggle API (yêu cầu đặt `~/.kaggle/kaggle.json`) để tải dataset:  
> `kaggle competitions download -c exploring-mental-health-data -p data/raw`

### Bước 5: Chạy các Notebooks theo đúng quy trình
Khởi động Jupyter Notebook bằng lệnh:

```bash
jupyter notebook
```

Tiếp theo, hãy chạy từng Notebook theo số thứ tự có sẵn trong thư mục `notebooks` bằng cách chọn Kernel → Restart & Run All lần lượt cho mỗi tệp:

1. Chạy `01_eda.ipynb` để thực hiện trực quan hoá phân bố dữ liệu ban đầu.  
2. Chạy `02_preprocessing_fe.ipynb`. Ở bước này, sau khi xử lý thành công và tính toán đặc trưng, một tệp dữ liệu sạch sẽ được sinh ra để truyền vào các mô hình tiếp theo.  
3. Chạy từ `03` đến `06` để xem quá trình thiết lập và huấn luyện từng họ thuật toán. Những mô-đun nào đạt kết quả tốt sẽ được tối ưu siêu tham số, tạo ra file kết quả Submission (`.csv`) lưu vào `outputs/` để nộp lên nền tảng Kaggle.

---
