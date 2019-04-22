# **VMware Workstation 15**
>## **1) Hướng dẫn cài đặt**
- Truy cập URL: https://my.vmware.com/en/web/vmware/info/slug/desktop_end_user_computing/vmware_workstation_pro/15_0 để download `VMware Workstation 15`
- Click vào file `vmware_workstation.exe` đã download
<img src=../images/vmware/1.jpg>
<img src=../images/vmware/2.jpg>
<img src=../images/vmware/3.jpg>
<img src=../images/vmware/4.jpg>
<img src=../images/vmware/5.jpg>
<img src=../images/vmware/6.jpg>
<img src=../images/vmware/7.jpg>
<img src=../images/vmware/8.jpg>

 Nhập Licence Key ` FC51U-43Z0L-H85TZ-NZQ5G-PZUW6 ` để kích hoạt bản Pro

 >## **2) Phân biệt các loại card mạng trong VMware**
 ### **Bridge**
 Ở chế độ này thì card mạng trên máy ảo được gắn vào VMnet0 và VMnet0 này liên kết trực tiếp với card mạng vật lý. Ở chế độ này máy ảo sẽ kết nối internet thông qua lớp card mạng vật lý và có chung lớp mạng với card mạng vật lý.

 <img src=../images/vmware/Bridge.png>

 ### **NAT**
 Ở chế độ này thì card mạng của máy ảo kết nối với VMnet8, VMnet8 cho phép máy ảo đi internet thông qua cơ chế NAT (NAT device). Lúc này lớp mạng bên trong máy ảo khác hoàn toàn với lớp mạng của card vật lý bên ngoài. IP của card mạng sẽ được cấp bởi DHCP VMnet8 cấp. trong trường hợp bạn muốn thiết lập IP tĩnh cho card mạng máy ảo bạn phải đảm bảo chung lớp mạng với VMnet8 thì máy ảo mới có thể đi internet.

 <img src=../images/vmware/NAT.png>

 ### **Host-only**
 ở cơ chế này máy ảo được kết nối với VMnet có tính có tính năng Host-only, trong trường hợp hình này là VMnet1 (bạn có thể add nhiều VMnet Host-only). VMnet Host-only kết nối ra một card mạng ảo tương ứng ngoài máy thật.( khi ta add một VMnet thì có một card tương ứng với VMnet sẽ được tạo ra)

<img src=../images/vmware/Host-only.png>

 ### **Custom** : VLAN
 ### **LAN Segment**
 Các card mạng của máy ảo có thể gắn kết với nhau thành từng LAN Segment. Không giống như VMnet, LAN Segment chỉ kết nối các máy ảo được gán trong một LAN Segment lại với nhau mà không có những tính năng như DHCP và LAN Segment không thể kết nối ra máy thật như các Virtual Switch VMnet.
