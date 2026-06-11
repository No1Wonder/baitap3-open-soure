SỬ DỤNG DOCKER TRÊN UBUNTU ĐỂ TẠO docker ccompose chứa:
+ Mariadb: sử dụng image: mariadb:latest để làm hệ quản trị csdl cho wordpress
+ Phpmyadmin: sư dụng image: phpmyadmin:latest để đăng nhập vào mariadb rồi tạo csdl trống (chỉ để xem, ko cần tạo bảng từ đây, wordpress sẽ làm hết)
+ WordPress: Sử dụng image: wordpress:latest, truyền các tham số môi trường cho wordpress là các thông tin truy cập csdl mariadb, tạo bởi Phpmyadmin
+ Yêu cầu: sau khi có 3 service này trong file docker-compose.yml :
Cấu hình để hệ thống chạy
+ Sử dụng cloudflare tunnel để public web này lên 1 sub-domain
+ Tạo 1 bài viết trong wordpress giới thiệu về bản thân sinh viên: thông tin cá nhân, sở thích, ... bài viết có thể chứa hình ảnh, âm thanh, video, ...
+ Tạo 1 bài viết trong wordpress giới thiệu về ngành học mà em yêu thích trong trường TNUT. bài viết phải chứa hình ảnh, video, ...
+ Nhận xét việc sử dụng mã nguồn mở wordpress để tạo website (tốn công sức thế nào, dễ/khó dùng ra sao, tốn kém tài nguyên(ssh/ram) của máy chủ ra sao,....)

setup
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/65f01588-c969-4549-822f-c20e4e405eca" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ee40bd6f-93cb-4297-9251-971d3fdcab4a" />
docker
<img width="1472" height="744" alt="image" src="https://github.com/user-attachments/assets/0a9d7d2e-e61e-4d88-8e3e-e13fc98d3936" />
tạo wordpress
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d7397f40-529d-47e4-9176-150f8eb618b4" />

cài cloudflare tạo turner
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/86ec8104-1d5d-43df-88ba-587232d8d24a" />
sau đó thêm turner vào cấu trúc
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e0082dd4-c516-4b6f-b8ac-bb36ea6d35bb" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b4675099-cdcf-482a-800e-65d904134f92" />
tạo wordpress
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c29f18b8-06f0-4ef9-95be-2b206a0bd9ea" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/964c5621-f169-4b57-a0ff-d93737ed5723" />
