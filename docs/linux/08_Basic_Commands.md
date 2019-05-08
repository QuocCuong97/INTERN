# Các lệnh Linux cơ bản
- Dòng lệnh **shell** có dạng tổng quát như sau :
<p align=center><strong><i>command &emsp;&emsp;[option]&emsp;&emsp;arguments</i></strong></p>

- Trong đó :
    - ***command***  - tên lệnh
    - ***options*** - các tùy chọn , thường bắt đầu bằng `-` hoặc `--` . Nhiều tùy chọn có thể kết hợp bằng 1 kí hiệu `-` <br>**VD :** `ls -l -a` <=> `ls -la`
    - ***arguments*** - tham số lệnh
> **Chú ý** : dòng lệnh shell có phân biệt *chữ thường* và *chữ hoa*
## **1) Lệnh trợ giúp : `man`  ( manual )**
```
                #  man <tên lệnh>
```
- Sử dụng "&uarr;" , "&darr;" hoặc `PgUp` , `PgDn` để di chuyển trong các trang manual .
- Gõ `Shilf` + `G` để đi đến cuối trang manual .
- Gõ `G` để đi lên đầu trang manual .
- Gõ `/` + `Từ khóa` để tìm kiếm trong manual , sau đó gõ `n` để đi đến từng kết quả tìm kiếm , gõ `Shift` + `n` để đến kết quả tìm kiếm trước đó .
- Gõ `q` để thoát trợ giúp lệnh .
## **2) Các lệnh file system thiết yếu**
### **2.1) `pwd` ( print name of current/working directory )**
- Cho biết thư mục hiện hành đang làm việc .
### **2.2) `cd` ( change directory )**
- Dùng để chuyển vị trí làm việc sang thư mục khác .
    ```
    # cd [path]
    ```
    - `cd /etc` - Chuyển đến thư mục `/etc` ( thư mục bất kỳ - đường dẫn tuyệt đối )
    - `cd usr` - Chuyển đến thư mục `usr` là thư mục con của thư mục hiện hành - đường dẫn tương đối )
    - `cd ..` - Chuyển đến thư mục cha
    - `cd` - Chuyển đến thư mục home của user hiện tại
    - `cd ~` - Chuyển đến thư mục home của user hiện tại
    - `cd -` - Chuyển đến thư mục mình vừa rời đi trước đó
    - `/` -> `cd /etc/sysconfig/network-scripts` -> `cd .. / .. / ..` -> `/`
### **2.3) `ls` ( list directory contents )**
- Dùng để xem ( liệt kê ) nội dung thư mục

    ``# ls [options] [path]``
    - **Options** : 
        - `-l` : liệt kê chi tiết
        - `-a` : liệt kê tất cả các file ẩn<br>
        ( `ls -l` = `ll`  ;  `ls -l -a` = `ls -la` )
        - `-tr` : liệt kê các file theo thứ tự thời gian mới nhất dưới cùng
        - `-h` : liệt kê file size theo định dạng quen thuộc ( `K M G` )
        - `-S` : sắp xêp kích cõ file từ cao xuống thấp
        - `-t` : tìm file được chỉnh sửa gần nhất

- Ý nghĩa các cột kết quả khi thực hiện lệnh `ls -l` :

    <p align=center><img src=https://i.imgur.com/MnjXLvf.png width=100%></p>

    | STT | Meanings |
    |-----|----------|
    | 1 | File type and access permission |
    | 2 | Number of Hardlink to the file |
    | 3 | Owner and the creator of the file |
    | 4 | Group of the owner |
    | 5 | File size in Bytes |
    | 6 | Date and Time |
    | 7 | Directory or File Name |
- Tìm file được chỉnh sửa gần nhất :

    `# ls -t | head -1`<br>`install.log`
- Lấy tên file , thư mục cách nhau bằng dấu `,` ; `""` ; `''` :

    `# ls -1m`<br>`install.log, install.logold, music`<br>`# ls -1mQ`<br>`"install.log", "install.logold", "music"`<br>`# ls -1m --qouting-style='shell-always`<br>`'install.log', 'install.logold', 'music'`

- Liệt kê những file có tên tương tự theo ý muốn :

    `# ls -l insta*`<br>`-rw-r--r- 1 root root 102092 Dec 18 11:57 install.log`<br>`-rw-r--r- 1 root root 102092 Dec 16 17:26 install.log`

    

