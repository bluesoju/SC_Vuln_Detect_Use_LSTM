# SC_Vuln_Detect_Use_LSTM
``` Dataset in my project: ``` https://drive.google.com/drive/folders/1T6GOIEuokV3PxBnSQx8PATDM6yUW2DF0?usp=share_link
# **Mô tả**
Smart Contract là ứng dụng phi tập trung dựa trên nền tảng BlockChain. Một số lượng rất lớn các SC được triển khai trên
Ethereum. Trong khi đó, các lỗi bảo mật của SC đã dẫn đến tổn thất lớn về tiền bạc và phá hủy sự ổn định sinh thái trên
Blockchain. Đây là một vấn đề mới nổi nhưng rất quan trọng. Để phát hiện các lỗ hổng trong SC, các công cụ hiện nay như
Oyente và Securify chủ yếu dựa trên việc thực hiện hoặc phân tích cú pháp. Các phương pháp này thường mất khá nhiều
thời gian. Vì vậy, chúng tôi đề xuất phương pháp phát hiện các lỗ hổng trong SC bằng các phương pháp học máy.
# **Công cụ**
Tôi đã thực hiện việc lấy Smart Contract từ các nguồn như EtherScan.io, Google BigQuery... </br>
Sau đó, thực hiện việc quét lổ hổng trên các Smart Contract bằng công cụ [Conkas](https://github.com/nveloso/conkas) và [Slither](https://github.com/crytic/slither) </br>
Tôi đã label mỗi lỗi theo kiểu OnevsRest ( [1,0,0,0,0], ...)
# **Feature Extraction**
Theo trang Ethereum thì có hơn 142 opcode của smart contract thì sau khi nhóm thực hiện gom nhóm và đơn giản hóa số lượng opcode còn hơn 60 opcode. </br>
Xử lý ngôn ngữ tự nhiên thì ta sẽ thực hiện mỗi opcode như là một text. Và thực hiện one-hot dựa trên word_index (chính là hơn 60 opcode). </br>
Dimention vector sẽ mang số chiều là 60.
# **Dataset**
Dataset sẽ có cấu trúc **Adress**, **Các cột biểu thị cho lỗi**, **Opcode**. </br>
Việc phân loại dựa trên kết quả sử dụng các công cụ detect đã được xác thực trên các paper uy tín. 
# **Build-up Model và predict**
LSTM là một mạng bố nhớ dài-ngắn (Long Short term Memory Networks), LSTM là một dạng đặc biệt của RNN (Recurrent Neural Networks), nó có thể học được các phụ thuộc xa.LSTM được thiết kế để tránh được vấn đề phụ thuộc xa (long-term dependency). Việc nhớ thông tin trong suốt thời gian dài là đặc tính mặc định của chúng, chứ ta không cần phải huấn luyện nó để có thể nhớ được. Tức là ngay nội tại của nó đã có thể ghi nhớ được mà không cần bất kì can thiệp nào. </br>
Mọi mạng hồi quy đều có dạng là một chuỗi các mô-đun lặp đi lặp lại của mạng nơ-ron. Với mạng RNN chuẩn, các mô-dun này có cấu trúc rất đơn giản, thường là một tầng tanh. LSTM cũng có kiến trúc dạng chuỗi như vậy, nhưng các mô-đun trong nó có cấu trúc khác với mạng RNN chuẩn. Thay vì chỉ có một tầng mạng nơ-ron, chúng có tới 4 tầng tương tác với nhau một cách rất đặc biệt. </br>
Sau khi xây dựng mô hình thì bước tiếp theo là thực hiện train và test trên tập dataset ( chia theo tỉ lệ 80:20) </br>
Sau khi thực hiện train thì mô hình cho ra một kết quả khá tốt là 0.912 (tính theo điểm cao nhất của model)
# **Tổng kết** 
Việc xây dựng mô hình này dùng để việc thực hiện phát hiện các lổ hổng trên Smart Contract sẽ tiết kiệm thời gian và sẽ phát hiện ra lổ hổng mới (so với label đã được chọn) nếu như ta sử dụng các mô hình như: **Tranfer**, **Tranformers**. Đây cũng là mục tiêu tôi hướng tới trong việc phát triển kỉ năng Machine learning nói chung hay Neural NetWorks nói riêng. 
