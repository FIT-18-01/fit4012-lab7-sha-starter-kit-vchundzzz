# FIT4012 Lab 7 - Báo cáo 1 trang: SHA-256

## 1. Mục tiêu / Objective

Mục tiêu của bài thực hành là tìm hiểu thuật toán băm SHA-256 và ứng dụng của nó trong bảo mật dữ liệu. Bài lab bao gồm việc chạy chương trình băm chuỗi, kiểm tra tính toàn vẹn của file, băm mật khẩu người dùng và cải tiến hệ thống bằng cách thêm salt để tăng độ an toàn khi lưu mật khẩu.

## 2. Cách làm / Approach

Trong bài lab, nhóm/cá nhân đã thực hiện các bước sau:

- Biên dịch và chạy chương trình sha_procedure.cpp để tạo hash SHA-256.
- Kiểm thử SHA-256 bằng known answer test vector với chuỗi abc.
- Viết và chạy chương trình kiểm tra toàn vẹn file bằng cách so sánh hash trước và sau khi chỉnh sửa nội dung file.
- Viết chương trình đăng ký và đăng nhập bằng cách lưu hash của mật khẩu thay vì lưu mật khẩu gốc.
- Bổ sung salt vào mật khẩu trước khi băm để tránh trường hợp nhiều người dùng có cùng mật khẩu sẽ tạo ra cùng một giá trị hash.
## 3. Kết quả / Result

Điền minh chứng chính:

- Hash của chuỗi abc:

ba7816bf8f01cfea414140de5dae2223b00361a396177a9cb410ff61f20015ad

- Hash của file mẫu trước khi sửa:

2cf24dba5fb0a30e26e83b2ac5b9e29e1b161e5c1fa7425e73043362938b9824

- Kết quả kiểm tra file sau khi sửa nội dung:

Integrity check FAILED - File has been modified.

- Kết quả đăng nhập với mật khẩu đúng:

Login successful.

- Kết quả đăng nhập với mật khẩu sai:

Login failed - Incorrect password.

- Hai bản ghi salt:hash của cùng một mật khẩu có giống nhau không?

Không giống nhau vì mỗi lần tạo salt khác nhau sẽ sinh ra hash khác nhau.

## 4. Kết luận / Conclusion

Nêu ngắn gọn điều rút ra:

- SHA-256 giúp phát hiện thay đổi dữ liệu bằng cách tạo ra giá trị hash duy nhất cho dữ liệu. Chỉ cần thay đổi một ký tự nhỏ trong dữ liệu thì hash cũng sẽ thay đổi hoàn toàn.
- Salt cần thiết khi lưu hash mật khẩu vì nó giúp chống rainbow table và tránh việc hai người dùng có cùng mật khẩu tạo ra cùng hash.
- SHA-256 trong bài lab chỉ là bản demo cơ bản và chưa phù hợp để dùng trực tiếp trong hệ thống xác thực thật vì còn thiếu các cơ chế bảo mật mạnh hơn như bcrypt, scrypt hoặc Argon2 với nhiều vòng lặp và chống brute-force tốt hơn.
