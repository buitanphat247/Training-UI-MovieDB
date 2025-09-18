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

## 🔀 Cách Gộp Mã Nguồn

### Cách 1: Pull Request (Khuyến Khích)

#### Tạo Pull Request:

1. Truy cập GitHub repository
2. Nhấn "Compare & pull request" khi thấy thông báo
3. Điền thông tin:
   - **Title**: `feat: Add login page with form validation`
   - **Description**: Mô tả chi tiết những gì đã thay đổi
   - **Reviewers**: Gán đồng đội để review code

#### Code Review và Merge:

1. Đồng đội review code trong tab "Files changed"
2. Để lại comment nếu cần chỉnh sửa
3. Sau khi approve, nhấn "Merge pull request"
4. Xóa nhánh feature sau khi merge

### Cách 2: Merge Trực Tiếp (Chỉ dùng khi cần thiết)

```bash
# Chuyển về nhánh main
git checkout main

# Cập nhật mã mới nhất
git pull origin main

# Gộp nhánh tính năng
git merge feature/login-page

# Đẩy lên GitHub
git push origin main

# Xóa nhánh local
git branch -d feature/login-page
git push origin --delete feature/login-page
```

# Phân quyền team leader

## ⚠️ Giải Quyết Xung Đột

### Khi có xung đột merge:

```bash
# Git sẽ báo lỗi như này:
# CONFLICT (content): Merge conflict in src/App.jsx
# Automatic merge failed; fix conflicts and then commit the result.
```

### Các bước giải quyết:

1. **Mở file bị xung đột**:

```bash
# Git sẽ đánh dấu xung đột như này:
<<<<<<< HEAD
// Code từ nhánh hiện tại
=======
// Code từ nhánh đang merge
>>>>>>> feature/login-page
```

2. **Chỉnh sửa file**:

   - Xóa các dấu `<<<<<<<`, `=======`, `>>>>>>>`
   - Giữ lại code đúng
   - Đảm bảo code hoạt động

3. **Commit giải pháp**:

```bash
git add .
git commit -m "resolve: Fix merge conflict in App.jsx"
```

## 💡 Lời Khuyên Hữu Ích

### Giao Tiếp

- **Trao đổi trước khi code**: Thông báo cho đồng đội về tính năng đang làm
- **Sử dụng Issues**: Tạo issue trên GitHub để theo dõi công việc
- **Comment rõ ràng**: Viết commit message và PR description chi tiết

### Thói Quen Tốt

- **Pull thường xuyên**: `git pull origin main` trước khi bắt đầu làm việc
- **Commit nhỏ**: Chia nhỏ công việc thành nhiều commit có ý nghĩa
- **Test trước khi push**: Đảm bảo code chạy được trước khi chia sẻ

### File .gitignore

Tạo file `.gitignore` để loại trừ các file không cần thiết:

```gitignore
# Dependencies
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Environment variables
.env
.env.local
.env.development.local
.env.test.local
.env.production.local

# Build outputs
dist/
build/

# IDE files
.vscode/
.idea/
*.swp
*.swo

# OS files
.DS_Store
Thumbs.db
```

## 📝 Quy Tắc Đặt Tên

### Nhánh (Branches)

```bash
# Tính năng mới
feature/user-authentication
feature/movie-search
feature/favorite-movies

# Sửa lỗi
bugfix/fix-login-validation
bugfix/resolve-movie-loading

# Sửa lỗi khẩn cấp
hotfix/security-patch
```

### Commit Messages

Sử dụng [Conventional Commits](https://www.conventionalcommits.org/):

```bash
# Cú pháp: type(scope): description

feat: Add user login functionality
fix: Resolve movie search not working
docs: Update README with installation guide
style: Format code with prettier
refactor: Extract movie card component
test: Add unit tests for login form
chore: Update dependencies
```

### Pull Request Titles

```bash
feat: Add movie search with filters
fix: Resolve responsive layout issues
docs: Add GitHub workflow documentation
```

## 🔧 Các Lệnh Git Hữu Ích

### Kiểm tra trạng thái

```bash
# Xem trạng thái hiện tại
git status

# Xem lịch sử commit
git log --oneline

# Xem các nhánh
git branch -a
```

### Undo/Reset

```bash
# Undo file chưa add
git checkout -- filename

# Undo file đã add
git reset HEAD filename

# Undo commit cuối (chưa push)
git reset --soft HEAD~1

# Undo commit cuối (đã push - cẩn thận!)
git revert HEAD
```

### Stash (Tạm lưu thay đổi)

```bash
# Lưu thay đổi tạm thời
git stash

# Xem danh sách stash
git stash list

# Lấy lại thay đổi
git stash pop
```

## 🚨 Xử Lý Tình Huống Khẩn Cấp

### Khi push nhầm lên main

```bash
# Tạo nhánh từ commit trước đó
git checkout -b feature/correct-branch
git checkout main
git reset --hard HEAD~1
git push origin main --force
```

### Khi cần sửa lỗi khẩn cấp

```bash
# Tạo hotfix branch từ main
git checkout main
git checkout -b hotfix/critical-bug-fix
# Sửa lỗi và commit
git push origin hotfix/critical-bug-fix
# Tạo PR để merge vào main
```

## 📞 Hỗ Trợ

Nếu gặp vấn đề với Git workflow:

1. Kiểm tra [Git Documentation](https://git-scm.com/doc)
2. Tìm kiếm trên [Stack Overflow](https://stackoverflow.com/questions/tagged/git)
3. Tạo issue trên GitHub repository
4. Liên hệ trực tiếp với team lead

---

**Lưu ý**: Luôn backup code quan trọng và test kỹ trước khi merge vào nhánh main!
