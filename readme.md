# PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG
### MIT App Inventor 2
### Ứng dụng: **Deadline Checker**

---
> **Sinh viên:** Nguuyễn Như Khiêm  
> **MSSV:** K225480106030

**Môn học:** Lập trình di động &nbsp;|&nbsp; **Công cụ:** MIT App Inventor 2 &nbsp;|&nbsp; **Nền tảng:** Android

</div>

---

## 📋 MỤC LỤC

- [1. Tổng Quan Ứng Dụng](#1-tổng-quan-ứng-dụng)
- [2. Giới Thiệu MIT App Inventor 2](#2-giới-thiệu-mit-app-inventor-2)
  - [2.1 Giao Diện Tổng Thể](#21-giao-diện-tổng-thể)
  - [2.2 Chế Độ Designer – Thanh Công Cụ Có Gì?](#22-chế-độ-designer--thanh-công-cụ-có-gì)
  - [2.3 Kéo Thả & Thay Đổi Thuộc Tính](#23-kéo-thả--thay-đổi-thuộc-tính)
- [3. Lập Trình Bằng Block](#3-lập-trình-bằng-block)
  - [3.1 Bản Chất Của Block Programming](#31-bản-chất-của-block-programming)
  - [3.2 Phân Loại Block](#32-phân-loại-block)
  - [3.3 Ưu Điểm So Với Viết Code](#33-ưu-điểm-so-với-viết-code)
  - [3.4 Nhược Điểm](#34-nhược-điểm)
  - [3.5 Backpack – Copy Paste Block](#35-backpack--copy-paste-block)
- [4. Thiết Kế & Lập Trình Từng Screen](#4-thiết-kế--lập-trình-từng-screen)
  - [Screen 1 – About](#screen-1--about-giới-thiệu-bản-thân)
  - [Screen 2 – Kiểm Tra Deadline](#screen-2--kiểm-tra-deadline)
  - [Screen 3 – WebViewer](#screen-3--webviewer)
- [5. Kết Quả Chạy Ứng Dụng](#5-kết-quả-chạy-ứng-dụng)
- [6. Quy Trình Hoàn Chỉnh](#6-quy-trình-hoàn-chỉnh)
- [7. Build & Xuất Ứng Dụng](#7-build--xuất-ứng-dụng)

---

## 1. Tổng Quan Ứng Dụng

Ứng dụng **Deadline Checker** được xây dựng trên nền tảng **MIT App Inventor 2** — công cụ lập trình trực quan dành cho Android, không cần viết code thuần, thay vào đó là kéo thả giao diện và ghép block logic.

Xây dựng một ứng dụng Android hoàn chỉnh bằng **MIT App Inventor** – nền tảng lập trình trực quan dạng kéo-thả (drag & drop). Ứng dụng gồm **3 màn hình (Screen)** với các chức năng:

| Screen | Tên | Chức năng |
|--------|-----|-----------|
| Screen1 | About Me | Giới thiệu bản thân + điều hướng sang 2 screen còn lại |
| Screen2 | Giải bài toán | Giải một bài toán đơn giản (ví dụ: tính BMI, giải phương trình bậc 1...) |
| Screen3 | WebView | Nhúng và hiển thị một trang web có sẵn |

### 🛠 Công cụ sử dụng

| Công cụ | Mô tả |
|---------|-------|
| [MIT App Inventor](https://appinventor.mit.edu/) | Nền tảng tạo ứng dụng Android bằng giao diện kéo-thả |
| Trình duyệt web | Chrome / Firefox / Edge – truy cập App Inventor online |
| MIT AI2 Companion | App cài trên điện thoại để test trực tiếp |
| Android Emulator | Giả lập thiết bị Android (nếu không có điện thoại thật) |

### 🗂️ Cấu Trúc Dự Án

```
DeadlineChecker/
├── 📱Screen1  (About Me)
│   ├── Label – Tên, MSSV, lớp
│   ├── Image – Ảnh đại diện
│   ├── Button → mở Screen2
│   └── Button → mở Screen3
│
├── 📱Screen2  (Giải bài toán)
│   ├── TextBox – Nhập dữ liệu
│   ├── Button  – Tính toán
│   └── Label   – Hiển thị kết quả
│
└── 📱Screen3  (WebView)
    ├── WebViewer – Hiển thị trang web
    └── Button    – Quay lại Screen1
```

### 📊 Bảng Tóm Tắt Tính Năng

| Screen | Tên | Chức năng chính | Components sử dụng |
|:------:|-----|-----------------|-------------------|
| 1 | About | Thông tin sinh viên, điều hướng sang Screen khác | Label, Button, Image, VerticalArrangement |
| 2 | Deadline Check | Nhập số ngày & %, trả về mức nguy hiểm + khuyến nghị | TextBox, Button, Label, Logic Block |
| 3 | WebViewer | Mở GitHub / StackOverflow / ChatGPT trong app | WebViewer, Button, HorizontalArrangement |

---

## 2. Giới Thiệu MIT App Inventor 2

### 2.1 Giao Diện Tổng Thể

MIT App Inventor 2 (AI2) là môi trường lập trình trực quan chạy trên trình duyệt, truy cập tại `appinventor.mit.edu`. Toàn bộ môi trường làm việc chia thành **2 chế độ chính** chuyển đổi bằng nút ở góc trên phải:

```
╔══════════════════════════════════════════════════════════════════╗
║              MIT App Inventor 2 — Giao diện chính               ║
╠════════════════════════════╦═════════════════════════════════════╣
║                            ║                                     ║
║    🎨  DESIGNER            ║    🔧  BLOCKS EDITOR                ║
║                            ║                                     ║
║  Thiết kế giao diện        ║  Lập trình logic bằng               ║
║  người dùng (UI) bằng      ║  cách kéo thả các                   ║
║  cách kéo thả component    ║  khối lệnh màu sắc                  ║
║  vào màn hình điện thoại   ║  và ghép chúng lại                  ║
║                            ║                                     ║
╚════════════════════════════╩═════════════════════════════════════╝
```

> 📸 **[Chèn ảnh chụp toàn bộ giao diện MIT App Inventor tại đây]**

---

### 2.2 Chế Độ Designer – Thanh Công Cụ Có Gì?

Khi ở chế độ **Designer**, màn hình chia thành **4 vùng làm việc**:

```
┌─────────────────┬───────────────────────┬──────────────┬──────────────────┐
│    PALETTE      │       VIEWER          │  COMPONENTS  │   PROPERTIES     │
│   (Kho linh     │   (Màn hình điện      │  (Cây thành  │  (Bảng thuộc     │
│    kiện)        │    thoại ảo)          │   phần)      │   tính)          │
│─────────────────│───────────────────────│──────────────│──────────────────│
│                 │                       │              │                  │
│ User Interface  │   ┌─────────────┐     │ ▼ Screen1    │ Width:           │
│  ├─ Button      │   │             │     │   Label1     │  [Fill Parent ▼] │
│  ├─ CheckBox    │   │  [Label]    │     │   Label2     │                  │
│  ├─ DatePicker  │   │            │     │   Label3     │ Height:          │
│  ├─ Image       │   │  [Button1] │     │   Button1    │  [Automatic  ▼] │
│  ├─ Label       │   │  [Button2] │     │   Button2    │                  │
│  ├─ ListPicker  │   │            │     │              │ Text:            │
│  ├─ TextBox     │   │             │     │              │ [Kiểm tra     ]  │
│  └─ ...         │   └─────────────┘     │              │                  │
│                 │                       │              │ FontSize: [16]   │
│ Layout          │   (kéo thả vào đây)   │              │ FontBold: [✓]    │
│  ├─ Horiz...    │                       │              │ BackgroundColor: │
│  ├─ Vertical... │                       │              │  [  Xanh   ]     │
│  └─ Table...    │                       │              │                  │
│                 │                       │              │ TextColor:       │
│ Media           │                       │              │  [  Trắng  ]     │
│  └─ WebViewer   │                       │              │                  │
│                 │                       │              │ Visible: [✓]     │
│ Connectivity    │                       │              │ Enabled: [✓]     │
│ Sensors         │                       │              │                  │
└─────────────────┴───────────────────────┴──────────────┴──────────────────┘
```

#### 🗃️ Chi Tiết Từng Vùng

**① PALETTE – Kho linh kiện (cột trái)**

Đây là "kho vũ khí" chứa tất cả các thành phần có thể thêm vào app, chia theo nhóm:

| Nhóm | Thành phần tiêu biểu | Dùng để làm gì |
|------|---------------------|----------------|
| `User Interface` | Button, Label, TextBox, Image, CheckBox | Các thành phần hiển thị & tương tác cơ bản |
| `Layout` | HorizontalArrangement, VerticalArrangement, TableArrangement | Sắp xếp vị trí các component |
| `Media` | Camera, Player, Sound, WebViewer | Xử lý hình ảnh, âm thanh, video, web |
| `Drawing & Animation` | Canvas, Ball, ImageSprite | Vẽ, game, hoạt ảnh |
| `Sensors` | AccelerometerSensor, LocationSensor, Clock | Cảm biến điện thoại |
| `Social` | PhoneCall, Texting, Twitter | Gọi điện, nhắn tin |
| `Storage` | TinyDB, File, CloudDB | Lưu trữ dữ liệu |
| `Connectivity` | Web, BluetoothClient | Kết nối mạng & Bluetooth |

**② VIEWER – Màn hình điện thoại ảo (giữa)**

- Hiển thị trực quan giao diện app đang được xây dựng
- Kéo component từ Palette thả vào đây để thêm vào app
- Click vào component trong Viewer để chỉnh sửa
- Không thể tương tác thật (bấm nút không chạy được) — đây chỉ là bản xem trước

**③ COMPONENTS – Cây thành phần (phải trên)**

- Liệt kê toàn bộ component đã thêm theo dạng cây phân cấp
- Click vào tên component để chọn và chỉnh sửa
- Có thể đổi tên (Rename), xóa (Delete) component tại đây

**④ PROPERTIES – Bảng thuộc tính (phải dưới)**

- Hiển thị toàn bộ thuộc tính của component đang được chọn
- Thay đổi trực tiếp: gõ vào ô, chọn màu, tick checkbox...

---

### 2.3 Kéo Thả & Thay Đổi Thuộc Tính

#### 🖱️ Quy Trình Kéo Thả Component

```
  PALETTE                    VIEWER                  PROPERTIES
┌──────────┐              ┌──────────┐              ┌──────────────┐
│          │   ① Giữ     │          │   ③ Chọn    │              │
│  Button  │──────────►  │ [Button] │─────────►   │ Text:        │
│          │   chuột &   │          │   component  │  [Đánh giá ] │
│          │   kéo sang  │          │              │              │
└──────────┘              └──────────┘   ④ Sửa    │ Width:       │
                          ② Thả vào     thuộc tính │  [Fill    ▼] │
                          vị trí mong              │              │
                          muốn                     │ FontSize:[18]│
                                                   └──────────────┘
```

**Các bước chi tiết:**

```
Bước 1 ──► Tìm component phù hợp trong PALETTE bên trái
            Ví dụ: cần nút bấm → tìm "Button" trong nhóm User Interface

Bước 2 ──► Giữ chuột trái vào component, kéo sang VIEWER
            (Màn hình điện thoại ảo ở giữa)

Bước 3 ──► Thả chuột tại vị trí muốn đặt component
            → Component xuất hiện trên màn hình ảo
            → Tên component tự động thêm vào cây COMPONENTS

Bước 4 ──► Click vào component vừa thêm
            → Bảng PROPERTIES bên phải hiển thị đầy đủ thuộc tính

Bước 5 ──► Chỉnh sửa thuộc tính theo ý muốn:
            • Text      → nội dung chữ hiển thị
            • Width     → Fill Parent (đầy màn hình) hoặc số pixel cụ thể
            • Height    → Automatic hoặc pixel cụ thể
            • FontSize  → cỡ chữ (số)
            • FontBold  → tick để in đậm
            • BackgroundColor → click để chọn màu nền
            • TextColor → màu chữ
            • Enabled   → true/false (có thể bấm hay không)
            • Visible   → true/false (ẩn/hiện)
```

#### 📐 Bảng Thuộc Tính Quan Trọng

| Thuộc tính | Kiểu giá trị | Ý nghĩa | Ví dụ |
|-----------|-------------|---------|-------|
| `Text` | Chuỗi | Nội dung hiển thị | `"📅 Kiểm tra Deadline"` |
| `Width` | Pixel / Fill Parent / Wrap Content | Chiều rộng component | `Fill Parent` |
| `Height` | Pixel / Automatic | Chiều cao component | `50` hoặc `Automatic` |
| `FontSize` | Số | Cỡ chữ (đơn vị sp) | `18` |
| `FontBold` | true/false | In đậm hay không | `true` |
| `FontItalic` | true/false | In nghiêng | `false` |
| `BackgroundColor` | Màu | Màu nền | Chọn từ bảng màu |
| `TextColor` | Màu | Màu chữ | `White` |
| `Enabled` | true/false | Có thể tương tác không | `true` |
| `Visible` | true/false | Ẩn hay hiện | `true` |
| `Hint` | Chuỗi | Chữ gợi ý (mờ) trong TextBox | `"Nhập số ngày..."` |
| `NumbersOnly` | true/false | TextBox chỉ nhận số | `true` |
| `HomeUrl` | URL | Trang mặc định của WebViewer | `"https://github.com"` |
| `Alignment` | Left/Center/Right | Căn lề chữ | `Center` |

> 💡 **Tại sao cần kéo thả?**  
> Thay vì viết XML layout phức tạp như Android Studio, AI2 cho phép bạn **thấy ngay kết quả** khi kéo thả — không cần biết cấu trúc XML, không cần gõ thuộc tính thủ công. Đây là cách tiếp cận **WYSIWYG** (What You See Is What You Get — thấy gì được nấy).

> 💡 **Tại sao dùng `Fill Parent` cho Width?**  
> Điện thoại Android có hàng trăm kích thước màn hình khác nhau. Đặt Width = `Fill Parent` giúp component **tự co giãn** để luôn vừa khít màn hình, thay vì bị cắt hoặc bị thừa khoảng trắng.

---

## 3. Lập Trình Bằng Block

### 3.1 Bản Chất Của Block Programming

MIT App Inventor dùng mô hình **Visual Block Programming** — thay vì gõ code chữ, lập trình viên **kéo thả các khối lệnh hình học** có màu sắc và **ghép chúng lại** như xếp LEGO.

Mỗi block có hình dạng đặc biệt: phần lồi (🔌) và phần lõm (🔳) khớp với nhau, giống mảnh ghép puzzle. Block **chỉ ghép được khi logic đúng** — ví dụ, không thể nhét một block "số" vào chỗ cần "chuỗi văn bản". Điều này giúp **tránh lỗi sai kiểu dữ liệu**.

**So sánh trực quan:**

```
──────────────────────────────────────────────────────────────────
 CODE TRUYỀN THỐNG (Java/Kotlin)     │  BLOCK (MIT App Inventor)
──────────────────────────────────────────────────────────────────

 // Sự kiện click nút                │  ┌──────────────────────────────┐
 button.setOnClickListener(new       │  │ 🟡 when Button1 . Click      │
   View.OnClickListener() {          │  │    do                        │
     @Override                       │  │  ┌───────────────────────┐   │
     public void onClick(View v) {   │  │  │ 🟠 if    ◄ 🔵 ngay ►  │   │
       int ngay = Integer.parseInt(  │  │  │       ≤  ◄ 🟢  1  ►   │   │
         txtNgay.getText().toString()│  │  │  then                  │   │
       );                            │  │  │  ┌─────────────────┐  │   │
       if (ngay <= 1) {              │  │  │  │ 🔵 set Label1   │  │   │
         label.setText("💀");        │  │  │  │   .Text to      │  │   │
       }                             │  │  │  │ ◄ 🟢 "💀 Nguy" ►│  │   │
     }                               │  │  │  └─────────────────┘  │   │
 });                                 │  │  └───────────────────────┘   │
                                     │  └──────────────────────────────┘
──────────────────────────────────────────────────────────────────
 ~10 dòng code, nhớ cú pháp Java     │  Kéo thả ~6 block, không cần nhớ
──────────────────────────────────────────────────────────────────
```

**Cơ chế ghép block:**

```
  Block sự kiện (Event) — màu vàng, có "mũ" ở trên:
  ┌─────────────────────────────┐
  │ when  [Button1] . [Click]   │
  │   do ▼                      │◄── Chỗ "cắm" block lệnh vào
  └─────────────────────────────┘

  Block lệnh — cắm vào vị trí "do":
                  ┌─────────────────────────────┐
                  │ set [Label_KQ] . [Text] to   │
                  │  ◄─────────────────────────► │◄── Chỗ cắm giá trị
                  └─────────────────────────────┘

  Block giá trị — cắm vào chỗ cần giá trị:
                              ┌───────────────┐
                              │  "💀 Nguy!"  │  ← Block chuỗi (màu xanh lá)
                              └───────────────┘
```

---

### 3.2 Phân Loại Block

Mỗi loại block có màu sắc riêng để dễ nhận biết:

| Màu | Nhóm | Chứa gì | Ví dụ cụ thể |
|-----|------|---------|-------------|
| 🟡 **Vàng** | Events (Sự kiện) | Khi nào thì chạy code | `when Button1.Click`, `when Screen1.Initialize` |
| 🟠 **Cam** | Control (Điều khiển) | Cấu trúc logic | `if / else if / else`, `for each`, `while`, `open another screen` |
| 🔵 **Xanh biển** | Component | Lấy/gán thuộc tính component | `set Label1.Text to`, `TextBox1.Text`, `call WebViewer1.GoToUrl` |
| 🟢 **Xanh lá** | Math & Text | Số học, chuỗi | `+`, `-`, `*`, `/`, `join`, `length`, `number` |
| 🔴 **Đỏ** | Variables (Biến) | Khai báo và dùng biến | `initialize global [tên] to`, `set [biến] to`, `get [biến]` |
| 🟣 **Tím** | Procedures (Hàm) | Tự định nghĩa hàm | `to [tên_hàm] do ...`, `call [tên_hàm]` |
| ⚫ **Xám** | Logic | Điều kiện so sánh | `and`, `or`, `not`, `=`, `<`, `>`, `true`, `false` |

> 📸 **[Chèn ảnh chụp màn hình Blocks Editor, hiển thị các block màu sắc tại đây]**

---

### 3.3 Ưu Điểm So Với Viết Code

```
✅  Không lỗi cú pháp (Syntax Error)
    → Block có hình dạng khớp nhau — sai kiểu dữ liệu thì không ghép được
    → Lập trình viên Java mới thường mất hàng giờ tìm dấu ";" hay "}" bị thiếu

✅  Trực quan — thấy ngay cấu trúc logic
    → Nhìn vào màn hình block là hiểu ngay chương trình làm gì
    → Code chữ: phải đọc dòng từng dòng, nhớ tên hàm, biết thư viện

✅  Học tư duy lập trình nhanh
    → Tập trung vào logic (IF này thì THEN kia) thay vì cú pháp ngôn ngữ
    → Phù hợp người mới hoàn toàn, kể cả không biết lập trình

✅  Prototype siêu nhanh
    → Từ ý tưởng đến app chạy được: vài giờ thay vì vài ngày
    → Test ngay trên điện thoại qua AI2 Companion mà không cần build

✅  Không cần cài đặt môi trường phức tạp
    → Chạy 100% trên trình duyệt — không cần Android Studio, JDK, Gradle
    → Mở máy tính bất kỳ → vào web → code ngay

✅  Dễ sửa và thử nghiệm
    → Thay đổi block → bấm Connect → xem kết quả ngay lập tức trên điện thoại
    → Không cần recompile như Java
```

---

### 3.4 Nhược Điểm

```
❌  Khó mở rộng khi ứng dụng phức tạp
    → App có >10 màn hình, >100 block → workspace trở nên rối rắm, khó quản lý
    → Không có tính năng tìm kiếm/lọc block hiệu quả như IDE chuyên nghiệp

❌  Giới hạn tính năng so với lập trình native
    → Không thể làm animation phức tạp, xử lý file nâng cao
    → Một số API Android không có trong App Inventor
    → Background service, notification nâng cao: không hỗ trợ

❌  Chỉ build được Android
    → Không thể tạo app iOS (iPhone/iPad)
    → APK xuất ra không được tối ưu như app viết bằng Kotlin/Java thuần

❌  Hiệu năng thấp hơn
    → App AI2 chạy chậm hơn app native vì qua thêm lớp trung gian
    → Xử lý dữ liệu lớn hoặc tính toán nặng: không phù hợp

❌  Không có version control tích hợp
    → Không dùng được Git để quản lý lịch sử thay đổi
    → Làm nhóm: mỗi người phải export .aia và trao đổi thủ công

❌  Phụ thuộc vào server MIT
    → Nếu server MIT bảo trì hoặc mất kết nối → không làm việc được
    → Dữ liệu lưu trên cloud của MIT, không toàn quyền kiểm soát
```

---

### 3.5 Backpack – Copy Paste Block

**Backpack** (Ba lô) là tính năng clipboard đặc biệt trong Blocks Editor, cho phép **sao chép block** giữa các Screen hoặc thậm chí giữa các project khác nhau.

**Icon Backpack** nằm ở **góc trên bên phải** của Blocks Editor (hình chiếc ba lô 🎒).

> 📸 **[Chèn ảnh chụp vị trí icon Backpack trên thanh công cụ Blocks Editor]**

#### Cách sử dụng Backpack:

```
  CÁCH THÊM VÀO BACKPACK:
  ┌─────────────────────────────────────────────────────────┐
  │  Bước 1: Click chuột phải vào block muốn copy           │
  │          ┌─────────────────────────────┐                │
  │          │ ✂  Duplicate                │                │
  │          │ 🗑  Delete                  │                │
  │          │ 💬  Add Comment             │                │
  │          │ 🎒  Add to Backpack  ◄─────│── chọn cái này │
  │          │ ⬇  Collapse Block          │                │
  │          └─────────────────────────────┘                │
  │                                                         │
  │  Bước 2: Block được copy vào Backpack                   │
  │          → Icon ba lô sáng lên, có số đếm               │
  └─────────────────────────────────────────────────────────┘

  CÁCH LẤY RA TỪ BACKPACK:
  ┌─────────────────────────────────────────────────────────┐
  │  Bước 1: Chuyển sang Screen hoặc project khác           │
  │                                                         │
  │  Bước 2: Click vào icon 🎒 Backpack (góc trên phải)     │
  │          → Danh sách block đã lưu xuất hiện             │
  │                                                         │
  │  Bước 3: Kéo block từ Backpack thả vào workspace        │
  │          → Block được copy (bản gốc vẫn còn trong Backpack) │
  └─────────────────────────────────────────────────────────┘
```

#### Backpack hoạt động ở đâu?

| Phạm vi | Có dùng được không | Ghi chú |
|---------|-------------------|---------|
| Giữa các Screen trong cùng project | ✅ Có | Dùng nhiều nhất |
| Giữa các project khác nhau | ✅ Có | Mở project mới, Backpack vẫn còn |
| Sau khi đóng trình duyệt & mở lại | ⚠️ Phụ thuộc | Lưu trong browser storage, có thể mất |
| Trên máy tính khác | ❌ Không | Backpack không đồng bộ qua tài khoản |

> ⚠️ **Lưu ý quan trọng:** Backpack lưu trong bộ nhớ trình duyệt (localStorage). Nếu xóa cache trình duyệt → **mất toàn bộ Backpack**. Hãy export `.aia` thường xuyên để backup project.

> 💡 **Mẹo sử dụng:** Block xử lý điều hướng Screen (open another screen) giống nhau ở mọi Screen → tạo 1 lần ở Screen1 → dùng Backpack copy sang các Screen còn lại, chỉ cần đổi tên Screen.

---

## 4. Thiết Kế & Lập Trình Từng Screen

---

### Screen 1 – About (Giới Thiệu Bản Thân)

#### 🎨 Bố Cục Giao Diện

```
┌─────────────────────────────┐
│         Screen 1            │
│         (About)             │
├─────────────────────────────┤
│                             │
│    [  Ảnh đại diện  ]       │
│                             │
│   Họ và tên:                │
│   Nguyễn Văn A              │
│                             │
│   MSSV: 2024XXXXXXXX        │
│                             │
│   Lớp: KTPM2024             │
│                             │
│   Trường: ĐH ABC            │
│                             │
│  ┌────────────┐ ┌─────────┐ │
│  │📅 Kiểm tra│ │📚 Tài   │ │
│  │  Deadline │ │  liệu   │ │
│  └────────────┘ └─────────┘ │
└─────────────────────────────┘
```

> 📸 **[Chèn ảnh chụp màn hình Designer – Screen 1 tại đây]**

#### 📋 Danh Sách Components & Cấu Hình

```
Screen1
│  AppName: "Deadline Checker"
│  BackgroundColor: [màu theo sở thích]
│  Title: "Về Tôi"
│
├── VerticalArrangement1
│     Width: Fill Parent
│     Height: Fill Parent
│     AlignHorizontal: Center
│     AlignVertical: Top
│
│   ├── Image1
│   │     Picture: [upload ảnh đại diện]
│   │     Width: 150px
│   │     Height: 150px
│   │
│   ├── Label_HoTen
│   │     Text: "Họ và tên: Nguyễn Văn A"
│   │     FontSize: 18
│   │     FontBold: true
│   │
│   ├── Label_MSSV
│   │     Text: "MSSV: 2024XXXXXXXX"
│   │     FontSize: 16
│   │
│   ├── Label_Lop
│   │     Text: "Lớp: KTPM2024"
│   │     FontSize: 16
│   │
│   └── HorizontalArrangement1
│         Width: Fill Parent
│         AlignHorizontal: Center
│
│       ├── Button_Deadline
│       │     Text: "📅 Kiểm tra Deadline"
│       │     BackgroundColor: [màu cam]
│       │     TextColor: White
│       │     FontBold: true
│       │     Width: Fill Parent
│       │
│       └── Button_WebView
│             Text: "📚 Tài liệu cứu mạng"
│             BackgroundColor: [màu xanh]
│             TextColor: White
│             FontBold: true
│             Width: Fill Parent
```

#### 🔧 Bước Thực Hiện Trong Designer

```
Bước 1 ──► Tạo project mới tại appinventor.mit.edu
            Projects → Start new project → Đặt tên: "DeadlineChecker"

Bước 2 ──► Thêm Screen2 và Screen3:
            Palette menu → Add Screen → đặt tên "Screen2"
            Lặp lại cho "Screen3"

Bước 3 ──► Quay lại Screen1
            Kéo VerticalArrangement từ Layout vào Viewer
            Chỉnh: Width = Fill Parent, Height = Fill Parent

Bước 4 ──► Kéo Image vào trong VerticalArrangement
            Click Image → Properties → Picture → upload ảnh

Bước 5 ──► Kéo 3 Label vào (HoTen, MSSV, Lop)
            Chỉnh Text, FontSize, FontBold cho từng Label

Bước 6 ──► Kéo HorizontalArrangement vào cuối
            Width = Fill Parent

Bước 7 ──► Kéo 2 Button vào HorizontalArrangement
            Chỉnh Text, màu sắc, Width = Fill Parent cho mỗi button
```

#### 🟡 Block Lập Trình – Screen1

> 📸 **[Chèn ảnh chụp màn hình Blocks Editor – Screen1 tại đây]**

```
╔══════════════════════════════════════════════════════════╗
║  🟡 when  [Button_Deadline] . Click                      ║
║       do                                                 ║
║     ┌──────────────────────────────────────────────┐     ║
║     │ 🟠 open another screen                        │     ║
║     │         screenName: ◄ 🟢 "Screen2" ►         │     ║
║     └──────────────────────────────────────────────┘     ║
╚══════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════╗
║  🟡 when  [Button_WebView] . Click                       ║
║       do                                                 ║
║     ┌──────────────────────────────────────────────┐     ║
║     │ 🟠 open another screen                        │     ║
║     │         screenName: ◄ 🟢 "Screen3" ►         │     ║
║     └──────────────────────────────────────────────┘     ║
╚══════════════════════════════════════════════════════════╝
```

**Giải thích block:**
- `when Button.Click` — block Event (vàng): lắng nghe sự kiện người dùng bấm nút
- `open another screen` — block Control (cam): mở Screen khác, truyền tên Screen dưới dạng chuỗi

---

### Screen 2 – Kiểm Tra Deadline

#### 🎨 Bố Cục Giao Diện

```
┌─────────────────────────────┐
│         Screen 2            │
│    ⏰ Deadline Checker       │
├─────────────────────────────┤
│                             │
│  Còn bao nhiêu ngày?        │
│  ┌───────────────────────┐  │
│  │   3                   │  │  ← TextBox (chỉ nhận số)
│  └───────────────────────┘  │
│                             │
│  Đã hoàn thành bao nhiêu %? │
│  ┌───────────────────────┐  │
│  │   20                  │  │  ← TextBox (chỉ nhận số)
│  └───────────────────────┘  │
│                             │
│  ┌───────────────────────┐  │
│  │    🔍  Đánh giá       │  │  ← Button
│  └───────────────────────┘  │
│                             │
│  ┌───────────────────────┐  │
│  │ Mức độ nguy hiểm: 😨  │  │  ← Label kết quả
│  │                       │  │
│  │ Khuyến nghị:          │  │
│  │ - Hủy kế hoạch đi chơi│  │
│  │ - Mở laptop ngay      │  │
│  └───────────────────────┘  │
│                             │
│  [◄ Quay lại Screen1]       │
└─────────────────────────────┘
```

> 📸 **[Chèn ảnh chụp màn hình Designer – Screen2 tại đây]**

#### 📋 Danh Sách Components & Cấu Hình

```
Screen2
│  Title: "⏰ Kiểm Tra Deadline"
│
├── Label_HuongDan1
│     Text: "Còn bao nhiêu ngày?"
│     FontSize: 16
│     FontBold: true
│
├── TextBox_Ngay
│     Hint: "Nhập số ngày còn lại (VD: 3)"
│     NumbersOnly: true       ← CHỈ NHẬN SỐ
│     Width: Fill Parent
│
├── Label_HuongDan2
│     Text: "Đã hoàn thành bao nhiêu %?"
│     FontSize: 16
│     FontBold: true
│
├── TextBox_Phan
│     Hint: "Nhập phần trăm (VD: 20)"
│     NumbersOnly: true       ← CHỈ NHẬN SỐ
│     Width: Fill Parent
│
├── Button_DanhGia
│     Text: "🔍 Đánh giá"
│     Width: Fill Parent
│     FontSize: 18
│     FontBold: true
│
├── Label_KetQua
│     Text: ""                ← Để trống, sẽ điền sau khi bấm
│     FontSize: 20
│     FontBold: true
│     Width: Fill Parent
│
├── Label_KhuyenNghi
│     Text: ""                ← Để trống, sẽ điền sau khi bấm
│     FontSize: 14
│     Width: Fill Parent
│
└── Button_Back
      Text: "◄ Quay lại"
      Width: Fill Parent
```

#### 📊 Bảng Logic Đánh Giá

| Điều kiện | Mức độ | Khuyến nghị |
|-----------|--------|-------------|
| `ngay ≤ 1` VÀ `phan ≤ 10%` | 💀 **Chúc may mắn** | Pha cà phê · Tắt Facebook · Cầu nguyện |
| `ngay ≤ 3` VÀ `phan ≤ 30%` | 😨 **Nguy hiểm** | Hủy kế hoạch đi chơi · Mở laptop ngay |
| `ngay ≤ 7` VÀ `phan ≤ 60%` | 😐 **Căng nhẹ** | Tăng tốc · Giảm Netflix đi |
| Còn lại | 🙂 **An toàn** | Bạn là người hiếm hoi làm đồ án đúng tiến độ 👏 |

#### 🟡 Block Lập Trình – Screen2

> 📸 **[Chèn ảnh chụp màn hình Blocks Editor – Screen2 tại đây]**

```
╔══════════════════════════════════════════════════════════════════╗
║  🟡 when  [Button_DanhGia] . Click                               ║
║       do                                                         ║
║                                                                  ║
║     🔴 initialize local [ngay] to                                ║
║              ◄ 🟢 number ◄ 🔵 TextBox_Ngay.Text ► ►             ║
║                                                                  ║
║     🔴 initialize local [phan] to                                ║
║              ◄ 🟢 number ◄ 🔵 TextBox_Phan.Text ► ►             ║
║                                                                  ║
║     ┌────────────────────────────────────────────────────────┐   ║
║     │ 🟠 if  ⚫ [ngay] ≤ [1]  AND  ⚫ [phan] ≤ [10]          │   ║
║     │    then                                                │   ║
║     │      🔵 set Label_KetQua.Text to                       │   ║
║     │              ◄ 🟢 "Mức độ nguy hiểm: 💀 Chúc may mắn" ►│   ║
║     │      🔵 set Label_KhuyenNghi.Text to                   │   ║
║     │              ◄ 🟢 "Khuyến nghị:                         │   ║
║     │                    - Pha cà phê                         │   ║
║     │                    - Tắt Facebook                       │   ║
║     │                    - Cầu nguyện" ►                     │   ║
║     │                                                        │   ║
║     │ 🟠 else if  ⚫ [ngay] ≤ [3]  AND  ⚫ [phan] ≤ [30]     │   ║
║     │    then                                                │   ║
║     │      🔵 set Label_KetQua.Text to                       │   ║
║     │              ◄ 🟢 "Mức độ nguy hiểm: 😨 Nguy hiểm" ►  │   ║
║     │      🔵 set Label_KhuyenNghi.Text to                   │   ║
║     │              ◄ 🟢 "Khuyến nghị:                         │   ║
║     │                    - Hủy kế hoạch đi chơi               │   ║
║     │                    - Mở laptop ngay" ►                 │   ║
║     │                                                        │   ║
║     │ 🟠 else if  ⚫ [ngay] ≤ [7]  AND  ⚫ [phan] ≤ [60]     │   ║
║     │    then                                                │   ║
║     │      🔵 set Label_KetQua.Text to                       │   ║
║     │              ◄ 🟢 "Mức độ nguy hiểm: 😐 Căng nhẹ" ►   │   ║
║     │      🔵 set Label_KhuyenNghi.Text to                   │   ║
║     │              ◄ 🟢 "Khuyến nghị:                         │   ║
║     │                    - Tăng tốc thôi                      │   ║
║     │                    - Giảm Netflix đi" ►                │   ║
║     │                                                        │   ║
║     │ 🟠 else                                                │   ║
║     │    then                                                │   ║
║     │      🔵 set Label_KetQua.Text to                       │   ║
║     │              ◄ 🟢 "Mức độ nguy hiểm: 🙂 An toàn" ►    │   ║
║     │      🔵 set Label_KhuyenNghi.Text to                   │   ║
║     │              ◄ 🟢 "Bạn là người hiếm hoi làm đồ án    │   ║
║     │                    đúng tiến độ. 👏" ►                 │   ║
║     └────────────────────────────────────────────────────────┘   ║
╚══════════════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════╗
║  🟡 when  [Button_Back] . Click                          ║
║       do                                                 ║
║     ┌───────────────────────────────────────────┐        ║
║     │ 🟠 close screen                           │        ║
║     └───────────────────────────────────────────┘        ║
╚══════════════════════════════════════════════════════════╝
```

**Giải thích các block:**
- `number(TextBox.Text)` — chuyển chuỗi văn bản sang số để so sánh được
- `if / else if / else` — chuỗi điều kiện, kiểm tra lần lượt từ trên xuống
- `AND` — cả hai điều kiện phải đúng cùng lúc
- `set Label.Text to` — gán nội dung cho nhãn hiển thị kết quả
- `close screen` — đóng Screen hiện tại, quay về Screen trước

---

### Screen 3 – WebViewer

#### 🎨 Bố Cục Giao Diện

```
┌─────────────────────────────┐
│         Screen 3            │
│    🌐 Tài Liệu Cứu Mạng    │
├─────────────────────────────┤
│ ┌────────┬────────┬───────┐ │
│ │🐙 Git  │📚Stack │🤖 GPT│ │  ← Thanh chọn web
│ └────────┴────────┴───────┘ │
├─────────────────────────────┤
│                             │
│                             │
│    [Nội dung trang web      │
│     hiển thị ở đây          │
│     — WebViewer Component]  │
│                             │
│                             │
│                             │
│                             │
│                             │
└─────────────────────────────┘
```

> 📸 **[Chèn ảnh chụp màn hình Designer – Screen3 tại đây]**

#### 📋 Danh Sách Components & Cấu Hình

```
Screen3
│  Title: "🌐 Tài Liệu Cứu Mạng"
│
├── HorizontalArrangement1    ← Thanh nút chọn web
│     Width: Fill Parent
│     Height: Automatic
│
│   ├── Button_GitHub
│   │     Text: "🐙 GitHub"
│   │     Width: Fill Parent
│   │     BackgroundColor: [xám đậm]
│   │     TextColor: White
│   │
│   ├── Button_Stack
│   │     Text: "📚 Stack"
│   │     Width: Fill Parent
│   │     BackgroundColor: [cam]
│   │     TextColor: White
│   │
│   └── Button_ChatGPT
│         Text: "🤖 ChatGPT"
│         Width: Fill Parent
│         BackgroundColor: [xanh lá]
│         TextColor: White
│
└── WebViewer1
      Width: Fill Parent
      Height: Fill Parent      ← Chiếm toàn bộ phần còn lại
      HomeUrl: https://github.com
```

> **💡 Vì sao chọn 3 trang web này?**  
> Đây là bộ ba "vũ khí sinh tồn" của sinh viên CNTT khi deadline đến gần:
> - **GitHub** → tìm source code mẫu, xem hướng dẫn, clone project tham khảo
> - **StackOverflow** → tra cứu lỗi, đọc giải pháp từ triệu lập trình viên khác
> - **ChatGPT** → hỏi giải thích nhanh, nhờ debug, tóm tắt tài liệu dài

> **💡 Về hỗ trợ giao diện điện thoại:**  
> WebViewer trong App Inventor dùng WebView của Android — trình duyệt nhúng sẵn. Các trang web responsive (GitHub, StackOverflow, ChatGPT) tự động điều chỉnh layout cho màn hình nhỏ. Cần đảm bảo `Width = Fill Parent` và `Height = Fill Parent` để WebViewer chiếm đủ diện tích màn hình.

#### 🟡 Block Lập Trình – Screen3

> 📸 **[Chèn ảnh chụp màn hình Blocks Editor – Screen3 tại đây]**

```
╔══════════════════════════════════════════════════════════╗
║  🟡 when  Screen3 . Initialize                           ║
║       do                                                 ║
║     ┌─────────────────────────────────────────────┐      ║
║     │ 🔵 call WebViewer1 . GoToUrl                │      ║
║     │         url: ◄ 🟢 "https://github.com" ►    │      ║
║     └─────────────────────────────────────────────┘      ║
╚══════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════╗
║  🟡 when  [Button_GitHub] . Click                        ║
║       do                                                 ║
║     ┌─────────────────────────────────────────────┐      ║
║     │ 🔵 call WebViewer1 . GoToUrl                │      ║
║     │         url: ◄ 🟢 "https://github.com" ►    │      ║
║     └─────────────────────────────────────────────┘      ║
╚══════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════╗
║  🟡 when  [Button_Stack] . Click                         ║
║       do                                                 ║
║     ┌──────────────────────────────────────────────────┐ ║
║     │ 🔵 call WebViewer1 . GoToUrl                     │ ║
║     │         url: ◄ 🟢 "https://stackoverflow.com" ►  │ ║
║     └──────────────────────────────────────────────────┘ ║
╚══════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════╗
║  🟡 when  [Button_ChatGPT] . Click                       ║
║       do                                                 ║
║     ┌───────────────────────────────────────────────┐    ║
║     │ 🔵 call WebViewer1 . GoToUrl                  │    ║
║     │         url: ◄ 🟢 "https://chatgpt.com" ►     │    ║
║     └───────────────────────────────────────────────┘    ║
╚══════════════════════════════════════════════════════════╝
```

**Giải thích block:**
- `when Screen3.Initialize` — chạy ngay khi Screen3 được mở, tải trang mặc định
- `call WebViewer1.GoToUrl` — lệnh điều hướng WebViewer đến URL chỉ định
- Khi bấm nút nào → WebViewer tải trang tương ứng, không cần rời khỏi app

---

## 5. Kết Quả Chạy Ứng Dụng

> 📸 **[Chèn ảnh chụp màn hình app đang chạy thực tế trên điện thoại tại đây]**

### 🎯 Demo Các Kịch Bản

**Kịch bản 1 – Sinh viên gương mẫu:**
```
Input:   Còn 30 ngày  |  Hoàn thành 80%
─────────────────────────────────────────
Output:  Mức độ nguy hiểm: 🙂 An toàn

         Bạn là người hiếm hoi làm đồ án
         đúng tiến độ. 👏
```

**Kịch bản 2 – Bắt đầu lo:**
```
Input:   Còn 7 ngày  |  Hoàn thành 40%
─────────────────────────────────────────
Output:  Mức độ nguy hiểm: 😐 Căng nhẹ

         Khuyến nghị:
         - Tăng tốc thôi
         - Giảm Netflix đi
```

**Kịch bản 3 – Báo động đỏ:**
```
Input:   Còn 3 ngày  |  Hoàn thành 20%
─────────────────────────────────────────
Output:  Mức độ nguy hiểm: 😨 Nguy hiểm

         Khuyến nghị:
         - Hủy kế hoạch đi chơi
         - Mở laptop ngay
```

**Kịch bản 4 – Không còn hy vọng:**
```
Input:   Còn 1 ngày  |  Hoàn thành 0%
─────────────────────────────────────────
Output:  Mức độ nguy hiểm: 💀 Chúc may mắn

         Khuyến nghị:
         - Pha cà phê
         - Tắt Facebook
         - Cầu nguyện
```

---

## 6. Quy Trình Hoàn Chỉnh

```
  BƯỚC 1                    BƯỚC 2                    BƯỚC 3
  Tạo Project               Thêm Screens              Thiết kế UI
  ─────────                 ────────────              ────────────
  Vào                       Add Screen                DESIGNER:
  appinventor.mit.edu   →   → Screen2             →   Kéo thả
  → Start new project       → Screen3                 component
  → Đặt tên project         (mỗi screen              từ Palette
                            1 màn hình)               vào Viewer
       │
       ▼
  BƯỚC 4                    BƯỚC 5                    BƯỚC 6
  Chỉnh Properties          Lập trình Block           Test ứng dụng
  ────────────────          ───────────────           ─────────────
  Click component       →   BLOCKS EDITOR:        →   Connect →
  → Properties panel        Kéo block Event           AI Companion
  → Sửa Text,               → Ghép block              → Quét QR
    Color, Size,              Control, Logic           → Test trực tiếp
    Width, Height             → Gán giá trị            trên điện thoại
       │
       ▼
  BƯỚC 7                    BƯỚC 8
  Sửa lỗi                   Export & Nộp bài
  ────────                  ────────────────
  Xem lỗi logic         →   Build → APK
  → Chỉnh block             Projects → Export .aia
  → Test lại                → Nộp file .aia + báo cáo
```

---

## 7. Build & Xuất Ứng Dụng

### 📲 Cách 1 – Test Realtime (Khuyên dùng khi làm)

```
1. Cài app "MIT AI2 Companion" từ Google Play Store
   (Tìm: MIT AI2 Companion)

2. Trên trình duyệt MIT App Inventor:
   Click menu "Connect" → chọn "AI Companion"

3. Hộp thoại xuất hiện với QR Code

4. Mở MIT AI2 Companion trên điện thoại
   → Bấm "Scan QR code" → Quét QR

5. App hiển thị ngay trên điện thoại
   → Mỗi lần thay đổi block/designer → app tự cập nhật
```

### 📦 Cách 2 – Build APK (Dùng khi nộp bài)

```
1. Trên MIT App Inventor: menu "Build"
   → Chọn "Android App (.apk)"

2. Chờ hệ thống compile (~1-3 phút)

3. Chọn "Download .apk to my computer"
   → File .apk tải về máy tính

4. Chuyển file .apk sang điện thoại Android
   (qua USB, Google Drive, Zalo...)

5. Trên điện thoại: mở file .apk
   → Bật "Cài từ nguồn không xác định" nếu được yêu cầu
   → Bấm "Cài đặt"

6. App xuất hiện trong danh sách ứng dụng
```

### 💾 Cách 3 – Export Project .aia (Backup & Nộp bài)

```
Menu "Projects" → "Export selected project (.aia) to my computer"
→ File DeadlineChecker.aia tải về

File .aia chứa TOÀN BỘ project: Designer + Blocks + Assets
→ Import lại: Projects → Import project (.aia)
→ Đây là file cần nộp cùng với báo cáo này
```

---

<div align="center">

---

**📁 File nộp bài**

| File | Mô tả |
|:----:|-------|
| `DeadlineChecker.aia` | Source code toàn bộ project |
| `DeadlineChecker.apk` | File cài đặt Android |
| `README.md` | Báo cáo này |

---

*Báo cáo thực hành — Lập trình di động với MIT App Inventor 2*  
*Ảnh minh họa tự chụp trong quá trình thực hiện*

</div>
