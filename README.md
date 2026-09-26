# BÁO CÁO BÀI TẬP LỚN: HỆ THỐNG ĐA TÊN MIỀN & LẬP TRÌNH API

## 1. Thông tin sinh viên
* **Họ và tên**: Trương Nam Tú
* **Mã sinh viên**: K235520201142
* **Trường**: Đại học Kỹ thuật Công nghiệp Thái Nguyên (TNUT)
* **Tên miền chính**: truongnamtu.id.vn
* **Subdomain**: sub.truongnamtu.id.vn

---

## 2. BÀI TẬP 1: TRIỂN KHAI HỆ THỐNG DỊCH VỤ VỚI DOCKER & CLOUDFLARE TUNNEL

### 2.1. Danh sách dịch vụ triển khai (Docker Containers)
- **Nginx**: Web server điều hướng đa tên miền (Ports 80, 443).
- **Node-RED**: Công cụ lập trình luồng / API (Port 1880).
- **MariaDB**: Cơ sở dữ liệu MySQL (Port 3306).
- **phpMyAdmin**: Giao diện quản trị CSDL (Port 8080).
- **Cloudflared**: Kết nối Tunnel bảo mật từ Local ra Internet.

![Docker Containers running](images/01-docker.png)

### 2.2. Quản lý Cloudflare Tunnel
![Cloudflare Tunnel Status](images/02-cloudflare.png)

### 2.3. Các dịch vụ hệ thống
* **Node-RED Interface:**
![Node-RED](images/03-nodered.png)

* **MariaDB Database:**
![MariaDB Container](images/04-mariadb.png)

* **phpMyAdmin Dashboard:**
![phpMyAdmin Management](images/05-phpmyadmin.png)

### 2.4. Kiểm tra truy cập đa tên miền
* **Website 1 (truongnamtu.id.vn):**
![Website 1](images/06-web1.png)

* **Website 2 (sub.truongnamtu.id.vn):**
![Website 2](images/07-web2.png)

---

## 3. BÀI TẬP 2: LẬP TRÌNH API TRÊN NODE-RED & CALL API BẰNG JAVASCRIPT

### 3.1. Cấu hình Flow API trên Node-RED
Thiết lập Endpoint `GET /api/sinhvien` trên Node-RED để trả về dữ liệu JSON chứa thông tin sinh viên và kích hoạt header CORS.

![Node-RED API Flow](images/08-nodered-flow.png)

### 3.2. Kiểm tra phản hồi API (JSON Output)
![API JSON Response](images/09-api-response.png)

### 3.3. Trang web gọi API bằng JavaScript (Fetch API)

* **Giao diện ban đầu:**
![Website Before API Call](images/10-web-api-before.png)

* **Giao diện sau khi nhấn nút "Tải dữ liệu Sinh viên" (Dữ liệu render động từ API):**
![Website After API Call](images/11-web-api-after.png)