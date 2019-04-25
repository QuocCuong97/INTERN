# EIGRP - Enhanced Interior Gateway Protocol ( D )
> ## **1) Đặc điểm**
- **EIGRP** là 1 giao thức định tuyến do Cisco phát triển , chỉ chạy trên các sản phẩm của Cisco
- Là giao thức định tuyến lai ( là 1 giao thức **Distance-Vector** nhưng lại có đặc điểm của giao thức **Link-State** )
- Sử dụng số IP **protocol-id** là `88`
- Sử dụng thuật toán ***DUAL*** - ***Diffusing Update Algorithym*** để tính toán đường đi và chống loop
- Hội tụ nhanh
- Hỗ trợ xác thực ***MD5***
- Hỗ trợ **VLSM**
- Theo mặc định , cân bằng tải với các đường có `metric` bằng nhau . Có thể cân bằng tải với các đường có `metric` không bằng nhau
- Chỉ số **AD** của **EIGRP** là `90` cho các Router *Internal* và là `170` cho các Router `External`
- Khả năng mở rộng cao , được sử dụng trong các mạng lớn
- Địa chỉ Multicast `224.0.0.10`
- Sử dụng 1 công thức tính toán `metric` rất phức tạp dựa trên nhiều thông số : `bandwidth` , `delay` , `load` , `reliability` , `MTU ` và bộ tham số `k` tương ứng
> ## **2) Hoạt động của EIGRP**