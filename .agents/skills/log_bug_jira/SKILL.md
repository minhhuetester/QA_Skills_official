# 🐞 Jira Bug Log Skill Template

## 📝 Bug Title Convention

### Recommended Format

```text
[Module] What happened when doing what
```

**Rules**

- Format: **[Module] What happened when doing what**
- Start with the feature or screen name.
- Describe the incorrect behavior, not the expected behavior.
- Describe the user action that triggers the issue.
- Use present tense.
- Keep the title concise (preferably under 80 characters).
- Do not include the root cause or solution.
- One bug title should describe only one issue.

---

### Examples

| Rule | English | Tiếng Việt | 한국어 |
|------|---------|------------|--------|
| **[Module] What happened when doing what** | `[Email Verification] Send Verification Code button remains enabled after requesting a verification code` | `[Xác thực Email] Nút Nhận mã xác thực vẫn được kích hoạt sau khi yêu cầu mã xác thực` | `[이메일 인증] 인증번호 요청 후에도 [인증번호 받기] 버튼이 활성화됨` |
| **[Module] What happened when doing what** | `[Login] Login fails when signing in with a Google account` | `[Đăng nhập] Không thể đăng nhập khi đăng nhập bằng tài khoản Google` | `[로그인] Google 계정으로 로그인 시 로그인에 실패함` |
| **[Module] What happened when doing what** | `[Hotel Search] No search results are returned when searching for a 28-night stay` | `[Tìm kiếm khách sạn] Không trả về kết quả khi tìm kiếm lưu trú 28 đêm` | `[호텔 검색] 28박 검색 시 검색 결과가 조회되지 않음` |
| **[Module] What happened when doing what** | `[Vote] Vote button remains enabled while the ranking popup is displayed` | `[Bình chọn] Nút Bình chọn vẫn được kích hoạt khi popup bảng xếp hạng đang hiển thị` | `[투표] 랭킹 팝업 노출 중에도 투표 버튼이 활성화됨` |
| **[Module] What happened when doing what** | `[Payment] Payment method changes to Manual Input after saving settings` | `[Thanh toán] Phương thức thanh toán chuyển thành Nhập thủ công sau khi lưu cài đặt` | `[결제] 설정 저장 후 결제 방식이 수동 입력으로 변경됨` |
| **[Module] What happened when doing what** | `[Comment] Spam warning message is not displayed when submitting duplicate comments` | `[Bình luận] Không hiển thị cảnh báo spam khi gửi bình luận trùng lặp` | `[댓글] 동일한 댓글 작성 시 스팸 경고 메시지가 표시되지 않음` |
---

# 🐞 Jira Bug Report Template (Simple / 간단 버전)

Template rút gọn chỉ gồm 5 thành phần cốt lõi — dùng khi cần log bug nhanh.

---

## 🇻🇳 Phiên bản Tiếng Việt

```
[Môi trường]: DEV/ STAGING/ PRODUCTION

[Điều kiện tiên quyết]
- Kết hợp class

[Các bước tái hiện]
Đặt phòng/Thanh toán > Thông tin hành khách > Thông tin người đặt
Email > Chọn [Nhận mã xác thực] rồi xác nhận

[Kết quả hiện tại]
Trước thời điểm nút gửi lại được kích hoạt (trong vòng 1 phút sau khi nhận mã xác thực), nút [Nhận mã xác thực] vẫn hiển thị ở trạng thái kích hoạt

[Kết quả mong đợi]
Từ trạng thái vô hiệu hóa, nút chỉ được kích hoạt lại khi đến thời điểm có thể gửi lại mã
```

---

## 🇬🇧 English Version

```
[Environment]: DEV/ STAGING/ PRODUCTION

[Precondition]
Class combination

[Steps to Reproduce]
Booking/Payment > Passenger Information > Booker Information
Email > Select [Get Verification Code] then confirm

[Actual Result]
Before the resend button becomes active (within 1 minute after receiving the verification code), the [Get Verification Code] button is displayed in an active state

[Expected Result]
The button should remain disabled and only become active again once resending is allowed
```

---

## 🇰🇷 한국어 버전

```
[서버]: DEV/ STAGING/ PRODUCTION

[사전 조건]
클래스 결합

[재현 경로]
예약/결제 > 탑승객 정보 > 예약자 정보
이메일 > [인증번호 받기] 선택 후 확인

[현재 결과]
재전송 버튼 활성화 전인데(인증번호 받기 후 1분 이내) [인증번호 받기] 버튼이 활성화 상태로 노출됨

[기대 결과]
비활성화 상태에서 재전송 가능한 시점부터 다시 활성화되어야 함
```

---

## 📋 Bảng đối chiếu thuật ngữ / Terminology Mapping / 용어 대조표

| 한국어 | Tiếng Việt | English |
|---|---|---|
| 서버 | Môi trường | Environment |
| 사전 조건 | Điều kiện tiên quyết | Precondition |
| 재현 경로 | Các bước tái hiện | Steps to Reproduce |
| 현재 결과 | Kết quả hiện tại | Actual Result |
| 기대 결과 | Kết quả mong đợi | Expected Result |
