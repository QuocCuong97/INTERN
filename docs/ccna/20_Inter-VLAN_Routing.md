# Inter-VLAN Routing
> ## 1) Định tuyến VLAN sử dụng Router
- Nếu sử dụng Router thì giải phap định tuyến này gọi là ***Router on a Stick*** .
- **VD :** 
![](/images)

    - Cấu hình để cổng `f0/1` của Switch là cổng **Trunk** :
    ```
    Switch(config) # interface f0/1
    Switch(config-if) # switchport trunk encapsulation dot1q
    Switch(config-if) # switchport mode trunk
    ```
    - Cấu hình chia **sub-interface trên Router :
    ```
    Router(config) # interface f0/0
    Router(config-if) # no shutdown

    Router(config-if) # interface f0/0.10
    Router(config-if) # encapsulation dot1q 10
    Router(config-if) # ip address 192.168.10.1 255.255.255.0
    Router(config-if) # interface f0/0.20
    Router(config-if) # encapsulation dot1q 20


