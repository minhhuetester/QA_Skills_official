# 🐞 Jira Bug Log Skill Template

## 📝 Bug Title Convention

### Recommended Format

```text
[Module] What happened when doing what
```

**Rules**

- Bắt đầu bằng tên Module hoặc Feature.
- Mô tả ngắn gọn vấn đề (không mô tả cách sửa).
- Dùng thì hiện tại.
- Tránh dùng các tiêu đề chung chung như "Bug", "Error", "Issue".
- Một bug chỉ mô tả **một vấn đề**.
- **Mô-đun**: Sử dụng tên tính năng hoặc tên màn hình.
- **Điều gì đã xảy ra**: Mô tả hành vi không chính xác.
- **Khi nào thực hiện thao tác nào**: Mô tả hành động của người dùng gây ra sự cố.
- Giữ tiêu đề ngắn gọn (tốt nhất là dưới 80 ký tự).
- Mô tả triệu chứng, không phải nguyên nhân gốc rễ hoặc giải pháp.
- Một tiêu đề lỗi chỉ nên mô tả một vấn đề duy nhất.

---

### 🇺🇸 English Examples

```text
[Login] Google login fails
```

```text
[Hotel Search] No results are returned for 28-night stay
```

```text
[Email Verification] Send Verification Code button remains enabled before resend timeout
```

```text
[Vote] Vote button is enabled while ranking popup is displayed
```

---

### 🇻🇳 Ví dụ Tiếng Việt

```text
[Đăng nhập] Không thể đăng nhập bằng Google
```

```text
[Tìm kiếm khách sạn] Không trả về kết quả khi tìm kiếm 28 đêm
```

```text
[Xác thực Email] Nút Nhận mã xác thực vẫn được kích hoạt trước thời gian gửi lại
```

---

### 🇰🇷 한국어 예시

```text
[로그인] Google 로그인 실패
```

```text
[호텔 검색] 28박 검색 시 결과가 조회되지 않음
```

```text
[이메일 인증] 재전송 가능 시간 전에도 [인증번호 받기] 버튼이 활성화됨
```

```text
[투표] 랭킹 팝업 노출 중에도 투표 버튼이 활성화됨
```

---

# 🐞 Jira Bug Report Template (Simple / 간단 버전)

Template rút gọn chỉ gồm 5 thành phần cốt lõi — dùng khi cần log bug nhanh.

---

## 🇻🇳 Phiên bản Tiếng Việt

```
[Môi trường]
DEV

[Điều kiện tiên quyết]
Kết hợp class

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
[Environment]
DEV

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
[서버]
DEV

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
