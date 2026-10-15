# Dàn ý Gợi ý Báo cáo Bài tập 1: Chân dung Trợ lý AI Google Gemini (Hướng A)

> **Tài liệu tham khảo học thuật chính thức (Google Scholar / arXiv) được dẫn theo quy tắc:**  
> `[Main content] [Google Scholar Link](link)`

---

## 1. Giới thiệu (Introduction)
* **Lý do lựa chọn Google Gemini:**
  * Gemini là hệ sinh thái trợ lý AI đa phương thức (native multimodal) tiên tiến do Google phát triển, tích hợp sâu vào hệ sinh thái Google (Gmail, Docs, Drive, Android, Google AI Studio).
  * Khả năng xử lý ngữ cảnh cực lớn (từ 1 triệu đến 2 triệu tokens) và khả năng suy luận logic, hỗ trợ học tập vượt trội ở các môn đại cương (Toán, Lập trình, Ngoại ngữ).
* **Mục đích sử dụng thực tế hằng ngày:**
  * Giải thích các khái niệm kỹ thuật phức tạp trong ngành Trí tuệ Nhân tạo và Khoa học Máy tính.
  * Hỗ trợ tìm kiếm, tóm tắt tài liệu học thuật và phân tích giáo trình, bài giảng dạng PDF.
  * Hỗ trợ lập trình (debug, gợi ý thuật toán, giải thích luồng code Python/C++).
  * Luyện tập phản xạ ngoại ngữ và soạn thảo văn bản học thuật.
* **Gợi ý chú thích chân trang (`\footnote`):**
  * Ghi rõ phiên bản ứng dụng Gemini và nền tảng đang sử dụng (ví dụ: Gemini Advanced phiên bản web và ứng dụng di động tính đến tháng 10/2026).

---

## 2. Nguồn gốc và Lịch sử Phát triển (Origin & Key Milestones)
* **Chủ thể nghiên cứu và phát triển:**
  * Phát triển bởi Google DeepMind và Google Research, đứng đầu bởi các chuyên gia AI hàng đầu thế giới (Demis Hassabis, Jeff Dean, Koray Kavukcuoglu).
* **Các cột mốc phát triển chính (dùng để lập Bảng cột mốc trong LaTeX):**
  * **Tháng 12/2023:** Ra mắt Gemini 1.0 với 3 phiên bản Nano, Pro, Ultra; là mô hình đa phương thức nguyên bản đầu tiên vượt qua các chuyên gia con người trên bài kiểm tra MMLU.
    * [Gemini was developed from the ground up to natively reason across text, code, images, audio, and video, introducing Gemini Ultra, Pro, and Nano architectures.] [Google Scholar Link](https://arxiv.org/abs/2312.11805)
  * **Tháng 02–03/2024:** Ra mắt Gemini 1.5 với kiến trúc Mixture-of-Experts (MoE) thưa và cửa sổ ngữ cảnh kỷ lục 1 triệu đến 2 triệu tokens.
    * [Gemini 1.5 introduces a sparse Mixture-of-Experts (MoE) architecture scaling multimodal context up to millions of tokens with near-perfect retrieval recall.] [Google Scholar Link](https://arxiv.org/abs/2403.05530)
  * **Năm 2025:** Ra mắt thế hệ Gemini 2.0 và Gemini 2.5 với năng lực suy luận sâu (Deep Think), khả năng tương tác thời gian thực (real-time multimodal streaming) và năng lực điều khiển agent tự động.
    * [Gemini 2.5 pushes frontier multimodal reasoning, long-horizon coding, and next-generation agentic capabilities with dedicated thinking processes.] [Google Scholar Link](https://arxiv.org/abs/2507.06261)
  * **Năm 2026:** Ra mắt thế hệ Gemini 3.1 Pro và Gemini 3.8 Flash tối ưu hóa tốc độ và tư duy suy luận phức tạp cho các tác vụ kỹ thuật chuyên sâu, cùng kiến trúc nền tảng 4.0 Argon.

---

## 3. Cách hoạt động ở mức khái niệm (Conceptual Mechanism)

### 3.1. Mô hình ngôn ngữ lớn (LLM) và Token là gì?
* **Khái niệm LLM:**
  * Là mạng nơ-ron học sâu (Deep Neural Network) với hàng chục đến hàng trăm tỷ tham số, được huấn luyện trên lượng dữ liệu khổng lồ (văn bản, mã nguồn, hình ảnh, âm thanh) nhằm hiểu và tạo lập ngôn ngữ tự nhiên.
* **Khái niệm Token:**
  * Đơn vị cơ bản mà mô hình sử dụng để biểu diễn ngôn ngữ (có thể là một từ, một phần của từ, một dấu câu hoặc ký tự đặc biệt).
  * Quy đổi thông thường: 1.000 tokens xấp xỉ 750 từ tiếng Anh (hoặc khoảng 1.500 ký tự tiếng Việt có dấu).
  * Bộ từ vựng $|V|$ (Vocabulary Size) chứa danh mục hữu hạn các token mà mô hình đã học.

### 3.2. Dự đoán từ tiếp theo (Next-Token Prediction) và Công thức Toán học
* **Bản chất xác suất:**
  * Mô hình sinh văn bản tự hồi quy (autoregressive) bằng cách dự đoán phân phối xác suất của token tiếp theo $w_t$ dựa trên toàn bộ chuỗi ngữ cảnh các token đã xuất hiện trước đó $w_1, \dots, w_{t-1}$.
  * Công thức xác suất tích chuỗi:
    $$P(w_1, w_2, \dots, w_n) = \prod_{t=1}^{n} P(w_t \mid w_1, \dots, w_{t-1})$$
* **Hàm kích hoạt Softmax:**
  * Điểm số (logits) $z_i$ do mạng nơ-ron tính toán cho từng token $i \in \{1, \dots, |V|\}$ được chuyển hóa thành xác suất hợp lệ qua hàm softmax:
    $$P(w_t = i \mid \cdot) = \frac{e^{z_i}}{\sum_{j=1}^{|V|} e^{z_j}}$$
* **Nền tảng kiến trúc Transformer và Cơ chế Tự chú ý (Self-Attention):**
  * Mô hình dựa trên kiến trúc Transformer với cơ chế Multi-Head Attention, cho phép tính toán mối liên hệ phụ thuộc xa giữa các token bất kể khoảng cách trong văn bản.
    * [The Transformer model relies entirely on an attention mechanism to draw global dependencies between input and output without using recurrent neural networks.] [Google Scholar Link](https://arxiv.org/abs/1706.03762)
* **Đặc trưng riêng biệt của Gemini: Native Multimodality & Sparse MoE:**
  * Gemini không ghép nối các mô hình thị giác/âm thanh rời rạc mà đưa trực tiếp các dạng dữ liệu vào không gian biểu diễn chung ngay từ giai đoạn tiền huấn luyện.
  * Kiến trúc Mixture-of-Experts (MoE) kích hoạt có chọn lọc các chuyên gia nơ-ron chuyên biệt cho từng token, tối ưu hóa chi phí tính toán và tăng tốc độ xử lý.

---

## 4. Tính năng và Các gói Sử dụng (Features & Pricing Plans)
* **Các tính năng nổi bật của Gemini:**
  * **Đa phương thức tự nhiên:** Phân tích hình ảnh, đọc biểu đồ, nghe hiểu âm thanh, phân tích video và tài liệu PDF dung lượng lớn trong cùng một lượt hỏi.
  * **Khả năng suy luận logic & Coding:** Sinh code, giải thích thuật toán, refactor mã nguồn và kiểm thử tự động trên nhiều ngôn ngữ (Python, C++, Java, Web).
  * **Cửa sổ ngữ cảnh khổng lồ:** Cho phép người dùng tải lên toàn bộ một cuốn sách giáo trình hoặc hàng ngàn dòng code để truy vấn thông tin chính xác.
  * **Tích hợp sâu hệ sinh thái Google:** Kết nối trực tiếp với Google Drive, Docs, Gmail, YouTube, Google Maps thông qua các tiện ích mở rộng (Extensions).
* **Bảng so sánh gói dịch vụ (Cần ghi rõ ngày tra cứu theo yêu cầu đề bài):**
  * **Gói Miễn phí (Gemini Free):**
    * Chi phí: 0 VNĐ / tháng.
    * Mô hình sử dụng: Gemini Flash (tốc độ cao, tối ưu cho tác vụ thường nhật).
    * Giới hạn: Cửa sổ ngữ cảnh tiêu chuẩn, tốc độ xử lý cao điểm có thể bị điều tiết, không đi kèm dung lượng lưu trữ đám mây 2TB.
  * **Gói Trả phí (Google One AI Premium / Gemini Advanced):**
    * Chi phí: Khoảng 490.000 VNĐ / tháng (hoặc 19.99 USD / tháng).
    * Mô hình sử dụng: Các mô hình Pro / Deep Think đỉnh cao (Gemini Pro, năng lực suy luận phức tạp bậc nhất).
    * Đặc quyền: Cửa sổ ngữ cảnh mở rộng tối đa (1–2 triệu tokens), ưu tiên tài nguyên tính toán, tích hợp trực tiếp Gemini vào Google Docs, Gmail, Slides và kèm 2TB lưu trữ Google Drive.

---

## 5. Trải nghiệm Thực tế của Người dùng (Personal Experience & Analysis)
* **Hướng dẫn chuẩn bị minh chứng hình ảnh (ít nhất 2 ảnh chụp màn hình thật):**
  * **Hình 1 (`anh1.png` - Ví dụ công cụ làm tốt):**
    * *Tình huống:* Nhờ Gemini giải thích một thuật toán hoặc định lý trong chương trình học (ví dụ: giải thích thuật toán A* / Gradient Descent / phép nhân ma trận trong Đại số tuyến tính, hoặc viết hàm đệ quy bằng Python kèm giải thích trực quan).
    * *Đánh giá:* Mô hình phân tích đúng bản chất, lập luận mạch lạc, mã nguồn chạy chuẩn xác và chú thích dễ hiểu.
  * **Hình 2 (`anh2.png` - Ví dụ công cụ trả lời sai / ảo giác / "bịa"):**
    * *Tình huống:* Đặt câu hỏi bẫy với tiền đề sai (ví dụ: hỏi về ngày mất của một nhà toán học còn sống, hoặc hỏi về một định lý giả định không có thật, hoặc bài toán đố mẹo chữ tiếng Việt phức tạp).
    * *Đánh giá:* Mô hình bị cuốn theo tiền đề sai, tự bịa ra công thức/sự kiện hoặc đưa ra lời giải thích nghe rất thuyết phục nhưng hoàn toàn sai lệch về mặt toán học/thực tế.
* **Nhận xét chuyên sâu:**
  * Phân tích nguyên nhân vì sao mô hình làm tốt (nhờ cơ chế so khớp mẫu dữ liệu lớn và lý luận đa bước).
  * Phân tích nguyên nhân sai sót (do giới hạn của việc tối ưu hóa xác suất từ ngữ thay vì thực sự "hiểu" chân lý luận lý, thiếu cơ sở tri thức cứng nếu không tra cứu thực tế).

---

## 6. Hạn chế và Sử dụng AI có Trách nhiệm (Limitations & Responsible AI)
* **Hiện tượng ảo giác (Hallucination):**
  * Mô hình sinh ra các thông tin nghe rất học thuật và đáng tin cậy nhưng hoàn toàn sai sự thật (bịa tài liệu tham khảo, bịa công thức, suy diễn sai).
  * Phương pháp giảm thiểu: Sử dụng cơ chế RAG (Retrieval-Augmented Generation), yêu cầu trích dẫn nguồn, áp dụng quy trình kiểm chứng chéo (fact-checking).
    * [Hallucination in large language models poses major reliability challenges, requiring mitigation through prompt engineering, retrieval-augmented grounding, and verification techniques.] [Google Scholar Link](https://arxiv.org/abs/2401.01313)
* **Vấn đề Quyền riêng tư và Bảo mật Dữ liệu (Data Privacy):**
  * Dữ liệu người dùng nhập vào có thể được sử dụng để tái huấn luyện mô hình nếu không tắt cài đặt chia sẻ lịch sử.
  * Nguy cơ rò rỉ mã nguồn nhạy cảm, thông tin cá nhân hoặc tài liệu nghiên cứu chưa công bố.
* **Quy định sử dụng AI trong môi trường Học thuật:**
  * Giới hạn liêm chính học thuật: Không được nộp bài do AI viết hoàn toàn (đạo văn học thuật), không được xem AI là nguồn chân lý tuyệt đối.
  * AI đóng vai trò người trợ giảng/cố vấn (AI as an Assistant/Tutor), người học phải chịu trách nhiệm 100% về tính đúng đắn của sản phẩm cuối cùng.
    * [The rapid integration of generative AI into education highlights critical challenges around academic integrity, student skill development, and proper institutional policy.] [Google Scholar Link](https://arxiv.org/abs/2403.15586)

---

## 7. Kết luận (Conclusion & Academic Road Ahead)
* **Bài học rút ra từ quá trình nghiên cứu và trải nghiệm:**
  * Gemini là công cụ gia tăng năng suất học tập và nghiên cứu cực kỳ mạnh mẽ nếu biết cách khai thác có phương pháp.
  * Năng lực đặt câu hỏi (Prompting), tư duy phản biện (Critical Thinking) và kỹ năng thẩm định tri thức là những kỹ năng cốt lõi của sinh viên ngành Trí tuệ Nhân tạo.
* **Định hướng sử dụng trong 4 năm đại học:**
  * Xem Gemini là "bạn học cùng bàn" và "trợ giảng 24/7" để giải đáp các khúc mắc kiến thức nền tảng.
  * Áp dụng nguyên tắc: "Học cùng AI, kiểm chứng độc lập, sáng tạo của chính mình".
  * Tuyệt đối không giao phó hoàn toàn bài tập lớn hay báo cáo nghiên cứu cho AI viết hộ.

---

## 8. Phụ lục bắt buộc: Nhật ký sử dụng AI (AI Usage Log)
* Bảng ghi nhận trung thực theo quy định mục 4 của đề bài:
  * **Cột 1 (Prompt / Link):** Ghi rõ các prompt đã dùng (hoặc link chia sẻ cuộc hội thoại).
  * **Cột 2 (AI giúp phần nào):** Gợi ý cấu trúc dàn ý, hướng dẫn cú pháp định dạng bảng và công thức trong LaTeX, rà soát lỗi chính tả.
  * **Cột 3 (Mình đã sửa lại gì):** Tự tay viết lại toàn bộ nội dung trải nghiệm, tự tìm kiếm và đối chiếu tài liệu Google Scholar, tự giải lại công thức toán và kiểm tra mã nguồn.
