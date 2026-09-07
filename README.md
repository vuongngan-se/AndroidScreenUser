# AndroidScreenUser (scrcpy v3.3.4 for Windows x64)

Công cụ kết nối, hiển thị và điều khiển màn hình điện thoại Android trực tiếp trên máy tính Windows (dựa trên nền tảng **scrcpy v3.3.4** và **Android Debug Bridge - ADB**).

---

## 🌟 Tính năng nổi bật

- **Không cần Root**: Hoạt động mượt mà với hầu hết các thiết bị Android (từ Android 5.0 trở lên).
- **Độ trễ cực thấp**: Tốc độ phản hồi chỉ từ 35ms - 70ms.
- **Chất lượng hiển thị cao**: Độ phân giải gốc, tốc độ khung hình lên tới 60fps+.
- **Truyền âm thanh**: Tự động chuyển tiếp âm thanh từ Android sang PC (yêu cầu Android 11+).
- **Điều khiển toàn diện**: Sử dụng chuột và bàn phím máy tính để thao tác, gõ tiếng Việt, chơi game, thao tác ứng dụng.
- **Hỗ trợ kết nối không dây**: Kết nối qua mạng Wi-Fi cùng lớp mạng mà không cần cắm cáp liên tục.
- **Chia sẻ Clipboard**: Tự động đồng bộ copy/paste văn bản 2 chiều giữa điện thoại và máy tính.
- **Kéo thả tiện lợi**: Kéo thả tệp APK để tự động cài đặt, kéo thả file để sao chép vào bộ nhớ máy.

---

## 📱 Yêu cầu chuẩn bị trên điện thoại

1. Mở **Cài đặt (Settings)** > **Thông tin điện thoại (About Phone)**.
2. Nhấn liên tục 7 lần vào mục **Số hiệu bản dựng (Build Number)** cho đến khi hiển thị thông báo *Bạn đã là nhà phát triển*.
3. Quay lại menu Cài đặt > chọn **Tùy chọn nhà phát triển (Developer Options)**.
4. Bật mục **Gỡ lỗi USB (USB Debugging)**.
5. *(Đối với Xiaomi / Redmi / POCO)*: Bật thêm mục **Cài đặt bảo mật (Gỡ lỗi USB / USB debugging (Security settings))** để có thể click chuột và nhập phím.

---

## 🚀 Hướng dẫn sử dụng

### 1. Kết nối qua cáp USB (Khuyên dùng - Ổn định nhất)
1. Cắm cáp USB kết nối điện thoại với máy tính.
2. Trên màn hình điện thoại sẽ xuất hiện hộp thoại hỏi *"Cho phép gỡ lỗi USB?"* -> Tích chọn **Luôn cho phép từ máy tính này** và chọn **Cho phép (OK)**.
3. Chạy một trong các cách sau:
   - **Cách 1**: Nhấp đúp chuột vào file `scrcpy.exe` hoặc `scrcpy-noconsole.vbs` (chạy ẩn cửa sổ dòng lệnh).
   - **Cách 2**: Nhấp đúp chuột vào `scrcpy-console.bat` (hiển thị log nếu có lỗi).

---

### 2. Kết nối không dây (Qua Wi-Fi)

> **Lưu ý**: Điện thoại và máy tính phải kết nối chung một mạng Wi-Fi.

1. **Bước 1**: Cắm cáp USB vào máy tính lần đầu.
2. **Bước 2**: Nhấp đúp chuột vào `open_a_terminal_here.bat` và gõ lệnh:
   ```cmd
   adb tcpip 5555
   ```
3. **Bước 3**: Tìm địa chỉ IP của điện thoại (Vào *Cài đặt > Wi-Fi > Chi tiết mạng* hoặc *Thông tin trạng thái IP*, ví dụ: `192.168.1.50`).
4. **Bước 4**: Rút cáp USB ra, sau đó gõ:
   ```cmd
   adb connect 192.168.1.50:5555
   ```
   *(Thay `192.168.1.50` bằng IP thực tế của điện thoại)*
5. **Bước 5**: Gõ `scrcpy` hoặc nhấp đúp vào `scrcpy.exe` để bắt đầu.

---

## ⌨️ Phím tắt tiện ích (Shortcuts)

> Phím bổ trợ `MOD` mặc định là **Alt trái** hoặc **Ctrl trái**.

| Phím tắt | Chức năng |
| :--- | :--- |
| `MOD` + `f` | Bật / Tắt chế độ toàn màn hình (Fullscreen) |
| `MOD` + `h` | Quay về màn hình chính (Home) |
| `MOD` + `b` / *Chuột phải* | Quay lại (Back) |
| `MOD` + `s` | Mở danh sách ứng dụng gần đây (App Switcher) |
| `MOD` + `p` | Bật / Tắt nguồn màn hình |
| `MOD` + `o` | **Tắt màn hình điện thoại** (nhưng vẫn thao tác bình thường trên PC - giúp giảm nhiệt & tiết kiệm pin) |
| `MOD` + `Shift` + `o` | Bật lại màn hình điện thoại |
| `MOD` + `r` | Xoay hướng màn hình |
| `MOD` + `Up` / `Down` | Tăng / Giảm âm lượng |
| `MOD` + `Shift` + `v` | Dán văn bản từ máy tính vào điện thoại |
| `MOD` + `k` | Mở thanh thông báo (Notification panel) |

---

## 🛠️ Một số lệnh nâng cao qua Terminal

Mở `open_a_terminal_here.bat` và gõ:

- **Giảm độ phân giải để tăng tốc độ / máy yếu**:
  ```cmd
  scrcpy -m 1024
  ```
- **Giới hạn tốc độ bit (Bitrate)**:
  ```cmd
  scrcpy -b 8M
  ```
- **Tắt âm thanh (chỉ truyền hình ảnh)**:
  ```cmd
  scrcpy --no-audio
  ```
- **Tự động tắt màn hình điện thoại khi mở scrcpy**:
  ```cmd
  scrcpy --turn-screen-off
  ```
- **Ghi lại màn hình vào file video**:
  ```cmd
  scrcpy --record=video.mp4
  ```

---

## ❓ Câu hỏi thường gặp & Khắc phục sự cố

1. **Lỗi `error: device unauthorized`**:
   - Mở màn hình điện thoại, kiểm tra thông báo xác thực USB Debugging và nhấn **Cho phép (Allow)**.
2. **Lỗi `error: no devices/emulators found`**:
   - Kiểm tra lại cáp kết nối USB (đảm bảo cáp hỗ trợ truyền dữ liệu, không chỉ là cáp sạc).
   - Đảm bảo đã bật **Gỡ lỗi USB** trong Cài đặt nhà phát triển.
3. **Không click chuột hoặc gõ chữ được trên máy Xiaomi / Redmi / POCO**:
   - Vào *Cài đặt nhà phát triển* > Bật **Cài đặt bảo mật (Gỡ lỗi USB)** (yêu cầu đăng nhập tài khoản Mi và có SIM trong máy để kích hoạt lần đầu).
