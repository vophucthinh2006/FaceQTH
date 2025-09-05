# 🚀 Hệ thống Nhận diện Khuôn mặt – **MTCNN + FaceNet**  
**Tác giả**: Võ Phúc Thịnh  
📅 **Ngày**: 31/08/2025  

---

## 📖 Giới thiệu  
Hệ thống này kết hợp **MTCNN** (phát hiện & căn chỉnh khuôn mặt) và **FaceNet** (tạo vector embedding), cùng với bộ phân loại (**SVM / Softmax**) để **nhận diện khuôn mặt chính xác cao**.  

👉 Hỗ trợ cả:  
- 🌐 **Giao diện Web** (_Streamlit/WebRTC_)  
- 🖥 **Giao diện GUI** (_PyQt_)  
- 📷 **Camera trực tiếp**  
- 🎞 **Video có sẵn**  

---

## 🌟 Điểm nổi bật  

### 🖥 GUI (PyQt)  
- Nút dễ sử dụng: **bật/tắt camera**, **thêm người dùng**, **nhận diện**.  
- Hiển thị **bounding box, tên, FPS** và **độ tin cậy (confidence)** trên ảnh trực tiếp.  
- Có thể gắn **logo thương hiệu**.  

### 🌐 Web (Streamlit + WebRTC)  
- Hỗ trợ **nhận diện trực tiếp qua webcam** trong trình duyệt.  
- Hiển thị **bounding box, tên, FPS** và **độ tin cậy (confidence)**.  
- Giao diện đẹp, trực quan, dễ dùng.  

---

## 📋 Tính năng chính  
- 🔍 **Phát hiện & căn chỉnh khuôn mặt** bằng _MTCNN_ với **5 điểm mốc** (mắt, mũi, miệng).  
- 🧠 **Sinh vector embedding** bằng _FaceNet_ (128 chiều).  
- 📊 **Nhận diện danh tính** bằng **SVM**.  
- 💾 Quản lý dataset:  
  - Ảnh gốc → `Dataset/FaceData/raw/`  
  - Ảnh đã căn chỉnh → `Dataset/FaceData/processed/` (_tự động sinh bounding boxes_).  

---

## 🚀 Khởi động nhanh  

### 1️⃣ Cài môi trường  
```bash
python -m venv venv  
source venv/bin/activate  # Linux/Mac  
venv\Scripts\activate     # Windows  

pip install -r requirements.txt
```
## Yêu cầu hệ thống:
-Python: 3.8 (đã thử và gợi ý)
-OS: Windows / Linux / MacOS
-RAM: ≥ 4GB (khuyên dùng ≥ 8GB)
-GPU: NVIDIA CUDA/cuDNN (tùy chọn, để tăng tốc)
