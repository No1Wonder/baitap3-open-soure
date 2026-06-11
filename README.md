# SỬ DỤNG DOCKER TRÊN UBUNTU ĐỂ TẠO docker ccompose chứa:
+ Mariadb: sử dụng image: mariadb:latest để làm hệ quản trị csdl cho wordpress
+ Phpmyadmin: sư dụng image: phpmyadmin:latest để đăng nhập vào mariadb rồi tạo csdl trống (chỉ để xem, ko cần tạo bảng từ đây, wordpress sẽ làm hết)
+ WordPress: Sử dụng image: wordpress:latest, truyền các tham số môi trường cho wordpress là các thông tin truy cập csdl mariadb, tạo bởi Phpmyadmin
+ Yêu cầu: sau khi có 3 service này trong file docker-compose.yml :
$ Cấu hình để hệ thống chạy
+ Sử dụng cloudflare tunnel để public web này lên 1 sub-domain
+ Tạo 1 bài viết trong wordpress giới thiệu về bản thân sinh viên: thông tin cá nhân, sở thích, ... bài viết có thể chứa hình ảnh, âm thanh, video, ...
+ Tạo 1 bài viết trong wordpress giới thiệu về ngành học mà em yêu thích trong trường TNUT. bài viết phải chứa hình ảnh, video, ...
+ Nhận xét việc sử dụng mã nguồn mở wordpress để tạo website (tốn công sức thế nào, dễ/khó dùng ra sao, tốn kém tài nguyên(ssh/ram) của máy chủ ra sao,....)

# setup và mariadb 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/65f01588-c969-4549-822f-c20e4e405eca" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ee40bd6f-93cb-4297-9251-971d3fdcab4a" />
$ cài docker
<img width="1472" height="744" alt="image" src="https://github.com/user-attachments/assets/0a9d7d2e-e61e-4d88-8e3e-e13fc98d3936" />
# tạo PdH
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d7397f40-529d-47e4-9176-150f8eb618b4" />

# cài cloudflare tạo turner
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/86ec8104-1d5d-43df-88ba-587232d8d24a" />
# sau đó thêm turner vào cấu trúc
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e0082dd4-c516-4b6f-b8ac-bb36ea6d35bb" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b4675099-cdcf-482a-800e-65d904134f92" />
# tạo wordpress
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c29f18b8-06f0-4ef9-95be-2b206a0bd9ea" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/964c5621-f169-4b57-a0ff-d93737ed5723" />

# đăng các bài đăng trên đây
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b715e2d6-e47c-4631-9d8c-6e88a7d08cc2" />

# các bài đăng được hiển thị 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cfa1b1f5-0ef2-4277-b52c-b25ecb012ec0" />

# 1. Chi tiết về công sức đầu tư (Tốn công thế nào?)
+ Góc độ Hệ thống (Cấu hình máy chủ): Đây là phần tốn công nhất trong bài tập. Việc phải viết file docker-compose.yml, cấu hình mạng cho các container, rồi cài đặt Cloudflare Tunnel để đưa web từ máy ảo LAN ra Internet đòi hỏi kiến thức về Linux và mạng. Tuy nhiên, khi các lệnh này đã "thông", hệ thống sẽ tự chạy mãi mãi mà không cần can thiệp lại.
+ Góc độ Nội dung (Làm Web): Cực kỳ tiết kiệm công sức. Thay vì phải ngồi gõ hàng nghìn dòng code HTML/CSS/PHP để tạo ra một khung trang web và chức năng đăng bài, WordPress đã làm sẵn 100%. Bạn chỉ mất 5 - 10 phút click chuột là có ngay bài viết hoàn chỉnh.
# 2. Chi tiết về độ dễ và khó (Dễ/Khó dùng ra sao?)
+ Điểm DỄ: Giao diện quản trị (Dashboard) bằng tiếng Việt rất thân thiện. Cơ chế viết bài kiểu Block Editor (Gutenberg) cho phép chèn ảnh, nhúng video YouTube chỉ bằng cách gõ dấu (+) rồi kéo thả, tương tự như đang dùng Microsoft Word hoặc Canva. Việc thay đổi giao diện (Theme) hay thêm tính năng (Plugin) hoàn toàn được thực hiện qua các cú click chuột trực quan.
+ Điểm KHÓ: Với người mới, WordPress có quá nhiều menu cấu hình dễ gây ngợp. Nếu không quản lý tốt, việc cài quá nhiều Plugin bổ sung sẽ dễ dẫn đến xung đột hệ thống, làm treo trang web hoặc lỗi trắng trang (White Screen of Death).
# 3. Chi tiết về tiêu tốn tài nguyên máy chủ (RAM/CPU/Storage)
+ Bộ nhớ RAM :
  + Bản thân WordPress (PHP-FPM/Apache): Tốn khoảng 80MB - 150MB RAM.
  + Cơ sở dữ liệu MySQL/MariaDB: Đây là ngốn RAM nhất, thường chiếm từ 250MB - 400MB RAM để duy trì bộ nhớ đệm (Cache) cho các bảng dữ liệu.
  + Cloudflare Tunnel & phpMyAdmin: Rất nhẹ, chỉ chiếm khoảng 20MB - 50MB RAM mỗi container.
# Kết luận: Một máy chủ (hoặc máy ảo) chỉ cần có 1GB RAM là đã dư sức chạy mượt mà cụm WordPress này ở quy mô vừa và nhỏ.
+ Bộ xử lý CPU: * Khi trang web ở trạng thái tĩnh (không có người truy cập), CPU của container WordPress gần như bằng 0%. CPU chỉ nhích lên (khoảng 5% - 20%) khi bạn bấm "Đăng bài", khi WordPress phải xử lý băm/nén hình ảnh bạn tải lên, hoặc khi có nhiều người cùng vào đọc bài một lúc.
+ Dung lượng lưu trữ (Storage):
Bộ mã nguồn WordPress ban đầu chỉ nặng khoảng 50MB - 60MB. Hệ thống của bạn nặng hay nhẹ phần lớn là do database (bài viết) và các file ảnh/video mà bạn đăng lên thư mục wp_data.
