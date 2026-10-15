# Task Plan: Hỗ trợ Soạn thảo và Hoàn thiện Báo cáo LaTeX Trợ lý AI Gemini (Hướng A)

## Objective
Hỗ trợ người dùng nghiên cứu tài liệu Google Scholar, xây dựng dàn ý gợi ý (`Plan/draft.md`), phản biện học thuật với vai trò giảng viên chấm bài trên `Plan/content.md` do người dùng tự biên soạn, và hỗ trợ định dạng/chuyển đổi nội dung vào `Main/main.tex` cùng `Main/refs.bib` chuẩn 10 yêu cầu kỹ thuật LaTeX.

## Proposed Actions
1. `Plan/draft.md`: Thu thập các công trình nghiên cứu mới từ Google Scholar về Gemini kèm liên kết trực tiếp mở được theo cú pháp `[CONTENT] [Source X](link)`, thiết lập hệ thống gạch đầu dòng (bullet points) gợi ý các ý trọng tâm giúp người dùng tự biên soạn nội dung đầy đủ.
2. `Plan/content.md` (Phản biện đóng vai Giảng viên): Đọc và thẩm định bài viết do người dùng soạn thảo trong `Plan/content.md`, đóng vai giảng viên chấm bài chỉ ra cụ thể các lỗ hổng lập luận, điểm chưa sâu hoặc chưa chuẩn học thuật để người dùng chỉnh sửa lặp lại.
3. `Main/main.tex` & `Main/refs.bib`: Hỗ trợ người dùng dán và định dạng nội dung đã hoàn thiện vào đúng các vị trí `<...>` (giữ nguyên cấu trúc khung mẫu LaTeX), cập nhật hình ảnh trực quan tại `Main/images/` và khai báo trích dẫn chuẩn vào `Main/refs.bib`.
4. Biên dịch và kiểm tra `Main/main.pdf`: Thực hiện kiểm thử biên dịch, xác minh độ dài nội dung (4–8 trang), bố cục trang, và đối chiếu 10/10 yêu cầu kỹ thuật cùng phụ lục Nhật ký sử dụng AI.

## Verification
- Tất cả liên kết bài báo từ Google Scholar trong `Plan/draft.md` đều mở được và tuân thủ đúng định dạng `[CONTENT] [Source X](link)`.
- Nhận xét phản biện bám sát tiêu chí chấm điểm đề bài CSC00006 và chỉ ra rõ phương hướng khắc phục cho `Plan/content.md`.
- File `Main/main.tex` chỉ cập nhật tại các vị trí `<...>`, bảo toàn toàn vẹn khung mẫu có sẵn.
- File `Main/main.pdf` biên dịch không lỗi, đạt 10/10 tiêu chí kỹ thuật và đáp ứng dung lượng 4–8 trang nội dung.
