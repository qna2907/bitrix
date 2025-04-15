Ngôn ngữ lập trình:
- Backend: Node.js
- Frontend: Vue.js
Ứng dụng quản lý danh bạ (Contact) tích hợp với OAuth2 Bitrix24. Gồm 2 phần:
bitrix-backend`: Backend Node.js, xử lý API, OAuth2 và lưu token.
bitrix-frontend`: Frontend Vue.js, giao diện quản lý contact
📁 CẤU TRÚC THƯ MỤC bitrix24-project/
├── bitrix-backend/ # Backend Node.js
├── bitrix-frontend/ # Frontend Vue.js
🛠 CÀI ĐẶT
1. Clone project
2. Cài đặt ngrok-v3
3. Cài đặt backend
4. Sửa file .env trong bitrix-backend
   - Với thông tin
     CLIENT_ID= YOUR_CLIENT_ID
     CLIENT_SECRET= YOUR_CLIENT_SECRET
     BITRIX_DOMAIN= YOUR_BITRIX_DOMAIN
5. Chạy Backend:
   - Di chuyển đến thư mục bitrix-backend: cd bitrix-backend
   - Chạy file server.js: node server.js Mặc định chạy tại: http://localhost:3000
6. Cài đặt Frontend
7. Chạy Frontend:
   - Di chuyển đến thư mục bitrix-frontend: cd bitrix-frontend
   - Chạy Frontend: npm run dev
   - Frontend sẽ chạy tại http://localhost:5173
🔐 CẤU HÌNH ỨNG DỤNG BITRIX24
1. Truy cập trang quản lý app:
   https://yourdomain.bitrix24.vn/devops/edit/application/
2. Tạo ứng dụng mới, điền thông tin:
   - Redirect URI:
https://<your-ngrok-url>/install
(ví dụ: https://abcd-1234.ngrok-free.app/install)
--> Từ đây sẽ lấy được thồn tin YOUR_CLIENT_ID và YOUR_CLIENT_SECRET
3. Chạy ngrok:
   - Đăng nhập https://ngrok.com/ để lấy yourauthtoken
   - Chạy ngrok config add-authtoken yourauthtoken
   - Chạy ngrok http 3000
4. Sau khi cài app, trình duyệt sẽ gọi /install?code=...&domain=...
=> server sẽ lưu access_token và refresh_token vào file bitrix_token.json
   
