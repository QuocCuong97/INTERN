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