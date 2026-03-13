# 📚 Kho Bài Tập Tự Luận

Trang web lưu trữ bài tập tự luận với hỗ trợ LaTeX, host miễn phí trên GitHub Pages.

---

## 🚀 Hướng dẫn cài đặt (5 bước)

### Bước 1 — Tạo GitHub repo

1. Đăng nhập [github.com](https://github.com)
2. Nhấn **+** → **New repository**
3. Điền tên repo (ví dụ: `bai-tap`)
4. Chọn **Public**
5. Nhấn **Create repository**

---

### Bước 2 — Upload file lên repo

Upload lần lượt các file theo đúng cấu trúc thư mục:

```
repo/
├── index.html          ← trang công khai
├── admin.html          ← trang admin
├── data/
│   └── exercises.json  ← dữ liệu bài tập
└── README.md
```

Cách upload:
- Vào repo → **Add file** → **Upload files**
- Kéo thả toàn bộ file vào (tạo folder `data/` bằng cách đặt tên `data/exercises.json`)

---

### Bước 3 — Bật GitHub Pages

1. Vào repo → **Settings** → **Pages** (thanh bên trái)
2. **Source**: chọn `Deploy from a branch`
3. **Branch**: chọn `main` → `/root`
4. Nhấn **Save**
5. Chờ ~1 phút → trang sẽ xuất hiện tại:
   ```
   https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
   ```

---

### Bước 4 — Sửa cấu hình trong `index.html`

Mở file `index.html`, tìm đoạn này (gần cuối, trong thẻ `<script>`):

```js
const REPO_OWNER = 'YOUR_GITHUB_USERNAME';  // ← đổi thành username của bạn
const REPO_NAME  = 'YOUR_REPO_NAME';         // ← đổi thành tên repo
```

Commit lại sau khi sửa.

---

### Bước 5 — Tạo Personal Access Token (để dùng trang Admin)

1. Vào [github.com/settings/tokens/new](https://github.com/settings/tokens/new)
2. **Note**: `BaiTapAdmin`
3. **Expiration**: chọn thời hạn bạn muốn (hoặc "No expiration")
4. **Scopes**: tick chọn ✅ `repo`
5. Nhấn **Generate token** → copy token (dạng `ghp_xxxx...`)

> ⚠️ Chỉ thấy token 1 lần! Hãy lưu lại ngay.

---

## 🔑 Sử dụng trang Admin

1. Mở `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/admin.html`
2. Điền:
   - **GitHub Username** (ví dụ: `nguyenvana`)
   - **Tên repo** (ví dụ: `bai-tap`)
   - **Personal Access Token** (token vừa tạo ở Bước 5)
3. Nhấn **Kết nối**
4. Thêm/xóa bài tập → mỗi thao tác tự động **commit lên GitHub**
5. Người dùng F5 trang chính là thấy bài mới ngay

> Token được lưu trong localStorage của trình duyệt admin, không gửi đi đâu khác.

---

## 📝 Định dạng LaTeX được hỗ trợ

```latex
\begin{ex}
Giải thích tại sao...
\loigiai{
Biến cố $A$: ...\\
Xác suất: $P(A) = \left(\dfrac{5}{6}\right)^4 \approx 0{,}5177$
}
\end{ex}
```

- `$...$` — công thức inline
- `$$...$$` — công thức display (căn giữa)
- `\\` — xuống dòng trong lời giải

---

## 🌙 Tính năng

- ✅ Dark / Light mode (nhớ lựa chọn)
- ✅ Lọc theo môn học
- ✅ Tìm kiếm toàn văn
- ✅ Render LaTeX / MathJax
- ✅ Admin qua GitHub API (không cần server)
- ✅ Nhập bài hàng loạt từ LaTeX
