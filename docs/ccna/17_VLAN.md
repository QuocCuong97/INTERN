# VLAN - Virtual LAN
> ## **1) Cấu hình VLAN**
- Tạo **VLAN** :
    ```
    Switch(config) # vlan [vlan-id]
    Switch(config-vlan) #
    ```
    - Dải giá trị **vlan-id** chạy từ `0` -> `4095` , trong đó :
        - `1` -> `1001` : dải **VLAN** thông thường , là dải **VLAN** thường được sử dụng
        - `1002` -> `1005` : dải **VLAN** dùng để giao tiếp với các kiểu mạng LAN khác
        - `1006` -> `4094` : dải **VLAN** mở rộng , dải này chỉ có thể sử dụng khi Switch hoạt động ở chế độ **Transparent**
        - `0` và `4095` : không sử dụng
        - Mặc định , các **VLAN** `1` , `1002` -> `1005` luôn tồn tại trên Switch , không thể xóa , sửa các **VLAN** này
- Đặt tên cho **VLAN** : 
    ```
    Switch(config-vlan) # name [vlan_name]
    ```
- Gán interface trên Switch vào **VLAN** :
    ```
    Switch(config) # interface [name]
    Switch(config-if) # switchport access vlan [vlan-id]
    ```
- Xem cấu hình **VLAN** đã thực hiện
    ```
    Switch # show vlan
    ```
> ## **2) Trunking**
