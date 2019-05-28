# Network Advanced
## **1) `ping`**
- Lệnh `ping` gửi các gói `ECHO_REQUEST` tới địa chỉ chỉ định .
- Lệnh này nhằm kiểm tra máy tính có thể kết nối với Internet hay một địa chỉ IP cụ thể nào đó hay không .
- Không giống lệnh `ping` trên Windows , câu lệnh `ping` trên Linux sẽ duy trì gửi các gói tin cho đến khi bạn kết thúc nó . Có thể định số lượng gói tối đa gửi đi bằng cách gõ thêm tùy chọn `–c` .
    ```
    # ping -c [number] [IP/domain_destination]
    ```
    <img src=https://i.imgur.com/aL5MaMZ.png>

## **2) `tracepath / traceroute`**
- Dùng để lần dấu đường đi trên mạng tới một đích chỉ định và báo cáo về mỗi **hop** dọc trên đường đi .

    <img src=https://i.imgur.com/JAt2lNY.png>

    <img src=https://i.imgur.com/ipPLmOk.png>

## **3) `mtr`**
- Là sự kết hợp `ping` và `tracepath` trong một câu lệnh .
- `mtr` sẽ gửi liên tục các gói và hiển thị thời gian `ping` cho mỗi **hop** . 
- Câu lệnh cũng giúp phát hiện một số vấn đề mạng qua tỉ lệ **Loss%** .
- Gõ `q` để thoát khỏi tiến trình .
    ```
    # mtr [IP/Domain_destination]
    ```
    <img src=https://i.imgur.com/eU0hPDC.png>

## **4) `host`**
- Lệnh `host` sẽ thực hiện tìm kiếm DNS . 
- Nhập vào tên miền khi muốn xem địa chỉ IP đi kèm và ngược lại , nhập vào địa chỉ IP khi muốn xem tên miền đi kèm .
    ```
    # host [IP/Domain]
    ```
    <img src=https://i.imgur.com/IRT976g.png>

## **5) `whois`**
- `whois` không được cài đặt mặc định trên **CentOS** , phải cài thủ công :
    ```
    # yum install -y whois
    ```
- Đưa ra các bản ghi trên server **whois** ( ***whois record*** ) của website , vì vậy bạn có thể xem thông tin về người hay tổ chức đã đăng ký và sở hữu website đó .
    ```
    # whois [Domain]
    ```

    <img src=https://i.imgur.com/ZNm0fGx.png>

    <img src=https://i.imgur.com/JzhCiBP.png>

## **6) `dhclient`**
- Giúp làm mới địa chỉ IP trên máy bằng cách giải phóng địa chỉ IP cũ và nhận một địa chỉ mới từ DHCP server .
    ```
    # dhclient -r   ( release )
    # dhclient      ( renew )
## **7) `netstat`**
- Là một lệnh nằm trong số các tập lệnh để giám sát hệ thống trên Linux .
- Giám sát cả chiều in và chiều out kết nối vào server , hoặc các tuyến đường route , trạng thái của card mạng .
- Rất hữu dụng trong việc giải quyết các vấn đề về sự cố liên quan đến network như là ***lượng connect kết nối , traffic , tốc độ , trạng thái của từng port , IP…***
- Cú pháp :
    ```
    # netstat [options]
    ```
    - **Options :**
        - `-a` : kiểm tra tổng quát tất cả các port trên Server
        - `-c` : kiểm tra tổng quát tất cả các port trên Server ở chế độ runtime
        - `-at` : kiểm tra các port chạy **TCP**
        - `-au` : kiểm tra các port chạy **UDP**
        - `-l` : kiểm tra các port ở trạng thái `LISTENING`
        - `-lt` : kiểm tra các port ở trạng thái `LISTENING` chạy **TCP**
        - `-plnt` : kiểm tra các port ở trạng thái `LISTENING` đang chạy dịch vụ gì
        - `-lu` : kiểm tra các port ở trạng thái `LISTENING` chạy **UDP**
        - `-rn` : Hiển thị bảng định tuyến
        - `-s` : thống kê theo các bộ giao thức **TCP** , **UDP** , **ICMP** , **IP**
        - `-st` : thống kê theo bộ giao thức **TCP**
        - `-su` : thống kê theo bộ giao thức **UDP**
        - `-i` : hiển thị hoạt động của các network interface
        - `-g` : hiển thị tình trạng IPv4 và IPv6
- Hiển thị tên service cùng **PID** :
    ```
    # netstat -tp
    ```
    <img src=https://i.imgur.com/5XmkPqs.png>

- Hiển thị hoạt động của các network interface :
    ```
    # netstat -i
    ```
    <img src=https://i.imgur.com/1mrXhd4.png>

- Hiển thị thông tin bảng định tuyến :
    ```
    # netstat -rn
    ```
    <img src=https://i.imgur.com/w4aebec.png>

- Hiển thị các kết nối sử dụng dịch vụ `http` :
    ```
    # netstat -ap | grep http
    ```
    <img src=https://i.imgur.com/QEb9qoo.png>
- Hiển thị số lượng gói `SYN_REC` trên Server ( nếu có quá nhiều là server đang bị **DDOS** )
    ```
    # netstat -np | grep SYN_REC | wc -l
    ```
## **8) `tcpdump`**

        

