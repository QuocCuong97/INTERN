# Swap file
- **Swap** là khái niệm bộ nhớ ảo được sử dụng trên Linux . Khi VPS / Server hoạt động , nếu hết RAM hệ thống sẽ tự động dùng 1 phần ổ cứng để làm bộ nhớ cho các ứng dụng hoạt động .
- Với những server không có **swap** , khi hết RAM hệ thống thường tự động *stop service* **MySQL** do đó hay xuất hiện thông báo lỗi "*Establishing a Database Connection*"
- Do sử dụng ổ cứng có tốc độ chậm hơn RAM , nhất là những Server không dùng **SSD** , do đó không nên thường xuyên sử dụng **swap** , sẽ làm giảm hiệu năng hệ thống .
- Với các VPS dùng công nghệ ảo hóa **OpenVZ** , có thể sẽ không tạo được **swap** do hệ thống đã tự động kích hoạt sẵn .
## **Các bước tạo Swap file**
- **B1 :** Kiểm tra phân vùng **swap** :
    ```
    # swapon -s
    ```
- **B2 :** Kiểm tra dung lượng còn trống trên ổ cứng :
    ```
    # df -h
    ```
- **B3 :** Tạo file **Swap** :
    ```
    # dd if=/dev/zero of=/var/swapfile bs=1M count=2048
    ```
    - Trong đó :
        - `bs` là đơn vị tính ( `M` , `G` , `K`)
        - `count` là số lượng `bs` cấp cho **swap file**<br>=> **swap file** có dung lượng = `count*bs`
- **B4 :** Tạo phân vùng **swap** :
    ```
    # mkswap /var/swapfile
    ```
- **B5 :** Kích hoạt **swap** :
    ```
    # swapon /var/swapfile
    ```
- **B6 :** Kiểm tra lại trạng thái **swap** :
    ```
    # swapon -s
    ```
- **B7 :** Lưu cấu hình vào file `/etc/fstab` :
    ```
    # echo /var/swapfile none swap defaults 0 0 >> /etc/fstab
    ```
- **B8 :** Bảo mật file **swap** :
    ```
    # chown root:root /var/swapfile
    # chmod 0600 /var/swapfile
    ```