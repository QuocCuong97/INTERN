# **CentOS 7**
## 1) Giới thiệu `CentOS 7`
## 2) Hướng dẫn cài đặt `CentOS 7` trên `VMware Workstation 15`
- Download file ISO của CentOS 7 Minimal tại URL: http://mirror.ehost.vn/centos/7.6.1810/isos/x86_64/CentOS-7-x86_64-Minimal-1810.iso
- Mở phần mềm VMware Workstation và tiến hành cài đặt máy ảo:
<img src=../images/centos7/Screenshot_0.png>
<img src=../images/centos7/Screenshot_1.png>
<img src=../images/centos7/Screenshot_2.png>
<img src=../images/centos7/Screenshot_3.png>
<img src=../images/centos7/Screenshot_4.png>
<img src=../images/centos7/Screenshot_5.png>
<img src=../images/centos7/Screenshot_6.png>
<img src=../images/centos7/Screenshot_7.png>
<img src=../images/centos7/Screenshot_8.png>
<img src=../images/centos7/Screenshot_9.png>
<img src=../images/centos7/Screenshot_10.png>
<img src=../images/centos7/Screenshot_11.png>
<img src=../images/centos7/Screenshot_12.png>
<img src=../images/centos7/Screenshot_13.png>
<img src=../images/centos7/Screenshot_14.png>
<img src=../images/centos7/Screenshot_15.png>
<img src=../images/centos7/Screenshot_16.png>
=> Kết quả
<img src=../images/centos7/Screenshot_17.png>
- Bật máy ảo và cài đặt ban đầu cho CentOS 7

    Click   `Power on this virtual machine`
    <img src=../images/centos7/Screenshot_18.png>

    Chọn ngôn ngữ . Thường là English (United States) - Anh Mỹ

    <img src=../images/centos7/Screenshot_19.png>

    Chọn thẻ DATE & TIME để cài đặt thời gian

    <img src=../images/centos7/Screenshot_20.png>

    Chọn Vùng (Region) là Asia, City : Ho Chi Minh City

    <img src=../images/centos7/Screenshot_21.png>

    Chọn thẻ INSTALLATION DESTINATION. Đây là bước phân vùng giống như trong Windows.

    <img src=../images/centos7/Screenshot_23.png>

    Chọn "I will configure partitioning" để phân vùng bằng tay.

    <img src=../images/centos7/Screenshot_24.png>

    Chọn kiểu phân vùng là Standard Partition

    <img src=../images/centos7/Screenshot_25.png>

    Tạo phân vùng đầu tiên là /boot. Đây là phân vùng chứa các thành phần liên quan đến quá trình khởi động của CentOS. Để dung lượng của phân vùng này là 500M.

    <img src=../images/centos7/Screenshot_26.png>

    Tạo phân vùng thứ 2 là swap. Swap là lượng RAM ảo sử dụng dung lượng từ ổ cứng cấp cho CentOS để phòng trường hợp hết RAM. Thông thường để dung lượng swap = 2*RAM

    <img src=../images/centos7/Screenshot_27.png>

    Cấp cho swap 2GB dung lượng ổ cứng

    <img src=../images/centos7/Screenshot_28.png>

    Phân vùng cuối cùng cần tạo là / .Là phân vùng chứa tất cả các folder trong CentOS. Để trống phân "Desired Capacity" để cấp cho / toàn bộ dung lượng còn lại của ổ đĩa.

    <img src=../images/centos7/Screenshot_29.png>
    <img src=../images/centos7/Screenshot_30.png>

    Chọn Accept Changes để hoàn tất quá trình cài đặt.

    <img src=../images/centos7/Screenshot_31.png>

    
    <img src=../images/centos7/Screenshot_32.png>
    <img src=../images/centos7/Screenshot_33.png>
    <img src=../images/centos7/Screenshot_34.png>
    <img src=../images/centos7/Screenshot_35.png>
    <img src=../images/centos7/Screenshot_36.png>
    <img src=../images/centos7/Screenshot_37.png>
    <img src=../images/centos7/Screenshot_38.png>
    <img src=../images/centos7/Screenshot_39.png>
    <img src=../images/centos7/Screenshot_40.png>
    <img src=../images/centos7/Screenshot_41.png>
    <img src=../images/centos7/Screenshot_42.png>

