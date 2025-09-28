# EV Co-ownership System - Use Case Diagrams (Simplified)

## 📊 **DIAGRAM 1: TỔNG QUAN ACTORS & SYSTEM**

```mermaid
graph TB
    %% Actors
    CoOwner[👤 Co-owner<br/>Chủ xe đồng sở hữu]
    Staff[👨‍💼 Staff<br/>Nhân viên vận hành]
    Admin[👨‍💻 Admin<br/>Quản trị viên]
    
    %% System
    System[🚗 EV Co-ownership System<br/>27 Use Cases]
    
    %% Relationships
    CoOwner --> System
    Staff --> System
    Admin --> System
    
    %% Styling
    classDef actor fill:#e1f5fe,stroke:#01579b,stroke-width:3px
    classDef system fill:#f3e5f5,stroke:#4a148c,stroke-width:3px
    
    class CoOwner,Staff,Admin actor
    class System system
```

---

## 📊 **DIAGRAM 2: CO-OWNER USE CASES (14 use cases)**

```mermaid
graph TB
    CoOwner[👤 Co-owner]
    
    subgraph CoOwnerUC["Chức năng Chủ xe (14 use cases)"]
        %% Account Management
        UC1[Đăng ký & Xác thực]
        UC2[Quản lý Tỷ lệ Sở hữu]
        UC3[Quản lý Hợp đồng]
        
        %% Scheduling
        UC4[Xem Lịch Chung]
        UC5[Đặt Lịch Sử dụng]
        
        %% Cost Management
        UC6[Quản lý Chi phí]
        UC7[Báo cáo Chi phí]
        UC8[Thanh toán Trực tuyến]
        
        %% History & Analysis
        UC9[Lịch sử Sử dụng]
        UC10[Phân tích Cá nhân]
        
        %% Group Management
        UC11[Quản lý Nhóm]
        UC12[Bỏ phiếu Quyết định]
        UC13[Quỹ chung]
        UC14[AI Gợi ý]
    end
    
    CoOwner --> UC1
    CoOwner --> UC2
    CoOwner --> UC3
    CoOwner --> UC4
    CoOwner --> UC5
    CoOwner --> UC6
    CoOwner --> UC7
    CoOwner --> UC8
    CoOwner --> UC9
    CoOwner --> UC10
    CoOwner --> UC11
    CoOwner --> UC12
    CoOwner --> UC13
    CoOwner --> UC14
    
    %% Grouping
    UC1 -.-> UC2
    UC1 -.-> UC3
    UC5 -.-> UC4
    UC6 -.-> UC7
    UC9 -.-> UC10
    UC11 -.-> UC12
    UC11 -.-> UC13
    UC14 -.-> UC9
    
    classDef coowner fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    class UC1,UC2,UC3,UC4,UC5,UC6,UC7,UC8,UC9,UC10,UC11,UC12,UC13,UC14 coowner
```

---

## 📊 **DIAGRAM 3: STAFF USE CASES (6 use cases)**

```mermaid
graph TB
    Staff[👨‍💼 Staff]
    
    subgraph StaffUC["Chức năng Nhân viên (6 use cases)"]
        UC15[Quản lý Nhóm xe]
        UC16[Quản lý Hợp đồng Pháp lý]
        UC17[Check-in/Check-out]
        UC18[Quản lý Dịch vụ xe]
        UC19[Giám sát Tranh chấp]
        UC20[Báo cáo Tài chính]
    end
    
    Staff --> UC15
    Staff --> UC16
    Staff --> UC17
    Staff --> UC18
    Staff --> UC19
    Staff --> UC20
    
    %% Dependencies
    UC15 -.->|depends on| UC11
    UC16 -.->|depends on| UC3
    UC17 -.->|depends on| UC5
    UC18 -.->|depends on| UC6
    UC19 -.->|depends on| UC12
    UC20 -.->|depends on| UC7
    
    classDef staff fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    class UC15,UC16,UC17,UC18,UC19,UC20 staff
```

---

## 📊 **DIAGRAM 4: ADMIN USE CASES (3 use cases)**

```mermaid
graph TB
    Admin[👨‍💻 Admin]
    
    subgraph AdminUC["Chức năng Admin (3 use cases)"]
        UC21[Quản lý Hệ thống]
        UC22[Quản lý Người dùng]
        UC23[Backup & Recovery]
    end
    
    Admin --> UC21
    Admin --> UC22
    Admin --> UC23
    
    classDef admin fill:#fff3e0,stroke:#e65100,stroke-width:2px
    class UC21,UC22,UC23 admin
```

---

## 📊 **DIAGRAM 5: EXTERNAL SYSTEMS (4 use cases)**

```mermaid
graph TB
    subgraph External["Hệ thống Bên ngoài (4 use cases)"]
        UC24[E-wallet<br/>Ví điện tử]
        UC25[Banking<br/>Ngân hàng]
        UC26[QR Code<br/>Mã QR]
        UC27[Digital Signature<br/>Chữ ký số]
    end
    
    %% External relationships
    UC8 --> UC24
    UC8 --> UC25
    UC17 --> UC26
    UC3 --> UC27
    UC16 --> UC27
    
    classDef external fill:#fce4ec,stroke:#880e4f,stroke-width:2px
    class UC24,UC25,UC26,UC27 external
```

---

## 📊 **DIAGRAM 6: RELATIONSHIPS OVERVIEW**

```mermaid
graph TB
    subgraph Include["Include Relationships"]
        I1[UC1 includes UC2, UC3]
        I2[UC5 includes UC4]
        I3[UC6 includes UC7]
        I4[UC9 includes UC10]
        I5[UC11 includes UC12, UC13]
        I6[UC14 includes UC9]
    end
    
    subgraph Extend["Extend Relationships"]
        E1[UC5 extends UC14]
        E2[UC6 extends UC24, UC25]
    end
    
    subgraph Dependencies["Dependencies"]
        D1[UC15 depends on UC11]
        D2[UC16 depends on UC3]
        D3[UC17 depends on UC5]
        D4[UC18 depends on UC6]
        D5[UC19 depends on UC12]
        D6[UC20 depends on UC7]
    end
    
    classDef include fill:#e3f2fd,stroke:#1976d2,stroke-width:2px
    classDef extend fill:#f1f8e9,stroke:#388e3c,stroke-width:2px
    classDef depend fill:#fff8e1,stroke:#f57c00,stroke-width:2px
    
    class I1,I2,I3,I4,I5,I6 include
    class E1,E2 extend
    class D1,D2,D3,D4,D5,D6 depend
```

---

## 📊 **DIAGRAM 7: USE CASE CATEGORIES**

```mermaid
graph TB
    subgraph Categories["Phân loại Use Cases"]
        subgraph CoOwnerCat["Co-owner (14)"]
            A1[Account & Ownership (3)]
            A2[Scheduling & Usage (2)]
            A3[Cost & Payment (3)]
            A4[History & Analysis (2)]
            A5[Group Management (4)]
        end
        
        subgraph StaffCat["Staff (6)"]
            B1[Vehicle Management]
            B2[Legal Contracts]
            B3[Check-in/out]
            B4[Services]
            B5[Dispute Resolution]
            B6[Financial Reports]
        end
        
        subgraph AdminCat["Admin (3)"]
            C1[System Management]
            C2[User Management]
            C3[Backup & Recovery]
        end
        
        subgraph ExternalCat["External (4)"]
            D1[E-wallet]
            D2[Banking]
            D3[QR Code]
            D4[Digital Signature]
        end
    end
    
    classDef coowner fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef staff fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    classDef admin fill:#fff3e0,stroke:#e65100,stroke-width:2px
    classDef external fill:#fce4ec,stroke:#880e4f,stroke-width:2px
    
    class A1,A2,A3,A4,A5 coowner
    class B1,B2,B3,B4,B5,B6 staff
    class C1,C2,C3 admin
    class D1,D2,D3,D4 external
```

---

## 📋 **TÓM TẮT CÁC DIAGRAM**

### **7 Diagrams nhỏ, dễ nhìn:**

1. **Diagram 1**: Tổng quan Actors & System
2. **Diagram 2**: Co-owner Use Cases (14)
3. **Diagram 3**: Staff Use Cases (6)
4. **Diagram 4**: Admin Use Cases (3)
5. **Diagram 5**: External Systems (4)
6. **Diagram 6**: Relationships Overview
7. **Diagram 7**: Use Case Categories

### **🎯 Lợi ích:**
- ✅ **Dễ nhìn** - Mỗi diagram nhỏ, rõ ràng
- ✅ **Dễ hiểu** - Tập trung vào từng nhóm
- ✅ **Dễ sử dụng** - Copy từng diagram riêng lẻ
- ✅ **Đầy đủ** - Bao gồm tất cả 27 use cases

Bây giờ bạn có thể xem từng diagram một cách rõ ràng và dễ hiểu! [[memory:7324052]]
