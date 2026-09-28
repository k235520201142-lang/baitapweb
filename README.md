# BÁO CÁO BÀI TẬP VỀ NHÀ MÔN LẬP TRÌNH WEB

**Thông tin sinh viên:**
* **Họ và tên:** Trương Nam Tú
* **Mã sinh viên:** K235520201142
* **Lớp:** K59HTĐ.K01

---

# BÀI TẬP 1: TRIỂN KHAI HỆ THỐNG DỊCH VỤ VỚI DOCKER COMPOSE & NGINX

## 1. Giả lập hệ điều hành Linux
Triển khai hệ điều hành **Ubuntu 26.04.1 LTS** thông qua môi trường **Windows Subsystem for Linux (WSL)**.

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/d125dc58-8231-436e-a852-3c15e0fd66b9" />


---

## 2. Cài đặt Docker & Docker Compose
Kiểm tra và xác nhận phiên bản Docker cũng như Docker Compose đã được cài đặt thành công trên hệ điều hành Ubuntu.

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/13eddd28-7459-42e1-9b9f-51aa38c438d5" />


---

## 3. Khởi chạy các dịch vụ trên Docker Compose
Tạo file `docker-compose.yml` khai báo đầy đủ các dịch vụ: `nginx`, `nodered`, `mariadb` (hoặc phpmyadmin) và `cloudflared`. Thực hiện khởi chạy container và kiểm tra trạng thái hoạt động (`Up`).

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/19e225c3-7da2-4df9-99dc-f92624e7fb04" />


---

**Minh chứng giao diện Quản trị phpMyAdmin (Port 8080):**

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/e4ea0d9e-6c9f-496b-a78f-be8fe236932f" />


---

**Minh chứng cấu hình Cloudflare Tunnel:**
Thiết lập đường truyền bảo mật kết nối các service ra tên miền cá nhân thành công (`truongnamtu.id.vn` và `sub.truongnamtu.id.vn`).

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/649ee808-0af7-454a-930a-e94852daa090" />


---

## 4. Cấu hình Nginx chạy 2 Website với 2 Domain khác nhau
Cấu hình Virtual Host trong Nginx điều hướng đồng thời 2 tên miền khác nhau chạy trên cùng một hạ tầng web server.

* **Website 1 (`truongnamtu.id.vn`):**

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/572907a1-05d9-4dce-9e96-687503a2e06e" />


---

* **Website 2 (`sub.truongnamtu.id.vn`):**

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/94891fbe-f1b4-422c-b9b7-c56b71710bcd" />


---

# BÀI TẬP 2: XÂY DỰNG API TRÊN NODE-RED & TÍNH NĂNG GỌI API

## 1. Xây dựng API đơn giản bằng Node-RED
Sử dụng các Node `[http in]`, `[function]` và `[http response]` để thiết lập một Endpoint tiếp nhận request và xử lý dữ liệu đầu ra dạng JSON.

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/1f7263f3-6418-4334-9bc3-8900a6992fe7" />


---

## 2. Cấu hình Nginx Proxy & Thuật toán API trả về JSON
Thiết lập Nginx làm Reverse Proxy để chuyển tiếp các request từ giao diện Web tới Node-RED. API trả về chuỗi JSON chứa thông tin sinh viên và trạng thái phản hồi.

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/41766841-5ae3-4fd8-ae44-a6c810a382e4" />


---

## 3. Tích hợp Code JavaScript vào trang HTML để gọi API

Viết mã JavaScript (sử dụng `fetch API`) tích hợp trực tiếp vào file `index.html` nhằm gửi yêu cầu tới Nginx Proxy, nhận phản hồi dữ liệu JSON từ Node-RED backend và render trực tiếp thông tin sinh viên lên giao diện người dùng.

* **Giao diện trang Web ban đầu (Khi chưa tương tác):**

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/3965da86-5e86-491e-bce3-ca9f0af989f2" />


---

* **Kết quả hiển thị sau khi người dùng bấm nút gọi API thành công:**

<img width="1535" height="863" alt="image" src="https://github.com/user-attachments/assets/ce7f5027-a5d7-429c-b48e-7cc05f78500f" />
