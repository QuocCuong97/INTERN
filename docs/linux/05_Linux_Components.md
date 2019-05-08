# Cấu trúc hệ điều hành Linux
- Kiến trúc hệ điều hành **Linux** chia thành 3 phần : **Kernel** , **Shell** , **Application**

<p align=center><img src=https://i.imgur.com/rxmES6P.png width=50%><p>

> ## **1) Kernel ( nhân )**
- Đây là phần quan trọng và được ví như trái tim của hệ điều hành .
- Phần **kernel** chứa các module , thư viện để quản lý và giao tiếp với phần cứng và các ứng dụng .
- **Kernel** trên **CentOS** 7 có version `3.10.0` .
> ## **2) Shell**
- **Shell** là 1 chương trình có chức năng thực thi các command từ người dùng hoặc từ các ứng dụng - tiện ích yêu cầu chuyển đến cho **Kernel** xử lý .
- Bên cạnh đó , **Shell** còn có khả năng bảo vệ **Kernel** từ các yêu cầu không hợp lệ .
- Có các loại **shell** : 
    - ***sh ( the Bourne Shell )*** : đây là **shell** nguyên thủy của **UNIX** được viết bởi Stephen Bournevào năm `1974` . Đến nay **shell sh** vẫn được sử dụng rộng rãi .
    - ***bash ( Bourne-again Shell )*** : là **shell** mặc định trên **Linux** được viết bởi Brian Fox .
    - ***csh ( the C shell )*** : **shell** được viết bằng ngôn ngữ lập trình C , được viết bởi Bill Joy năm `1978` .
    - Ngoài ra còn có các loại **shell** khác như ***ash ( the Almquist shell )*** , ***tsh ( the TENEX shell )*** , ***zsh ( the Z shell )*** .
- Khi làm việc với user **root** , dấu nhắc **shell** có dạng :
    ```
    [root@localhost ~]#
    ```
- Khi làm việc với user thường , dấu nhắc **shell** có dạng :
    ```
    [username@localhost root]$
    ```
> ## **3) Applications**
- Là các ứng dụng và tiện ích mà người dùng cài đặt trên Linux .<br> **VD :** ftp , samba , proxy ,...