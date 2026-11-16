# Quy tắc khởi tạo tài liệu

> **Định dạng: mọi tài liệu học là HTML (`.html`), không viết Markdown.** Ngoại lệ (giữ Markdown để xem trực tiếp trên GitHub): `CLAUDE.md`, `README.md` ở gốc repo và `docs/RULES.md`. Xem mục 0.

Áp dụng cho mọi file tài liệu học tiếng Anh trong repo này (do người hoặc Claude tạo).

## 0. Định dạng HTML

- Mọi tài liệu học mới và cũ đều là file `.html` (UTF-8, `lang="vi"`). Không tạo file `.md` mới ngoài ba ngoại lệ: `CLAUDE.md`, `README.md` (gốc repo) và `docs/RULES.md`, giữ Markdown để xem trên GitHub và để Claude Code đọc.
- Dùng chung stylesheet `docs/assets/style.css`, nhúng bằng đường dẫn tương đối (ví dụ `../assets/style.css`). Không viết CSS inline trong từng file (riêng SVG sơ đồ dùng class có sẵn trong stylesheet).
- Chỉ hiển thị chế độ sáng (light mode). Không viết `prefers-color-scheme: dark` hay màu riêng cho dark mode.
- Khung chuẩn của một file (xem mẫu trong `docs/templates/`):

```html
<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Tiêu đề</title>
  <meta name="doc:type" content="grammar">
  <meta name="doc:level" content="B1">
  <meta name="doc:created" content="2026-10-15">
  <meta name="doc:updated" content="2026-10-15">
  <meta name="doc:status" content="active">
  <meta name="doc:tags" content="tag1, tag2">
  <link rel="stylesheet" href="../assets/style.css">
</head>
<body>
<main>
  <h1>Tiêu đề</h1>
  <p class="doc-meta">grammar · B1 · active · updated 2026-10-15</p>
  ...
</main>
</body>
</html>
```

- Dùng thẻ ngữ nghĩa: `h1`/`h2`/`h3`, `p`, `ul`/`ol`, `table` (có `thead`/`tbody`), `pre > code class="language-text"`, `blockquote`. Không dùng `div` thay cho các thẻ này.
- `index.html` ở gốc repo là trang chủ cho GitHub Pages (kèm `.nojekyll`). Thêm hoặc đổi tên tài liệu thì cập nhật cả `index.html` và `README.md`.
- Sơ đồ (timeline, flowchart) vẽ bằng SVG inline, tham khảo `docs/grammar/08-common-tenses.html`.
- Liên kết nội bộ trỏ tới `.html` (riêng `README.md` và `RULES.md` trỏ tới `.md`). Khi người dùng đưa Markdown, chuyển sang HTML rồi xóa bản `.md`.

## 1. Cấu trúc thư mục

```
english/
├── CLAUDE.md                 # trỏ tới docs/RULES.md
├── README.md                 # mục lục + tiến độ
└── docs/
    ├── RULES.md              # file này (Markdown, ngoại lệ)
    ├── assets/style.css      # stylesheet dùng chung
    ├── roadmap.html            # lộ trình tổng
    ├── templates/            # mẫu tài liệu
    ├── 00-foundation/        # GĐ 0: sửa nền (B1 thấp)
    ├── 01-consolidation/     # GĐ 1: vững B1
    ├── 02-upper-intermediate/# GĐ 2: B1+ → B2
    ├── 03-work-english/      # GĐ 3: B2, tiếng Anh công việc
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

- Đuôi `.html`. Chữ thường, ngăn cách bằng dấu gạch ngang (`kebab-case`), không dấu tiếng Việt, không khoảng trắng.
- Tài liệu theo thứ tự có tiền tố số hai chữ số: `01-present-simple.html`.
- Tài liệu theo ngày có tiền tố ISO: `2026-10-15-sample-test-1.html`.
- Một file một chủ đề. Nếu quá 400 dòng thì tách ra.

## 3. Metadata bắt buộc

Metadata nằm trong `<head>` (thay cho front matter YAML cũ), và lặp lại ở dòng `<p class="doc-meta">` ngay dưới `h1`:

```html
<title>&lt;tiêu đề&gt;</title>
<meta name="doc:type" content="grammar | vocabulary | listening | reading | writing | speaking | log | roadmap | resource">
<meta name="doc:level" content="A1 | A2 | B1 | B2 | B2-work">
<meta name="doc:created" content="YYYY-MM-DD">
<meta name="doc:updated" content="YYYY-MM-DD">
<meta name="doc:status" content="draft | active | done | archived">
<meta name="doc:tags" content="tag1, tag2">
```

`RULES.md` và `README.md` không cần metadata này.

- Khi sửa nội dung, cập nhật `doc:updated` (cả dòng `doc-meta`).
- Ngày tuyệt đối (YYYY-MM-DD), không dùng "hôm nay", "tuần trước".

## 4. Ngôn ngữ và trình bày

- Giải thích bằng **tiếng Việt**. Ví dụ, câu mẫu, thuật ngữ và từ vựng bằng **tiếng Anh**.
- Mỗi từ vựng mới ghi đủ: từ, loại từ, IPA, nghĩa tiếng Việt, một câu ví dụ, collocation nếu có.
- Mỗi điểm ngữ pháp có: công thức, khi nào dùng, 3 ví dụ, lỗi thường gặp, bài tập ngắn kèm đáp án ở cuối file.
- Dùng một `<h1>` duy nhất (tiêu đề), các mục chính dùng `<h2>`.
- Bảng cho dữ liệu so sánh, danh sách cho các bước. Không viết đoạn văn dài khi bảng hoặc danh sách rõ hơn.
- Code block là `<pre><code class="language-text">`, luôn có class ngôn ngữ.

## 5. Nội dung bắt buộc theo loại

| Loại | Phải có |
|---|---|
| grammar | Công thức, cách dùng, ví dụ, lỗi thường gặp, bài tập + đáp án |
| vocabulary | Bảng từ (từ, loại, IPA, nghĩa, ví dụ), chủ đề, ngày bắt đầu ôn |
| listening / reading | Nguồn, thời lượng, điểm số, câu sai và lý do sai |
| writing | Đề bài, bài viết gốc, bản sửa, lỗi chính, chấm theo tiêu chí trong `schedule.html` (nội dung, bố cục, từ vựng, ngữ pháp) |
| speaking | Đề bài, dàn ý, transcript (nếu ghi âm), lỗi phát âm/ngữ pháp |
| log | Ngày, thời gian học, nội dung, lỗi lặp lại, mục tiêu ngày mai |

## 6. Mục tiêu đo được

Mỗi tài liệu giai đoạn (`00-`, `01-`, `02-`, `03-`) phải mở đầu bằng mục **Mục tiêu** có tiêu chí kiểm tra cụ thể (số từ, điểm test, số phút nói), khớp với `roadmap.html`.

## 7. Liên kết và nguồn

- Liên kết nội bộ dùng đường dẫn tương đối: `<a href="../grammar/01-present-simple.html">Present simple</a>`.
- Mọi tài liệu từ bên ngoài phải ghi nguồn (tên, tác giả hoặc kênh, link). Không chép nguyên văn nội dung có bản quyền (sách, đề Cambridge); chỉ ghi tham chiếu và ghi chú của riêng bạn.
- Thêm file mới thì cập nhật mục lục trong `README.md` và `index.html`.

## 8. Ghi chép tiến độ

- `docs/logs/` giữ nhật ký theo ngày hoặc tuần; mỗi 2 tuần tổng kết lỗi lặp lại.
- Kết quả sample test lưu thành file riêng và thêm một dòng vào bảng tiến độ trong `README.md`.
- Không xóa log cũ; chỉ đánh dấu `status: done`.
- Tài liệu không còn trong lộ trình (ví dụ giáo trình A1 cũ) đánh dấu `status: archived` và ghi banner trỏ tới tài liệu thay thế; không xóa.

## 9. Quy tắc khi Claude tạo tài liệu

1. Đọc `docs/RULES.md` và `docs/roadmap.html` trước khi tạo file.
2. Kiểm tra file cùng chủ đề đã tồn tại chưa; nếu có thì cập nhật thay vì tạo mới.
3. Dùng mẫu trong `docs/templates/` nếu có loại tương ứng.
4. Không bịa số liệu, điểm số hay tên giáo trình; nếu không chắc thì ghi `TODO: xác minh`.
5. Sau khi tạo hoặc sửa, cập nhật `README.md` (mục lục) và trường `updated`.
6. Không commit nếu người dùng chưa yêu cầu.
