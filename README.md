# DevOps Lab 1 - CI/CD Portfolio Page

## Thông tin sinh viên
- **Họ và tên:** Nguyễn Đức Thắng
- **Mã sinh viên:** DTC235200704
- **Lớp:** KTPM K22A
- **Repository URL:** https://github.com/NguyenDucThang-debug/devops-lab1-portfolio
- **Link Live Website:** https://NguyenDucThang-debug.github.io/devops-lab1-portfolio/

---

## Báo cáo Kết quả Bài Lab

### 1. Bảng So sánh: Cách Thủ công vs Cách DevOps (CI/CD)

| Tiêu chí | Cách THỦ CÔNG (Traditional) | Cách DEVOPS (CI/CD Pipeline) |
| :--- | :--- | :--- |
| **Làm sao để deploy?** | Upload file qua FTP/SFTP hoặc copy/paste thủ công lên server. | Push code lên GitHub → pipeline tự chạy |
| **Mất bao lâu?** | Vài phút đến vài giờ. | ~10 giây |
| **Ai làm deploy?** | Con người (Developer / SysAdmin). | GitHub Actions (máy tự làm) |
| **Có bị sai sót không?** | Rất dễ sai sót (quên file, nhầm thư mục, ghi đè hỏng code). | Không — pipeline nhất quán 100% |
| **Rollback nếu lỗi?** | Tìm file cũ upload lại thủ công (tốn thời gian). | `git revert` + push → tự động rollback |
| **Làm sao biết deploy thành công?** | Mở web kiểm tra thủ công hoặc vào server soi log. | GitHub Actions gửi notification ✔/✖ |

---

### 2. DevOps Workflow của bài Lab
+-------------------+     +-------------------+     +-------------------+
|       PLAN        |     |       CODE        |     |       BUILD       |
|    QUYẾT ĐỊNH     | --> |     VIẾT CODE     | --> |  GIAI ĐOẠN BUILD  |
| Quyết định làm    |     |  Viết index.html  |     |   GitHub Actions  |
|     portfolio     |     |                   |     |        chạy       |
+-------------------+     +-------------------+     +-------------------+
|
v
+-------------------+     +-------------------+     +-------------------+
|      MONITOR      |     |      DEPLOY       |     |       TEST        |
| THEO DÕI & BÁO CÁO| <-- | DEPLOY PRODUCTION | <-- | KIỂM THỬ VALIDATE |
| Actions tab ->    |     |   GitHub Pages    |     |   Validate HTML   |
|     xem log       |     |      public       |     |       file        |
+-------------------+     +-------------------+     +-------------------+