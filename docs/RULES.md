# Quy tắc khởi tạo tài liệu

Áp dụng cho mọi file tài liệu học tiếng Anh trong repo này (do người hoặc Claude tạo).

## 1. Cấu trúc thư mục

```
english/
├── CLAUDE.md                 # trỏ tới docs/RULES.md
├── README.md                 # mục lục + tiến độ
└── docs/
    ├── RULES.md              # file này
    ├── roadmap.md            # lộ trình tổng
    ├── templates/            # mẫu tài liệu
    ├── 00-foundation/        # A1
    ├── 01-elementary/        # A2
    ├── 02-intermediate/      # B1
    ├── 03-work-english/      # B2, tiếng Anh công việc
    │   ├── listening/
    │   ├── reading/
    │   ├── writing/
    │   └── speaking/
    ├── vocabulary/           # từ vựng theo chủ đề
    ├── grammar/              # ngữ pháp theo chủ điểm
    ├── logs/                 # error log, nhật ký học, kết quả sample test
    └── resources/            # danh sách sách, kênh, app
```

Tạo thư mục con khi cần, không tạo trước thư mục rỗng.

## 2. Đặt tên file

- Chữ thường, ngăn cách bằng dấu gạch ngang (`kebab-case`), không dấu tiếng Việt, không khoảng trắng.
- Tài liệu theo thứ tự có tiền tố số hai chữ số: `01-present-simple.md`.
- Tài liệu theo ngày có tiền tố ISO: `2026-10-15-sample-test-1.md`.
- Một file một chủ đề. Nếu quá 400 dòng thì tách ra.

## 3. Front matter bắt buộc

Mỗi file bắt đầu bằng front matter YAML:

```yaml
---
title: <tiêu đề>
type: grammar | vocabulary | listening | reading | writing | speaking | log | roadmap | resource
level: A1 | A2 | B1 | B2 | B2-work
created: YYYY-MM-DD
updated: 2026-10-16
status: draft | active | done
tags: []
---
```

- Khi sửa nội dung, cập nhật `updated`.
- Ngày tuyệt đối (YYYY-MM-DD), không dùng "hôm nay", "tuần trước".

## 4. Ngôn ngữ và trình bày

- Giải thích bằng **tiếng Việt**. Ví dụ, câu mẫu, thuật ngữ và từ vựng bằng **tiếng Anh**.
- Mỗi từ vựng mới ghi đủ: từ, loại từ, IPA, nghĩa tiếng Việt, một câu ví dụ, collocation nếu có.
- Mỗi điểm ngữ pháp có: công thức, khi nào dùng, 3 ví dụ, lỗi thường gặp, bài tập ngắn kèm đáp án ở cuối file.
- Dùng một `# H1` duy nhất (tiêu đề), các mục chính dùng `##`.
- Bảng cho dữ liệu so sánh, danh sách cho các bước. Không viết đoạn văn dài khi bảng hoặc danh sách rõ hơn.
- Code block có ngôn ngữ, ví dụ ```` ```text ````.

## 5. Nội dung bắt buộc theo loại

| Loại | Phải có |
|---|---|
| grammar | Công thức, cách dùng, ví dụ, lỗi thường gặp, bài tập + đáp án |
| vocabulary | Bảng từ (từ, loại, IPA, nghĩa, ví dụ), chủ đề, ngày bắt đầu ôn |
| listening / reading | Nguồn, thời lượng, điểm số, câu sai và lý do sai |
| writing | Đề bài, bài viết gốc, bản sửa, lỗi chính, chấm theo tiêu chí trong `schedule.md` (nội dung, bố cục, từ vựng, ngữ pháp) |
| speaking | Đề bài, dàn ý, transcript (nếu ghi âm), lỗi phát âm/ngữ pháp |
| log | Ngày, thời gian học, nội dung, lỗi lặp lại, mục tiêu ngày mai |

## 6. Mục tiêu đo được

Mỗi tài liệu giai đoạn (`00-`, `01-`, `02-`, `03-`) phải mở đầu bằng mục **Mục tiêu** có tiêu chí kiểm tra cụ thể (số từ, điểm test, số phút nói), khớp với `roadmap.md`.

## 7. Liên kết và nguồn

- Liên kết nội bộ dùng đường dẫn tương đối: `[Present simple](../grammar/01-present-simple.md)`.
- Mọi tài liệu từ bên ngoài phải ghi nguồn (tên, tác giả hoặc kênh, link). Không chép nguyên văn nội dung có bản quyền (sách, đề Cambridge); chỉ ghi tham chiếu và ghi chú của riêng bạn.
- Thêm file mới thì cập nhật mục lục trong `README.md`.

## 8. Ghi chép tiến độ

- `docs/logs/` giữ nhật ký theo ngày hoặc tuần; mỗi 2 tuần tổng kết lỗi lặp lại.
- Kết quả sample test lưu thành file riêng và thêm một dòng vào bảng tiến độ trong `README.md`.
- Không xóa log cũ; chỉ đánh dấu `status: done`.

## 9. Quy tắc khi Claude tạo tài liệu

1. Đọc `docs/RULES.md` và `docs/roadmap.md` trước khi tạo file.
2. Kiểm tra file cùng chủ đề đã tồn tại chưa; nếu có thì cập nhật thay vì tạo mới.
3. Dùng mẫu trong `docs/templates/` nếu có loại tương ứng.
4. Không bịa số liệu, điểm số hay tên giáo trình; nếu không chắc thì ghi `TODO: xác minh`.
5. Sau khi tạo hoặc sửa, cập nhật `README.md` (mục lục) và trường `updated`.
6. Không commit nếu người dùng chưa yêu cầu.
