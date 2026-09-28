# BÀI TẬP 1: TRIỂN KHAI HỆ THỐNG DỊCH VỤ VỚI DOCKER & CLOUDFLARE TUNNEL

* **Họ và tên:** Trương Nam Tú
* **Lớp:** K59HTĐ.K01
* **MSSV:** K235520201142

---

## 🖥️ Môi Trường Triển Khai System

Triển khai môi trường hệ điều hành **Ubuntu 26.04.1 LTS** trực tiếp thông qua **Windows Subsystem for Linux (WSL)**[cite: 12].


<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/6c6749f6-85ab-498a-aaec-c01a14387196" />


---

## 🛠️ Danh Sách Dịch Vụ Triển Khai (Docker Containers)

Sử dụng **Docker Compose** để khởi chạy đồng thời các dịch vụ cần thiết trong cùng một môi trường mạng nội bộ:

* **Nginx:** Đóng vai trò Web Server hiển thị giao diện và Reverse Proxy điều hướng API.
* **Node-RED:** Đóng vai trò Backend lập trình luồng nhận/xử lý request và trả dữ liệu JSON.
* **Cloudflared:** Tạo đường truyền mã hóa (Tunnel) bảo mật để kết nối dịch vụ Local ra ngoài Internet.

*(Kéo và thả ảnh chụp lệnh docker compose / docker ps vào dòng dưới đây)*


---

## 🌐 Cấu Hình Cloudflare Tunnel & Domain

Thực hiện kết nối bảo mật từ máy Local tới Domain cá nhân mã nguồn mở (`*.id.vn`) đã xác thực thông qua Cloudflare Dashboard.

*(Kéo và thả ảnh chụp giao diện Cloudflare Tunnel vào dòng dưới đây)*


---

## 📄 Cấu Hình Nginx & Giao Diện Web

* Khởi tạo trang giao diện web đơn giản `index.html` xử lý sự kiện tương tác người dùng.
* Cấu hình Reverse Proxy trong Nginx (`location /api/`) chuyển tiếp request trực tiếp tới Node-RED trên port `1880`.

*(Kéo và thả ảnh chụp trang web hoặc file conf Nginx vào dòng dưới đây)*


---

## ⚙️ Xây Dựng Luồng API Trên Node-RED

Thiết lập luồng xử lý Backend hoàn chỉnh bằng cách liên kết 3 Node cơ bản:
`[http in]` ➡️ `[function]` ➡️ `[http response]`

*(Kéo và thả ảnh chụp màn hình Flow Node-RED vào dòng dưới đây)*


---

## ✅ Kiểm Tra Tương Tác Web & API

Truy cập trực tiếp thông qua tên miền công cộng, thực hiện thao tác gọi API từ giao diện web và kiểm tra kết quả dữ liệu JSON phản hồi từ Node-RED.

*(Kéo và thả ảnh chụp kết quả gọi API thành công trên web vào dòng dưới đây)*
