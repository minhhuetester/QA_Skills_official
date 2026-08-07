# Antigravity Testing Kit 🚀

Chào mừng bạn đến với **Antigravity Testing Kit**! Đây là bộ công cụ tích hợp các cấu hình tác tử (agent customizations) bao gồm Rules, Workflows, Skills và Prompts để hỗ trợ quy trình kiểm thử (QA/QC), thiết kế kịch bản kiểm thử (Manual Testcase) chất lượng cao và báo cáo lỗi (Jira Bug Reporting) tự động hóa bằng AI.

---

## 📁 Cấu trúc thư mục (Folder Structure)

Bộ kit được cấu trúc bên trong thư mục `.agents/` như sau:

```text
antigravity-testing-kit/
│
├── .agents/
│   ├── rules/
│   │   └── manual-testcases-rule.md         # Bộ quy tắc tiêu chuẩn viết Manual Testcase (QA Standards)
│   │
│   ├── workflows/
│   │   ├── manual-testcases-workflow.md     # Quy trình tạo Testcase chi tiết qua AI-RBT 6 bước
│   │   ├── generate_manual_testcases_rbt.md # Workflow kích hoạt tạo Testcase theo RBT
│   │   └── generate_testcases_from_requirements.md # Workflow tạo Testcase nhanh (QUICK mode)
│   │
│   ├── skills/
│   │   ├── rbt_generate_manual_testcases/   # Master Skill hỗ trợ cả 2 chế độ QUICK & FULL RBT
│   │   ├── generate_manual_testcases/       # Skill phụ trợ sinh Testcase chuyên nghiệp
│   │   ├── bug_template/                    # Skill tạo khuôn mẫu Bug Report đa ngôn ngữ (VI, EN, KO)
│   │   └── log_bug_jira/                    # Skill tích hợp log Bug trực tiếp lên Jira
│   │
│   └── prompts/
│       ├── manual_testcases_prompt.md       # Prompts mẫu để làm việc với AI
│       └── prompts_note.txt                 # Hướng dẫn cách áp dụng prompt và rules hiệu quả
│
└── README.md                                # File giới thiệu tổng quan này
```

---

## 🌟 Các thành phần chính

### 1. Quy tắc QA Tiêu chuẩn (Rules)
*   **[manual-testcases-rule.md](file:///.agents/rules/manual-testcases-rule.md):** 
    *   Quy định chặt chẽ về cách đặt tên ID (`[PREFIX]-[MODULE]-[SỐ_THỨ_TỰ]`), tiêu đề kịch bản (sử dụng động từ hành động: *Verify*, *Check*, *Ensure*).
    *   Yêu cầu bắt buộc về tính thực tế của **Test Data** (không dùng dữ liệu rác như `abc`, `123`, phải sử dụng email, mã thật).
    *   Cách viết **Expected Results** đo lường được, không cảm tính.

### 2. Quy trình kiểm thử dựa trên rủi ro (Workflows)
*   **[manual-testcases-workflow.md](file:///.agents/workflows/manual-testcases-workflow.md) / [generate_manual_testcases_rbt.md](file:///.agents/workflows/generate_manual_testcases_rbt.md):** 
    *   Quy trình **AI-RBT 6 bước** chuyên sâu:
        1. **Context & Role-play:** Nhận diện bối cảnh hệ thống.
        2. **Analysis & QnA:** Phân tích tài liệu, tìm điểm mờ (Ambiguity) và đặt câu hỏi làm rõ logic.
        3. **Decomposition:** Phân rã hệ thống thành các module nhỏ.
        4. **Traceability:** Đảm bảo độ bao phủ của testcase.
        5. **Risk Assessment:** Đánh giá rủi ro (High/Medium/Low) để phân bổ số lượng testcase phù hợp.
        6. **Generate & Export:** Tạo kịch bản kiểm thử chi tiết và xuất ra định dạng bảng Markdown (Dễ dàng import vào Google Sheets, Excel hoặc Jira).
*   **[generate_testcases_from_requirements.md](file:///.agents/workflows/generate_testcases_from_requirements.md):** Quy trình chế độ **QUICK**, giúp sinh nhanh testcase từ yêu cầu rõ ràng mà không cần qua 6 bước phân tích.

### 3. Kỹ năng nâng cao của Agent (Skills)
*   **[rbt_generate_manual_testcases](file:///.agents/skills/rbt_generate_manual_testcases/SKILL.md):** Master Skill điều phối việc lựa chọn và thực thi giữa 2 chế độ **QUICK** (Sinh nhanh) và **FULL RBT** (Quy trình 6 bước).
*   **[bug_template](file:///.agents/skills/bug_template/SKILL.md) & [log_bug_jira](file:///.agents/skills/log_bug_jira/SKILL.md):** Hỗ trợ QA viết bug report chuẩn hóa bằng tiếng Việt, tiếng Anh và tiếng Hàn, cùng cấu hình giúp đưa bug trực tiếp lên hệ thống Atlassian Jira của dự án.

---

## 🛠️ Hướng dẫn sử dụng nhanh

Bạn có thể kích hoạt các chức năng thông qua chat với Antigravity bằng cách:

1.  **Sinh testcases theo quy trình đầy đủ (FULL RBT):**
    *   Sử dụng lệnh: `/generate_manual_testcases_rbt`
    *   Hoặc ra lệnh: *"Sinh bộ test cases bài bản cho tính năng [Tên tính năng] theo quy trình 6 bước"*
2.  **Sinh testcases nhanh (QUICK mode):**
    *   Sử dụng lệnh: `/generate_testcases_from_requirements`
    *   Hoặc ra lệnh: *"Viết nhanh test cases từ yêu cầu này: [Nội dung yêu cầu]"*
3.  **Xem cấu trúc mẫu prompts gợi ý:**
    *   Xem chi tiết tại file [prompts_note.txt](file:///.agents/prompts/prompts_note.txt) để biết cách kết hợp Rules, Skills và Workflows tối ưu nhất trong câu lệnh.
