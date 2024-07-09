> https://www.udemy.com/course/manual-and-automation-software-testing-with-help-of-chatgpt/learn/lecture/43343386#overview
 
# Assistance in writing SQL queries
- Chat GPT có thể support tester viết những câu truy vấn database, visualized 1 database dưới dạng 1 table, hoặc hỗ trợ kiểm tra kết quả câu truy vấn 
- VD: QE team cần tham gia test 1 website bán hàng, hiện có 100 khách hàng từ US, Italy và India, trong độ tuổi từ 20 > 66, có cả người độc thân và đã kết hôn. QE có thể dùng ChatGPT để: 
    - Visualized database dưới dạng 1 table, với data được ChatGPT gen tự động => QE có cái nhìn rõ hơn về cấu trúc database
        - Prompt: Show me the example of the database table with 100 users ten from Italy, ten from USA, ten from India with ages from 20 to 66. Single and married.
    - Viết câu truy vấn để tìm thông tin nhất định từ database: 
        - Prompt: Select from your table name where country equals USA and age between 30 and 40 and marital status equals single.
    - Kiểm tra kết quả của một câu truy vấn bất kì: 
        - I will type queries and you will reply with what the terminal would show.
- Với những cơ sở dữ liệu phức tạp hơn, ChatGPT vẫn khá hữu dụng, tuy nhiên vẫn theo nguyên tắc cũ, cung cấp thông tin về database càng chi tiết càng tốt, và không ngừng hỏi thêm nếu ChatGPT chưa đưa ra kết quả chính xác ngay từ đầu. 

