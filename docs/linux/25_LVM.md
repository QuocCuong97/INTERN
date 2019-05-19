# LVM - Logical Volume Manager
- **Logical Volume Manager ( LVM )** là phương pháp cho phép ấn định không gian đĩa cứng thành những ***Logical Volume*** khiến cho việc thay đổi kích thước trở nên dễ dàng hơn so với ***partition*** .
- Với kỹ thuật **LVM** , có thể thay đổi kích thước phân vùng mà không cần phải sửa lại table của OS . Điều này rất hữu ích với trường hợp đã sử dụng hết phần bộ nhớ còn trống của partition và muốn mở rộng dung lượng của nó .
- Vai trò của **LVM** : **LVM** là kỹ thuật quản lý việc thay đổi kích thước lưu trữ của ổ cứng :
    - Không để hệ thống bị gián đoạn hoạt động
    - Không làm hỏng dịch vụ
    - Có thể kết hợp với cơ chế ***hot swapping*** ( phương pháp thay thế nóng các thành phần bên trong máy tính )
## **1) Mô hình các thành phần trong LVM**
### **1.1) Hard drives - Drives**
- Là các thiết bị lưu trữ dữ liệu , có dạng `/dev/xxxx`
### **1.2) Partition**
- Là các phân vùng của **hard drives** , mỗi **hard drive** có `4` **partition** trong đó **partition** bao gồm 2 loại là ***primary partition*** và ***extended partition*** :
- **Primary Partition** : 
    - Là phân vùng chính , có thể boot
    - Mỗi đĩa cứng có thể có tối đa `4` phân vùng này
- **Extended Partition** :
    - Là phân vùng mở rộng chứa dữ liệu , trong nó có thể tạo các **logical partition**
### **1.3) Physical Volume** 
- Là 1 tên gọi khác của **partition** trong kỹ thuật **LVM** , nó là những thành phần cơ bản được sử dụng bởi **LVM**
- Một **Physical Volume** không thể mở rộng ra ngoài phạm vi 1 ổ đĩa .
- Có thể kết hợp nhiều **Physical Volume** thành một **Volume Group** .
### **1.4) Volume Group**
- Nhiều **Physical Volume** trên những ổ đĩa khác nhau kết hợp lại thành 1 **Volume Group**
- **Volume Group** được dùng để tạo ra các **Logical Volume** , trong đó người dùng có thể tạo , thay đổi kích thước , gỡ bỏ và sử dụng .
> ***Lưu ý :** Boot Loader không thể đọc `/boot` khi nó nằm trên **Logical Volume Group** . Do đó không thể sử dụng **LVM** với **boot mount point*** .
### **1.5) Logical Volume**
- **Volume Group** được chia nhỏ thành các **Logical Volume** , mỗi **Logical Volume** có ý nghĩa tương tự 1 partition . Nó được dùng cho các mount point và được format với những định dạng khác nhau như `ext2` , `ext3` , `ext4` , `xfs` ,...
- Khi dung lượng của **Physical volume** được sử dụng hết ta có thể đưa thêm ổ đĩa mới bổ sung cho **Volume Group** và do đó tăng được dung lượng của **Logical Volume** .<br>**VD :** Có thể tạo ra 4 ổ đĩa mỗi ổ `5GB` , kết hợp thành 1 **Volume Group** `20G`  , có thể tạo ra 2 **Logical Volume** mỗi cái `10G` .
### **1.6) File Systems**
- Tổ chức và kiểm soát các tập tin
- Được lưu trữ trên ổ đĩa cho phép truy cập nhanh chóng và an toàn
- Sắp xếp dữ liệu đĩa cứng trên máy tính
- Quản lý vị trí vật lý của mọi thành phần dữ liệu
### **1.7) Physical Extend ( PE )**
- Là 1 đại lượng thể hiện 1 khối dữ liệu dùng làm đơn vị tính dung lượng của **Logical Volume** .
## **2) Ưu điểm và nhược điểm của LVM**
### **2.1) Ưu điểm**
- Có thể gom nhiều đĩa cứng vật lý lại thành 1 đĩa ảo dung lượng lớn
- Có thể tạo ra các vùng dung lượng lớn nhỏ tùy ý
- Có thể thay đổi các vùng dung lượng đó dễ dàng , linh hoạt
### **2.2) Nhược điểm**
- Các bước thiết lập phức tạp , khó khăn hơn
- Càng gắn nhiều đĩa cứng và thiết lập càng nhiều **LVM** thì hệ thống khởi động càng lâu
- Khả năng mất dữ liệu khi 1 trong các đĩa cứng vật lý bị hỏng
- Windows không thể nhận ra vùng dữ liệu của **LVM** . Nếu *dual-boot* Windows sẽ không thể truy cập dữ liệu chứa trong **LVM**
## **3) Các lệnh trong LVM**
- **Physical Volume** :
    - `pvcreate` : tạo **physical volume**
    - `pvdisplay` : xem **physical volume** đã tạo
    - `pvremove` : xóa **physical volume**
- **Volume Group** :
    - `vgcreate` : tạo **volume group**
    - `vgdisplay` : xem **volume group** đã tạo
    - `vgremove` : xóa **volume group**
    - `vgextend` : tăng dung lượng của **volume group**
    - `vgreduce` : giảm dung lượng của **volume group**
- **Logical Volume** :
    - `lvcreate` : tạo **logical volume**
    - `lvdisplay` : xem **logical volume** đã tạo
    - `lvremove` : xóa **logical volume**
    - `lvextend` : tăng dung lượng **logical volume**
    - `lvreduce` : giảm dung lượng **logical volume**