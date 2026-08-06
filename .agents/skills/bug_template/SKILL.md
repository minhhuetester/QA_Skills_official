# 🐞 Jira Bug Report Template

---

# Reporter Information

| Field | Value |
|---|---|
| Reported By | |
| Date Reported | YYYY-MM-DD |
| Assignee | |
| Labels | e.g. `regression`, `ui`, `payment` |
| Component | e.g. `Hotel Search`, `Login`, `Payment Gateway` |

---

# Summary

> Một câu ngắn gọn mô tả lỗi.

**Format khuyến nghị**
```
[Module] What happened when doing what
```

Ví dụ:
```
[Login] User cannot login using Google Account
[Hotel Search] Search returns empty result when selecting 28-night stay
```

---

# Environment

| Item | Value | Ghi chú |
|------|-------|---------|
| Environment | Dev / Staging / Production | |
| Build Version | v1.2.3 | Lấy từ footer app / About page / response header — **note rõ lấy từ đâu** |
| Browser | Chrome 138 | Nếu bug chỉ xảy ra trên 1 browser cụ thể |
| Device | Desktop / Mobile | |
| OS | Windows 11 | |
| API Version | v2 | |
| Account / Test Data | QA Account – username: `qa_test01` | Ghi rõ username, booking ID, tenant... nếu bug liên quan dữ liệu cụ thể để dev tái hiện nhanh hơn |

---

# Regression Check

| Field | Value |
|---|---|
| Is Regression? | Yes / No |
| Last Known Working Version | v2.3.0 (nếu có) |
| Introduced In Version | v2.3.1 (nếu xác định được) |

> Regression là bug quan trọng, ảnh hưởng trực tiếp đến priority — nên xác định sớm nếu có thể.

---

# Preconditions

Các điều kiện cần có trước khi thực hiện.

Ví dụ
- User đã đăng nhập
- Có quyền Admin
- Có dữ liệu khách sạn
- Feature Flag đã bật

---

# Steps To Reproduce

1.
2.
3.
4.

---

# Actual Result

Mô tả kết quả hiện tại.

Ví dụ
- Popup không hiển thị
- API trả về HTTP 500
- Danh sách bị trống

---

# Expected Result

Mô tả hành vi đúng.

Ví dụ
- Popup phải xuất hiện.
- User được chuyển sang Dashboard.
- API trả về HTTP 200.

---

# Frequency

| Option | Tỷ lệ tái hiện |
|---|---|
| Always | 100% |
| Often | ~80% |
| Sometimes | ~30–50% |
| Rare | < 10% |
| Cannot Reproduce | Không tái hiện được, chỉ ghi nhận qua log/report từ user |

---

# Severity

- Critical
- High
- Medium
- Low
- Cosmetic

**Guideline**

| Severity | Ý nghĩa |
|-----------|---------|
| Critical | System unusable / Data loss |
| High | Chức năng chính không dùng được, không có workaround |
| Medium | Có workaround |
| Low | Ảnh hưởng nhỏ, không cản trở luồng chính |
| Cosmetic | Chỉ ảnh hưởng UI, không ảnh hưởng chức năng |

---

# Priority

- P0
- P1
- P2
- P3

**Guideline**

| Priority | Ý nghĩa | Thời gian xử lý gợi ý |
|---|---|---|
| P0 | Blocker – cần fix ngay lập tức | Trong ngày / hotfix |
| P1 | Urgent – ảnh hưởng lớn đến user/business | Trong sprint hiện tại |
| P2 | Normal – cần fix nhưng không khẩn cấp | Sprint kế tiếp |
| P3 | Low – có thể trì hoãn | Backlog, ưu tiên thấp |

> Lưu ý: Severity mô tả **mức độ nghiêm trọng kỹ thuật**, Priority mô tả **mức độ khẩn cấp cần xử lý**. Một bug Severity thấp vẫn có thể Priority cao nếu ảnh hưởng đến khách hàng lớn hoặc sự kiện quan trọng.

---

# Impact

Đối tượng bị ảnh hưởng.

Ví dụ
- All users
- Admin only
- BTMS customers
- Mobile users only

---

# Workaround

> Cách xử lý tạm thời trong lúc chờ fix (nếu có). Áp dụng đặc biệt với bug Severity = Medium.

Ví dụ
- User có thể refresh lại trang để tiếp tục thao tác.
- Dùng trình duyệt khác (Firefox) thay vì Chrome.
- Không có workaround.

---

# Attachments

Đính kèm theo loại bug (đánh dấu mục nào bắt buộc tùy tình huống):

| Loại bug | Bắt buộc đính kèm |
|---|---|
| UI/UX bug | Screenshot (bắt buộc), Video (khuyến khích) |
| API/Backend bug | Network Log, Request/Response (bắt buộc) |
| Crash/App die | Crash Log, Console Log (bắt buộc) |
| Performance bug | Video, Log thời gian phản hồi |

Danh sách đính kèm:
- [ ] Screenshot
- [ ] Video
- [ ] Console Log
- [ ] Network Log
- [ ] Crash Log

---

# Additional Information

Thông tin bổ sung.

Ví dụ
- Chỉ xảy ra sau khi refresh.
- Không xảy ra trên Firefox.
- Chỉ xảy ra với tài khoản có nhiều hơn 10 booking.

---

# API Information (Optional)

Request
```json
{}
```

Response
```json
{}
```

---

# Log (Optional)

```
Paste server log / console log
```

---

# Root Cause (Developer)

> Developer cập nhật sau khi fix.

Ví dụ
- Null Pointer Exception
- Missing validation
- Wrong SQL condition
- Cache issue
- Race condition

---

# Solution

Developer ghi cách fix.

Ví dụ
- Add null check
- Update API validation
- Fix SQL query
- Handle timeout

---

# QA Verification

| Step | Status | Verified By | Date |
|---|---|---|---|
| Reproduced | [ ] | | |
| Fixed | [ ] | | |
| Regression Tested | [ ] | | |
| Closed | [ ] | | |

---

# Related Issues

- Story:
- Task:
- Epic:
- Previous Bug:

---

# Change Log

| Date | Người sửa | Thay đổi |
|---|---|---|
| | | Tạo bug ban đầu |
| | | Cập nhật Root Cause / Solution |
| | | Đóng bug sau khi verify |

---

# 🛠️ Jira Bug Logging Prompt Guide (프롬프트 가이드)

Dưới đây là các câu lệnh/prompt mẫu để hướng dẫn AI log bug trên Jira theo đúng ngôn ngữ yêu cầu:

### 1. Log bug song ngữ Việt - Hàn (Vietnamese & Korean)
* **Prompt:** `Hãy log bug lên Jira bằng Tiếng Việt và Tiếng Hàn dựa trên thông tin sau: [Thông tin bug/mô tả lỗi]`
* **Cách AI thực hiện:** Viết Summary, Preconditions, Steps to Reproduce, Actual Result, Expected Result bằng cả 2 ngôn ngữ (tiếng Việt trước, tiếng Hàn sau hoặc viết song song).
  * *Ví dụ Summary:* `[Login] Lỗi đăng nhập bằng Google / Google 로그인 오류`

### 2. Log bug tiếng Hàn (Korean Only)
* **Prompt:** `Hãy log bug lên Jira bằng Tiếng Hàn dựa trên thông tin sau: [Thông tin bug/mô tả lỗi]`
* **Cách AI thực hiện:** Dịch và điền toàn bộ các trường thông tin trong template hoàn toàn bằng tiếng Hàn.
  * *Ví dụ Summary:* `[Login] Google 계정으로 로그인할 수 없음`

### 3. Log bug song ngữ Hàn - Anh (Korean & English)
* **Prompt:** `Hãy log bug lên Jira bằng Tiếng Hàn và Tiếng Anh dựa trên thông tin sau: [Thông tin bug/mô tả lỗi]`
* **Cách AI thực hiện:** Viết tiêu đề và nội dung các bước bằng tiếng Hàn kèm bản dịch tiếng Anh tương ứng.
  * *Ví dụ Summary:* `[Login] Google 로그인 실패 / Google Login Failure`

---

# 🐞 Jira Bug Report Template (한국어 버전)

---

# Reporter Information (보고자 정보)

| Field | Value |
|---|---|
| Reported By (보고자) | |
| Date Reported (보고일자) | YYYY-MM-DD |
| Assignee (담당자) | |
| Labels (레이블) | 예: `regression`, `ui`, `payment` |
| Component (컴포넌트) | 예: `Hotel Search`, `Login`, `Payment Gateway` |

---

# Summary (요약)

> 버그를 간략하게 설명하는 한 줄 요약입니다.

**추천 형식**
```
[모듈명] 어떤 동작을 할 때 발생한 현상
```

예시:
```
[Login] 구글 계정으로 로그인할 수 없음
[Hotel Search] 28박 이상 선택 시 검색 결과가 비어 있음
```

---

# Environment (테스트 환경)

| 항목 | 값 | 비고 |
|------|-------|---------|
| Environment (환경) | Dev / Staging / Production | |
| Build Version (빌드 버전) | v1.2.3 | 앱 푸터 / 정보 페이지 / 응답 헤더에서 확인 — **확인 경로 기재** |
| Browser (브라우저) | Chrome 138 | 특정 브라우저에서만 발생하는 경우 |
| Device (기기) | Desktop / Mobile | |
| OS (운영체제) | Windows 11 | |
| API Version (API 버전) | v2 | |
| Account / Test Data (테스트 데이터) | QA Account – username: `qa_test01` | 재현을 위해 필요한 사용자명, 예약 ID, 테넌트 등을 명시 |

---

# Regression Check (회귀 테스트 여부)

| Field | Value |
|---|---|
| Is Regression? (회귀 버그 여부) | Yes / No |
| Last Known Working Version (이전 정상 버전) | v2.3.0 (있는 경우) |
| Introduced In Version (버그 도입 버전) | v2.3.1 (확인 가능한 경우) |

> Regression(회귀 버그)은 기존에 잘 작동하던 기능이 깨진 것으로, 우선순위에 직접적인 영향을 미치므로 가능한 빠르게 파악해야 합니다.

---

# Preconditions (사전 조건)

테스트 수행 전 필요한 사전 설정 조건들입니다.

예시:
- 사용자가 로그인한 상태여야 함
- 관리자(Admin) 권한 보유
- 호텔 데이터가 등록되어 있어야 함
- 기능 플래그(Feature Flag)가 켜져 있어야 함

---

# Steps To Reproduce (재현 절차)

1.
2.
3.
4.

---

# Actual Result (실제 결과)

현재 나타나는 오류 현상에 대해 설명합니다.

예시:
- 팝업이 표시되지 않음
- API가 HTTP 500 오류를 반환함
- 목록이 비어 있음

---

# Expected Result (기대 결과)

올바른 시스템 동작에 대해 설명합니다.

예시:
- 팝업이 정상적으로 표시되어야 함.
- 사용자가 대시보드 페이지로 이동해야 함.
- API가 HTTP 200 성공을 반환해야 함.

---

# Frequency (재현 빈도)

| 옵션 | 재현율 |
|---|---|
| Always (항상) | 100% |
| Often (자주) | ~80% |
| Sometimes (가끔) | ~30–50% |
| Rare (드물게) | < 10% |
| Cannot Reproduce (재현 불가) | 재현이 불가능하며, 사용자의 로그/보고를 통해서만 확인됨 |

---

# Severity (심각도)

- Critical (치명적)
- High (높음)
- Medium (보통)
- Low (낮음)
- Cosmetic (UI 개선)

**가이드라인**

| Severity | 의미 |
|-----------|---------|
| Critical | 시스템 사용 불가 / 데이터 손실 |
| High | 핵심 기능을 사용할 수 없으며 우회 방법(Workaround)이 없음 |
| Medium | 우회 방법이 존재함 |
| Low | 경미한 영향, 메인 흐름에 지장을 주지 않음 |
| Cosmetic | 기능에는 영향이 없고 UI 레이아웃/스타일만 영향을 받음 |

---

# Priority (우선순위)

- P0
- P1
- P2
- P3

**가이드라인**

| Priority | 의미 | 제안 처리 시간 |
|---|---|---|
| P0 | Blocker – 즉각적인 수정 필요 | 당일 처리 / 핫픽스 |
| P1 | Urgent – 사용자/비즈니스에 영향이 큼 | 현재 스프린트 내 완료 |
| P2 | Normal – 수정이 필요하나 긴급하지 않음 | 다음 스프린트 |
| P3 | Low – 보류 가능 | 백로그, 낮은 우선순위 |

> 참고: Severity는 **기술적인 심각도**를 설명하고, Priority는 **처리 긴급도**를 설명합니다. 심각도가 낮은 버그라도 중요 고객사 영향이나 중요 이벤트가 있는 경우 우선순위가 높아질 수 있습니다.

---

# Impact (영향 범위)

영향을 받는 대상입니다.

예시:
- 모든 사용자 (All users)
- 관리자 권한만 (Admin only)
- BTMS 고객사 (BTMS customers)
- 모바일 사용자만 (Mobile users only)

---

# Workaround (우회 방법)

> 수정을 기다리는 동안 임시로 조치할 수 있는 방법입니다. (주로 Severity = Medium인 버그에 해당)

예시:
- 사용자가 페이지를 새로고침하여 계속 진행할 수 있음.
- Chrome 대신 다른 브라우저(Firefox 등)를 사용함.
- 우회 방법 없음.

---

# Attachments (첨부 자료)

버그 유형에 맞춰 필요한 자료를 첨부합니다 (상황에 따라 필수 지정):

| 버그 유형 | 필수 첨부 자료 |
|---|---|
| UI/UX 버그 | 스크린샷 (필수), 화면 녹화 (권장) |
| API/Backend 버그 | 네트워크 로그, Request/Response 전문 (필수) |
| 크래시/앱 중단 | 크래시 로그, 콘솔 로그 (필수) |
| 성능 버그 | 화면 녹화, 응답 시간 측정 로그 |

첨부 목록:
- [ ] Screenshot (스크린샷)
- [ ] Video (동영상 녹화)
- [ ] Console Log (콘솔 로그)
- [ ] Network Log (네트워크 로그)
- [ ] Crash Log (크래시 로그)

---

# Additional Information (추가 정보)

추가 참고 사항입니다.

예시:
- 페이지 새로고침 후에만 발생함.
- Firefox에서는 발생하지 않음.
- 예약 건수가 10개 이상인 계정에서만 발생함.

---

# API Information (Optional - API 정보)

Request
```json
{}
```

Response
```json
{}
```

---

# Log (Optional - 로그)

```
Paste server log / console log (서버 로그 또는 콘솔 로그 붙여넣기)
```

---

# Root Cause (Developer - 발생 원인)

> 버그 수정 후 개발자가 작성합니다.

예시:
- Null Pointer Exception
- 검증 유효성 누락 (Missing validation)
- 잘못된 SQL 조건 (Wrong SQL condition)
- 캐시 문제 (Cache issue)
- 레이스 컨디션 (Race condition)

---

# Solution (해결 방안)

개발자가 작성한 버그 수정 내용입니다.

예시:
- Null Check 추가
- API 검증 규칙(Validation) 업데이트
- SQL 쿼리 수정
- 타임아웃 예외 처리

---

# QA Verification (QA 검증)

| Step | Status | Verified By | Date |
|---|---|---|---|
| Reproduced (재현 확인) | [ ] | | |
| Fixed (수정 확인) | [ ] | | |
| Regression Tested (회귀 테스트) | [ ] | | |
| Closed (종료) | [ ] | | |

---

# Related Issues (관련 이슈)

- Story:
- Task:
- Epic:
- Previous Bug:

---

# Change Log (변경 이력)

| Date | 작업자 | 변경 내용 |
|---|---|---|
| | | 최초 버그 생성 |
| | | Root Cause / Solution 업데이트 |
| | | 검증 완료 후 버그 종료 |

