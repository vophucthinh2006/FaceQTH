🚀 Hệ thống Nhận diện Khuôn mặt – MTCNN + FaceNet (GUI + Web)  
Tác giả: Võ Phúc Thịnh  
Ngày: 2025-08-31  

Hệ thống này kết hợp MTCNN (phát hiện & căn chỉnh khuôn mặt) và FaceNet (biểu diễn embedding), cùng với bộ phân loại (SVM / Softmax) để nhận diện khuôn mặt. Dự án hỗ trợ cả giao diện Web (Streamlit/WebRTC) và GUI (PyQt) cho thử nghiệm thời gian thực.  

🧭 Mục lục  
- Tổng quan  
- Điểm nổi bật GUI & Web  
- Tính năng chính  
- Khởi động nhanh  
- Cách sử dụng  
- Kiến trúc & Quy trình xử lý  
- Cấu trúc dự án  
- Cấu hình & Tinh chỉnh  
- Hiệu năng & Đánh giá  
- Ảnh minh họa  
- Phát triển & Đóng góp  
- Lời cảm ơn & Liên hệ  

---

🌟 Tổng quan  
Dự án này là một hệ thống AI nhận diện khuôn mặt. Pipeline gồm:  

🎯 **MTCNN (Multi-task Cascaded CNNs)** – phát hiện khuôn mặt và dự đoán 5 điểm đặc trưng.  
🤖 **FaceNet (Google)** – chuyển đổi mỗi khuôn mặt thành vector embedding 128 chiều.  
🧠 **Bộ phân loại (SVM / Softmax)** – nhận dạng danh tính dựa trên embeddings đã huấn luyện.  

Các chế độ hoạt động:  
- 📷 Nhận diện trực tiếp qua webcam  
- 🎞 Nhận diện từ video có sẵn  
- 🌐 Giao diện Web (Streamlit)  
- 🖥 Giao diện GUI (PyQt)  

---

🎨 Điểm nổi bật GUI & Web  
**Web (Streamlit + WebRTC):**  
- Truyền hình ảnh trực tiếp, nhận diện theo thời gian thực.  
- Hiển thị FPS và độ tin cậy (confidence) của nhận diện.  
- Giao diện hiện đại, đơn giản, có bảng điều khiển (chọn chế độ, thêm dữ liệu).  

**GUI (PyQt):**  
- Nút dễ dùng: bật/tắt camera, thêm người dùng, nhận diện.  
- Hiển thị hộp khuôn mặt + tên trên ảnh trực tiếp.  
- Hỗ trợ logo thương hiệu.  

---

📋 Tính năng chính  
🔍 **Phát hiện & Căn chỉnh**  
- MTCNN phát hiện khuôn mặt + căn chỉnh qua 5 điểm mốc (mắt, mũi, khóe miệng).  

🧠 **Embedding & Nhận diện**  
- FaceNet sinh embedding → Bộ phân loại dự đoán danh tính.  
- Hỗ trợ huấn luyện mô hình mới bằng `classifier.py`.  

📊 **Đánh giá hiệu năng**  
- Đo FPS trong chế độ webcam/video.  
- Đo Accuracy qua `validate_on_ifw.py` hoặc bộ dữ liệu thử nghiệm.  

💾 **Quản lý Dataset**  
- Ảnh gốc lưu tại `Dataset/FaceData/raw/`.  
- Ảnh đã căn chỉnh lưu tại `Dataset/FaceData/processed/`.  
- Bounding box được lưu tự động trong giai đoạn xử lý trước.  

---

🚀 Khởi động nhanh  

1) **Cài môi trường**  
```bash
python -m venv venv  
source venv/bin/activate  # Linux/Mac  
venv\Scripts\activate     # Windows  

pip install -r requirements.txt  
