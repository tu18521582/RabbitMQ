# RabbitMQ

- RabbitMQ là một AMQP message broker hay còn gọi là phần mềm quản lý hàng đợi message.
- RabbitMQ như là một hộp thư nơi mà xếp chồng các bức thư. RabbitMQ sau đó lấy từng bức thư và đưa nó đến đích của nó.

# Tại sao cần dùng RabbitMQ?
- Trong một hệ thống lớn, có rất nhiều thành phần. Nếu muốn các thành phần này giao tiếp được với nhau thì chúng phải biết nhau. Nhưng điều này gây rắc rối cho việc viết code. Một thành phần phải biết quá nhiều đâm ra rất khó maintain, debug. Với sự tham gia của message broker thì producer sẽ không hề biết consumer. Nó chỉ việc gửi message đến các queue trong message broker. Consumer chỉ việc đăng ký nhận message từ các queue này.
- Vì producer giao tiếp với consumer trung gian qua message broker nên dù producer và consumer có khác biệt nhau về ngôn ngữ thì giao tiếp vẫn thành công. Dù viết bằng java, python hay php... thì chỉ cần thỏa mãn giao thức với message broker thì thông suốt hết. Hiện nay, rabbitmq cũng đã cung cấp client library cho khá nhiều  ngôn ngữ. Tính năng này cho phép tích hợp hệ thống linh hoạt.

# Cấu trúc cơ bản của RabbitMQ:
![Imgur Image](https://www.cloudamqp.com/img/blog/exchanges-bidings-routing-keys.png)
## Producer
Thành phần thực hiện quá trình gửi tin lên RabbitMQ

## Queue
Là nơi lưu trữ các tin theo nguyên tắc FIFO

## Consumer
Thành phần thực hiện việc lấy các tin từ queue về

## Exchange
Nhận message từ producer và đẩy chúng đến hàng đợi dựa trên những nguyên tắc của từng loại exchange hiện tại

![](src/main/java/com/mycompany/app/image/image-demo.png)
