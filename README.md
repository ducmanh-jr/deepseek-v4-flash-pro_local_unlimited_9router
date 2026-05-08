# 🚀 deepseek-v4-flash-pro_local_unlimited_9router

Chào mừng các bạn đã sở hữu "vũ khí" tối thượng: Biến tài khoản DeepSeek Web miễn phí thành một API xịn xò để tích hợp thẳng vào VS Code. 

---

## 🌟 ĐIỂM NỔI BẬT & BÍ KÍP "VƯỢT RÀO" (QUAN TRỌNG)

### 1. 🛡️ Cơ chế "Vượt rào" khi bị chặn (Captcha/Rate Limit)
Đây là điểm quan trọng nhất bạn cần nhớ khi sử dụng hệ thống này:
*   **Hiện tượng:** Khi Cline hoặc VS Code báo lỗi (429 Too Many Requests hoặc 403 Forbidden), nghĩa là DeepSeek đang nghi ngờ bạn là Robot và bắt giải Captcha.
*   **Cách xử lý (Bí kíp):** 
    1.  Mở trình duyệt và truy cập ngay vào [chat.deepseek.com](https://chat.deepseek.com).
    2.  Nếu thấy bảng xác thực (chọn hình, kéo thanh trượt...), hãy tự tay hoàn thành nó.
    3.  Gõ một câu chat bất kỳ trên web để đảm bảo phiên làm việc (session) đã được "mở khóa".
    4.  Quay lại VS Code và nhấn **Retry**. Mọi thứ sẽ hoạt động bình thường!

### 2. 🧠 Hỗ trợ Full Tư duy (Reasoning/Thinking)
Hệ thống này hỗ trợ đầy đủ luồng **Reasoning** của DeepSeek. Khi Cline hoạt động, bạn sẽ thấy phần "Thinking" hiện ra – đây là lúc AI đang phân tích logic cực sâu trước khi viết code.

### 3. 💸 Tiết kiệm chi phí tuyệt đối
Bạn không cần nạp tiền vào API chính thức. Hệ thống tận dụng gói miễn phí của Web, cho phép bạn thực hiện những dự án lớn mà không lo "cháy túi".

---

## 🛠️ THÔNG TIN CẤU HÌNH HỆ THỐNG

### 1. Thông số kết nối API (OpenAI Compatible)
Khi tích hợp vào bất kỳ đâu (VS Code, Cline, Cherry Studio...), hãy dùng thông số sau:
*   **Base URL:** `http://localhost:5001/v1`
*   **API Key:** `antigravity_2026`
*   **Model ID:** `deepseek-v4-flash` hoặc `deepseek-v4-pro`

### 🔄 Cách chuyển đổi giữa bản Flash và Pro
Tùy vào độ khó của công việc, bạn nên chọn Model ID phù hợp:
*   **deepseek-v4-flash (Mặc định):** Phản hồi cực nhanh. Dùng cho chat bình thường, giải thích code hoặc sửa lỗi nhỏ.
*   **deepseek-v4-pro (Khuyên dùng cho dự án):** Kích hoạt khả năng suy nghĩ sâu (Reasoning). Dùng khi cần xây dựng tính năng mới, viết logic phức tạp hoặc cấu trúc lại toàn bộ project.

**Cách đổi trong Cline:** Nhấn vào **Settings (Răng cưa)** -> Sửa ô **Model ID** thành tên bạn muốn -> Nhấn **Done**.


### 2. Cách khởi động hệ thống
Mỗi khi mở máy tính để code, bạn cần chạy file này đầu tiên:
*   **Đường dẫn:** `c:\Users\Admin\ducmanhjr\agent son\run_ds2api.bat`
*   *Lưu ý: Không được đóng cửa sổ Command Prompt này trong suốt quá trình code.*

---

## 💻 TÍCH HỢP VS CODE (CLINE & CONTINUE)

### ✅ Đối với Cline (Khuyên dùng)
Cline là công cụ mạnh nhất để tự động hóa lập trình.
1.  Vào **Settings** (biểu tượng Răng cưa) trong bảng Cline.
2.  Tại ô **API Provider**, chọn: **OpenAI Compatible**.
3.  Tại ô **Base URL**, điền: `http://localhost:5001/v1`
4.  Tại ô **API Key**, điền: `antigravity_2026`
5.  Tại ô **Model ID**, điền: `deepseek-v4-flash` (hoặc `deepseek-v4-pro`).
6.  Nhấn **Done** ở dưới cùng để lưu lại.

### ✅ Đối với Continue
1.  Mở file `config.json` của Continue (biểu tượng răng cưa trong bảng Continue).
2.  Thêm đoạn cấu hình sau vào mục `models`:
```json
{
  "title": "DeepSeek Free",
  "model": "deepseek-v4-flash",
  "apiBase": "http://localhost:5001/v1",
  "apiKey": "antigravity_2026",
  "provider": "openai"
}
```

---

## ⚠️ LƯU Ý BẢO MẬT & SỬ DỤNG
*   **Không chia sẻ API Key:** Mặc dù chạy ở localhost, nhưng bạn nên giữ kín Key `antigravity_2026` để tránh xung đột dữ liệu.
*   **Cập nhật tài khoản:** Nếu bạn đổi mật khẩu DeepSeek, hãy cập nhật lại trong file `config.json` tại thư mục `ds2api_bin`.
*   **Quản lý phiên:** Trang quản trị của Bridge nằm tại: `http://127.0.0.1:5001/admin` (Dùng Admin Key: `antigravity_2026` để đăng nhập).

---

