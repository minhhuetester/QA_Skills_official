# Quy tắc xây dựng Manual Testcase (QA Standards)

## 1. Mô tả (Description)
- **Phạm vi áp dụng:** Bộ quy tắc này là **BẮT BUỘC** và phải được tuân thủ nghiêm ngặt mỗi khi Agent (hoặc QA/Tester) thực hiện quá trình phân tích, thiết kế, tạo mới hoặc định dạng các kịch bản kiểm thử thủ công (Manual Testcases).
- **Mục tiêu:** Đảm bảo toàn bộ testcase được tạo ra đạt tiêu chuẩn cao nhất của một Senior QA: chuyên nghiệp, nhất quán, rõ ràng, dễ bảo trì, và có khả năng thực thi (execution-ready) trên mọi hệ thống quản lý (Test Management Tools, JIRA, hoặc Google Sheets).

## 2. Ràng buộc dữ liệu (Data Constraints)
- **Tính thực tế & Cụ thể:** Dữ liệu chuẩn bị cho quá trình test (Test Data) phải là dữ liệu thực tế, có ý nghĩa và bám sát nghiệp vụ. Tuyệt đối **không** sử dụng dữ liệu rác (dummy data) như *"abc"*, *"123"*, *"test"* trừ khi có yêu cầu đặc thù.
- **Tình trạng của Tiền điều kiện (Pre-conditions):** Bắt buộc phải xác định chính xác môi trường, trạng thái của hệ thống và tài khoản ngữ cảnh trước khi bắt đầu test. 
  - *Ví dụ:* *"Tài khoản User hạng Gold đã được verify email và đang có 2 sản phẩm A, B trong giỏ hàng."*
- **Phân định rõ Input và Expected Output:** Tách biệt hoàn toàn dữ liệu đầu vào (Input data) và dữ liệu dùng để xác nhận (Expected Output data) trong Test Steps hoặc Expected Results.
- **Tính trọn vẹn (Self-contained):** Bất kỳ QA nào khác (hoặc automation script) đọc testcase đều phải có đủ thông tin, dữ liệu để thực thi thành công từ đầu đến cuối mà không phải lục lọi tài liệu khác.

## 3. Quy tắc bao phủ (Coverage Rules)
- **Traced & Mapped (Truy xuất nguồn gốc):** 100% Testcase phải đối chiếu (map) với ít nhất một Requirement (Yêu cầu nghiệp vụ), User Story, hoặc Acceptance Criteria cụ thể. Không được phép tồn tại testcase không có mục đích rõ ràng.
- **Happy Path (Luồng chính):** Tối thiểu phải có 1-2 testcase (Priority High/Critical) cho mỗi luồng nghiệp vụ chuẩn, mô tả trọn vẹn quá trình từ khi bắt đầu đến khi hoàn tất (End-to-End process).
- **Negative/Exception Testing (Luồng lỗi/Ngoại lệ):** Bắt buộc bao phủ các trường hợp người dùng thao tác sai, nhập liệu sai quy tắc, lỗi hệ thống, mất kết nối, hoặc quyền truy cập không đủ (Permission bounds). Yêu cầu hệ thống hiển thị thông báo lỗi thân thiện (Graceful degradation).
- **Boundary Value & Equivalence Partitioning:** Luôn áp dụng phân tích giá trị biên và phân vùng tương đương đối với các tham số đầu vào (Min, Max, Min-1, Max+1, giá trị rỗng, vượt giới hạn ký tự, sai định dạng).
- **Cross-platform / Environment:** Tùy từng đặc thù tính năng, QA cần nhắc nhở hoặc liệt kê rõ testcase cần cover trên thiết bị, trình duyệt hoặc hệ điều hành nào.

## 4. Quy tắc định dạng và Naming (Formatting & Naming Convention)

### 4.1. Naming Convention (Quy tắc đặt tên)
- **Testcase ID:** Phải tuân theo định dạng chuẩn hóa: `[PREFIX_DỰ_ÁN/MODULE]-[SUB_MODULE]-[SỐ_THỨ_TỰ]`. Hệ thống ID phải có tính duy nhất (Unique).
  - *Ví dụ:* `LUNA-LOGIN-001`, `TOURVIS-SEARCH-005`.
- **Testcase Title / Summary:**
  - Ngắn gọn, súc tích (khuyến nghị dưới 100 ký tự).
  - **Cấu trúc bắt buộc:** `[Action Verb (Verify/Check/Ensure)] + [Đối tượng/Tính năng] + [Điều kiện/Ngữ cảnh]`.
  - *Ví dụ Tốt:* `Verify that user can log in successfully with valid credentials`
  - *Ví dụ Xấu:* `Test chức năng login`, `Login lỗi password`.

### 4.2. Formatting Rules (Quy tắc định dạng chi tiết)
- **Ngôn ngữ & Giọng văn:** Sử dụng ngôn ngữ chuyên nghiệp (ưu tiên tiếng Việt, hoặc tuân thủ đúng ngôn ngữ của dự án). Sử dụng thể chủ động, câu mệnh lệnh (Imperative mood) để hướng dẫn thao tác rõ ràng.
- **Test Steps (Các bước thực hiện):**
  - Đánh số thứ tự từng bước rành mạch (1, 2, 3...).
  - Mỗi bước tương ứng với một thao tác hoặc một nhóm thao tác nhỏ có liên quan logic. Không gộp quá nhiều bước phức tạp vào một dòng.
  - Phải chỉ định rõ ràng định danh của thành phần UI người dùng cần tương tác. 
  - *Ví dụ:* `1. Enter valid email "test@example.com" into the "Email" field.`
- **Expected Results (Kết quả mong đợi):**
  - **CẤM** dùng các từ ngữ cảm tính, mơ hồ như: *"Lưu thành công"*, *"Hoạt động tốt"*, *"Hiển thị đúng"*.
  - Kết quả phải đo lường, quan sát hoặc kiểm chứng (verify) được. Mô tả rành mạch UI chuyển thiết kế ra sao, data phản hồi mã gì, có alert/message cụ thể gì bật lên.
  - *Ví dụ Tốt:* `The system redirects to the "Dashboard" page and displays a toast message "Login Successful" in green.`
- **Trường phụ trợ (Meta fields):** Yêu cầu gán đầy đủ thuộc tính để phục vụ cho việc quản lý test plan & regression test:
  - **Priority:** (Critical, High, Medium, Low)
  - **Test Type:** (Functional, UI/UX, Security, Performance...)
