---
title: Tiếng Anh cho Solution Architect, Senior DevOps/SRE/Backend, Platform Engineer
type: resource
level: B2-work
created: 2026-10-16
updated: 2026-10-16
status: draft
tags: [work-english, software, interview, architecture, devops]
---

# Tiếng Anh cho vị trí kỹ sư phần mềm cấp cao

## Mục tiêu

Đến cuối giai đoạn 3 (khoảng tháng 20), với các vị trí Solution Architect, Senior DevOps/SRE/Backend Engineer, Platform Engineer, bạn làm được:

- Phỏng vấn 45–60 phút bằng tiếng Anh: giới thiệu kinh nghiệm 2 phút, kể 3 tình huống STAR (xem bên dưới), không dừng quá 3 giây khi nghĩ ý.
- Trình bày một thiết kế hệ thống (system design) 10–15 phút: yêu cầu → kiến trúc → trade-off → rủi ro, và trả lời câu hỏi đào sâu.
- Viết tài liệu kỹ thuật ngắn (design doc 1 trang, ADR, postmortem) và email/tin nhắn công việc, mỗi đoạn rõ ý, ít lỗi.
- Nghe hiểu họp kỹ thuật và cuộc gọi với khách hàng hoặc đội ở múi giờ khác, ghi được action items.

Kế hoạch phỏng vấn sớm (sau Tết 2027) và hai đường A/B: [interview-plan.md](../interview-plan.md).

Các tiêu chí này bổ sung cho bảng tiêu chí trong [schedule.md](../schedule.md); mâu thuẫn thì theo `schedule.md`.

## Tình huống chính theo vai trò

| Tình huống | Solution Architect | Senior Backend | DevOps/SRE | Platform Engineer |
|---|---|---|---|---|
| Phỏng vấn hành vi (behavioral) | Có | Có | Có | Có |
| Trình bày system design | Rất quan trọng | Quan trọng | Quan trọng | Quan trọng |
| Giải thích trade-off cho người không chuyên | Rất quan trọng (khách hàng, quản lý) | Vừa | Vừa | Quan trọng (đội nội bộ) |
| Incident / on-call: báo cáo, postmortem | Ít | Vừa | Rất quan trọng | Quan trọng |
| Viết design doc, ADR, RFC | Rất quan trọng | Quan trọng | Quan trọng | Rất quan trọng |
| Code review, pull request bằng tiếng Anh | Vừa | Rất quan trọng | Quan trọng | Quan trọng |

## Nhóm từ vựng và cụm câu cần xây (không ghi nghĩa ở đây, đưa vào Anki theo `docs/templates/vocabulary.md`)

- **Kiến trúc:** scalability, availability, latency, throughput, consistency, trade-off, bottleneck, single point of failure.
- **Vận hành:** deploy, rollback, roll out, on-call, incident, root cause, mitigation, postmortem.
- **Làm việc nhóm:** stakeholder, requirement, deadline, blocker, follow up, align on, take ownership.
- **Cụm câu thuyết trình:** *Let me walk you through...*, *The main trade-off here is...*, *If we expect X, we could...*, *One risk is...*
- **Cụm câu họp:** *Could you clarify what you mean by...?*, *Let me make sure I understood...*, *I'd suggest we...*, *I'm not sure I agree, because...*

Mỗi nhóm học dần theo tuần từ giai đoạn 2; TODO: soạn file từ vựng riêng khi bắt đầu giai đoạn 2.

## Lộ trình thêm vào lịch hiện tại

Không thêm giờ học; thay nội dung trong khung 7 giờ mỗi tuần của [schedule.md](../schedule.md).

| Giai đoạn | Nội dung kỹ thuật cần thêm |
|---|---|
| 1 (A2, tháng 4–8) | Giới thiệu bản thân và công việc 1 phút; đọc README, thông báo lỗi, tài liệu đơn giản; viết commit message, câu hỏi ngắn trên chat |
| 2 (B1, tháng 9–14) | Đọc docs kỹ thuật (cloud, framework); mô tả dự án đã làm 2 phút; viết PR description, email 100 từ; nghe video kỹ thuật có phụ đề |
| 3 (B2, tháng 15–20) | System design 10–15 phút; câu chuyện STAR; design doc, ADR, postmortem; nhập vai phỏng vấn mỗi tuần; nghe họp/conference talk không phụ đề |

## STAR cho phỏng vấn hành vi

| Chữ | Nghĩa | Ví dụ ý |
|---|---|---|
| Situation | Bối cảnh | Hệ thống thanh toán bị chậm vào giờ cao điểm |
| Task | Nhiệm vụ của bạn | Giảm p95 latency xuống dưới ngưỡng cam kết |
| Action | Việc bạn làm | Thêm cache, tách truy vấn nặng, đặt cảnh báo |
| Result | Kết quả, nên có số | Latency giảm còn một nửa, không còn incident trong 3 tháng |

Chuẩn bị 6 câu chuyện (một lần xử lý incident, một lần bất đồng với đồng nghiệp, một quyết định kiến trúc khó, một lần thất bại, một lần dẫn dắt, một lần làm việc với khách hàng). Viết ra, nhờ AI sửa, luyện nói đủ 2 phút cho mỗi chuyện.

## Nguồn

TODO: xác minh trước khi ghi link. Gợi ý loại nguồn: tài liệu chính thức của cloud/framework, tài liệu SRE công khai của các công ty lớn, conference talk kỹ thuật có transcript, bộ câu hỏi system design công khai. Chọn nguồn theo ngành bạn đang làm và ghi tên, tác giả, link khi dùng thật.
