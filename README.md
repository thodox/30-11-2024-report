# 30-11-2024-report

**Topic 1:**

Theo góc nhìn của em thì em có đưa ra một số góc nhìn khách quan như sau:

Dưới góc nhìn của user:

- Tối ưu giao diện người dùng (UI/UX):  có thể tạo một khu vực preview ngắn gọn với mô tả 1–2 câu cho mỗi tính năng kèm theo icon hoặc animation nhỏ, giúp người dùng nhanh chóng nắm bắt thông tin nổi bật mà không cần kéo dài tới cúi màn hình để xem phần học sắp ra mắt là gì.

- Thêm chế độ bỏ qua luyện tập nếu như người dùng đã biết về một mức lưng chừng nào đó. (ví dụ như task1 về các âm người dùng đã biết thì có thể cho người dùng pass qua để tới phần tiếp theo như task2 nếu như người dùng không muốn luyện tập lại mà học tiếp nhưng phần chưa biết).

- Có thể mở rộng thêm một vài phần miễn phí để thu hút người dùng hơn hoặc hỗ trợ cộng đồng và học tập nhóm (phòng riêng).


**Ba công việc AI muốn tham gia trong dự án:**

- Phát triển hệ thống gợi ý cá nhân hóa (Personalized Learning System): Thu thập dữ liệu chơi cá nhân của người dùng dựa trên số nốt đã chơi, sự sai số, lịch sử luyện tập, thời gian chơi,... để có thể phát ra điểm yếu từ đó gợi ý và cung cấp lộ trình học tập phù hợp với trình độ và tiến độ của từng người dùng.

-  Xây dựng một AI - người thầy hướng dẫn học nhạc và tích hợp feedback.

-  Phát triển hệ thống tạo nhạc tự động (Music Generation).

**Topic 2**

Các giải pháp research.

-  **Madmom**: Sử dụng các thuật toán như Hidden Markov Models (HMM) và Recurrent Neural Networks (RNN) để phân tích và nhận diện nhịp điệu trong âm nhạc. HMM, một mô hình xác suất, được dùng để phân loại tín hiệu âm thanh thành các trạng thái beat và non-beat, trong khi RNN, đặc biệt là các biến thể như LSTM và GRU, giúp phân tích các chuỗi âm thanh và nhận diện các mẫu nhịp điệu qua thời gian. Quá trình xử lý của Madmom bao gồm việc chuyển đổi tín hiệu âm thanh thành các đặc trưng như Spectrogram hoặc Chromagram, sau đó áp dụng HMM hoặc RNN để phát hiện beat và downbeat.
-  link git và paper:

-  **Beat Transformer**: 
