<p align="center">
 <h1 align="center">Tìm hiểu Docker compose </h1>
</p>

## Docker Compose là gì?

![image](https://github.com/thangdtph27626/LearnDockerCompose.github.io/assets/109157942/850a84bc-32a7-4001-b44b-05b0d4aca045)

Docker Compose là một công cụ giúp quản lý các container Docker trong một ứng dụng. Với Docker Compose, bạn có thể dễ dàng quản lý các container của ứng dụng mà không cần phải khởi động một container một cách thủ công.

Docker Compose cho phép bạn tạo và quản lý các container của ứng dụng trong một tệp YAML duy nhất. Tệp YAML này sẽ chứa thông tin về các container, các mối quan hệ giữa chúng và các cài đặt khác.

## Các tính năng của Docker Compose
Docker Compose cung cấp nhiều tính năng hữu ích để giúp bạn quản lý các ứng dụng của mình. Dưới đây là một số tính năng quan trọng của Docker Compose:

- Định nghĩa dịch vụ: Bạn có thể định nghĩa các dịch vụ khác nhau và cấu hình chúng bằng cách sử dụng Docker Compose. Ví dụ: bạn có thể định nghĩa một dịch vụ database và một dịch vụ web để triển khai ứng dụng của mình.
- Tự động tạo container: Docker Compose sẽ tự động tạo các container cần thiết để triển khai ứng dụng của bạn. Nó sẽ tạo các container dựa trên cấu hình mà bạn đã định nghĩa.
- Quản lý mạng: Docker Compose cung cấp các công cụ để quản lý mạng cho các container. Bạn có thể định nghĩa các mạng riêng để giữ cho các container của bạn an toàn và đảm bảo chúng không bị tấn công từ bên ngoài.
- Quản lý lưu trữ: Bạn có thể định nghĩa các khối lượng lưu trữ để sử dụng cho các container. Docker Compose sẽ giúp bạn quản lý các khối lượng lưu trữ này và đảm bảo chúng được lưu trữ và quản lý một cách an toàn và hiệu quả.
- Tích hợp với Docker Swarm: Docker Compose có thể tích hợp với Docker Swarm để triển khai ứng dụng của bạn trên một cụm máy chủ Docker. Điều này giúp bạn quản lý và mở rộng các ứng dụng của mình một cách dễ dàng.
- Khả năng mở rộng: Docker Compose cho phép bạn mở rộng ứng dụng của mình bằng cách thêm các dịch vụ mới hoặc tăng số lượng container cho các dịch vụ hiện có. Điều này giúp bạn quản lý tốt hơn sự tăng trưởng của ứng dụng của mình.

##  Những lưu ý quan trọng khi sử dụng Docker Compose
- Đặt tên cho các container: Để dễ dàng quản lý các container, bạn nên đặt tên cho chúng. Điều này sẽ giúp bạn xác định được container nào đang chạy trong ứng dụng của bạn.
- Sử dụng mạng riêng: Khi sử dụng Docker Compose, bạn nên sử dụng một mạng riêng để giữ cho các container của bạn an toàn và được cô lập khỏi mạng bên ngoài.
- Sử dụng các biến môi trường: Sử dụng các biến môi trường trong tệp YAML của bạn để tránh lưu trữ các thông tin nhạy cảm trong tệp YAML. Các biến môi trường có thể được đặt trong một tệp .env riêng biệt.
- Để tránh xung đột khi khởi động container, bạn nên đặt các cổng cho container của mình trong tệp YAML. Bạn nên sử dụng cổng được khuyến nghị của Docker.
- Các lệnh Docker Compose có thể được thực thi thông qua một Makefile. Điều này giúp cho việc sử dụng Docker Compose trở nên đơn giản và hiệu quả hơn.

## Các bước sử dụng Docker Compose 

### Bước 1: Tạo tệp YAML

Đầu tiên, chúng ta cần tạo một tệp YAML để định nghĩa các container cho ứng dụng của chúng ta. Dưới đây là ví dụ về tệp YAML cho ứng dụng của chúng ta

```

version: '3'
services:
  web:
    build: .
    ports:
      - "3000:3000"
    depends_on:
      - db
  db:
    image: mongo
    ports:
      - "27017:27017"

```

> bạn có thể tìm hiểu tạo docker compose [tại đây](https://www.baeldung.com/ops/docker-compose)

### Bước 2: Khởi động các container
Sau khi chúng ta đã định nghĩa các container trong tệp YAML, chúng ta có thể sử dụng lệnh docker-compose up để khởi động các container của chúng ta. Docker Compose sẽ tự động tải xuống các hình ảnh và khởi động các container cho chúng ta.

### Bước 3: Kiểm tra trạng thái của các container
Sau khi chúng ta đã khởi động các container, chúng ta có thể sử dụng lệnh docker-compose ps để kiểm tra trạng thái của các container.

### Bước 4: Dừng các container
Khi chúng ta đã hoàn thành việc sử dụng các container, chúng ta có thể sử dụng lệnh docker-compose down để dừng các container.

## Kết luận
Trên đây là bài viết giới thiệu về Docker Compose là gì và cách sử dụng nó. Chúng tôi hy vọng bài viết này đã giúp bạn hiểu rõ hơn về Docker Compose và cách sử dụng nó để quản lý các ứng dụng Docker. Nếu bạn gặp bất kỳ vấn đề hoặc thắc mắc nào trong quá trình sử dụng Docker Compose, hãy truy cập trang chủ của Docker để tìm kiếm thông tin hỗ trợ hoặc đặt câu hỏi trên các diễn đàn hoặc cộng đồng liên quan đến Docker.
