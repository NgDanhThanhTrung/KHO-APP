# 📱 Kho Ứng Dụng iOS - Nguyễn Danh Thành Trung

[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg)]()
[![Platform](https://img.shields.io/badge/Platform-iOS-lightgrey.svg)]()
[![License](https://img.shields.io/badge/License-MIT-blue.svg)]()

Một trang web cung cấp trình cài đặt ứng dụng iOS trực tiếp qua trình duyệt với giao diện **Glassmorphism** hiện đại và hiệu ứng tương tác 3D.

---

## ✨ Tính năng nổi bật

* **Giao diện Kính mờ (Glassmorphism):** Hiệu ứng nền mờ chồng lớp cực sang trọng.
* **Tương tác 3D Parallax:** Thẻ nội dung tự động xoay theo hướng chuột người dùng.
* **Hệ thống hạt (Particle System):** Hình nền động mượt mà được xử lý bằng HTML5 Canvas.
* **Cài đặt 1-Click:** Tích hợp giao thức `itms-services` để cài đặt file IPA nhanh chóng.
* **Tối ưu Mobile:** Thiết kế Responsive, ưu tiên trải nghiệm trên iPhone/iPad.

---

## 🚀 Danh sách ứng dụng

| Biểu tượng | Tên ứng dụng | Mô tả | Trạng thái |
| :---: | :--- | :--- | :---: |
| <img src="https://github.com/NgDanhThanhTrung/APP/raw/main/locket/logo_locket.jpg" width="40" style="border-radius:10px"> | **Locket Gold** | Widget chia sẻ ảnh khoảnh khắc | ✅ Sẵn sàng |
| <img src="https://github.com/NgDanhThanhTrung/APP/raw/main/shadowrocket/logo_shadowrocket.jpg" width="40" style="border-radius:10px"> | **Shadowrocket** | Công cụ Proxy & VPN mạnh mẽ | ✅ Sẵn sàng |
| <img src="https://github.com/NgDanhThanhTrung/APP/raw/main/rophim/logo_rophim.jpg" width="40" style="border-radius:10px"> | **Rophim** | Xem phim chất lượng cao | ✅ Sẵn sàng |

---

## 🛠 Công nghệ sử dụng

Dự án được viết hoàn toàn bằng mã nguồn thuần (Vanilla) để tối ưu hóa tốc độ:
* **Frontend:** HTML5, CSS3 (Flexbox/Grid/Animations).
* **Interaction:** JavaScript (Canvas API, Mouse Events).
* **Icons:** Font Awesome 6.0, Safari Brands.
* **Fonts:** Montserrat & Inter từ Google Fonts.

---

## 📥 Hướng dẫn cài đặt

1.  **Clone dự án:**
    ```bash
    git clone [https://github.com/NgDanhThanhTrung/APP.git](https://github.com/NgDanhThanhTrung/APP.git)
    ```
2.  **Cấu hình Link IPA:**
    Để thay đổi liên kết tải app, hãy chỉnh sửa thuộc tính `url` trong đoạn mã sau tại file `index.html`:
    ```html
    <a href="itms-services://?action=download-manifest&url=ĐƯỜNG_DẪN_FILE_PLIST_CỦA_BẠN">
    ```
3.  **Deploy lên GitHub Pages:**
    * Vào tab **Settings** của repository này.
    * Chọn mục **Pages**.
    * Chọn nhánh `main` và bấm **Save**.

---

## ⚠️ Lưu ý quan trọng

> [!IMPORTANT]
> Để cài đặt được ứng dụng, bạn **BẮT BUỘC** phải mở trang web bằng trình duyệt **Safari** trên thiết bị iOS. Các trình duyệt như Chrome hay Facebook In-app Browser sẽ không kích hoạt được trình cài đặt của Apple.

---

## 💖 Đóng góp & Ủng hộ

Nếu dự án này giúp ích cho bạn, hãy tặng mình một ⭐️ hoặc hỗ trợ mình qua:
👉 [**Cổng thanh toán Donate**](https://ngdanhthanhtrung.github.io/Bank/)

---

## 📄 Giấy phép

Dự án được phát hành dưới giấy phép **MIT License**. Bạn có thể tùy ý sử dụng và phát triển lại.

**Phát triển bởi [Nguyễn Danh Thành Trung](https://github.com/NgDanhThanhTrung)**
