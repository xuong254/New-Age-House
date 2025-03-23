
<h1 align="center">New-Age-House </h1>
<div align="center">

<p align="center">
  <img src="logoDaiNam (1).png" alt="DaiNam University Logo" width="200"/>
  <img src="LogoAIoTLab (1).png" alt="AIoTLab Logo" width="170"/>
</p>

[![Made by AIoTLab](https://img.shields.io/badge/Made%20by%20AIoTLab-blue?style=for-the-badge)](https://www.facebook.com/DNUAIoTLab)
[![Fit DNU](https://img.shields.io/badge/Fit%20DNU-green?style=for-the-badge)](https://fitdnu.net/)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-red?style=for-the-badge)](https://dainam.edu.vn)

</div>

---

## 🌟 Giới thiệu

- Nhận diện khuôn mặt: Dùng OpenCV và Face Recognition để quét, mã hóa và so sánh khuôn mặt. Nếu trùng khớp, cho phép điều khiển thiết bị. Nếu không, sẽ không điều khiển được thiết bị.
- Nhận diện giọng nói: Dùng Speech Recognition để chuyển giọng nói thành văn bản, kiểm tra lệnh và gửi tín hiệu điều khiển qua Arduino.
- Sử dụng các cảm biến: Cảm biến mưa - đóng cửa sổ trời. Cảm biến hồng ngoại - bật/ tắt đèn và mở cửa ra vào. Cảm biến khí gas -  tia lửa
- Kết nối IoT:Arduino để sử dụng các cảm biến: khí gas, tia lửa, mưa, hồng ngoại.

---

## ⚙ Hệ thống
<p align="center">
  <img src="hethong.jpg" alt="System Architecture" width="800"/>
</p>

---
## 📂 Cấu trúc dự án

📦 Project

├── 📂bat_tat den ID

| ├──bat_tat_den_ID.ino     # Mã nguồn Arduino điều khiển các thiết bị.
| ├──huanluyen.py     # Huấn luyện id.
| ├──python face_voice_control.py   #  Nhận diện khuôn mặt.
| ├──voice_control.py    # Điều khiển bằng giọng nói.

├── cambienkhigass.rar
├── cambienmua.rar
├── cambientialua.rar
├── HongNgoai.rar

---
## 💻 Công nghệ sử dụng 
### Phần cứng


| **PHẦN CỨNG** | **SỬ DỤNG** |
|---------------------|-------------|
| Arduini           | Nhận tín hiệu điều khiển các thiết bị |
| Flame Sensor         | Cảm biến tia lửa         |
|  FM-20B         | Còi báo      |
|   LCD 1604       | Màn hình    |
|  PIR HC-SR501        | Cảm Biến Thân Nhiệt Chuyển Động      |
| relay 12VDC         | Cảm biến mưa       |
| Động cơ servo     | Động cơ điều khiển cửa |
| Metan MQ-4     | Cảm biến khí gas |
| Đèn Led       |           bật đèn cửa ra vào và bật đèn hệ thống trong nhà      |

### Phần mềm
| **PHẦN MỀM** | **SỬ DỤNG** |
|---------------------|-------------|
| PYTHON
| Arduino IDE| Để nạp file .ino|

###  Các thư viện Python cần thiết
Cài đặt các thư viện cần thiết:

    pip install opencv-python face-recognition SpeechRecognition
---
## 🧮 Bảng mạch

### 🔩 Kết nối phần cứng:
- bat_tat den ID
<img src="arduno_giongnoi.jpg" alt="System Architecture" width="300"/>
- cambienkhigass.rar
<img src="ard_khigas.jpg" alt="System Architecture" width="300"/>
- cambienmua.rar
<img src="mua.jpg" alt="System Architecture" width="300"/>
- cambientialua.rar
<img src="tialua.jpg" alt="System Architecture" width="300"/>
- HongNgoai.rar
<img src="hongngoai.jpg" alt="System Architecture" width="300"/>

### ⛓️‍💥 Hướng dẫn cắm dây
- bat_tat den ID
<img src="banggiongnoi.jpg" alt="System Architecture" width="800"/>
- cambienkhigass.rar
<img src="bangkhigas.jpg" alt="System Architecture" width="800"/>
- cambienmua.rar
<img src="bangmua.jpg" alt="System Architecture" width="800"/>
- cambientialua.rar
<img src="bangtialua.jpg" alt="System Architecture" width="800"/>
- HongNgoai.rar
<img src="banghongngoai.jpg" alt="System Architecture" width="800"/>
---
## 🖇 Hướng dẫn cài đặt và chạy
1️⃣ Chuẩn bị phần cứng: Nạp arduino
- Mở file esp32.ino bằng Arduino IDE.
- Kết nối board Arduino với máy tính.
- Nạp (upload) mã nguồn lên board.
- Mở Serial Monitor hiện ESP32_IP 

2️⃣ Cài đặt PushOver

- Tải App PushOver và đăng nhập trên điện thoại(Androi/IOS)
- Vào https://pushover.net/ đăng nhập 
- Tạo Create an Application/API Token để lấy 'Your User Key' và 'API Token/Key'

3️⃣ Chạy chương trình

- Lấy địa chỉ IP ở Arduino IDE vào chương trình `esp32_control.py` 
- Lấy User Key và API Token/Key ở PushOver vào chương trình `notification_module.py`
- Chạy chương trình `main.py`

### 📑 Hướng dẫn sử dụng
1️⃣ Nhận diện khuôn mặt

- Khi người dùng chạy chương trình camera quét khuôn mặt trong phạm vi giám sát.
- So sánh khuôn mặt hiện tại vs khuôn mặt đã lưu
    
    - ✅ Đúng với khuôn mặt → Có thể điều khiển được các thiết bị bằng giọng nói.
    - ❌ Khuôn mặt không khớp → Chụp, lưu dữ liệu vào `unknown_faces` và thông báo đến điện thoại qua App PushOver.

2️⃣ Nhận giọng nói điều khiển thiết bị trong nhà

- Sử dụng các câu lệnh điều khiển các thiết bị
   
   - Quạt: 'bật quạt', 'tắt quạt'.
   - Đèn: 'bật đèn phòng ngủ', 'tắt đèn phòng ngủ','bật đèn phòng khách', 'tắt đèn phòng khách'.
   - Cửa sổ: 'mở cửa sổ', 'đóng cửa sổ'
   - Loa: 'mở nhạc', 'tắt nhạc'.

3️⃣ Xem thông báo cảnh báo người lạ

- Qua App PushOver xem được ảnh chụp người lạ kèm ngày tháng.
- Ảnh sẽ được lưu vào data/unknown_faces kèm thời gian.

--- 
## 📰 Poster

<p align="center">
  <img src="\image\Poster_CNTT06_NHOM9.png" alt="System Architecture" width="800"/>
</p>

---
## 🤝 Đóng góp
Các thành viên nhóm

- Nguyễn Thu Anh
- Nguyễn Thị Khuyên
- Hà Duy Dương
- Đỗ Văn Thuyên

© 2025 NHÓM 9, CNTT16-06, TRƯỜNG ĐẠI HỌC ĐẠI NAM
