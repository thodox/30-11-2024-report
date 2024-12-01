# 30-11-2024-report

# Topic 1:
**Simpia** là một ứng dụng giáo dục tiên tiến được thiết kế để giúp người dùng học chơi piano nhanh chóng và hiệu quả. Ứng dụng sử dụng công nghệ AI để hỗ trợ học tập, cung cấp các khóa học từ cơ bản đến nâng cao, và mang lại trải nghiệm cá nhân hóa cho từng người dùng.

---

## **Tính năng chính**

1. **Học piano toàn diện**:
   - Cung cấp các bài học về nốt nhạc, hợp âm, và cách chơi các bài hát.
   - Phù hợp cho người mới bắt đầu và người chơi nâng cao.

2. **Phản hồi thời gian thực với AI**:
   - Công nghệ AI phân tích và đánh giá kỹ năng chơi piano.
   - Đưa ra phản hồi cụ thể giúp cải thiện cách chơi.

3. **Thư viện bài học phong phú**:
   - Hàng trăm bài học và khóa học được cập nhật thường xuyên. Có thể chơi các bài nhạc bằng cách liên kết API với youtube

4. **Giao diện thân thiện**:
   - Thiết kế đơn giản, trực quan, dễ sử dụng.

5. **Tùy chọn nâng cấp Premium**:
   - Mở khóa các khóa học độc quyền và nội dung nâng cao với gói trả phí.

Theo góc nhìn của em thì em có đưa ra một số góc nhìn khách quan như sau:

Dưới góc nhìn của user:

- Tối ưu giao diện người dùng (UI/UX):  có thể tạo một khu vực preview ngắn gọn với mô tả 1–2 câu cho mỗi tính năng kèm theo icon hoặc animation nhỏ, giúp người dùng nhanh chóng nắm bắt thông tin nổi bật mà không cần kéo dài tới cúi màn hình để xem phần học sắp ra mắt là gì.

- Thêm chế độ bỏ qua luyện tập nếu như người dùng đã biết về một mức lưng chừng nào đó. (ví dụ như task1 về các âm người dùng đã biết thì có thể cho người dùng pass qua để tới phần tiếp theo như task2 nếu như người dùng không muốn luyện tập lại mà học tiếp nhưng phần chưa biết).

- Tăng tính tương tác và cộng đồng: Hiện ứng dụng chưa đề cập đến chức năng kết nối giữa các người dùng (như diễn đàn hoặc nhóm học trực tuyến). Bổ sung tính năng này sẽ giúp tăng cường động lực học tập thông qua việc chia sẻ và học hỏi kinh nghiệm từ cộng đồng


**Ba công việc AI muốn tham gia trong dự án:**

- Phát triển hệ thống gợi ý cá nhân hóa (Personalized Learning System): Thu thập dữ liệu chơi cá nhân của người dùng dựa trên số nốt đã chơi, sự sai số, lịch sử luyện tập, thời gian chơi,... để có thể phát ra điểm yếu từ đó gợi ý và cung cấp lộ trình học tập phù hợp với trình độ và tiến độ của từng người dùng.

-  Xây dựng một AI - người thầy hướng dẫn học nhạc và tích hợp feedback.

-  Phát triển hệ thống tạo nhạc tự động (Music Generation).

# Topic 2

Các giải pháp research.

  **Madmom**: 
  - Sử dụng các thuật toán như Hidden Markov Models (HMM) và Recurrent Neural Networks (RNN) để phân tích và nhận diện nhịp điệu trong âm nhạc. HMM, một mô hình xác suất, được dùng để phân loại tín hiệu âm thanh thành các trạng thái beat và non-beat, trong khi RNN, đặc biệt là các biến thể như LSTM và GRU, giúp phân tích các chuỗi âm thanh và nhận diện các mẫu nhịp điệu qua thời gian. Quá trình xử lý của Madmom bao gồm việc chuyển đổi tín hiệu âm thanh thành các đặc trưng như Spectrogram hoặc Chromagram, sau đó áp dụng HMM hoặc RNN để phát hiện beat và downbeat.
-  link git và paper: https://github.com/CPJKU/madmom.git

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





# Triển khai

**Librosa** là một thư viện Python phổ biến dành cho xử lý và phân tích tín hiệu âm thanh, đặc biệt là âm nhạc. Thư viện này cung cấp các công cụ mạnh mẽ để trích xuất đặc trưng âm thanh như Mel-frequency cepstral coefficients (MFCC), spectrograms, pitch, tempo, và nhiều yếu tố khác, giúp các nhà nghiên cứu và lập trình viên trong các ứng dụng như nhận dạng giọng nói, phân tích âm nhạc và học máy. Librosa cũng hỗ trợ việc tải và xử lý các tệp âm thanh từ nhiều định dạng phổ biến.

**Madmom** là một mã nguồn mở trong Python mạnh mẽ dành cho xử lý và phân tích âm nhạc, đặc biệt trong các bài toán nhận dạng nhịp điệu, phân đoạn âm nhạc và phân loại âm nhạc. Mã nguồn này áp dụng các công nghệ học máy và học sâu (deep learning), bao gồm mạng nơ-ron convolutional (CNNs) để nhận dạng nhịp điệu và phân đoạn âm nhạc. Ngoài ra, Madmom còn sử dụng các mô hình Hidden Markov Models (HMMs) để cải thiện khả năng phân loại và dự đoán các yếu tố trong tín hiệu âm nhạc, như nhận dạng tempo và onset. Madmom cũng cung cấp các mô hình đã được huấn luyện sẵn, giúp tiết kiệm thời gian khi triển khai các ứng dụng phân tích âm nhạc








## Mô tả
Sử dụng thư viện **librosa** và mã nguồn mở **madmom** để thực hiện tracking beats và downbeats trong file audio piano, sau đó trực quan hóa kết quả và lưu lại file piano  đã được xử lý.


### Kịch bản
**1. File Âm Thanh**
Chuẩn bị 1 file âm thanh cần tracking.

**2. Tiền Xử Lý Dữ Liệu với librosa**

Đọc File Âm Thanh: Sử dụng librosa.load() để đọc file âm thanh vào dưới dạng tín hiệu sóng (waveform).

Trích Xuất Các Đặc Trưng Âm Thanh: Sau khi đọc tín hiệu âm thanh, bạn sẽ trích xuất các đặc trưng như MFCCs (Mel-frequency cepstral coefficients) hoặc chroma features. Những đặc trưng này cung cấp thông tin về cấu trúc âm nhạc, đặc biệt là giúp nhận diện các điểm mạnh của beat và downbeat.

**3. Tracking Beats và Downbeats với madmom**

Sử dụng madmom để thực hiện tracking beats và downbeats, với hai bộ xử lý chính: **RNNBeatProcessor** và **RNNDownBeatProcessor.**

**RNNBeatProcessor – Nhận diện Beat**

Đầu vào: Tín hiệu âm thanh được chuyển đổi thành các đặc trưng như spectrogram hoặc chroma features. Những đặc trưng này giúp mô hình nhận diện sự thay đổi trong âm thanh, đặc biệt là những điểm mạnh liên quan đến beats.RNN (Recurrent Neural Network): Mô hình sử dụng mạng nơ-ron hồi tiếp (RNN) để phân tích tín hiệu âm thanh theo chuỗi thời gian. RNN giúp mô hình học được cách nhận diện các beats dựa trên các thay đổi trong tín hiệu âm thanh theo thời gian.

Quá trình nhận diện: Mô hình học cách nhận diện các beats bằng cách quan sát sự thay đổi đột ngột trong năng lượng hoặc các đặc trưng âm thanh khác. Mỗi frame tín hiệu sẽ được đánh giá dựa trên thông tin từ các frame trước đó, giúp nhận diện chính xác các beats trong âm nhạc.
Kết quả: RNNBeatProcessor sẽ xác định các vị trí trong tín hiệu âm thanh mà ở đó có beats. Các beats này thường xuất hiện đều đặn, và mô hình có thể đánh dấu chính xác các điểm này trong tín hiệu âm thanh.


**RNNDownBeatProcessor – Nhận diện Downbeat**

Đầu vào: Giống như RNNBeatProcessor, tín hiệu âm thanh sẽ được chuyển đổi thành các đặc trưng như spectrogram hoặc chroma features. Tuy nhiên, với downbeats, mô hình cần nhận diện những điểm đặc biệt đầu tiên của mỗi chu kỳ nhịp (downbeats), thường là những điểm mạnh nhất trong mỗi bar.RNN (Recurrent Neural Network): RNNDownBeatProcessor sử dụng RNN để phân tích các đặc trưng âm thanh theo thời gian. Mục tiêu là nhận diện các downbeats, là các beats đầu tiên và mạnh nhất trong mỗi chu kỳ nhịp.

Quá trình nhận diện: Mô hình học cách nhận diện các downbeats bằng cách tìm kiếm sự tăng trưởng đột ngột trong năng lượng âm thanh tại các điểm đầu của mỗi chu kỳ nhịp. Những downbeats này có sự khác biệt rõ rệt so với các beats khác.

Kết quả: RNNDownBeatProcessor sẽ xác định chính xác vị trí của các downbeats trong tín hiệu âm thanh. Những downbeats này sẽ được đánh dấu rõ ràng và có thể được sử dụng trong các phân tích âm nhạc chi tiết hơn.

**4. Vẽ Biểu Đồ**

Biểu đồ 1: Hiển thị tín hiệu âm thanh gốc mà không có bất kỳ đánh dấu nào.

Biểu đồ 2: Hiển thị tín hiệu âm thanh với các beats được đánh dấu (đường thẳng đỏ để đánh dấu beats).

Biểu đồ 3: Hiển thị tín hiệu âm thanh với các downbeats được đánh dấu (đường thẳng xanh để đánh dấu downbeats).




# Kết quả đạt được.

Có sự đụng độ về thư viện trong madmom, em đang cố gắng fix lỗi. Theo như em research thì lỗi đang gặp phải là do thư viện madmom đang sử dụng kiểu dữ liệu np.float, nhưng kiểu này đã bị loại bỏ trong NumPy phiên bản 1.20 và các phiên bản mới hơn.  Mặc dù đã hạ phiên bản xuống 1.19.0 nhưng vẫn lỗi không thể hoàn thành tải mã nguồn mở/thư viện madmom xuống và sử dụng nó.

![image](https://github.com/user-attachments/assets/4c064b61-f0b6-44f8-9fa0-927ca40a81f3)










