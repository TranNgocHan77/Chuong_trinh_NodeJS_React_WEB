# Chuong_trinh_NodeJS_React_WEB
Chương trình React trên đang tạo một dashboard đơn giản để hiển thị nhiệt độ và độ ẩm, lấy dữ liệu từ API `/data` mỗi 5 giây. Để chạy chính xác chương trình này, bạn làm theo các bước sau:

---

### 1. **Cài đặt Node.js và npm**
Trước tiên, bạn cần có **Node.js** và **npm** trên máy. Kiểm tra bằng lệnh:
```sh
node -v
npm -v
```
Nếu chưa có, tải và cài đặt từ:  
🔗 [https://nodejs.org/](https://nodejs.org/)

---

### 2. **Tạo và thiết lập dự án React**
Nếu bạn chưa có dự án React, tạo một dự án mới bằng lệnh:
```sh
npx create-react-app esp32-dashboard
cd esp32-dashboard
```
Sau đó, thay thế nội dung của `src/App.js` bằng code bạn đã cung cấp.

---

### 3. **Chạy Server Backend (Nếu Cần)**
Do code này fetch dữ liệu từ `/data`, bạn cần một server backend để cung cấp API. Nếu bạn đang chạy ESP32 với giao diện web server, hãy đảm bảo API `/data` có thể truy cập từ trình duyệt.

Nếu muốn tạo một server giả lập bằng Node.js, có thể dùng `json-server`:
```sh
npm install -g json-server
```
Tạo một file `db.json`:
```json
{
  "temperature": 25,
  "humidity": 60
}
```
Chạy server JSON:
```sh
json-server --watch db.json --port 3001
```
Thay đổi đường dẫn API trong `App.js`:
```js
const response = await fetch("http://localhost:3001");
```

---

### 4. **Chạy ứng dụng React**
Chạy lệnh:
```sh
npm start
```
Mở trình duyệt và truy cập `http://localhost:3000`.

---

### 5. **Xử lý lỗi phổ biến**
- **Lỗi CORS khi fetch dữ liệu** → Sử dụng proxy trong `package.json`:
```json
"proxy": "http://localhost:3001"
```
- **Lỗi thiếu module** → Cài đặt các package cần thiết:
```sh
npm install
```
- **Trang trắng, lỗi fetch** → Kiểm tra xem backend có đang chạy không.

---

Chạy thử và báo lỗi nếu gặp vấn đề nhé! 🚀
