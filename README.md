# 📱 Ứng Dụng Quản Lý Chi Tiêu Cá Nhân (Personal Expense Tracker)

> **Môn học:** Lập trình Thiết bị Di động (Mobile Application Development)  
> **Nhóm thực hiện:** Nhóm 16 - CSE441  
> **Nền tảng:** Flutter (Cross-platform Android / iOS)  

---

## 📖 1. Giới thiệu dự án

**Ứng dụng Quản lý Chi tiêu Cá nhân** là giải pháp hỗ trợ người dùng theo dõi, kiểm soát và tối ưu hóa tài chính hằng ngày một cách tiện lợi, nhanh chóng và bảo mật. Ứng dụng tập trung vào tính trực quan, hoạt động mượt mà offline và hỗ trợ tính năng thông minh bằng AI để quét hóa đơn tự động.

### 🌟 Tính năng cốt lõi
* 💵 **Quản lý thu - chi:** Thêm, sửa, xóa và xem lịch sử các khoản thu/chi với đầy đủ thông tin (số tiền, danh mục, thời gian, ghi chú, hóa đơn đính kèm).
* 🏷️ **Phân loại danh mục:** Phân chia danh mục thu/chi rõ ràng (Ăn uống, Đi lại, Mua sắm, Giải trí, Hóa đơn, Lương, Thưởng...).
* 📊 **Báo cáo & Thống kê trực quan:** Thống kê chi tiêu theo ngày, tuần, tháng và năm thông qua các biểu đồ tròn, biểu đồ cột sinh động.
* 📷 **Quét hóa đơn thông minh (AI OCR):** Tự động nhận diện nội dung, tổng tiền và ngày tháng từ ảnh chụp hóa đơn (sử dụng AI/ML Kit).
* 💾 **Lưu trữ Offline an toàn:** Lưu dữ liệu ngoại tuyến bảo mật và tốc độ cao bằng **Hive / SQLite**, đảm bảo sử dụng mọi lúc không phụ thuộc internet.

---

## 👥 2. Thành viên nhóm & Vai trò

| STT | MSSV | Họ và tên | Vai trò |
|:---:|:---:|:---|:---:|
| 1 | **2351170599** | **Nguyễn Văn Huỳnh** | Nhóm trưởng |
| 2 | **2151060296** | **Lê Anh Tuấn** | Thành viên |
| 3 | **2251172394** | **NGUYỄN TRUNG KIÊN** | Thành viên |
| 4 | **2351170629** | **Trần Anh Tuấn** | Thành viên |

*(Ghi chú: Nhiệm vụ chi tiết của từng thành viên sẽ được phân công và cập nhật cụ thể theo từng giai đoạn của dự án).*

---

## 🛠️ 3. Công nghệ & Thư viện sử dụng

* **Framework:** [Flutter](https://flutter.dev/) (SDK 3.x+), [Dart](https://dart.dev/)
* **Kiến trúc ứng dụng:** Feature-First / Clean Architecture
* **Cơ sở dữ liệu Offline:** [Hive](https://pub.dev/packages/hive) / [sqflite](https://pub.dev/packages/sqflite)
* **Quản lý trạng thái (State Management):** Provider / Bloc / Riverpod
* **Trực quan hóa dữ liệu:** [fl_chart](https://pub.dev/packages/fl_chart)
* **Xử lý hình ảnh & AI nhận diện:** [google_mlkit_text_recognition](https://pub.dev/packages/google_mlkit_text_recognition) / `image_picker`

---

## 📁 4. Cấu trúc thư mục dự án (Chuẩn đề xuất)

```text
cse441_group_16/
├── .github/                      # GitHub configurations & templates
│   └── pull_request_template.md  # Template cho Pull Request
├── android/                      # Native Android code
├── ios/                          # Native iOS code
├── assets/                       # Tài nguyên hình ảnh, biểu tượng, fonts
│   ├── icons/
│   └── images/
├── lib/                          # Mã nguồn chính (Dart)
│   ├── core/                     # Thành phần dùng chung toàn app
│   │   ├── constants/            # Màu sắc, kích thước, chuỗi tĩnh
│   │   ├── theme/                # Light/Dark Theme
│   │   └── utils/                # Helper functions, formatters (tiền tệ, ngày)
│   ├── data/                     # Tầng dữ liệu (Data layer)
│   │   ├── models/               # Data models (Transaction, Category...)
│   │   ├── datasources/          # Local storage (Hive / SQLite helper)
│   │   └── repositories/         # Xử lý logic truy xuất dữ liệu
│   ├── presentation/             # Tầng giao diện (UI layer)
│   │   ├── screens/              # Màn hình chính (Home, Add, Stat, Camera...)
│   │   └── widgets/              # Reusable UI widgets (Card, Button...)
│   └── main.dart                 # Điểm khởi chạy ứng dụng
├── test/                         # Unit test & Widget test
├── .gitignore                    # Các file/thư mục bỏ qua khi commit
├── pubspec.yaml                  # Khai báo thư viện & dependencies
└── README.md                     # Tài liệu giới thiệu dự án
```

---

## 🚀 5. Hướng dẫn cài đặt & Khởi chạy

### Yêu cầu tiên quyết (Prerequisites)
* Đã cài đặt [Flutter SDK](https://docs.flutter.dev/get-started/install) (Khuyến nghị bản Stable >= 3.x).
* Đã cấu hình [Android Studio](https://developer.android.com/studio) hoặc [Visual Studio Code](https://code.visualstudio.com/) với Flutter extension.
* Máy ảo (Android Emulator) hoặc thiết bị thật đã bật tính năng USB Debugging.

### Các bước khởi chạy

1. **Clone repository về máy:**
   ```bash
   git clone git@github.com:hhuynh2005/cse441_group_16.git
   cd cse441_group_16
   ```

2. **Cài đặt các gói phụ thuộc (Dependencies):**
   ```bash
   flutter pub get
   ```

3. **Kiểm tra thiết bị kết nối:**
   ```bash
   flutter devices
   ```

4. **Chạy ứng dụng:**
   ```bash
   flutter run
   ```

---

## 🌿 6. Quy trình phối hợp & Đóng góp mã nguồn (Git Workflow)

Để đảm bảo tính nhất quán, tránh xung đột code (conflict) và kiểm soát chất lượng, các thành viên **bắt buộc tuân thủ quy trình sau**:

### 6.1. Quy tắc nhánh (Branching Strategy)
* Nhánh `main`: Nhánh chứa mã nguồn ổn định nhất, chỉ cập nhật thông qua Pull Request được duyệt. **Không commit trực tiếp lên `main`**.
* Nhánh tính năng: Mỗi thành viên tạo nhánh riêng xuất phát từ `main` theo cú pháp:
  * `feature/<tên-tính-năng>` (VD: `feature/add-expense-screen`, `feature/sqlite-storage`)
  * `fix/<tên-lỗi>` (VD: `fix/chart-overflow-bug`)

### 6.2. Các bước đóng góp code
1. **Lấy code mới nhất từ nhánh `main`:**
   ```bash
   git checkout main
   git pull origin main
   ```
2. **Tạo nhánh làm việc mới:**
   ```bash
   git checkout -b feature/ten-tinh-nang
   ```
3. **Thực hiện code, kiểm tra và commit:**
   ```bash
   git add .
   git commit -m "feat: mo ta ngan gon ve tinh nang"
   ```
   *Tuân thủ Conventional Commits (`feat:`, `fix:`, `refactor:`, `docs:`, `ui:`).*
4. **Đẩy nhánh lên GitHub:**
   ```bash
   git push origin feature/ten-tinh-nang
   ```
5. **Tạo Pull Request (PR):**
   * Truy cập GitHub Repository và bấm **Compare & pull request**.
   * Điền mô tả theo mẫu có sẵn, gán Nhóm trưởng / Thành viên khác làm **Reviewer**.
   * Sau khi được kiểm tra và duyệt (Approved), tiến hành merge vào `main`.