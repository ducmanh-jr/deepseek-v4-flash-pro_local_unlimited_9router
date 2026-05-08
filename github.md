# 🛡️ Hướng dẫn thiết lập Trạng thái "Showcase Bảo mật" trên GitHub

Tài liệu này ghi lại các bước kỹ thuật để tạo ra một kho lưu trữ GitHub có thể **hiển thị cấu trúc thư mục** nhưng **chặn hoàn toàn quyền truy cập và tải về** đối với các thư mục quan trọng.

---

## ✨ Trạng thái đạt được
1.  **Hiển thị tên thư mục:** Người xem vẫn thấy đầy đủ các thư mục như `9router`, `ds2api`... (Tạo uy tín cho dự án).
2.  **KHÔNG thể truy cập:** Các thư mục hiển thị dưới dạng "liên kết rỗng" (Gitlinks - mode 160000). Click vào sẽ không ra nội dung hoặc báo lỗi 404.
3.  **KHÔNG thể tải về:** Khi người khác `Download ZIP` hoặc `clone`, các thư mục này sẽ hoàn toàn rỗng.
4.  **An toàn tuyệt đối:** Toàn bộ mã nguồn và công cụ (linh hồn dự án) chỉ nằm duy nhất trên máy cá nhân của bạn.

---

## 🛠️ Các bước thực hiện (Bí thuật Git)

### Bước 1: Khởi tạo Git nội bộ cho từng thư mục cần bảo mật
Truy cập vào từng thư mục và biến chúng thành một kho lưu trữ độc lập (nhưng không đẩy lên mạng).
```bash
cd 9router
git init
git add .
git commit -m "Locking content"
cd ..
```
*(Lặp lại tương tự với các thư mục khác)*

### Bước 2: Xóa dấu vết cũ trên GitHub (nếu lỡ đẩy lên)
Nếu trước đó bạn đã lỡ đẩy code lên, phải xóa chúng khỏi bộ nhớ đệm (cache) của Git nhưng vẫn giữ lại file trên máy.
```bash
git rm -r --cached 9router ds2api ds2api_bin
```

### Bước 3: Cấu hình chặn trong .gitignore
Đảm bảo Git không bao giờ cố gắng đẩy nội dung bên trong các thư mục này lên nữa.
```text
# Thêm vào file .gitignore
9router/
ds2api/
ds2api_bin/
```

### Bước 4: Đẩy "Liên kết rỗng" (Gitlinks) lên GitHub
Đây là bước quan trọng nhất. Khi bạn `git add` một thư mục có chứa `.git` bên trong (nhưng không phải submodule chính thức), Git sẽ chỉ ghi lại "dấu vân tay" của thư mục đó.
```bash
git add 9router ds2api ds2api_bin
git commit -m "Secure gitlinks: show folders but lock contents"
git push origin main
```

---

## 💡 Lưu ý cho chủ sở hữu
*   **Dữ liệu của bạn:** Chỉ tồn tại trên máy tính này. Nếu bạn xóa thư mục trên máy, bạn sẽ mất dữ liệu vì GitHub không lưu bản sao của các thư mục này.
*   **Cách sao lưu:** Hãy sao lưu các thư mục này ra ổ cứng ngoài hoặc một kho lưu trữ **Private** (Riêng tư) khác nếu cần dự phòng.

---
*Tài liệu được soạn thảo bởi trợ lý Antigravity AI.*
