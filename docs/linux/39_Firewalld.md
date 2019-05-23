# Firewalld
## **1) Khái niệm**
- **FirewallD** là giải pháp tường lửa mạnh mẽ, toàn diện được cài đặt mặc định trên **CentOS/RHEL 7** , nhằm thay thế **Iptables** với những khác biệt cơ bản :
    - **FirewallD** sử dụng “**zones**” và “**services**” thay vì “**chain**” và “**rules**” trong **Iptables** .
    - **FirewallD** quản lý các quy tắc được thiết lập tự động , có tác dụng ngay lập tức mà không làm mất đi các kết nối và session hiện có.
## **2) Các khái niệm cơ bản trong FirewallD**
### **2.1) Zone**
- Trong **FirewallD** , **zone** là một nhóm các quy tắc nhằm chỉ ra những luồng dữ liệu được cho phép , dựa trên mức độ tin tưởng của điểm xuất phát luồng dữ liệu đó trong hệ thống mạng . Để sử dụng , bạn có thể lựa chọn **zone** mặc định , thiết lập các quy tắc trong **zone** hay chỉ định network interface để quy định hành vi được cho phép .
- Các **zone** được xác định trước theo mức độ tin cậy , theo thứ tự từ “ít-tin-cậy-nhất” đến “đáng-tin-cậy-nhất”:
    - `drop` : ít tin cậy nhất – toàn bộ các kết nối đến sẽ bị từ chối mà không phản hồi , chỉ cho phép duy nhất kết nối đi ra .
    - `block` : tương tự như drop nhưng các kết nối đến bị từ chối và phản hồi bằng tin nhắn từ icmp-host-prohibited ( hoặc icmp6-adm-prohibited ).
    - `public` : đại diện cho mạng công cộng , không đáng tin cậy . Các máy tính/services khác không được tin tưởng trong hệ thống nhưng vẫn cho phép các kết nối đến trên cơ sở chọn từng trường hợp cụ thể .
    - `external` : hệ thống mạng bên ngoài trong trường hợp bạn sử dụng tường lửa làm gateway, được cấu hình giả lập NAT để giữ bảo mật mạng nội bộ mà vẫn có thể truy cập.
    - `internal` : đối lập với `external zone` , sử dụng cho phần nội bộ của gateway. Các máy tính/services thuộc zone này thì khá đáng tin cậy .
    - `dmz` : sử dụng cho các máy tính/service trong khu vực **DMZ ( Demilitarized )** – cách ly không cho phép truy cập vào phần còn lại của hệ thống mạng , chỉ cho phép một số kết nối đến nhất định .
    - `work` : sử dụng trong công việc, tin tưởng hầu hết các máy tính và một vài services được cho phép hoạt động.
    - `home` : môi trường gia đình – tin tưởng hầu hết các máy tính khác và thêm một vài services được cho phép hoạt động .
    - `trusted` : đáng tin cậy nhất – tin tưởng toàn bộ thiết bị trong hệ thống .
### **2.2) Hiệu lực của các quy tắc**
- `Runtime` ( mặc định ) : có tác dụng ngay lập tức , mất hiệu lực khi reboot hệ thống .
- `Permanent` : không áp dụng cho hệ thống đang chạy, cần reload mới có hiệu lực , tác dụng vĩnh viễn cả khi reboot hệ thống .
## **3) Cài đặt Firewalld**
- **FirewallD** được cài đặt mặc định trên **CentOS 7** . Cài đặt nếu chưa có :
    ```
    # yum install firewalld
    ```
- Khởi động **firewalld** :
    ```
    # systemctl start firewalld
    ```
- Thiết lập **firewalld** khởi động cùng hệ thống :
    ```
    # systemctl enable firewalld
    ```
- Khởi động lại **firewalld** :
    ```
    # systemctl restart firewalld
    hoặc
    # firewall-cmd --reload
    ```
- Tạm dừng và vô hiệu hóa **firewalld** :
    ```
    # systemctl stop firewalld
    # systemctl disable firewalld
    ```
- Kiểm tra tình trạng **firewalld** :
    ```
    

