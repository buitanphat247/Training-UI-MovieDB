# 🤝 Hướng Dẫn Làm Việc Nhóm với GitHub

Tài liệu này hướng dẫn chi tiết cách làm việc nhóm hiệu quả với Git và GitHub cho dự án UI Movie Database.

## 📋 Mục Lục

- [Quy Trình Git Cơ Bản](#quy-trình-git-cơ-bản)
- [Các Bước Làm Việc Thực Tế](#các-bước-làm-việc-thực-tế)
- [Cách Gộp Mã Nguồn](#cách-gộp-mã-nguồn)
- [Giải Quyết Xung Đột](#giải-quyết-xung-đột)
- [Lời Khuyên Hữu Ích](#lời-khuyên-hữu-ích)
- [Quy Tắc Đặt Tên](#quy-tắc-đặt-tên)

## 🌳 Quy Trình Git Cơ Bản

### Cấu Trúc Nhánh

```
main (nhánh chính)
├── feature/login-page
├── feature/movie-list
├── feature/user-profile
└── bugfix/fix-search-function
```

- **main**: Nhánh ổn định, chứa phiên bản hoàn chỉnh và sẵn sàng triển khai
- **feature/**: Nhánh phát triển tính năng mới
- **bugfix/**: Nhánh sửa lỗi
- **hotfix/**: Nhánh sửa lỗi khẩn cấp

## 🚀 Các Bước Làm Việc Thực Tế

### Bước 1: Khởi Tạo Dự Án (Chỉ làm 1 lần)

```bash
# Khởi tạo repo local
git init

# Tạo file README
echo "# UI Movie Database" > README.md

# Lưu thay đổi ban đầu
git add .
git commit -m "feat: Initial commit - setup project structure"

# Liên kết với GitHub
git remote add origin https://github.com/your-username/UI-Movie-DB.git

# Đẩy lên GitHub
git push -u origin main
```

### Bước 2: Đồng Đội Tham Gia

```bash
# Clone dự án về máy
git clone https://github.com/your-username/UI-Movie-DB.git
cd UI-Movie-DB

# Cài đặt dependencies
npm install
```

### Bước 3: Phát Triển Tính Năng

#### Trước khi bắt đầu làm việc:

```bash
# Chuyển về nhánh main
git checkout main

# Cập nhật mã nguồn mới nhất
git pull origin main
```

#### Tạo nhánh mới cho tính năng:

> **💡 Tại sao cần tạo nhánh riêng?**
>
> - Mỗi tính năng có nhánh riêng giúp tránh xung đột khi 2 người cùng làm việc
> - Dễ dàng theo dõi và quản lý từng tính năng
> - Có thể rollback dễ dàng nếu tính năng có vấn đề
> - Cho phép code review trước khi gộp vào main

```bash
# Tạo và chuyển sang nhánh mới cho tính năng
git checkout -b feature/login-page

# Hoặc tạo nhánh sửa lỗi
git checkout -b bugfix/fix-search-function
```

**📝 Quy tắc đặt tên nhánh:**

- `feature/tên-tính-năng`: Cho tính năng mới (VD: `feature/user-profile`, `feature/movie-search`)
- `bugfix/mô-tả-lỗi`: Cho sửa lỗi (VD: `bugfix/fix-login-error`, `bugfix/resolve-movie-loading`)
- `hotfix/sửa-khẩn-cấp`: Cho sửa lỗi khẩn cấp (VD: `hotfix/security-patch`)

**🔍 Kiểm tra nhánh hiện tại:**

```bash
# Xem nhánh đang làm việc
git branch

# Xem tất cả nhánh (cả local và remote)
git branch -a
```

#### Làm việc và commit:

> **⚠️ Lưu ý quan trọng:**
>
> - Luôn làm việc trên nhánh feature, KHÔNG BAO GIỜ code trực tiếp trên main
> - Commit thường xuyên để không mất công việc
> - Mỗi commit nên có một mục đích rõ ràng

```bash
# 1. Làm việc trên code...
# Ví dụ: Tạo file LoginForm.jsx, LoginForm.css, etc.

# 2. Kiểm tra những file đã thay đổi
git status

# 3. Thêm file vào staging area (chuẩn bị commit)
git add .                    # Thêm tất cả file thay đổi
# HOẶC
git add src/components/LoginForm.jsx  # Thêm file cụ thể

# 4. Commit với thông điệp rõ ràng
git commit -m "feat: Add login form with validation"

# 5. Đẩy nhánh lên GitHub (lần đầu cần -u để liên kết)
git push -u origin feature/login-page

# Các lần sau chỉ cần:
git push
```

**📋 Ví dụ workflow hoàn chỉnh cho 1 tính năng:**

```bash
# Bước 1: Cập nhật main trước khi bắt đầu
git checkout main
git pull origin main

# Bước 2: Tạo nhánh mới
git checkout -b feature/movie-card-component

# Bước 3: Làm việc và commit từng phần
# Tạo component
git add src/components/MovieCard.jsx
git commit -m "feat: Create MovieCard component structure"

# Thêm styles
git add src/components/MovieCard.css
git commit -m "style: Add MovieCard styling and responsive design"

# Thêm props và logic
git add src/components/MovieCard.jsx
git commit -m "feat: Add props handling and click events to MovieCard"

# Bước 4: Đẩy lên GitHub
git push -u origin feature/movie-card-component
```

**🎯 Best Practices khi commit:**

- **Commit nhỏ và thường xuyên**: Mỗi commit nên có 1 mục đích rõ ràng
- **Message rõ ràng**: Sử dụng [Conventional Commits](https://www.conventionalcommits.org/)
- **Test trước khi commit**: Đảm bảo code chạy được
- **Không commit code bị comment**: Xóa code thừa trước khi commit

```

```
