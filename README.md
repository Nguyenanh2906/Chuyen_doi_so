
<h1 align="center">PHÂN TÍCH CẢM XÚC SINH VIÊN </h1>
<div align="center">

<p align="center">
  <img src="./img/logoDaiNam.png" alt="DaiNam University Logo" width="200"/>
  <img src="./img/LogoAIoTLab.png" alt="AIoTLab Logo" width="170"/>
</p>

[![Made by AIoTLab](https://img.shields.io/badge/Made%20by%20AIoTLab-blue?style=for-the-badge)](https://www.facebook.com/DNUAIoTLab)
[![Fit DNU](https://img.shields.io/badge/Fit%20DNU-green?style=for-the-badge)](https://fitdnu.net/)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-red?style=for-the-badge)](https://dainam.edu.vn)

</div>

🌟 Introduction

- Student Sentiment Analysis là hệ thống phân tích cảm xúc trong phản hồi của sinh viên, giúp nhà trường đánh giá mức độ hài lòng và phát hiện sớm các vấn đề trong quá trình học tập.

- Hệ thống kết hợp sức mạnh của PHoBERT – mô hình ngôn ngữ mạnh mẽ cho tiếng Việt – cùng CNN và GRU để phát hiện cụm từ mang tính cảm xúc (“chưa hiểu”, “rất hay”, “khó tiếp thu”…), đồng thời nắm bắt ngữ cảnh của toàn câu để phân loại cảm xúc chính xác hơn.

- Các nhãn cảm xúc được chia thành ba nhóm chính:

😃 Tích cực (Positive)

😐 Trung tính (Neutral)

😞 Tiêu cực (Negative)

---
## ⚙ System Overview
### 🧠 Mô hình đề xuất

- PHoBERT: Sinh embedding ngữ cảnh tiếng Việt.

- CNN (Convolutional Neural Network): Phát hiện các cụm từ đặc trưng cảm xúc.

- GRU (Gated Recurrent Unit): Nắm bắt mối quan hệ chuỗi trong câu phản hồi.

- Kết hợp CNN-GRU: Giúp mô hình vừa học được đặc trưng cục bộ vừa hiểu được ngữ cảnh tổng thể, nâng cao độ chính xác phân loại.

<p align="center">
  <img src="./img/Bảng 1.jpg" alt=""/>
</p>

### 🧩 System Architecture
```
📂 StudentSentimentAnalysis/
├── data/
│   ├── train.csv
│   ├── dev.csv
│   └── test.csv
├── models/
│   ├── phobert_cnn_gru.py
│   ├── train.py
│   └── evaluate.py
├── results/
│   ├── learning_rate_analysis.csv
│   ├── performance_report.json
│   └── confusion_matrix.png
├── requirements.txt
└── README.md
```

### ⚙ Installation & Usage
1️⃣ Create Environment and Install Packages
   ```shell
    conda create -n sentiment-dev python=3.9
   ```

   ```shell
    conda activate sentiment-dev
   ```

   ```shell
    pip install -r requirements.txt
   ```
2️⃣ Train Model
```shell
python train.py --model phobert-cnn-gru --epochs 10 --lr 0.0001
```
3️⃣ Evaluate Model
```shell
python evaluate.py --dataset test.csv
```
4️⃣ Predict New Feedback
```shell
python predict.py --text "Môn học rất thú vị và dễ hiểu"
```
### 🧠 Technologies
| Component | Description |
|-------|--------|
| PHoBERT | Mô hình ngôn ngữ tiền huấn luyện cho tiếng Việt, tạo vector embedding ngữ cảnh. |
| CNN | Phát hiện cụm từ cảm xúc và đặc trưng cục bộ. |
| GRU | Nắm bắt chuỗi thời gian và ngữ cảnh trong phản hồi. |
|Scikit-learn / Pandas / NumPy | Xử lý dữ liệu và đánh giá mô hình. |


## 📈 Result

<p align="center">
  <img src="./img/Nhãn 1.jpg" alt=""/>
</p>

<p align="center">
  <img src="./img/Nhãn 2.jpg" alt=""/>
</p>

## 📚 Reference

- PhoBERT: Nguyen et al., “PhoBERT: Pre-trained language models for Vietnamese,” (2020).

- GRU: Cho et al., “Learning Phrase Representations using RNN Encoder–Decoder,” (2014).

- CNN: Kim, “Convolutional Neural Networks for Sentence Classification,” (2014).
