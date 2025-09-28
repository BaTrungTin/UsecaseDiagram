# EV Co-ownership & Cost-sharing System
## Tổng quan Use Case & Chi tiết phân chia

---

## 📊 **TỔNG QUAN HỆ THỐNG**

### **Tên hệ thống**: EV Co-ownership & Cost-sharing System
### **Mô tả**: Phần mềm quản lý đồng sở hữu & chia sẻ chi phí xe điện

### **3 Actors chính**:
1. **👤 Co-owner** (Chủ xe đồng sở hữu) - 14 use cases
2. **👨‍💼 Staff** (Nhân viên vận hành) - 6 use cases  
3. **👨‍💻 Admin** (Quản trị viên) - 3 use cases
4. **🔗 External Systems** (Hệ thống bên ngoài) - 4 use cases

**Tổng cộng: 27 Use Cases**

---

## 🎯 **CHI TIẾT PHÂN CHIA THEO ACTOR**

---

## 1. 👤 **CO-OWNER (Chủ xe đồng sở hữu) - 14 Use Cases**

### **A. QUẢN LÝ TÀI KHOẢN & QUYỀN SỞ HỮU** (3 use cases)

#### **UC1: Đăng ký & Xác thực**
- **Mô tả**: Đăng ký tài khoản và xác thực danh tính
- **Chi tiết**:
  - Đăng ký với CMND/CCCD
  - Xác thực giấy phép lái xe
  - Xác minh danh tính qua OTP/SMS
  - Upload và xác thực tài liệu
- **Input**: Thông tin cá nhân, CMND/CCCD, GPLX
- **Output**: Tài khoản được tạo và xác thực

#### **UC2: Quản lý Tỷ lệ Sở hữu**
- **Mô tả**: Thiết lập và quản lý tỷ lệ sở hữu xe
- **Chi tiết**:
  - Thiết lập tỷ lệ sở hữu (VD: A 40%, B 30%, C 30%)
  - Cập nhật tỷ lệ khi có thay đổi
  - Xem tỷ lệ sở hữu hiện tại
  - Lịch sử thay đổi tỷ lệ
- **Input**: Tỷ lệ sở hữu mới
- **Output**: Tỷ lệ sở hữu được cập nhật

#### **UC3: Quản lý Hợp đồng E-contract**
- **Mô tả**: Tạo và quản lý hợp đồng đồng sở hữu điện tử
- **Chi tiết**:
  - Tạo hợp đồng đồng sở hữu điện tử
  - Ký số hợp đồng
  - Lưu trữ và quản lý hợp đồng
  - Xem lịch sử hợp đồng
- **Input**: Thông tin hợp đồng, chữ ký số
- **Output**: Hợp đồng được tạo và ký

### **B. ĐẶT LỊCH & SỬ DỤNG XE** (2 use cases)

#### **UC4: Xem Lịch Chung**
- **Mô tả**: Xem lịch sử dụng xe của tất cả đồng sở hữu
- **Chi tiết**:
  - Hiển thị thời gian xe trống/đang sử dụng
  - Xem lịch sử sử dụng
  - Thông báo trạng thái xe
  - Lọc theo ngày/tuần/tháng
- **Input**: Khoảng thời gian muốn xem
- **Output**: Lịch sử dụng xe

#### **UC5: Đặt Lịch Sử dụng**
- **Mô tả**: Đặt lịch sử dụng xe với hệ thống ưu tiên công bằng
- **Chi tiết**:
  - Đặt lịch trước để đảm bảo quyền sử dụng
  - Hệ thống ưu tiên công bằng dựa trên tỷ lệ sở hữu
  - Xem lịch sử đặt lịch
  - Hủy/chỉnh sửa lịch đã đặt
- **Input**: Thời gian muốn sử dụng, mục đích sử dụng
- **Output**: Lịch đặt được xác nhận

### **C. CHI PHÍ & THANH TOÁN** (3 use cases)

#### **UC6: Quản lý Chi phí**
- **Mô tả**: Tự động chia chi phí theo tỷ lệ sở hữu hoặc mức độ sử dụng
- **Chi tiết**:
  - Tự động chia chi phí theo tỷ lệ sở hữu
  - Quản lý các khoản: sạc điện, bảo dưỡng, bảo hiểm, đăng kiểm, vệ sinh
  - Tính toán chi phí theo mức độ sử dụng
  - Thông báo chi phí mới
- **Input**: Chi phí phát sinh, loại chi phí
- **Output**: Chi phí được chia và thông báo

#### **UC7: Báo cáo Chi phí**
- **Mô tả**: Xem báo cáo chi phí theo tháng/quý
- **Chi tiết**:
  - Bảng tổng kết chi phí theo tháng/quý
  - Phân tích chi phí theo từng khoản
  - Xuất báo cáo PDF/Excel
  - So sánh chi phí các tháng
- **Input**: Khoảng thời gian, loại báo cáo
- **Output**: Báo cáo chi phí chi tiết

#### **UC8: Thanh toán Trực tuyến**
- **Mô tả**: Thanh toán chi phí qua các phương thức trực tuyến
- **Chi tiết**:
  - Thanh toán qua e-wallet
  - Thanh toán qua banking
  - Lịch sử thanh toán
  - Thông báo thanh toán thành công
- **Input**: Số tiền, phương thức thanh toán
- **Output**: Giao dịch thanh toán hoàn tất

### **D. LỊCH SỬ & PHÂN TÍCH CÁ NHÂN** (2 use cases)

#### **UC9: Lịch sử Sử dụng**
- **Mô tả**: Xem lịch sử sử dụng xe chi tiết
- **Chi tiết**:
  - Lịch sử sử dụng xe: thời gian, quãng đường
  - Chi phí phát sinh trong mỗi lần sử dụng
  - Thống kê sử dụng theo tháng/quý
  - Xuất báo cáo lịch sử
- **Input**: Khoảng thời gian muốn xem
- **Output**: Lịch sử sử dụng chi tiết

#### **UC10: Phân tích Cá nhân**
- **Mô tả**: Phân tích và so sánh mức sử dụng cá nhân
- **Chi tiết**:
  - So sánh mức sử dụng với tỷ lệ sở hữu
  - Phân tích hiệu quả sử dụng
  - Đề xuất tối ưu hóa
  - Biểu đồ thống kê
- **Input**: Dữ liệu sử dụng cá nhân
- **Output**: Báo cáo phân tích cá nhân

### **E. NHÓM ĐỒNG SỞ HỮU** (4 use cases)

#### **UC11: Quản lý Nhóm**
- **Mô tả**: Quản lý thành viên và quyền hạn trong nhóm
- **Chi tiết**:
  - Thêm/xóa thành viên
  - Phân quyền (admin nhóm, thành viên)
  - Quản lý thông tin nhóm
  - Mời thành viên mới
- **Input**: Thông tin thành viên, quyền hạn
- **Output**: Nhóm được cập nhật

#### **UC12: Bỏ phiếu Quyết định**
- **Mô tả**: Bỏ phiếu cho các quyết định chung của nhóm
- **Chi tiết**:
  - Bỏ phiếu cho các quyết định chung
  - Ví dụ: nâng cấp pin, bảo hiểm, bán xe
  - Theo dõi kết quả bỏ phiếu
  - Thông báo kết quả
- **Input**: Lựa chọn bỏ phiếu
- **Output**: Kết quả bỏ phiếu

#### **UC13: Quỹ chung**
- **Mô tả**: Quản lý quỹ chung của nhóm
- **Chi tiết**:
  - Quỹ bảo dưỡng, phí dự phòng
  - Hiển thị minh bạch số dư
  - Lịch sử chi tiêu
  - Đóng góp vào quỹ
- **Input**: Số tiền đóng góp, mục đích chi
- **Output**: Quỹ được cập nhật

#### **UC14: AI Gợi ý Sử dụng**
- **Mô tả**: AI phân tích và gợi ý lịch sử dụng tối ưu
- **Chi tiết**:
  - Phân tích sử dụng xe
  - Đề xuất lịch sử dụng công bằng
  - Tối ưu hóa hiệu quả
  - Dự đoán nhu cầu sử dụng
- **Input**: Dữ liệu sử dụng lịch sử
- **Output**: Gợi ý tối ưu hóa

---

## 2. 👨‍💼 **STAFF (Nhân viên vận hành) - 6 Use Cases**

#### **UC15: Quản lý Nhóm xe**
- **Mô tả**: Quản lý các nhóm xe đồng sở hữu
- **Chi tiết**:
  - Quản lý các nhóm xe đồng sở hữu
  - Theo dõi trạng thái nhóm
  - Cập nhật thông tin nhóm
  - Thống kê hoạt động nhóm

#### **UC16: Quản lý Hợp đồng Pháp lý**
- **Mô tả**: Quản lý hợp đồng pháp lý điện tử
- **Chi tiết**:
  - Quản lý hợp đồng pháp lý điện tử
  - Xác thực và lưu trữ
  - Theo dõi hiệu lực
  - Gia hạn hợp đồng

#### **UC17: Check-in/Check-out**
- **Mô tả**: Quản lý quá trình nhận và trả xe
- **Chi tiết**:
  - Quét QR khi nhận và trả xe
  - Ký số xác nhận
  - Ghi nhận trạng thái xe
  - Chụp ảnh tình trạng xe

#### **UC18: Quản lý Dịch vụ xe**
- **Mô tả**: Quản lý các dịch vụ bảo dưỡng và sửa chữa
- **Chi tiết**:
  - Quản lý thực hiện các dịch vụ xe
  - Lên lịch bảo dưỡng
  - Theo dõi chất lượng dịch vụ
  - Quản lý nhà cung cấp dịch vụ

#### **UC19: Giám sát Tranh chấp**
- **Mô tả**: Theo dõi và xử lý các tranh chấp
- **Chi tiết**:
  - Theo dõi và giám sát tranh chấp
  - Ghi nhận và xử lý
  - Báo cáo tình hình
  - Liên hệ với các bên liên quan

#### **UC20: Báo cáo Tài chính**
- **Mô tả**: Xuất báo cáo tài chính minh bạch
- **Chi tiết**:
  - Xuất báo cáo tài chính minh bạch
  - Báo cáo cho từng nhóm
  - Thống kê tổng quan
  - Phân tích xu hướng

---

## 3. 👨‍💻 **ADMIN (Quản trị viên) - 3 Use Cases**

#### **UC21: Quản lý Hệ thống**
- **Mô tả**: Quản lý và bảo trì hệ thống
- **Chi tiết**:
  - Cấu hình hệ thống
  - Giám sát hoạt động
  - Bảo trì hệ thống
  - Cập nhật phần mềm

#### **UC22: Quản lý Người dùng**
- **Mô tả**: Quản lý tài khoản và quyền hạn người dùng
- **Chi tiết**:
  - Quản lý tài khoản người dùng
  - Phân quyền và vai trò
  - Xử lý yêu cầu
  - Khóa/mở khóa tài khoản

#### **UC23: Backup & Recovery**
- **Mô tả**: Sao lưu và khôi phục dữ liệu
- **Chi tiết**:
  - Sao lưu dữ liệu
  - Khôi phục hệ thống
  - Quản lý bảo mật
  - Kiểm tra tính toàn vẹn dữ liệu

---

## 4. 🔗 **EXTERNAL SYSTEMS (Hệ thống bên ngoài) - 4 Use Cases**

#### **UC24: E-wallet Integration**
- **Mô tả**: Tích hợp với các ví điện tử
- **Chi tiết**: MoMo, ZaloPay, ViettelPay, etc.

#### **UC25: Banking Integration**
- **Mô tả**: Tích hợp với hệ thống ngân hàng
- **Chi tiết**: Internet Banking, Mobile Banking

#### **UC26: QR Code System**
- **Mô tả**: Hệ thống mã QR cho check-in/out
- **Chi tiết**: Tạo và quét mã QR

#### **UC27: Digital Signature**
- **Mô tả**: Hệ thống chữ ký số
- **Chi tiết**: Ký số hợp đồng, xác thực

---

## 📈 **THỐNG KÊ TỔNG QUAN**

| Actor | Số Use Cases | Tỷ lệ |
|-------|-------------|-------|
| Co-owner | 14 | 51.9% |
| Staff | 6 | 22.2% |
| Admin | 3 | 11.1% |
| External Systems | 4 | 14.8% |
| **Tổng cộng** | **27** | **100%** |

---

## 🔄 **MỐI QUAN HỆ GIỮA CÁC USE CASES**

### **Include Relationships** (Bao gồm):
- UC1 includes UC2, UC3
- UC5 includes UC4
- UC6 includes UC7
- UC9 includes UC10
- UC11 includes UC12, UC13
- UC14 includes UC9

### **Extend Relationships** (Mở rộng):
- UC5 extends UC14
- UC6 extends UC24, UC25

### **Dependencies** (Phụ thuộc):
- UC15 depends on UC11
- UC16 depends on UC3
- UC17 depends on UC5
- UC18 depends on UC6
- UC19 depends on UC12
- UC20 depends on UC7
