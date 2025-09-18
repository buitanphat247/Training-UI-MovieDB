# UI Movie Database

Dự án giao diện người dùng cho cơ sở dữ liệu phim được xây dựng bằng React và Vite.

## 📋 Yêu cầu hệ thống

- **Node.js**: phiên bản 16.0.0 trở lên
- **npm**: phiên bản 7.0.0 trở lên (hoặc yarn/pnpm)
- **Trình duyệt**: Chrome, Firefox, Safari, Edge (phiên bản mới nhất)

## 🚀 Hướng dẫn cài đặt

### Bước 1: Clone dự án
```bash
git clone <repository-url>
cd UI-Movie-DB
```

### Bước 2: Cài đặt dependencies
```bash
npm install
```

### Bước 3: Chạy dự án
```bash
npm run dev
```

Dự án sẽ chạy tại: `http://localhost:5173`

## 📜 Các lệnh có sẵn

| Lệnh | Mô tả |
|------|-------|
| `npm run dev` | Chạy dự án ở chế độ development |
| `npm run build` | Build dự án cho production |
| `npm run preview` | Xem trước dự án đã build |
| `npm run lint` | Kiểm tra lỗi code với ESLint |

## 🛠️ Công nghệ sử dụng

- **React 19.1.1** - Thư viện UI
- **Vite 7.1.2** - Build tool và dev server
- **ESLint** - Code linting
- **SWC** - Compiler nhanh cho React

## 📁 Cấu trúc dự án

```
UI-Movie-DB/
├── public/                 # Thư mục chứa file tĩnh
│   └── vite.svg
├── src/                    # Source code chính
│   ├── assets/            # Hình ảnh, icons
│   ├── App.jsx           # Component chính
│   ├── App.css           # Styles cho App
│   ├── main.jsx          # Entry point
│   └── index.css         # Global styles
├── package.json          # Dependencies và scripts
├── vite.config.js        # Cấu hình Vite
└── eslint.config.js      # Cấu hình ESLint
```

## 🔧 Cấu hình

### Vite Configuration
Dự án sử dụng Vite với plugin React SWC để có hiệu suất tốt nhất.

### ESLint Configuration
Dự án đã được cấu hình ESLint với các rules cơ bản cho React.

## 🌐 Triển khai

### Build cho production
```bash
npm run build
```

File build sẽ được tạo trong thư mục `dist/`.

### Preview build
```bash
npm run preview
```

## 🤝 Đóng góp

1. Fork dự án
2. Tạo feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Mở Pull Request

## 📞 Hỗ trợ

Nếu gặp vấn đề trong quá trình cài đặt hoặc chạy dự án, vui lòng tạo issue hoặc liên hệ qua email.

## 📄 License

Dự án này được phân phối dưới MIT License.
