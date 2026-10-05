#Cửa sổ 1
Trong terminal, gõ: cd AI. Tạo môi trường ảo: python -m venv venv. Kích hoạt nó — Windows: venv\Scripts\activate, Mac/Linux: source venv/bin/activate (bạn sẽ thấy chữ '(venv)' xuất hiện đầu dòng lệnh). Cài thư viện: pip install -r requirements.txt (lần đầu sẽ khá lâu, vài phút, vì tải cả PyTorch). Sau khi cài xong, chạy: uvicorn main:app --reload --port 5000. Chờ đến khi thấy dòng 'Application startup complete'. Mở trình duyệt vào http://127.0.0.1:5000/docs để chắc chắn service đã sống — thấy giao diện Swagger là ổn. GIỮ NGUYÊN terminal này đang chạy, đừng đóng.

#Cửa sổ 2
Mở một terminal MỚI (không đóng terminal AI ở bước trước) — trong VS Code bấm dấu '+' ở góc phải panel terminal. Gõ: cd backend rồi npm install (chờ tải xong các gói). Sau đó chạy: node server.js. Bạn cần thấy 2 dòng: 'Đã kết nối thành công tới MySQL Database!' và 'Server Backend đang chạy tại http://localhost:3000'. Nếu không thấy dòng kết nối MySQL, quay lại Bước 3 kiểm tra lại .env. GIỮ NGUYÊN terminal này cũng đang chạy.
sửa database thành như này:
USE smart_parking_db;

CREATE TABLE IF NOT EXISTS users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(50) NOT NULL UNIQUE,
  password_hash VARCHAR(255) NOT NULL,
  full_name VARCHAR(100) DEFAULT NULL,
  role ENUM('admin', 'staff') NOT NULL DEFAULT 'staff',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
); 
#Cửa sổ 3
cd C:\Nam4\Ki1\DACN\DACN-main-updated\DACN-main\backend
node seed.js 
