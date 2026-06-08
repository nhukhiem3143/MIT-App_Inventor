# 📱 BÀI TẬP LỚN – PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG
### TEE0419 | MIT App Inventor

---

> **Sinh viên:** Nguuyễn Như Khiêm
> **MSSV:** K225480106030

---

## 📋 MỤC LỤC

- [Giới thiệu tổng quan](#-giới-thiệu-tổng-quan)
- [Công cụ sử dụng](#-công-cụ-sử-dụng)
- [Cấu trúc ứng dụng](#-cấu-trúc-ứng-dụng)
- [Hướng dẫn tạo dự án](#-hướng-dẫn-tạo-dự-án)
- [Screen 1 – About Me](#-screen-1--about-me)
- [Screen 2 – Giải bài toán](#-screen-2--giải-bài-toán)
- [Screen 3 – WebView](#-screen-3--webview)
- [Thanh công cụ & Palette](#-thanh-công-cụ--palette)
- [Lập trình Block](#-lập-trình-block)
- [Backpack – Copy & Paste Block](#-backpack--copy--paste-block)
- [Ưu & Nhược điểm của lập trình Block](#-ưu--nhược-điểm-của-lập-trình-block)
- [Kết quả & Demo](#-kết-quả--demo)

---

## 🌟 Giới thiệu tổng quan

Bài tập lớn xây dựng một ứng dụng Android hoàn chỉnh bằng **MIT App Inventor** – nền tảng lập trình trực quan dạng kéo-thả (drag & drop). Ứng dụng gồm **3 màn hình (Screen)** với các chức năng:

| Screen | Tên | Chức năng |
|--------|-----|-----------|
| Screen1 | About Me | Giới thiệu bản thân + điều hướng sang 2 screen còn lại |
| Screen2 | Giải bài toán | Giải một bài toán đơn giản (ví dụ: tính BMI, giải phương trình bậc 1...) |
| Screen3 | WebView | Nhúng và hiển thị một trang web có sẵn |

---

## 🛠 Công cụ sử dụng

| Công cụ | Mô tả |
|---------|-------|
| [MIT App Inventor](https://appinventor.mit.edu/) | Nền tảng tạo ứng dụng Android bằng giao diện kéo-thả |
| Trình duyệt web | Chrome / Firefox / Edge – truy cập App Inventor online |
| MIT AI2 Companion | App cài trên điện thoại để test trực tiếp |
| Android Emulator | Giả lập thiết bị Android (nếu không có điện thoại thật) |

---

## 📂 Cấu trúc ứng dụng

```
MyApp/
├── Screen1  (About Me)
│   ├── Label – Tên, MSSV, lớp
│   ├── Image – Ảnh đại diện
│   ├── Button → mở Screen2
│   └── Button → mở Screen3
│
├── Screen2  (Giải bài toán)
│   ├── TextBox – Nhập dữ liệu
│   ├── Button  – Tính toán
│   └── Label   – Hiển thị kết quả
│
└── Screen3  (WebView)
    ├── WebViewer – Hiển thị trang web
    └── Button    – Quay lại Screen1
```

---

## 🚀 Hướng dẫn tạo dự án

### Bước 1 – Đăng nhập và tạo project mới

1. Truy cập **[https://appinventor.mit.edu](https://appinventor.mit.edu)**
2. Nhấn **"Create Apps!"** → Đăng nhập bằng tài khoản Google
3. Chọn **Projects → Start new project**
4. Đặt tên project (không dấu, không khoảng trắng): ví dụ `BaiTapLon_TEE0419`

> ✅ Giao diện chính gồm 2 phần: **Designer** (thiết kế giao diện) và **Blocks** (lập trình logic)

### Bước 2 – Thêm Screen mới

1. Ở góc trên cùng, nhấn **"Add Screen"**
2. Đặt tên: `Screen2`, `Screen3`
3. Mỗi screen được thiết kế và lập trình độc lập

<!-- Gợi ý: chèn ảnh giao diện tổng quan App Inventor tại đây -->
> 📌 **[CHÈN ẢNH: Giao diện tổng quan MIT App Inventor – Designer view]**

---

## 👤 Screen 1 – About Me

### Mục đích
Giới thiệu thông tin bản thân và cung cấp nút điều hướng sang 2 màn hình còn lại.

### Các thành phần (Components)

| Component | Vị trí trong Palette | Thuộc tính cần chỉnh |
|-----------|---------------------|----------------------|
| `Label` | User Interface | Text = "Họ và tên", FontSize = 20, Bold = ✓ |
| `Label` | User Interface | Text = "MSSV: ...", FontSize = 16 |
| `Image` | User Interface | Picture = [upload ảnh], Width = 150px |
| `Button` | User Interface | Text = "📊 Giải bài toán", Width = Fill parent |
| `Button` | User Interface | Text = "🌐 Xem Web", Width = Fill parent |

### Cách kéo thả và chỉnh thuộc tính

1. Trong tab **Designer**, tìm component trong bảng **Palette** bên trái
2. **Kéo** component vào vùng **Viewer** (khung giả lập điện thoại ở giữa)
3. Sau khi thả, click chọn component → bảng **Properties** bên phải sẽ hiện ra
4. Chỉnh các thuộc tính: màu sắc, font chữ, kích thước, căn lề...

<!-- Gợi ý: chèn ảnh Screen1 đã hoàn thiện tại đây -->
> 📌 **[CHÈN ẢNH: Giao diện Screen1 – About Me đã thiết kế xong]**

### Lập trình Block – Nút chuyển Screen

```
Khi [Button_Screen2].Click
→ Thực hiện: mở màn hình [Screen2]
```

```
Khi [Button_Screen3].Click
→ Thực hiện: mở màn hình [Screen3]
```

<!-- Gợi ý: chèn ảnh block chuyển screen tại đây -->
> 📌 **[CHÈN ẢNH: Block code chuyển Screen1 → Screen2 và Screen3]**

---

## 🧮 Screen 2 – Giải bài toán

> **Ví dụ bài toán:** Tính chỉ số BMI (Body Mass Index)
> Công thức: `BMI = Cân nặng (kg) / (Chiều cao (m))²`

### Các thành phần

| Component | Chức năng |
|-----------|-----------|
| `Label` | Tiêu đề "Tính chỉ số BMI" |
| `TextBox (tb_cannang)` | Nhập cân nặng (kg) |
| `TextBox (tb_chieucao)` | Nhập chiều cao (m) |
| `Button (btn_tinh)` | Nút "Tính BMI" |
| `Label (lbl_ketqua)` | Hiển thị kết quả BMI |
| `Button (btn_quaylai)` | Quay lại Screen1 |

### Cách chỉnh thuộc tính quan trọng

- `TextBox` → **NumbersOnly = True** (chỉ cho nhập số)
- `TextBox` → **Hint = "Nhập cân nặng..."** (placeholder gợi ý)
- `Label` → **Text = ""** (để trống, sẽ hiện kết quả sau khi tính)

<!-- Gợi ý: chèn ảnh giao diện Screen2 tại đây -->
> 📌 **[CHÈN ẢNH: Giao diện Screen2 – Tính BMI]**

### Lập trình Block

**Logic tính BMI:**
```
Khai báo biến: cannang, chieucao, bmi

Khi [btn_tinh].Click:
  cannang ← [tb_cannang].Text (chuyển sang số)
  chieucao ← [tb_chieucao].Text (chuyển sang số)
  bmi ← cannang / (chieucao × chieucao)
  [lbl_ketqua].Text ← "BMI của bạn: " + làm tròn(bmi, 2)
  
  Nếu bmi < 18.5 → hiện "Gầy"
  Nếu bmi < 25.0 → hiện "Bình thường"
  Nếu bmi < 30.0 → hiện "Thừa cân"
  Ngược lại     → hiện "Béo phì"
```

<!-- Gợi ý: chèn ảnh block tính BMI tại đây -->
> 📌 **[CHÈN ẢNH: Block code tính BMI hoàn chỉnh]**

---

## 🌐 Screen 3 – WebView

### Mục đích
Hiển thị một trang web bên trong ứng dụng (không cần mở trình duyệt ngoài). Trang web cần hỗ trợ giao diện điện thoại (responsive).

> **Gợi ý trang web:** `https://www.wikipedia.org` hoặc `https://m.youtube.com`

### Các thành phần

| Component | Palette | Chức năng |
|-----------|---------|-----------|
| `WebViewer` | User Interface | Khung hiển thị trang web |
| `Button` | User Interface | Nút "Quay lại" về Screen1 |

### Chỉnh thuộc tính WebViewer

| Thuộc tính | Giá trị | Ý nghĩa |
|------------|---------|---------|
| `HomeUrl` | `https://www.wikipedia.org` | URL trang web mặc định khi mở |
| `Width` | Fill parent | Chiếm toàn bộ chiều ngang |
| `Height` | Fill parent | Chiếm toàn bộ chiều cao còn lại |
| `FollowLinks` | True | Cho phép click vào link bên trong |

<!-- Gợi ý: chèn ảnh Screen3 đang hiển thị trang web tại đây -->
> 📌 **[CHÈN ẢNH: Screen3 WebView đang hiển thị trang web trên giả lập điện thoại]**

### Lập trình Block

```
Khi [btn_quaylai].Click:
  → close screen (đóng Screen3, quay về Screen1)
```

---

## 🎨 Thanh công cụ & Palette

### Giao diện Designer gồm các khu vực chính:

```
┌─────────────────────────────────────────────────────┐
│  [Palette]   │    [Viewer]      │   [Components]     │
│              │                  │   [Properties]     │
│  Danh sách   │  Giả lập         │                    │
│  component   │  điện thoại      │  Thuộc tính của    │
│  có thể dùng │  (kéo thả vào)   │  component đang    │
│              │                  │  được chọn         │
└─────────────────────────────────────────────────────┘
```

### Các nhóm trong Palette

| Nhóm | Các component chính |
|------|---------------------|
| **User Interface** | Button, Label, TextBox, Image, CheckBox, Slider, Spinner |
| **Layout** | HorizontalArrangement, VerticalArrangement, TableArrangement |
| **Media** | Camera, ImagePicker, Player, Sound, VideoPlayer |
| **Drawing and Animation** | Canvas, Ball, ImageSprite |
| **Connectivity** | Web, BluetoothClient, ActivityStarter |
| **Sensors** | AccelerometerSensor, LocationSensor, Clock |
| **Storage** | TinyDB, File, CloudDB |

### Quy trình kéo thả và chỉnh thuộc tính

```
1. Tìm component trong Palette (bên trái)
         ↓
2. Kéo (drag) vào Viewer (màn hình giả lập ở giữa)
         ↓
3. Component xuất hiện trong danh sách Components (bên phải)
         ↓
4. Click chọn component → bảng Properties hiện ra
         ↓
5. Chỉnh các thuộc tính: Text, Color, Size, Visible...
```

**Mỗi thuộc tính có tác dụng khác nhau:**
- `Text` → Nội dung hiển thị
- `BackgroundColor` → Màu nền
- `FontSize` → Cỡ chữ
- `Width / Height` → Kích thước (px, % hoặc Fill parent)
- `Visible` → Ẩn/hiện component
- `Enabled` → Cho phép tương tác hay không

---

## 🔲 Lập trình Block

### Bản chất của lập trình Block

Lập trình Block trong App Inventor là cách **biểu diễn các câu lệnh bằng hình khối màu sắc** thay vì gõ text code. Mỗi khối đại diện cho một lệnh, và các khối có thể **ghép với nhau như puzzle (trò chơi ghép hình)**.

```
Ví dụ câu lệnh dạng code:
if (score > 100) { label.Text = "Bạn thắng!"; }

Tương đương dạng Block:
[Nếu] [score > 100]
  └── [lbl_kq].Text = ["Bạn thắng!"]
```

### Các loại Block cơ bản

| Màu | Loại Block | Ý nghĩa |
|-----|-----------|---------|
| 🟡 Vàng | **Events** (Sự kiện) | Khi nào thực thi (khi click, khi app khởi động...) |
| 🟢 Xanh lá | **Actions** (Hành động) | Làm gì (set text, open screen...) |
| 🔵 Xanh dương | **Control** (Điều khiển) | If/else, vòng lặp, gọi procedure |
| 🟠 Cam | **Math** (Toán học) | Cộng, trừ, nhân, chia, làm tròn... |
| 🔴 Đỏ | **Logic** | And, Or, Not, so sánh |
| 🟣 Tím | **Variables** (Biến) | Khai báo và sử dụng biến |
| ⚫ Xám | **Text** | Ghép chuỗi, tách chuỗi... |

<!-- Gợi ý: chèn ảnh giao diện Blocks editor tại đây -->
> 📌 **[CHÈN ẢNH: Giao diện màn hình Blocks với các block màu sắc]**

---

## 📦 Backpack – Copy & Paste Block

### Backpack là gì?

**Backpack** là tính năng "ba lô" trong App Inventor, cho phép **sao chép block từ screen này sang screen khác** hoặc từ project này sang project khác.

### Vị trí

> Backpack nằm ở **góc trên bên phải** màn hình Blocks, biểu tượng hình chiếc ba lô 🎒

### Cách sử dụng

**Copy block vào Backpack:**
```
1. Click chuột phải vào block cần sao chép
2. Chọn "Add to Backpack"
   HOẶC kéo trực tiếp block thả vào biểu tượng Backpack
```

**Lấy block từ Backpack ra dùng:**
```
1. Click vào biểu tượng Backpack (góc trên phải)
2. Backpack mở ra, hiển thị các block đã lưu
3. Kéo block từ Backpack vào vùng làm việc
```

**Xóa block khỏi Backpack:**
```
1. Mở Backpack
2. Click chuột phải vào block → "Remove from Backpack"
```

> ⚠️ **Lưu ý:** Block copy qua Backpack chỉ sao chép cấu trúc logic, các tên component tham chiếu có thể cần chỉnh lại cho phù hợp với screen đích.

<!-- Gợi ý: chèn ảnh Backpack đang mở tại đây -->
> 📌 **[CHÈN ẢNH: Backpack đang mở với các block đã lưu]**

---

## ⚖️ Ưu & Nhược điểm của lập trình Block

### ✅ Ưu điểm

| Ưu điểm | Giải thích |
|---------|-----------|
| **Dễ học, dễ nhớ** | Không cần nhớ cú pháp phức tạp – chỉ kéo và ghép |
| **Trực quan** | Cấu trúc logic hiện rõ qua màu sắc và hình dạng khối |
| **Hạn chế lỗi cú pháp** | Các khối chỉ ghép được khi đúng kiểu – compiler tự kiểm tra |
| **Tốc độ tạo prototype nhanh** | Phù hợp xây dựng ứng dụng đơn giản trong thời gian ngắn |
| **Phù hợp người mới** | Giúp người chưa biết code hiểu được tư duy lập trình |
| **Backpack tiện lợi** | Tái sử dụng logic giữa các màn hình dễ dàng |

### ❌ Nhược điểm

| Nhược điểm | Giải thích |
|-----------|-----------|
| **Khó quản lý dự án lớn** | Khi ứng dụng phức tạp, màn hình Blocks trở nên rối rắm |
| **Không linh hoạt** | Bị giới hạn bởi các block có sẵn, không thể tùy biến sâu |
| **Hiệu năng thấp hơn** | App Inventor tạo ra app có hiệu năng kém hơn code thuần |
| **Không tái sử dụng tốt** | Không có khái niệm module/library như lập trình thực sự |
| **Khó làm việc nhóm** | Không có version control (Git), khó merge code |
| **Phụ thuộc nền tảng** | Chỉ tạo được app Android, không build iOS |

### So sánh nhanh

```
Lập trình Block (App Inventor)     |    Lập trình Code (Java/Kotlin)
-----------------------------------|----------------------------------
Kéo thả, ghép hình                 |    Gõ văn bản thuần
Không cần cài đặt IDE              |    Cần Android Studio
Phù hợp nguyên mẫu (prototype)    |    Phù hợp sản phẩm thật
Giới hạn tính năng                 |    Không giới hạn
Dễ học trong vài giờ               |    Học hàng tháng đến năm
```

---

## 📸 Kết quả & Demo

### Ảnh màn hình ứng dụng

> 📌 **[CHÈN ẢNH: Screen1 – About Me trên điện thoại thật / giả lập]**

> 📌 **[CHÈN ẢNH: Screen2 – Giao diện nhập số và kết quả tính toán]**

> 📌 **[CHÈN ẢNH: Screen3 – WebView đang hiển thị trang web]**

### File đính kèm

| File | Mô tả |
|------|-------|
| `BaiTapLon_TEE0419.aia` | File dự án App Inventor (import vào App Inventor để chạy) |
| `BaiTapLon_TEE0419.apk` | File cài đặt Android (cài trực tiếp lên điện thoại) |

### Cách cài APK lên điện thoại

```
1. Trong App Inventor → Build → Android App (.apk)
2. Quét QR code hoặc tải file .apk về máy
3. Trên điện thoại: Cài đặt → Bảo mật → Cho phép cài từ nguồn không rõ
4. Mở file .apk → Cài đặt → Mở app
```

---

## 📚 Tài liệu tham khảo

- [MIT App Inventor Official](https://appinventor.mit.edu/)
- [App Inventor Documentation](https://docs.mit.edu/appinventor)
- [App Inventor Tutorials](http://appinventor.mit.edu/explore/ai2/tutorials)
- [App Inventor Community](https://community.appinventor.mit.edu/)

---

<div align="center">

**🎓 Bài tập lớn – Môn TEE0419**
Phát triển Ứng dụng trên Thiết bị Di động

*[Tên trường] – [Khoa/Bộ môn]*

</div>
