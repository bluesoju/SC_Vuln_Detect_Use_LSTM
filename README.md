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
# **Xử lý ngôn ngữ tự nhiên**
Theo trang Ethereum thì có hơn 142 opcode của smart contract thì sau khi nhóm thực hiện gom nhóm và đơn giản hóa số lượng opcode còn hơn 60 opcode. </br>
Xử lý ngôn ngữ tự nhiên thì ta sẽ thực hiện mỗi opcode như là một text. Và thực hiện one-hot dựa trên word_index (chính là hơn 60 opcode). </br>
Dimention vector sẽ mang số chiều là 60.
# **Build-up Model và predict**
# **Tổng kết** 
