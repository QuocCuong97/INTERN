# Users and Groups
## **1) Quản trị Users**
- Trên Linux có 2 loại user :
    - **User hệ thống**
    - **User người dùng**
- **User hệ thống** : dùng để thực thi các module , script cần thiết phục vụ cho hệ điều hành .
- **User người dùng** : là những tài khoản để login sử dụng hệ điều hành .
- Trong các tài khoản người dùng thì tài khoản user `root` ( ***super user*** ) là tài khoản quan trọng nhất :
    - Tài khoản này được tự động tạo ra khi cài đặt Linux . 
    - Tài khoản này không thể đổi tên hoặc xóa bỏ .
    - User `root` còn gọi là ***super user*** vì nó có full quyền trên hệ thống .
    - Chỉ làm việc với user `root` khi muốn thực hiện công tác quản trị hệ thống , trong các trường hợp khác , chỉ nên làm việc với user thường .
- Mỗi user thường có đặc điểm như sau :
    - Tên tài khoản user là duy nhất , có thể đặt tên *chữ thường , chữ hoa* .
    - Mỗi user có 1 mã định danh duy nhất ( **uid** ) .
    - Mỗi user có thể thuộc về nhiều group .
    - Tài khoản ***super user*** có **uid**=**gid**=`0` .
### **1.1) File `/etc/passwd`**
- Là file văn bản chứa thông tin về các tài khoản user trên máy .
- Mọi user đều có thể đọc tập tin này nhưng chỉ có user `root` mới có quyền thay đổi .
- Để xem nội dung file ta dùng lệnh :
    ```
    # cat /etc/passwd
    ```
- Cấu trúc file gồm nhiều hàng , mỗi hàng là 1 thông tin của user . Dòng đầu tiên của tập tin mô tả thông tin cho user `root` ( có **uid**=`0` ) , tiếp theo là các tài khoản khác của hệ thống , cuối cùng là tên các tài khoản người dùng bình thường . Mỗi hàng được chia thành `7` cột cách nhau bằng dấu `:` <br><br>
    <img src=https://i.imgur.com/yF07I26.png>
- Ý nghĩa các cột trong file :
    - `1` - Tên user ( ***login name*** )
    - `2` - Mã liên quan đến mật khẩu ( `x` cho Linux )
    - `3` - User ID ( ***uid*** )
    - `4` - Group ID ( ***gid*** )
    - `5` - Tên mô tả người sử dụng ( ***comment*** )
    - `6` - Thư mục home của user ( thường là `/home/user_name` )
    - `7` - Loại shell sẽ hoạt động khi user login , thường là `/bin/bash`
