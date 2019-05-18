# Linux Partition
## **1) MBR và GPT**
- Là 2 tiêu chuẩn ổ cứng quy định cách thức nhập xuất dữ liệu , sắp xếp và phân vùng ổ đĩa .
- **MBR ( Master Boot Record )** : là `512 bytes` đầu tiên của 1 thiết bị lưu trữ . Nó chứa hệ thống nạp khởi động và **partition table** của ổ cứng . Nó đóng vai trò quan trọng trong quá trình khởi động hệ thống **BIOS** .
    - Hỗ trợ ổ cứng tối đa `2TB` 
    - Hỗ trợ tối đa `4` phân vùng / `1` ổ đĩa ( `3` **primary** + `1` **extended** )
- **GPT ( GUID Partition Table )** : là chuẩn mới thay thế cho **MBR** . Nó kết hợp với **UEFI** - đang thay thế **BIOS** trên nhiều mainboard
    - Hỗ trợ ổ cứng tối đa `1ZB` ( = `1 tỷ TB` )
    - Hỗ trợ tối đa `128` phân vùng / `1` ổ đĩa ( `128` **primary** )
    - Chỉ hỗ trợ các máy tính dùng chuẩn **UEFI**
## **2) Công cụ phân vùng ổ cứng**
### **2.1 ) `fdisk`**
- Chỉ để tạo phân vùng dưới `2TB`
- Chỉ hỗ trợ ổ cứng chuẩn **MBR** 
- Cấu trúc lệnh :
    ```
    # fdisk [options] [/dev/...]
    ```
    - **Options :** `-l` : liệt kê tất cả các ổ cứng và các partition
    - **Command** sử dụng trong lệnh :
        - `n` : tạo mới 1 partition
        - `p` : hiển thị **partition table**
        - `q` : thoát mà không lưu thay đổi
        - `w` : lưu thay đổi và thoát
        - `d` : xóa 1 partition
### **2.2) `gdisk`**
- Hỗ trợ ổ cứng chuẩn **GPT**
- Cấu trúc lệnh :
    ```
    # gdisk [options] [/dev/...]
    ```
    - **Options :** 
        - `-l` : liệt kê các ổ cứng và phân vùng chuẩn **GPT**
        - `-g` : chuyển ổ cứng từ **MBR** sang **GPT**
        - `-m` : chuyển ổ cứng từ **GPT** sang **MBR**
    - **Command** : tương đương lệnh `fdisk`
### **2.3) `parted`**
- Tên đầy đủ là **GNU Parted 3.x**
- Hoạt động với tất cả các chuẩn ổ cứng như **MBR** , **GPT** ,...
- Hỗ trợ nhiều tính năng hơn `fdisk` và cũng dễ sử dụng hơn .
- Cấu trúc lệnh : 
    ```
    # parted [options] [/dev/...]
    ```
    - **Options :** 
        - `-l` : liệt kê các ổ cứng và phân vùng
        - `-v` : hiển thị version của **GNU Parted**
    - **Command** :
        - `mkpart [type] [start] [end]` : tạo 1 phân vùng mới
            - **Type** : "`btrfs`" , "`ext3`" , "`ext4`" , "`fat16`" , "`fat32`" , "`hfs`" , "`linux-swap`" , "`ntfs`" , "`reiserfs`" , "`xfs`" + "`primary`" , "`logical`" , "`extended`"

