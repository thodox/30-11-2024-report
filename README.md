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

  **Madmom**: 
  - Sử dụng các thuật toán như Hidden Markov Models (HMM) và Recurrent Neural Networks (RNN) để phân tích và nhận diện nhịp điệu trong âm nhạc. HMM, một mô hình xác suất, được dùng để phân loại tín hiệu âm thanh thành các trạng thái beat và non-beat, trong khi RNN, đặc biệt là các biến thể như LSTM và GRU, giúp phân tích các chuỗi âm thanh và nhận diện các mẫu nhịp điệu qua thời gian. Quá trình xử lý của Madmom bao gồm việc chuyển đổi tín hiệu âm thanh thành các đặc trưng như Spectrogram hoặc Chromagram, sau đó áp dụng HMM hoặc RNN để phát hiện beat và downbeat.
-  link git và paper:

 **Beat Transformer**: 
 
 - Là một mô hình học sâu được thiết kế để nhận diện beat và downbeat trong âm nhạc, sử dụng kiến trúc Transformer kết hợp với các thuật toán tiên tiến như Convolutional Neural Networks (CNN) và Long Short-Term Memory (LSTM). Tín hiệu âm thanh ban đầu được chuyển đổi thành các đặc trưng như Spectrogram hoặc Chromagram, sau đó mô hình sử dụng cơ chế self-attention trong Transformer để học và nhận diện các mối quan hệ giữa các phần xa nhau trong chuỗi âm thanh mà không cần phải xử lý tuần tự như các mô hình RNN truyền thống. Điều này giúp mô hình có thể nhận diện chính xác các điểm beat và downbeat, đồng thời cải thiện hiệu suất so với các phương pháp trước đây. Các CNN được sử dụng để trích xuất các đặc trưng không gian từ tín hiệu âm thanh, trong khi LSTM giúp giữ lại thông tin dài hạn của nhịp điệu qua thời gian. Kết quả là Beat Transformer có thể nhận diện beat và downbeat một cách chính xác
 - Git: https://github.com/zhaojw1998/Beat-Transformer.git
   
 - paper: https://arxiv.org/abs/2209.07140

**BeatNet**

- Kết hợp phân tách nguồn (source separation) và tăng cường dữ liệu (data augmentation). Phương pháp này bao gồm việc sử dụng các stem nhạc cụ (như trống) được tách ra từ bản mix gốc để cải thiện hiệu quả của mô hình khi xử lý beat và downbeat. Cụ thể, dữ liệu đầu vào được chia thành nhiều loại khác nhau, bao gồm cả phần trống và không phải trống, từ đó mô hình học được cách xử lý thông tin trong các trường hợp có hoặc không có âm trống.
- git: https://github.com/mjhydri/beatnet
- paper: https://arxiv.org/abs/2108.03576



# Đánh giá các giải pháp nhận diện nhịp điệu trong âm nhạc

## Tiêu chí đánh giá
1. **Hiệu quả phân tích nhịp điệu (Accuracy)**: Độ chính xác trong việc phát hiện beat và downbeat.
2. **Tính linh hoạt (Scalability)**: Mức độ phù hợp khi áp dụng trên các thiết bị khác nhau (Mobile, Hardware).
3. **Thời gian triển khai (Implementation Time)**: Độ phức tạp và thời gian cần thiết để triển khai.
4. **Hiệu suất thời gian thực (Real-Time Processing)**: Khả năng hoạt động theo thời gian thực.
5. **Tính đổi mới (Innovative Approach)**: Ứng dụng công nghệ mới và sáng tạo.

## Bảng đánh giá khách quan

| **Giải pháp**      | **Hiệu quả (Accuracy)** | **Tính linh hoạt (Scalability)** | **Thời gian triển khai** | **Thời gian thực** | **Tính đổi mới** | **Tổng điểm** |
|---------------------|-------------------------|-----------------------------------|--------------------------|--------------------|------------------|---------------|
| **Madmom**         | 8/10                   | 7/10                              | 7/10                     | 8/10               | 7/10             | 37/50         |
| **Beat Transformer** | 9/10                   | 8/10                              | 6/10                     | 8/10               | 9/10             | 40/50         |
| **BeatNet**         | 7/10                   | 8/10                              | 8/10                     | 7/10               | 8/10             | 38/50         |

## Phân tích chi tiết

### 1. Beat Transformer *(40/50 - Xếp hạng 1)*
- **Hiệu quả (9/10)**:  
  Cơ chế self-attention giúp mô hình nhận diện chính xác beat và downbeat trên các chuỗi âm thanh dài, vượt trội hơn so với các mô hình truyền thống.  
- **Tính linh hoạt (8/10)**:  
  Hoạt động tốt trên phần cứng hiện đại nhưng yêu cầu tài nguyên cao, gây khó khăn khi triển khai trên thiết bị hạn chế.  
- **Thời gian triển khai (6/10)**:  
  Cấu trúc phức tạp đòi hỏi thời gian và chuyên môn cao để tích hợp đầy đủ.  
- **Thời gian thực (8/10)**:  
  Khả năng xử lý gần thời gian thực với hiệu suất cao nhưng cần phần cứng mạnh.  
- **Tính đổi mới (9/10)**:  
  Ứng dụng Transformer trong lĩnh vực âm nhạc là bước tiến đột phá.

### 2. BeatNet *(38/50 - Xếp hạng 2)*
- **Hiệu quả (7/10)**:  
  Sử dụng phân tách nguồn và tăng cường dữ liệu, phù hợp với âm nhạc có cấu trúc đơn giản.  
- **Tính linh hoạt (8/10)**:  
  Tối ưu hóa tốt cho các thiết bị phổ thông và di động.  
- **Thời gian triển khai (8/10)**:  
  Cấu trúc đơn giản hơn giúp triển khai nhanh hơn so với Beat Transformer.  
- **Thời gian thực (7/10)**:  
  Hoạt động ổn định trong thời gian thực, nhưng bị giới hạn khi xử lý nhạc phức tạp.  
- **Tính đổi mới (8/10)**:  
  Áp dụng sáng tạo phân tách nguồn và tăng cường dữ liệu.

### 3. Madmom *(37/50 - Xếp hạng 3)*
- **Hiệu quả (8/10)**:  
  Sử dụng HMM và RNN giúp đạt độ chính xác ổn định, nhưng khó xử lý dữ liệu phức tạp như các phương pháp mới hơn.  
- **Tính linh hoạt (7/10)**:  
  Phù hợp với thiết bị hạn chế nhưng không tối ưu cho các ứng dụng hiện đại.  
- **Thời gian triển khai (7/10)**:  
  Thiết kế đơn giản, dễ tích hợp vào các dự án nghiên cứu hoặc thử nghiệm ban đầu.  
- **Thời gian thực (8/10)**:  
  Hoạt động tốt trong thời gian thực với dữ liệu âm thanh cơ bản.  
- **Tính đổi mới (7/10)**:  
  Là giải pháp đáng tin cậy nhưng công nghệ không còn tiên tiến.























