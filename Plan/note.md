# Bảng Ghi Nhớ Dữ Liệu Trích Dẫn, Tham Chiếu và Phụ Lục (Plan/note.md)

Tài liệu này tổng hợp toàn bộ các điểm neo kỹ thuật, chú thích chân trang, bảng biểu, hình ảnh, tài liệu tham khảo BibTeX và phụ lục phục vụ việc ráp nối chính xác vào `Main/main.tex` và `Main/refs.bib`.

---

## 1. Chú thích chân trang (`\footnote`, `\footnotemark`, `\footnotetext`)
* **Footnote 1 (Mục 1):** Cuối đoạn giới thiệu ở Mục 1 (`\subsection{Sử dụng Gemini trong các tác vụ hằng ngày}`).
  > `\footnote{Các thử nghiệm và khảo sát trong báo cáo được thực hiện trên phiên bản Gemini Web; cụ thể sử dụng Gemini Flash-Lite 3.5 cho việc hỏi câu hỏi đơn giản, Gemini Flash 3.8 cho tác vụ thông thường và Gemini 4 Argon cho các tác vụ phức tạp như code (thời điểm ghi nhận: tháng 10/2026).}`
* **Footnote 2 (Mục 4):** Đặt ở tiêu đề Bảng 2 (`\caption{...}\footnotemark`) và xuất ra chân trang (`\footnotetext{...}`).
  > `\footnotetext{Thông tin giá và giới hạn được tác giả tra cứu trực tiếp trên giao diện của Gemini~\cite{google-one-pricing} và tài liệu hướng dẫn của Google Support~\cite{google-support-limits}.}`
* **Footnote 3 (Mục 5.2):** Đặt ở phần phân tích nguyên nhân lỗi thiên kiến đồng thuận (sycophancy) do căn chỉnh RLHF.
  > `\footnote{Bản chất lỗi này bắt nguồn từ giai đoạn căn chỉnh học tăng cường từ phản hồi con người (RLHF), khiến mô hình có xu hướng làm hài lòng con người theo cơ chế phần thưởng đã được học~\cite{casper2023open}.}`
* **Mục đích kỹ thuật:** Đáp ứng yêu cầu **[YC8]** (ít nhất 1 chú thích chân trang).

---

## 2. Danh mục Bảng Biểu (`table`, `\caption`, `\label`)

### Bảng 1: Các cột mốc phát triển chính của Google Gemini
* **Vị trí:** Mục 2 (`\section{Nguồn gốc}`).
* **Nhãn (`\label`):** `\label{tab:mocs}`.
* **Tham chiếu trong văn bản:** `Bảng~\ref{tab:mocs} tóm tắt các cột mốc phát triển chính...`
* **Dữ liệu bảng:**
  * 12/2023: Ra mắt Gemini 1.0 với 3 phiên bản Nano, Pro, Ultra; mô hình đa phương thức nguyên bản đầu tiên vượt qua chuyên gia con người trên benchmark MMLU~\cite{team2023gemini}.
  * 02--05/2024: Ra mắt Gemini 1.5 Pro với cửa sổ ngữ cảnh kỷ lục 1 triệu tokens~\cite{team2024gemini}~\cite{google-gemini-15-pro}; sau đó bổ sung phiên bản Gemini 1.5 Flash tối ưu tốc độ và chi phí tính toán~\cite{google-gemini-15-flash-debut}.
  * 11/2024: Ra mắt Gemini 2.0 Flash, mở đầu kỷ nguyên Agent với khả năng tự thực thi tác vụ nhiều bước, hỗ trợ input/output đa phương tiện và tính năng Deep Research~\cite{google-gemini-2-agent}.
  * 02--03/2025: Công bố Gemini 2.0 Pro, Gemini 2.0 Flash-Lite~\cite{google-gemini-2-updates-feb2025}; tiếp nối là Gemini 2.5 Pro với khả năng suy nghĩ (thinking process) trước khi trả lời~\cite{comanici2025gemini}~\cite{google-gemini-25-thinking-mar2025}.
  * 05--06/2025: Mở rộng họ mô hình với Gemini 2.5 Flash, Gemini 2.5 Flash-Lite và ra mắt công cụ dòng lệnh mã nguồn mở Gemini CLI.
  * 11--12/2025: Ra mắt Gemini 3 Pro với tư duy suy nghĩ sâu (Deep Think), đồng thời giới thiệu nền tảng tác tử tự hành Antigravity và phiên bản Gemini 3 Flash~\cite{google-gemini-3}.
  * 02--05/2026: Ra mắt Gemini 3.1 Pro với năng lực xử lý chuyên sâu vượt trội; giới thiệu trợ lý chủ động Gemini Spark, mô hình đa phương thức sinh video Gemini Omni, Gemini 3.5 Flash và Antigravity 2.0~\cite{google-spark-omni}.
  * 07/2026: Phát hành Gemini 3.6 Flash, Gemini 3.5 Flash-Lite và Gemini 3.5 Flash-Lite Cyber chuyên dụng cho an toàn thông tin.
  * 09--10/2026: Ra mắt kiến trúc thế hệ mới Gemini 4 Argon, tăng cường tối đa năng lực lập trình và khả năng đối thoại kỹ thuật chuyên sâu~\cite{google-gemini-4-argon}.

### Bảng 2: So sánh gói miễn phí và trả phí của Gemini Web
* **Vị trí:** Mục 4 (`\section{Tính năng và các gói sử dụng}`).
* **Nhãn (`\label`):** `\label{tab:goi}`.
* **Tham chiếu trong văn bản:** `Bảng~\ref{tab:goi} so sánh chi tiết giữa gói miễn phí và trả phí...`
* **Tiêu chí so sánh:** Giá/tháng, Mô hình khả dụng, Cửa sổ ngữ cảnh (Context Window), Giới hạn đầu ra (Output Limit), Tính năng tích hợp Google Workspace.
* **Thời điểm tra cứu:** 15/10/2026 theo nguồn chính thức~\cite{google-one-pricing,google-support-limits}.

### Bảng 3 (Phụ lục): Bảng Nhật ký sử dụng AI
* **Vị trí:** Phụ lục A (`\appendix \section{Nhật ký sử dụng AI}`).
* **Cấu trúc:** 3 cột (`Prompt / Link hội thoại`, `AI giúp phần nào`, `Mình đã sửa lại gì`) gồm 6 hàng ghi nhận trung thực.

---

## 3. Danh mục Hình Ảnh Minh Chứng Thực Tế (`figure`, `\includegraphics`)

| Nhãn (`\label`) | Tên file ảnh | Vị trí / Mục | Nội dung minh chứng | Link hội thoại gốc |
| :--- | :--- | :--- | :--- | :--- |
| `\label{fig:tot}` | `anh1.png` | Mục 5 | Gemini làm tốt: Phân tích và chứng minh thuật toán/định lý Toán học rõ ràng từng bước. | [https://share.gemini.google/t2gbXH9W8Y2z](https://share.gemini.google/t2gbXH9W8Y2z) |
| `\label{fig:sai_sycophancy}` | `anh2.png` | Mục 5 & 6.1 | Gemini trả lời sai do ảo giác đồng thuận (sycophancy): Bị dẫn dắt bởi tiền đề sai của người dùng. | [https://share.gemini.google/0lwOt5oaqwR5](https://share.gemini.google/0lwOt5oaqwR5) |
| `\label{fig:sai_link}` | `anh3.png` | Mục 5 & 6.1 | Gemini bịa đường dẫn (link hallucination): Cung cấp các URL không tồn tại. | [https://share.gemini.google/iy4SQsG7k5Gm](https://share.gemini.google/iy4SQsG7k5Gm) |

* **Mục đích kỹ thuật:** Đáp ứng yêu cầu **[YC6]** (ảnh chụp màn hình thật) và **[YC8]** (tham chiếu chéo qua `Hình~\ref{fig:tot}`, `Hình~\ref{fig:sai_sycophancy}`, `Hình~\ref{fig:sai_link}`).

---

## 4. Công Thức Toán Học (`equation`, `\eqref`) và Đánh Số `(1)`, `(2)`

### Lưu ý quan trọng từ mã nguồn `main.tex`:
Toàn bộ mục `\subsection{Đoán từ tiếp theo}` và 2 khối công thức này **đã được định nghĩa sẵn trong khung mã nguồn mẫu `Main/main.tex`** (dòng 230--245, nằm ngoài thẻ `<...>`).
Khi trình biên dịch LaTeX chạy:
* Môi trường `\begin{equation} ... \end{equation}` tự động đánh số thứ tự **(1)** và **(2)** hiển thị ngay bên phải công thức trên trang in PDF.
* Lệnh `\eqref{eq:lm}` trong câu dẫn sẽ tự động xuất ra chuỗi **(1)** có liên kết bấm được.
* Do tuân thủ nghiêm ngặt quy tắc *"chỉ thay thế các thẻ `<...>`"*, phần công thức này không cần viết lại mã mà giữ nguyên cấu trúc mẫu đã được thiết lập sẵn.

### Chi tiết 2 công thức:
1. **Công thức (1) — Quy tắc nhân xác suất tự hồi quy (Next-Token Prediction):**
   ```latex
   \begin{equation}
     P(w_1, \dots, w_n) = \prod_{t=1}^{n} P(w_t \mid w_1, \dots, w_{t-1}).
     \label{eq:lm}
   \end{equation}
   ```
   * Tham chiếu trong bài: `xem~\eqref{eq:lm}:` $\rightarrow$ hiển thị thành `xem (1):`.

2. **Công thức (2) — Hàm phân phối xác suất Softmax:**
   ```latex
   \begin{equation}
     P(w_t = i \mid \cdot) = \frac{e^{z_i}}{\sum_{j=1}^{|V|} e^{z_j}},
     \label{eq:softmax}
   \end{equation}
   ```
   * Tự động được đánh số **(2)** ở lề phải, giải thích rõ $z_i$ là logit và $|V|$ là kích thước bộ từ vựng.
   * Dẫn chứng kiến trúc nền tảng: `Transformer~\cite{vaswani2017}`.
   * Mục đích kỹ thuật: Đáp ứng hoàn hảo yêu cầu **[YC7]** (công thức toán đánh số) và **[YC8]** (tham chiếu chéo qua `\eqref`).

---

## 5. Danh Mục Tài Liệu Tham Khảo BibTeX Hoàn Chỉnh (`refs.bib`)

Dưới đây là 8 mục BibTeX chuẩn đã được đối chiếu kiểm tra thực tế:

```bibtex
% 1. Kiến trúc Transformer kinh điển
@inproceedings{vaswani2017,
  title     = {Attention Is All You Need},
  author    = {Vaswani, Ashish and Shazeer, Noam and Parmar, Niki and
               Uszkoreit, Jakob and Jones, Llion and Gomez, Aidan N. and
               Kaiser, {\L}ukasz and Polosukhin, Illia},
  booktitle = {Advances in Neural Information Processing Systems},
  volume    = {30},
  year      = {2017},
  note      = {\url{https://arxiv.org/abs/1706.03762}}
}

% 2. Báo cáo kỹ thuật Gemini 1.0 (Google Scholar / arXiv)
@article{team2023gemini,
  title   = {Gemini: A Family of Highly Capable Multimodal Models},
  author  = {{Gemini Team, Google}},
  journal = {arXiv preprint arXiv:2312.11805},
  year    = {2023},
  note    = {\url{https://arxiv.org/abs/2312.11805}}
}

% 3. Báo cáo kỹ thuật Gemini 1.5 (Google Scholar / arXiv)
@article{team2024gemini,
  title   = {Gemini 1.5: Unlocking Multimodal Understanding Across Millions of Tokens of Context},
  author  = {{Gemini Team, Google}},
  journal = {arXiv preprint arXiv:2403.05530},
  year    = {2024},
  note    = {\url{https://arxiv.org/abs/2403.05530}}
}

% 4. Báo cáo kỹ thuật Gemini 2.5 (Google Scholar / arXiv)
@article{comanici2025gemini,
  title   = {Gemini 2.5: Pushing the Frontier with Advanced Reasoning, Multimodality, Long Context, and Next Generation Agentic Capabilities},
  author  = {Comanici, Gheorghe and others},
  journal = {arXiv preprint arXiv:2507.06261},
  year    = {2025},
  note    = {\url{https://arxiv.org/abs/2507.06261}}
}

% 5. Nghiên cứu về hạn chế căn chỉnh RLHF (Google Scholar / arXiv)
@article{casper2023open,
  title   = {Open Problems and Fundamental Limitations of Reinforcement Learning from Human Feedback},
  author  = {Casper, Stephen and Davies, Xander and Shi, Claudia and Gilbert, Thomas Krendl and Scheurer, J{\'e}r{\'e}my and Rando, Javier and Freedman, Rachel and Korbak, Tomasz and Lindner, David and Freire, Pedro and others},
  journal = {arXiv preprint arXiv:2307.15217},
  year    = {2023},
  note    = {\url{https://arxiv.org/abs/2307.15217}}
}

% 6. Khảo sát về Hallucination trong LLM (Google Scholar / arXiv)
@article{tonmoy2024comprehensive,
  title   = {A Comprehensive Survey of Hallucination Mitigation Techniques in Large Language Models},
  author  = {Tonmoy, S. M. Towhidul Islam and Zaman, S. M. Mehedi and Jain, Vinija and Rani, Anku and Rawte, Vipula and Chadha, Aman and Das, Amitava},
  journal = {arXiv preprint arXiv:2401.01313},
  year    = {2024},
  note    = {\url{https://arxiv.org/abs/2401.01313}}
}

% 6. Nghiên cứu khảo sát về AI trong Giáo dục đại học (Google Scholar / arXiv)
@article{ghimire2024generativeaieducationstudy,
  title   = {Generative {AI} in Education: A Study of Educators' Awareness, Sentiments, and Influencing Factors},
  author  = {Ghimire, Aashish and Prather, James and Edwards, John},
  journal = {arXiv preprint arXiv:2403.15586},
  year    = {2024},
  note    = {\url{https://arxiv.org/abs/2403.15586}}
}

% 7. Tổng quan lịch sử Gemini (Wikipedia)
@misc{wiki-gemini,
  author       = {{Wikipedia}},
  title        = {Google Gemini},
  howpublished = {\url{https://en.wikipedia.org/wiki/Google_Gemini}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 8. Công bố Gemini 1.5 Pro (Google Blog)
@misc{google-gemini-15-pro,
  author       = {Sundar Pichai and Demis Hassabis},
  title        = {Our next-generation model: Gemini 1.5},
  howpublished = {\url{https://blog.google/innovation-and-ai/products/google-gemini-next-generation-model-february-2024/}},
  year         = {2024},
  note         = {Truy cập ngày 15/10/2026}
}

% 9. Ra mắt Gemini 1.5 Flash và Gemma (Google Blog)
@misc{google-gemini-15-flash-debut,
  author       = {{Google for Developers}},
  title        = {Gemini 1.5 Pro Updates, 1.5 Flash Debut and 2 New Gemma Models},
  howpublished = {\url{https://blog.google/innovation-and-ai/technology/developers-tools/gemini-gemma-developer-updates-may-2024/}},
  year         = {2024},
  note         = {Truy cập ngày 15/10/2026}
}

% 10. Công bố kỷ nguyên Agent với Gemini 2.0 (Google Blog)
@misc{google-gemini-2-agent,
  author       = {Demis Hassabis},
  title        = {Introducing Gemini 2.0: our new AI model for the agentic era},
  howpublished = {\url{https://blog.google/innovation-and-ai/models-and-research/google-deepmind/google-gemini-ai-update-december-2024/}},
  year         = {2024},
  note         = {Truy cập ngày 15/10/2026}
}

% 11. Cập nhật dòng mô hình Gemini 2.0 tháng 2/2025 (Google Blog)
@misc{google-gemini-2-updates-feb2025,
  author       = {{Google DeepMind}},
  title        = {Gemini 2.0 Model Updates: 2.0 Flash, Flash-Lite, Pro Experimental},
  howpublished = {\url{https://blog.google/innovation-and-ai/models-and-research/google-deepmind/gemini-model-updates-february-2025/}},
  year         = {2025},
  note         = {Truy cập ngày 15/10/2026}
}

% 12. Công bố tính năng Thinking của Gemini 2.5 tháng 3/2025 (Google Blog)
@misc{google-gemini-25-thinking-mar2025,
  author       = {{Google DeepMind}},
  title        = {Gemini 2.5: Our Newest Gemini Model with Thinking},
  howpublished = {\url{https://blog.google/innovation-and-ai/models-and-research/google-deepmind/gemini-model-thinking-updates-march-2025/}},
  year         = {2025},
  note         = {Truy cập ngày 15/10/2026}
}

% 11. Ra mắt công cụ Gemini CLI mã nguồn mở (Google Blog)
@misc{google-gemini-cli,
  author       = {{Google for Developers}},
  title        = {Google Announces Gemini {CLI}: Your Open-Source {AI} Agent},
  howpublished = {\url{https://blog.google/innovation-and-ai/technology/developers-tools/introducing-gemini-cli-open-source-ai-agent/}},
  year         = {2025},
  note         = {Truy cập ngày 15/10/2026}
}

% 12. Công bố Gemini 3 (Google Blog)
@misc{google-gemini-3,
  author       = {{Google DeepMind}},
  title        = {A new era of intelligence with Gemini 3},
  howpublished = {\url{https://blog.google/products-and-platforms/products/gemini/gemini-3/}},
  year         = {2025},
  note         = {Truy cập ngày 15/10/2026}
}

% 13. Công bố bài phát biểu Sundar Pichai tại Google I/O 2026
@misc{google-spark-omni,
  author       = {Sundar Pichai},
  title        = {Google {I/O} 2026: Sundar Pichai's Opening Keynote},
  howpublished = {\url{https://blog.google/intl/en-in/company-news/technology/sundar-pichai-io-2026/}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 14. Ra mắt 3 mô hình Gemini mới tháng 7/2026 (TechCrunch)
@misc{techcrunch-gemini-models-2026,
  author       = {Rebecca Bellan},
  title        = {Google Releases Three New Gemini Models --- But No 3.5 Pro},
  howpublished = {\url{https://techcrunch.com/2026/07/21/google-releases-three-new-gemini-models-but-no-3-5-pro/}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 15. Công bố kiến trúc thế hệ mới Gemini 4 Argon (Google DeepMind)
@misc{google-gemini-4-argon,
  author       = {{Google DeepMind}},
  title        = {Introducing Gemini 4 Argon},
  howpublished = {\url{https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-4-argon/}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 16. Bảng giá và thông số gói Google One AI Pro
@misc{google-one-pricing,
  author       = {{Google}},
  title        = {Google One {AI} Pro Plan Overview},
  howpublished = {\url{https://one.google.com/ai}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 17. Giới hạn kỹ thuật từ tài liệu hỗ trợ Google Support
@misc{google-support-limits,
  author       = {{Google Support}},
  title        = {Các bản nâng cấp và hạn mức sử dụng của Các ứng dụng Gemini dành cho người đăng ký Google AI},
  howpublished = {\url{https://support.google.com/gemini/answer/16275805}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 18. Bài báo tin tức về quyền riêng tư và tranh cãi nghiên cứu (CafeF)
@misc{cafef-openai-dispute,
  author       = {{CafeF}},
  title        = {OpenAI tuyên bố 10.000 {AI} Agent của họ vừa giải được bài toán thế kỷ, giáo sư toán học lên tiếng: ``Họ đang cướp công của tôi''},
  howpublished = {\url{https://cafef.vn/openai-tuyen-bo-10000-ai-agent-cua-ho-vua-giai-duoc-bai-toan-the-ky-giao-su-toan-hoc-len-tieng-ho-dang-cuop-cong-cua-toi-188260910072500287.chn}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}

% 19. Chỉ đạo pháp lý về liêm chính học thuật khi sử dụng AI trong giáo dục
@misc{thuvienphapluat-ai-giaoduc,
  author       = {{Thư Viện Pháp Luật}},
  title        = {Từ 15/8, sử dụng {AI} trong giáo dục phải bảo đảm liêm chính học thuật},
  howpublished = {\url{https://thuvienphapluat.vn/chinh-sach-phap-luat-moi/vn/ho-tro-phap-luat/chi-dao-dieu-hanh/4444/tu-15-8-su-dung-ai-trong-giao-duc-phai-bao-dam-liem-chinh-hoc-thuat}},
  year         = {2025},
  note         = {Truy cập ngày 15/10/2026}
}
```

---

## 6. Bảng Nhật Ký Sử Dụng AI (Chi tiết cho Phụ lục A)

| Prompt / Link hội thoại | AI giúp phần nào | Mình đã sửa lại gì |
| :--- | :--- | :--- |
| `https://share.gemini.google/MXGnNn9FVFtC` | Hỗ trợ soạn prompt ràng buộc ban đầu, thiết lập nguyên tắc nghiêm ngặt để AI chỉ lập kế hoạch và không can thiệp viết hộ. | Bổ sung thêm các tiêu chí phân định rõ vai trò và yêu cầu phê duyệt kế hoạch trước khi làm. |
| `Dự án Antigravity IDE (15/10/2026)` | Gợi ý cấu trúc dàn ý bài báo cáo (`draft.md`), hỗ trợ sửa lỗi chính tả và trau chuốt văn phong học thuật (`polish_content.md`), giải thích sâu cơ chế Transformer và hỗ trợ chuyển đổi mã nguồn $\text{\LaTeX}$ chuẩn. | Tự tay biên soạn toàn bộ nội dung chi tiết trong `content.md`, trực tiếp tìm kiếm và thẩm định các mã trích dẫn BibTeX từ Google Scholar, tự giải lại bài toán kiểm chứng. |
| `https://share.gemini.google/XhbafID6cTah` | Khảo sát các loại token trong thực tế của hệ thống đa phương thức. | Chọn lọc và phân loại chính xác các nhóm token (văn bản, thị giác, âm thanh) phù hợp với bản chất native multimodal của Gemini. |
| `https://share.gemini.google/t2gbXH9W8Y2z` | Tình huống thử nghiệm 1: Nhờ giải thích chi tiết và trực quan từng bước chứng minh một định lý toán học. | Tự kiểm chứng tính chính xác của các bước lập luận, chụp lại màn hình kết quả thực tế để làm minh chứng `Hình 1`. |
| `https://share.gemini.google/0lwOt5oaqwR5` | Tình huống thử nghiệm 2: Đặt câu hỏi có tiền đề giả định sai về sự tồn tại của tính năng mô hình. | Phát hiện hiện tượng ảo giác đồng thuận (sycophancy) khi mô hình tin theo lời người dùng, chụp lại màn hình làm minh chứng `Hình 2`. |
| `https://share.gemini.google/iy4SQsG7k5Gm` | Tình huống thử nghiệm 3: Yêu cầu cung cấp tài liệu tham khảo và nguồn liên kết kiểm chứng. | Phát hiện mô hình tự sinh ra các đường dẫn không tồn tại (link ảo giác), chụp lại màn hình làm minh chứng `Hình 3`. |
