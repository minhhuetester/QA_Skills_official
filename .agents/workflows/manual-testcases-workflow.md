---
description: 
---

# Quy trình tạo Testcase (Testcase Generation Workflow)

## 1. Triggers
Hành động kích hoạt tiến trình: `/generate testcases`

## 2. Input Required
Trước khi bắt đầu tiến trình sinh testcases, hệ thống yêu cầu người dùng (hoặc prompt cung cấp) các tham số đầu vào bắt buộc sau:
- **System_type**: Loại nền tảng/hệ thống triển khai (Ví dụ: Web application, iOS App, Android App, Backend API, v.v.).
- **Module_name**: Tên phân hệ nghiệp vụ, tính năng đang cần test (Ví dụ: Authentication, Thanh toán, Tìm kiếm chuyến bay).
- **Project_name**: Tên dự án để bám sát context (Ví dụ: Tidesquare, Tourvis, Luna).
- **Requirement_source**: Nguồn tham chiếu tài liệu yêu cầu (Có thể là trích đoạn Text, Link ảnh UI/Mockup, PRD/SRS Document, hoặc Link Jira/Ticket).

---

## 3. Workflow Steps (Tiến trình thực thi)

### Step 1: Phân tích luồng (Flow Analysis)
- Đọc, nghiên cứu và bóc tách toàn bộ tài liệu từ **Requirement_source**.
- Xác định mục tiêu chính (Main goal) của bản thiết kế/tài liệu.
- Định nghĩa và mô hình hóa các luồng nghiệp vụ:
  - **Happy path**: Luồng đi chính (Main User Journey) diễn ra suôn sẻ không có lỗi.
  - **Alternative flows**: Các nhánh rẽ tùy chọn mang tính nghiệp vụ (Các trường hợp thay thế).
  - **Exceptional paths**: Các luồng đặc biệt/ngoại lệ trong quá trình người dùng sử dụng.
  - **Failure/Error flows**: Các luồng dẫn đến lỗi (Network error, Invalid data, System failure).

### Step 2: Tìm điểm mờ và Q&A (Identify Ambiguities & Q&A)
- Quét qua toàn bộ logic xem có điểm thiếu sót, mâu thuẫn (conflicting) hoặc mơ hồ (ambiguous) nào giữa các yêu cầu hay không.
- Chủ động nhận diện những khoảng trống: Missing validation rules, error messages không có tài liệu, limit của các field dữ liệu, edge cases chưa được mention.
- Lập danh sách Q&A để clarify nghiệp vụ. 
- *Hành động bổ trợ:* Nếu đang sinh testcase tự động, Agent cần `⚠️ AMBIGUOUS` đánh dấu điểm mờ, tự đưa ra các giả định (assumptions) tối ưu rủi ro để tiếp tục công việc và yêu cầu xác nhận sau.

### Step 3: Đánh giá rủi ro (Risk Assessment)
- Đánh giá sơ bộ tác động nghiệp vụ (Business core), bảo mật, hay khả năng gây gián đoạn để phân bổ Testcase theo độ Risk:
  - **High Risk**: Các module cốt lõi liên quan tới giao dịch tài chính, dữ liệu người dùng, tính năng quan trọng. 
    `-> Đề xuất số lượng: Sinh ra từ 8 - 15 testcases.`
  - **Medium Risk**: Các chức năng phổ biến, logic xử lý thông thường không liên quan hệ thống sâu.
    `-> Đề xuất số lượng: Sinh ra từ 5 - 8 testcases.`
  - **Low Risk**: Chỉ chứa validate giao diện UX/UI (Text, label, minor info), ít nghiệp vụ ẩn.
    `-> Đề xuất số lượng: Sinh ra từ 2 - 4 testcases.`

### Step 4: Tạo Testcases (Generate Testcases)
- Từ kết quả rủi ro tổng hợp ở trên, xây dựng danh sách các kịch bản kiểm thử (Testcases).
- Ứng dụng kỹ thuật kiểm thử phù hợp: Phân vùng tương đương (Equivalence Partitioning) và Phân tích giá trị biên (Boundary Value Analysis) nhằm tối đa độ bao phủ rủi ro (Coverage).
- Viết testcase tuân thủ chuẩn QA Formatting:
  - Đặt tên ID & Title chuẩn convention.
  - Tách bạch rành mạch Pre-conditions, Input, Test Steps.
  - Expected Results phải đo lường (Measurable) và xác minh (Verifiable) được, KHÔNG dùng từ ngữ cảm giác (VD: tuyệt đối không dùng "Hiển thị đúng").

### Step 5: Xuất file (Export Document)
- Review lại độ ổn định của toàn bộ những testcases được sinh ra, đảm bảo 100% trace và cover toàn bộ Requirement truyền vào.
- Format kết quả dưới dạng lưới Bảng (Markdown table) gọn gàng có cấu trúc: [ID, Type, Priority, Title, Pre-conditions, Steps, Expected Results, Status].
- Chuẩn bị kết quả ở dạng dễ dàng Copy/Paste import vào Excel/Google Sheets hoặc import trực tiếp vào các Test Management Tools.