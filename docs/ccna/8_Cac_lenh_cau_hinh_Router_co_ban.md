# Các lệnh cấu hình Router cơ bản
>## **1) Các thành phần của Router**
![](/images/ccna/8_Cac_lenh_cau_hinh_Router_co_ban/1.jpg)

- **CPU** : bộ xử lý trung tâm.

- **ROM** : chứa chương trình kiểm tra khởi động ( POST ) , Bootstrap ( giống BIOS của máy tính ) và mini-IOS ( recovery password , upgrade IOS ) . Nhiệm vụ chính của **ROM** là kiểm tra phần cứng khi khởi động , sau đó chép HĐH Cisco IOS từ **FLASH** vào **RAM** . Nội dung trong bộ nhớ **ROM** là không thể xóa được .
- **RAM / DRAM** : lưu trữ routing table , ARP cache , fast-switching cache , packet buffering ( shared RAM ) và packet hold queues . Đa số HĐH Cisco IOS chạy trên **RAM** . **RAM** còn lưu trữ cấu hình đang chạy của Router ( running-config ) . Nội dung lưu trên RAM bị mất khi tắt nguồn hoặc restart Router .
- **FLASH** : lưu trữ toàn bộ HĐH Cisco IOS ( giống ổ cứng ) .
- **NVRAM** - Non-volatile RAM : lưu trữ file cấu hình backup / startup của Router ( startup-config ) ; nội dung của **NVRAM** vẫn được giữ sau khi tắt nguồn hoặc bật / tắt Router .
- **Interface** : còn gọi là cổng , được kết nối trên board mạch chủ hoặc trên interface module riêng biệt , qua đó những packet đi vào và đi ra Router . Cổng ` Console` sử dụng cáp `Rollover` , dùng để cấu hình trực tiếp Router . Cổng `AUX` giống với cổng `Console` nhưng sử dụng kết nối Dial-up tới modem , hỗ trợ việc cấu hình từ xa . Còn lại là các cổng mạng thông thường : `Gigabi Ethernet` , `Fast Ethernet` , `Serial`,...
>## **2) Các chế độ cấu hình Router Cisco**