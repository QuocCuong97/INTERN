# Network Configurations
## **MỤC LỤC**
![### **1) Các file cấu hình Network**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#1-c%C3%A1c-file-c%E1%BA%A5u-h%C3%ACnh-network-1)
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.1) `/etc/hosts`**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#11-etchosts)<br>
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.2) `/etc/resolv`**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#12-etcresolv)<br> 
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.3) `/etc/sysconfig/network-scripts/ifcfg-[tên_card_mạng]`**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#13-etcsysconfignetwork-scriptsifcfg-t%C3%AAn_card_m%E1%BA%A1ng)<br>
![### **2) Các lệnh Network cơ bản**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#2-c%C3%A1c-l%E1%BB%87nh-network-c%C6%A1-b%E1%BA%A3n-1)
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.1) Xem địa chỉ IP**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#21-xem-%C4%91%E1%BB%8Ba-ch%E1%BB%89-ip)<br>
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.2) Tắt / Bật card mạng**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#22-t%E1%BA%AFt--b%E1%BA%ADt-card-m%E1%BA%A1ng)<br>
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.3) Khởi động lại `network.service`**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#23-kh%E1%BB%9Fi-%C4%91%E1%BB%99ng-l%E1%BA%A1i-networkservice)<br>
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2.4) Xem thông tin gateway**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#24-xem-th%C3%B4ng-tin-gateway)<br>
![### **3) Cấu hình IP**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#3-c%E1%BA%A5u-h%C3%ACnh-ip-1)
![&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**3.1) Cấu hình bằng lệnh ( tạm thời )**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#31-c%E1%BA%A5u-h%C3%ACnh-b%E1%BA%B1ng-l%E1%BB%87nh--t%E1%BA%A1m-th%E1%BB%9Di-) <br>
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.2) Cấu hình bằng file**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#32-c%E1%BA%A5u-h%C3%ACnh-b%E1%BA%B1ng-file) <br>
![**&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.3) Cấu hình bằng giao diện GUI**](https://github.com/QuocCuong97/INTERN/blob/master/docs/linux/12_Network_Configuration.md#33-c%E1%BA%A5u-h%C3%ACnh-b%E1%BA%B1ng-giao-di%E1%BB%87n-gui) <br>

-------
## **1) Các file cấu hình Network**
### **1.1) `/etc/hosts`**
- Dùng để phân giải những hostname không thể phân giải được .
- Có thể dùng thay DNS trong hệ thống mạng LAN
    - `127.0.0.1` <=> `localhost.localdomain`
    - `::1` <=> `localhost.localdomain`<br><br>
<img src=https://i.imgur.com/4Mg2DpV.png>
### **1.2) `/etc/resolv`**
- Cấu hình DNS
### **1.3) `/etc/sysconfig/network-scripts/ifcfg-[tên_card_mạng]`**
- Chứa thông tin cấu hình của từng card mạng
    - `ens33` : ethernet ( có sẵn )
    - `sl*` : serial line IP
    - `wl*` : wlan ( wifi )
    - `ww*` : wwan ( wireless WAN - 3G/4G )
    - `virbr0` : bridge ( có sẵn )
    - `lo*` : loopback ( có sẵn )
## **2) Các lệnh Network cơ bản**
### **2.1) Xem địa chỉ IP**
```
# ifconfig       ( Ethernet + Loopback )
# iwconfig       ( Wifi )
# ifconfig -a    ( đầy đủ thông tin )
# ip a s         ( đầy đủ thông tin )
```
<img src=https://i.imgur.com/Bkm0Crs.png>

### **2.2) Tắt / Bật card mạng**
```
# ifup [tên_card_mạng]       : bật card mạng
# ifdown [tên_card_mạng]     : tắt card mạng
```
### **2.3) Khởi động lại `network.service`**
```
    # service network restart
<=> # /etc/init.d/network restart
<=> # systemctl restart network.service
```
### **2.4) Xem thông tin gateway**
```
# route
# ip route
```
<br>
    <img src=https://i.imgur.com/WOSYkSb.png>

## **3) Cấu hình IP**
### **3.1) Cấu hình bằng lệnh ( tạm thời )**
```
# ifconfig [tên_card_mạng] [IP] netmask [subnet_mask] up
```
> ***Chú ý*** : IP sẽ mất mỗi khi tắt mở card mạng hay restart `network.service` . Đây còn gọi là cách đặt IP tạm thời , thường dùng để test .
### **3.2) Cấu hình bằng file**
- Thay đổi nội dung trong file cấu hình của card mạng :
```
# vi etc/sysconfig/network-scripts/ifcfg-[tên_card_mạng]
```
<img src=https://i.imgur.com/Rbr32T6.png>

- Ý nghĩa các thông số trong file :
    - `DEVICE` : tên của card mạng
    - `ONBOOT` :
        - `yes` : Khởi động khi restart `network.service`
        - `no` : không khởi động khi restart `network.service`
    - `BOOTPROTO` : 
        - `static` : dùng IP tĩnh
        - `dhcp` : nhận IP từ DHCP Server
    - `IPADDR` : địa chỉ IP của card mạng ( khi cấu hình IP tĩnh )
    - `NETMASK` : địa chỉ subnetmask ( khi cấu hình IP tĩnh )
    - `GATEWAY` : địa chỉ gateway ( khi cấu hình IP tĩnh )
    - `DNS[1|2]` : địa chỉ DNS Server ( khi cấu hình IP tĩnh )
    - `USERCTL` :
        - `yes` : cho phép user thường cấu hình sửa đổi
        - `no` : không cho phép user thường cấu hình sửa đổi
- **VD :** Thiết lập IP tĩnh cho Server với IP `10.10.10.10/24` , gateway `10.10.10.254` , DNS là `8.8.8.8` , `8.8.8.4`
```
DEVICE=ens33
ONBOOT=yes
BOOTPROTO=static
IPADDR=10.10.10.10
NETMASK=255.255.255.0
GATEWAY=10.10.10.254
DNS1=8.8.8.8
DNS2=8.8.4.4
USERCTL=no
```
- **VD :** Thiết lập IP động
```
DEVICE=ens33
ONBOOT=yes
BOOTPROTO=dhcp
USERCTL=no
```
### **3.3) Cấu hình bằng giao diện GUI**
- Trong Terminal gõ lệnh `# nmtui`
- Cửa sổ **NetworkManager TUI** hiện ra , chọn ***Edit a connection*** => ***OK***<br><br>
    <img src=https://i.imgur.com/DmkBT3j.png>

- Chọn Card mạng cần đặt IP ( ens33 ) :

    <img src=https://i.imgur.com/17eijW6.png>

- Chọn ***IPV4 CONFIGURATION*** => ***Manual*** => ***&lt;Show&gt;***

    <img src=https://i.imgur.com/RSVrpJd.png>

- Đặt các thông số IP => ***OK***

    <img src=https://i.imgur.com/rbU1tFV.png>
