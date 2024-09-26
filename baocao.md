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
