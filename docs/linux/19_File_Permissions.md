# File Permissions
## **1) Quyền truy xuất**
- Quyền truy xuất trên file và thư mục được trình bày khi thực hiện lệnh `ls -l`

    <img src=https://i.imgur.com/MudtSDu.png>

- Danh sách quyền truy xuất trình bày ở cột đầu tiên của kết quả . Các loại quyền truy xuất gồm :
    - **Read ( r ) :** cho phép đọc nội dung tập tin và xem nội dung của thư mục bằng lệnh
    - **Write ( w ) :** cho phép thay đổi nội dung hoặc xóa tập tin . Đối với thư mục , quyền này cho phép tạo , xóa hoặc đổi tên mà không phụ thuộc quyền sở hữu của thư mục chứa mình .
    - **Execute ( x ) :** cho phép thực thi chương trình , đối với thư mục , quyền này cho phép vào thư mục bằng lệnh `cd` .
- Quyền truy xuất gồm 3 nhóm :

    <img src=https://i.imgur.com/9k9Pv64.png>

    
    - Bảng cờ đặc tính ( ***flag*** ) :

        | Ký hiệu | Kiểu file |
        |---------|-----------|
        | `-` | Regular file |
        | `d` | Directory |
        | `l` | Symbolic link ( Soft link ) |
        | `b` | Block special file |
        | `c` | Character special file |
        | `p` | Named pipe |
        | `s` | Socket |

    - **Nhóm 1 :** Quyền của người sở hữu ( owner hoặc user ) , ký hiệu bằng kí tự `u` : người tạo ra thư mục / file hoặc được gán quyền sở hữu .
    - **Nhóm 2 :** Quyền của nhóm ( group ) ký hiệu bằng kí tự `g` : nhóm người sử dụng được gắn quyền .
    - **Nhóm 3 :** Quyền của người dùng khác ( others ) ký hiệu bằng kí tự `o` : là những người sử dụng khác không thuộc 2 nhóm trên . 
## **2) Biểu diễn quyền truy xuất**
- Biểu diễn quyền truy xuất có 2 cách : bằng chữ và bằng số
### **2.1) Bằng chữ**
- Trong cách biểu diễn này , quyền truy xuất được viết bằng các ký tự :
    - `r` : read
    - `w` : write
    - `x` : execute
    - `-` : không có quyền
    - **VD :**
        - `rwx` : có full quyền
        - `r--` : chỉ có quyền đọc
        - `rw-` : chỉ có quyền đọc và ghi
        - `---` : không có quyền gì
- Quyền hạn trên 1 file sẽ gồm cả 3 nhóm quyền ( **owner , group , others** ) nên danh sách quyền sẽ gồm `9` kí tự :
    - **VD :**
        - `rwxrw----` : người sở hữu có full quyền , các user cùng nhóm chỉ có quyền đọc/ghi còn mọi người khác không có quyền truy xuất .
        - `rw-r-----` : người sở hữu có quyền đọc/ghi , các user cùng nhóm chỉ có quyền đọc còn mọi người khác không có quyền truy xuất .
        - `rwxr-xr--` : người sở hữu có full quyền , các user cùng nhóm chỉ có quyền đọc và thực thi chương trình còn mọi người khác chỉ có quyền đọc .
### **2.2) Bằng số**
- Trong cách biểu diễn này , mỗi quyền được gán cho 1 trị số theo bảng sau : 

    | Quyền | Giá trị |
    |-------|---------|
    | `r` | `4` |
    | `w` | `2` |
    | `x` | `1` |

- Mỗi nhóm quyền truy xuất là tổng của các loại quyền trên :

    | Quyền | Ý nghĩa | Biểu diễn bằng số |
    |-------|---------|-------------------|
    | `rwx` | Có full quyền | `7` |
    | `rw-` | Chỉ có quyền đọc và ghi | `6` |
    | `r-x` | Chỉ có quyền đọc và thực thi | `5` |
    | `r--` | Chỉ có quyền đọc | `4` |
    | `---` | Không có quyền gì | `0` |

- Vì quyền thực sự gồm cả 3 nhóm quyền ( **owner , group , others** ) nên danh sách quyền biểu diễn dưới dạng số sẽ gồm `3` chữ số .
    - **VD :** 
        - `rwxrw----` ( `760` ) : người sở hữu có toàn quyền , các user cùng nhóm chỉ có quyền đọc/ghi còn mọi người khác không có quyền truy xuất .
        - `rw-r--r--` ( `644` ) : người sở hữu có quyền đọc/ghi , các user cùng nhóm chỉ có quyền đọc còn mọi người khác không có quyền truy xuất .
        - `rwxr-xr--` ( `754` ) : người sở hữu có toàn quyền , các user cùng nhóm chỉ có quyền đọc và thực thi chương trình còn mọi người khác chỉ có quyền đọc .
        > ***Lưu ý :** Người sử dụng có quyền đọc thì có quyền sao chép tập tin và tập tin sau khi sao chép sẽ thuộc về sở hữu của người thực hiện sao chép .*
## **3) Các lệnh về quyền**
### **3.1) `chmod`**
- Là lệnh thay đổi quyền truy xuất trên thư mục / tập tin
    ```
    # chmod [options] [mode] [file]
    ```
    - **Options :**
        - `-R` : áp dụng với mọi thư mục làm cho lệnh `chmod` có hiệu lực trên cả các thư mục con
    - **Mode :** Quyền truy xuất mới cho tập tin
        - `u` : quyền của người sở hữu ( **owner** )
        - `g` : quyền sở hữu của nhóm ( **group** )
        - `o` : quyền của mọi user khác ( **others** )
        - `+` : thêm quyền
        - `-` : rút bớt quyền
        - `=` : gán quyền
        - **VD :** 
            - `g+w` : thêm quyền ghi cho group
            - `o-rwx` : loại bỏ tất cả các quyền của các user khác
            - `u+x` : thêm quyền thực thi cho user
            - `+x` : thêm quyền thực thi cho cả
            - `a+rw` : thêm quyền đọc ghi cho tất cả
            - `ug+r` : thêm quyền đọc cho owner và group
            - `o=x` : chỉ cho phép mọi người thực thi
### **3.2) `chown`**
- Là lệnh thay đổi chủ sở hữu thư mục / tập tin ( **owner** )
    ```
    # chown [options] [owner] [file]
    ```
    - **Options :**
        - `-R` : áp dụng đối với thư mục làm cho lệnh `chown` có tác dụng trên cả các thư mục con
    - **Owner :** chủ sở hữu mới của tập tin
- Có thể thay đổi đồng thời chủ sở hữu và group sở hữu file
    ```
    # chown [options] [owner]:[group_owner] [file]
    ```

### **3.3) `chgrp`**
- Là lệnh thay đổi nhóm sở hữu thư mục / tập tin
    ```
    # chgrp [options] [group_owner] [file]
    ```
    - **Options :**
        - `-R` : áp dụng đối với thư mục làm cho lệnh `chgrp` có tác dụng trên cả các thư mục con
    - **Group_owner :** nhóm sở hữu mới của tập tin