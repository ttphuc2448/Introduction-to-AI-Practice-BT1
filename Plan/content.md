# Tóm tắt nội dung
Bài viết này tìm hiểu về công cụ Gemini của Google qua việc tìm hiểu các thông tin cơ bản như nguồn gốc, cách hoạt động, tính năng và các gói sử dụng. Đồng thời thì cũng đưa ra những trải nghiệm thực tế của mình, hạn chế và dùng có trách nhiệm. Cuối cùng, đúc kết lại và đưa ra những kết luận quan trọng về cách mình sử dụng AI trong 4 năm đại học. 

# 1 Giới thiệu

## 1.1 Lý do chọn Gemini
Gemini là mô hình trí tuệ nhân tạo xử lý đa phương thức, hỗ trợ công việc và học tập một các hiệu quả, tích hợp sâu hệ sinh thái Google giúp thuận tiện trong việc làm việc và trò chuyện thời gian thực.
Sự phù hợp của Google Gemini trong công việc và học tập là do việc Gemini có khả năng hiểu và phản hồi các yêu cầu phức tạp, đa dạng, hỗ trợ nhiều ngôn ngữ và định dạng dữ liệu, giúp người dùng dễ dàng tiếp cận và sử dụng. Đồng thời thì giới hạn token không quá ít, có thể trả lời nhanh, đáp ứng nhu cầu của đại đa số người dùng.
Hỗ trợ sinh viên với việc miễn phí một năm Google AI Plus và giảm giá cho sinh viên các gói khác, giúp các bạn có thể dễ dàng tiếp cận hơn.
Đồng thời mình chọn Gemini là do một phần là mình am hiểu nhiều nhất về Gemini do việc sử dụng Gemini trong thời gian dài. 

## 1.2 Sử dụng Gemini trong các tác vụ hằng ngày
Hằng ngày, mình sử dụng Gemini (Chatbot) cho đa số mọi tác vụ như là soạn lịch, hỏi các thông tin thường ngày và sử dụng phiên bản agent (Antigravity) để xây dựng những phần mềm mà mình mong muốn nhằm cải thiện những nhu cầu cơ bản trong cuộc sống của mình.

(Chú thích chân trang: Phiên bản Gemini sử dụng: Gemini 3.8 Flash cho các tác vụ đơn giản, Gemini 4 Argon cho các tác vụ khó)

# 2 Nguồn gốc
Phát triển bởi Google DeepMind và Google Research, đứng đầu bởi các chuyên gia AI hàng đầu thế giới (Demis Hassabis, Jeff Dean, Koray Kavukcuoglu). Bảng 1 tóm tắt các cột mốc chính.

12/2023: Ra mắt Gemini 1.0 với 3 phiên bản Nano, Pro, Ultra; là mô hình đa phương thức nguyên bản đầu tiên vượt qua các chuyên gia con người trên bài kiểm tra MMLU. 
```
@article{team2023gemini,
  title={Gemini: a family of highly capable multimodal models},
  author={Team, Gemini and Anil, Rohan and Borgeaud, Sebastian and Alayrac, Jean-Baptiste and Yu, Jiahui and Soricut, Radu and Schalkwyk, Johan and Dai, Andrew M and Hauth, Anja and Millican, Katie and others},
  journal={arXiv preprint arXiv:2312.11805},
  year={2023}
}
```

02/2024: Ra mắt Gemini 1.5 với kiến trúc Mixture-of-Experts (MoE) thưa và cửa sổ ngữ cảnh kỷ lục 1 triệu đến 2 triệu tokens. 
```
@article{team2024gemini,
  title={Gemini 1.5: Unlocking multimodal understanding across millions of tokens of context},
  author={Team, Gemini and Georgiev, Petko and Lei, Ving Ian and Burnell, Ryan and Bai, Libin and Gulati, Anmol and Tanzer, Garrett and Vincent, Damien and Pan, Zhufeng and Wang, Shibo and others},
  journal={arXiv preprint arXiv:2403.05530},
  year={2024}
}
```

12/2024 - 2025: Ra mắt Gemini 2.0 và Gemini 2.5 với năng lực suy luận sâu (Deep Think), khả năng tương tác thời gian thực (real-time multimodal streaming) và năng lực điều khiển agent tự động. 
```
@article{comanici2025gemini,
  title={Gemini 2.5: Pushing the frontier with advanced reasoning, multimodality, long context, and next generation agentic capabilities},
  author={Comanici, Gheorghe and Bieber, Eric and Schaekermann, Mike and Pasupat, Ice and Sachdeva, Noveen and Dhillon, Inderjit and Blistein, Marcel and Ram, Ori and Zhang, Dan and Rosen, Evan and others},
  journal={arXiv preprint arXiv:2507.06261},
  year={2025}
}
```

11/2025 - 2026: Phát triển Gemini 3, phát triển với kiến trúc thế hệ mới 4 Argon được tối ưu hoá hiệu năng, và tư duy suy luận chuyên sâu cho các tác vụ kỹ thuật. 
```
@misc{google-gemini-official,
  author       = {{Google DeepMind}},
  title        = {Gemini Models: Architecture, Capabilities, and Benchmarks},
  howpublished = {\url{https://deepmind.google/technologies/gemini/}},
  year         = {2026},
  note         = {Truy cập ngày 15/10/2026}
}
```

# 3. Cách hoạt động ở mức khái niệm
## 3.1 Mô hình ngôn ngữ lớn là gì?
Mô hình ngôn ngữ lớn dùng mô hình cấu trúc mạng neuron (Tranformer), hoạt động theo cách dự đoán xác suất từ tiếp theo sẽ xuất hiện chứ không hẳn là có khả năng hiểu. 
Bằng việc cho càng nhiều dữ liệu đầu vào thì mô hình có thể phát triển mạng neuron và điều chỉnh tham số phù hợp giúp mô hình trả lời giống con người và dự đoán tốt hơn.
Ví dụ về một số mô hình LLM:
+ GPT (OpenAI)
+ PaLM (Google)
+ LLaMA (Meta)
+ Claude (Anthropic)
+ Gemini (Google)

## 3.2 Token là gì?
Token là đơn vị cơ bản được sử dụng trong AI. Thường thì một token tương ứng với khoảng 4 kí tự trong tiếng Anh, hoặc khoảng 1.5 kí tự trong tiếng Việt có dấu. Tuy vậy do AI không hiểu chữ nên là các cái chữ sẽ chuyển hết thành vector số và cho vào neuron để tính toán.

Khi sử dụng, ta quan tâm tới hai loại token: 
- Đầu vào / Ngữ cảnh / Context Window: số lượng token mà mô hình có thể ghi nhớ để có thể trả lời. 
- Đầu ra / Output Token: Lượng token cho phép tối đa cho một câu trả lời.

Các loại token phổ biến:
- Text and Symbol Tokens: Dùng cho văn bản, Code, Ký tự đặc biệt, Thẻ cấu trúc prompt
- Vision Tokens: Lưới ảnh tĩnh (ViT patches), Khung hình video qua thời gian
- Audio Tokens: Biểu đồ phổ Mel, Mã nén âm thanh rời rạc.

# 3.3 Đoán từ tiếp theo
Mô hình tính xác suất của một câu w1, w2, . . . , wn bằng cách nhân xác suất của từng
token khi biết các token đứng trước, xem (1):
P (w1, . . . , wn) =
n∏︂
t=1
P (wt | w1, . . . , wt−1). (1)
Xác suất cho từng token tiếp theo thường tính bằng hàm softmax:
P (wt = i | ·) = ezi∑︁
|V |
j=1 ezj
, (2)
trong đó zi là “điểm” mô hình gán cho token i và |V | là kích thước bộ từ vựng. Nền tảng
của các mô hình này là kiến trúc Transformer [5].

```
@article{vaswani2017attention,
  title={Attention is all you need},
  author={Vaswani, Ashish and Shazeer, Noam and Parmar, Niki and Uszkoreit, Jakob and Jones, Llion and Gomez, Aidan N and Kaiser, {\L}ukasz and Polosukhin, Illia},
  journal={Advances in neural information processing systems},
  volume={30},
  year={2017}
}
```

# 4 Tính năng và các gói sử dụng
Gemini cho phép sử dụng nhiều tính năng
- Xử lý đa phương thức: văn bản, hình ảnh, âm thành, nhiều loại file.
- Khả năng suy luận logic
- Code
- Cửa sổ ngữ cảnh lớn: giúp người dùng có thể cung cấp nhiều dữ liệu đầu vào
- Tích hợp sâu hệ sinh thái Google: Google Calendar, Google Docs, Google Sheet, Google Drive.
- Giao diện sử dụng dễ dàng, trực quan, nhiều tính năng nâng cao.
- Tốc độ phản hồi nhanh
- Gemini Spark có khả năng nhìn vào hệ sinh thái google của bản th để có thể dễ dàng trả lời và có khả năng lập lịch, lập kế hoạch một cách tự động mà không phụ thuộc vào máy tính có đang mở hay không.
- Tính năng Agent (Antigravity) cho phép AI có thể "làm" thay vì chỉ có "nói". 

Bảng 2: So sánh gói miễn phí và trả phí của Gemini Web (tra cứu ngày 15/10/2026)
Miễn phí: 
- Giá / tháng: 0
- Mô hình dùng: Gemini Flash-Lite 3.5
- Giới hạn ngữ cảnh: 32.000 token
- Giới hạn đầu ra: 8.192 token

Trả phí:
- Giá / tháng: 489.000 VNĐ / tháng
- Mô hình dùng: Gemini Flash-Lite 3.5, Gemini Flash 3.8, Gemini 3.1 Pro, Gemini 4 Argon.
- Giới hạn ngữ cảnh: 1.000.000 token
- Giới hạn đầu ra: 65.536 token

(nguồn: (note: tui không biết đưa vào latex nhwu thế nào) tra cứu giá trực tiếp trên giao diện của gemini (https://one.google.com/ai?utm_source=gemini&utm_medium=web&utm_campaign=gemini_ail_upsell_zero_state_banner&g1_landing_page=75), thông tin giới hạn: https://support.google.com/gemini/answer/16275805?hl=en)

# 5. Trải nghiệm của mình
Mô hình sử dụng: Gemini Flash-Lite 3.5.
Hình 1 là một ví dụ công cụ làm tốt, còn Hình 2 và 3 là hai lần công cụ trả lời sai hoặc “bịa”

Hình 1: Mô hình phân tích dễ hiểu, chi tiết cho người không biết có thể hiểu rõ từng bước làm.
(đoạn chat: https://share.gemini.google/t2gbXH9W8Y2z)


Hình 2: Mô hình trả lời sai khi mà tin tưởng rằng thông tin của người dùng cung cấp là đúng dù nó không đúng
(Đoạn chat: https://share.gemini.google/0lwOt5oaqwR5)


Hình 3: Mô hình cung cấp các link không tồn tại. (đoạn chat: https://share.gemini.google/iy4SQsG7k5Gm)

Nhận xét: Qua các ví dụ trên ta có thể thấy với các kiến thức rất cơ bản và phổ biến như là một định lý Toán thì mô hình có thể làm tốt nhưng mà đối với các câu hỏi không phổ biến bằng hoặc là người dùng đưa ra một luận điểm sai thì có khả năng mô hình sẽ nghe theo và làm hài lòng người dùng thay vì phản bác, hay là mô hình tạo ra được các đường link không tồn tại, không sử dụng được. 

# 6 Hạn chế và dùng có trách nhiệm.

## 6.1 Hallucination
- Mô hình sinh ra các thông tin nghe rất học thuật và đáng tin cậy nhưng hoàn toàn sai sự thật (bịa tài liệu tham khảo, bịa công thức, suy diễn sai). Chi tiết ví dụ ở Hình 2 (dẫn link về hình 2) và Hình 3 (dẫn link về hình 3).

- Phương pháp giảm thiểu: Phương pháp giảm thiểu: Sử dụng cơ chế RAG (Retrieval-Augmented Generation), yêu cầu trích dẫn nguồn, áp dụng quy trình kiểm chứng chéo (fact-checking)

```
@article{tonmoy2024comprehensive,
  title={A comprehensive survey of hallucination mitigation techniques in large language models},
  author={Tonmoy, SM and Zaman, SM and Jain, Vinija and Rani, Anku and Rawte, Vipula and Chadha, Aman and Das, Amitava},
  journal={arXiv preprint arXiv:2401.01313},
  year={2024}
}
```
## 6.2 Quyền riêng tư dữ liệu
- Dữ liệu người dùng nhập vào có thể được sử dụng để tái huấn luyện mô hình nếu không tắt cài đặt chia sẻ lịch sử.

- Nguy cơ rò rỉ mã nguồn nhạy cảm, thông tin cá nhân hoặc tài liệu nghiên cứu chưa công bố.
+ Ví dụ: OpenAI tuyên bố một hệ thống AI nội bộ siêu việt giải được bài toán thế kỉ nhưng vướng phải tranh cãi khi bị tố cáo ăn cắp hướng đi nghiên cứu của nhà toán học qua việc sử dụng Codex (dẫn nguồn link như đề bài yêu cầu, ngày truy cập: 15/10/2026 này https://cafef.vn/openai-tuyen-bo-10000-ai-agent-cua-ho-vua-giai-duoc-bai-toan-the-ky-giao-su-toan-hoc-len-tieng-ho-dang-cuop-cong-cua-toi-188260910072500287.chn)

- Phương pháp giảm thiểu: Cài đặt không chia sẻ dữ liệu (nếu có) và cẩn trọng khi đưa dữ liệu vào khi hỏi AI. 

## 6.3 Quy định dùng AI trong học tập
Dẫn Link theo đề bài: https://thuvienphapluat.vn/chinh-sach-phap-luat-moi/vn/ho-tro-phap-luat/chi-dao-dieu-hanh/4444/tu-15-8-su-dung-ai-trong-giao-duc-phai-bao-dam-liem-chinh-hoc-thuat

### 6.3.1 Các quy định chính
- AI và công nghệ chỉ là công cụ hỗ trợ, vai trò người trợ giảng/cố vấn, người học phải chịu trách nhiệm 100% về tính đúng đắn của sản phẩm cuối cùng.
```
@misc{ghimire2024generativeaieducationstudy,
      title={Generative AI in Education: A Study of Educators' Awareness, Sentiments, and Influencing Factors}, 
      author={Aashish Ghimire and James Prather and John Edwards},
      year={2024},
      eprint={2403.15586},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2403.15586}, 
}
```
- Việc dùng AI để gian lận là vi phạm liêm chính học thuật
- Các ứng dụng công nghệ phải đảm bảo tính trung thực, khách quan, minh bạch, bảo mật dữ liệu và tôn trọng quyền sở hữu trí tuệ.

### 6.3.2 Các hành vi vi phạm
- Dùng AI để gian lận, sao chép, đạo văn hoặc làm sai lệch dữ liệu nghiên cứu.
- Nhờ người khác thực hiện thay nhiệm vụ học tập, nghiên cứu.
- Không công bố hoặc công bố không đầy đủ việc sử dụng AI theo yêu cầu.

### 6.3.3 Trách nhiệm của cơ sở giáo dục
Phải ban hành quy định nội bộ về liêm chính học thuật, xác định rõ chế tài, biện pháp phòng ngừa và trang bị hệ thống quản lý học tập hỗ trợ xác thực danh tính, lưu vết quá trình học tập nhằm ngăn chặn gian lận.

# 7 Kết luận
## 7.1 Những kỹ năng khi sử dụng AI
- Kỹ năng đặt câu hỏi
- Kỹ năng tư duy phản biện

## 7.2 Định hướng sử dụng trong 4 năm đại học
- Xây dựng các công cụ tự động hóa bằng AI để hỗ trợ việc học tập được hiệu quả hơn
- Chỉ nhờ AI làm bạn đồng hành, người thầy chỉ dạy đánh giá, gợi ý chứ không phải sử dụng AI để tạo đáp án chép vào.

# A Nhật ký sử dụng AI
Hàng 1: 
- Link: https://share.gemini.google/MXGnNn9FVFtC
- AI giúp: Soạn prompt nghiêm ngặt ban đầu, viết prompt để cho Agent không tự làm mọi thứ 
- Mình đã sửa gì: củng cố thêm những cái như là không làm hộ, chỉ lập kế hoạch. 

Hàng 2: 
- Link: (cái chat antigravity hiện tại sau khi chat xong, hiện tại chưa cần render) (trích dần nguồn github project trong appendix đầy đủ với định dạng web: ngày truy cập 15/10/2026)
- AI giúp: 
    - Hỗ trợ làm dàn ý mẫu (file draft.md)
    - Chỉnh sửa nội dung sau khi mình viết để được mạch lạc, chỉnh lỗi chính tả. (polished_content.md)
    - Hỗ trợ trích dẫn nguồn bài báo.
    - Hỏi về một số khái niệm chưa biết như là "Transformer" hay là các mốc thời gian phát triển của Gemini.
    - Nhờ việc chuyển nội dung sang định dạng LaTeX chuẩn và đẹp
    - Đánh giá giúp về bài làm xem đã ổn chưa.
- Mình đã sửa những gì: 
    - Triển khai bản nội dung chi tiết và đầy đủ từ bản nháp (content.md)
    - Nguồn bài báo chỉ lấy link và tự lấy BibTex từ Google Scholar

Hàng 3
- Link: https://share.gemini.google/XhbafID6cTah
- AI giúp phần nào: cho biết thực tế có các loại token nào
- Mình đã sửa lại gì: Bổ sung thông tin về các loại token đúng hơn so với thông tin từ bản draft.md

Hàng 4
- Link: https://share.gemini.google/t2gbXH9W8Y2z
- AI giúp phần nào: Ví dụ hình 1 (thêm cái link để quay lại hình 1)
- Mình đã sửa lại gì: Chụp hình câu trả lời để sử dụng trong bài

Hàng 5
- Link: https://share.gemini.google/0lwOt5oaqwR5
- AI giúp phần nào: Ví dụ hình 2 (thêm cái link để quay lại hình 2)
- Mình đã sửa lại gì: Chụp hình câu trả lời để sử dụng trong bài

Hàng 6
- Link: https://share.gemini.google/iy4SQsG7k5Gm
- AI giúp phần nào: Ví dụ hình 3 (thêm cái link để quay lại hình 3)
- Mình đã sửa lại gì: Chụp hình câu trả lời để sử dụng trong bài

