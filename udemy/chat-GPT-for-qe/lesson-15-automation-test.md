> https://www.udemy.com/course/manual-and-automation-software-testing-with-help-of-chatgpt/learn/lecture/43343738#overview

# Selenium/java test case with ChatGPT 

## Xác định requirement với ChatGPT 
- Trong quá trình làm việc, nhiều khi manual tester sẽ nhận được những request kiểm thử những sản phẩm với requirement không rõ ràng
=> Có thể sử dụng ChatGPT và DOM HTML để clear requirement, dựng user story: 
    - VD: Tester cần viết auto cho form nhập user info của trang [testing101.net](https://www.testing101.net/seleniumlocators), nhưng chưa rõ requirement của form này, tester có thể: 
        - Bật devtool (nhấn F12 hoặc Nhấn chuột phải > Inspect)
        - Kiểm tra các attribute của các element trong DOM HTML, Vd: maxlength, pattern, ..... => tím ra requirement. tại trah này là các field first name, last name, .....
        - Với những thông tin collect được, có thể dùng chatGPT để tạo user story: 
        ```diff
        Write a user story with acceptance criteria for the Find Elements form on the testing101.net website, which consists of:
            - First name field with maxlength of 100 characters
            - Last name field with maxlength of 100 characters
            - Email field with a specific pattern
            - Confirm email field with the same pattern
            - Account type dropdown with options Personal and Business
            - Terms and Conditions checkbox
            - Submit button
        ```

## Viết manual test cases
- Bước tiếp theo là viết manual test cases từ các thông tin bên trên. Prompt: 
```diff
Write a positive test case for submitting the Find Elements form on testing101.net that consists of the following fields:
- First name
- Last name
- Email
- Confirm email
- Account type
- Terms and Conditions
- Submit button

```

## Automated test cases với Selenium Java bằng ChatGPT
- B1: Tạo 1 project auto và viết step auto mở trang [testing101.net](https://www.testing101.net/seleniumlocators)
    - Sử dụng IDE IntelliJ > tạo 1 project Selenium
    - Automate step open page bằng chatGPT: 
    ```bash
    Write a Selenium Java test script with TestNG for opening the testing101.net page.

    ```
    - Copy vào file test và fix các issue (nếu có) (chủ yếu là các issue về import class, có thể resolve bằng gợi ý của IDE): 
        - File name
        - ChromeDirverPath
        - .....
- B2: Với form nhập data, cần xác định xpath trước: 
    - Inspect element cần tìm (VD: first name) > Copy html content > Sử dụng chatGPT để generate xpath: 
    ```diff
    Generate XPath for select element. 
    HTML content
    ```
    - Kiểm tra xpath có bị lặp tại DOM không
- B3: Automate step fill/click sau khi có xpath
    - Với xpath tìm được, automate xpath bằng chatGPT: 
    ```diff
    Generate a Selenium Java single line of code to click/fill on the .....
    ```
    - Tương tự với các field khác trong test cases
- B4: Add steps waiting 
    - Sau khi click/fill 1 field nào đó, có thể cần wait trước khi chuyển sang action tiếp theo: 
    ```bash 
    Thread.sleep(1000);
    ```
    - Nếu cần scroll: 
    ```diff
    Write me Selenium Java code to scroll the page by 15%.
    ```
- B5: Run auto test bằng cách click btn Run trong IDE
