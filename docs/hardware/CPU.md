# CPU - Central Processing Unit
## **1) Khái niệm**
- **CPU ( *Central Processing Unit* )** , chính là bộ xử lý trung tâm của máy tính, có nhiệm vụ xử lý  các chương trình vi tính và dữ liệu . Hiểu đơn giản thì CPU chính là “bộ não” của một chiếc máy tính. Máy tính có hoạt động trơn tru hay không, xử lý thông tin nhanh hay không phụ thuộc phần lớn vào linh kiện này .

    <img src=https://i.imgur.com/bNQ5Fjk.png>

- **CPU** cần sự hỗ trợ của **chipset** để thực hiện các công việc của nó . **Chipset** là một tập các bộ vi xử lý trên **mainboard** , điều khiển các luồng dữ liệu và lệnh in/out cho **CPU** . **Chipset** chịu trách nhiệm điều khiển thời gian và điều phối các hoạt động . **Chipset** là thành phần được tích hợp trên **mainboard** và chứa 2 phần gắn trên **mainboard** .

    <p align=center><img src=https://i.imgur.com/bWvz7zb.jpg width=80%></p>

## **2) Các đặc điểm của CPU**
### **2.1) Tốc độ bus hệ thống mà CPU hỗ trợ** :
- **CPU Intel** hiện nay làm việc với bus hệ thống có tốc độ `1600` , `1333` , `1066` hoặc `800MHz` .
- **CPU AMD** hiện nay làm việc với bus hệ thống có tốc độ `1800` , `1000` hoặc `800MHz` .
### **2.2) Tần số nhân CPU** :
- Được tính toán bằng ***gigahertz*** , vd như `3.2GHz` .
### **2.3) Socket và Chipset phù hợp** :
- **Socket Intel** cho máy để bàn hiện là `LGA1366` , `LGA771` , `LGA755`
- **Socket AMD** cho máy để bàn hiện là `AM3` , `AM2+` , `AM2`
### **2.4) Khả năng đa xử lý** :
- Đánh giá khả năng có thể làm nhiều việc cùng một lúc của **CPU** .
- Hệ thống có được khả năng xử lý này bằng nhiều phương pháp , bao gồm :
    - Lắp đặt 2 đơn vị xử lý trong cùng 1 **CPU** ( được sử dụng lần đầu tiên với chíp **Pentium** )
    - Một mainboard sử dụng 2 **socket CPU** ( được hỗ trợ trong bộ xử lý **Xeon** cho Server )
    - Nhiều nhân đặt trong cùng 1 không gian **CPU** ( gọi là ***dual-core*** - lõi kép , 2 nhân ; ***triple-core*** - lõi tam , 3 nhân ; ***quad-core*** - lõi tứ , 4 nhân ; ***octo-core*** - lõi tám , 8 nhân )
### **2.5) Bộ nhớ Cache trong CPU** :
- Vùng nhớ mà CPU dùng để lưu các phần của chương trình , các tài liệu sắp được sử dụng . Khi cần , **CPU** sẽ tìm thông tin trên **cache** trước khi tìm trên bộ nhớ chính.
- **L1 Cache** : **Integrated cache ( cache tích hợp )** - cache được hợp nhất ngay trên mạch **CPU** . **Cache tích hợp** tăng tốc độ CPU do thông tin truyền đến và truyền đi từ cache nhanh hơn là phải chạy qua bus hệ thống. Các nhà chế tạo thường gọi cache này là **on-die cache** . **L1 Cache** - ***cache chính*** của **CPU** . **CPU** trước hết tìm thông tin cần thiết ở cache này .
- **L2 Cache** : **Cache thứ cấp** . Thông tin tiếp tục được tìm trên **L2 cache** nếu không tìm thấy trên **L1 cache** . **L2 cache** có tốc độ thấp hơn **L1 cache** và cao hơn tốc độ của các chip nhớ ( memory chip ) . Trong một số trường hợp ( như Pentium Pro ) , **L2 cache** cũng là cache tích hợp .
- **L3 Cache** : **L3 cache** là bộ nhớ cache đặc biệt được CPU sử dụng & được tích hợp trên mainboard . Nó làm việc cùng với bộ nhớ **cache L1 & L2** để tăng hiệu năng bằng cách chống lại hiện tượng nút cổ chai xảy ra trong quá trình thực thi các câu lệnh & tải dữ liệu . **L3 cache** cung cấp thông tin cho **L2 cache** sau đó chuyển thông tin cho **L1** . Thông thường **L3 cache** có tốc độ truy xuất thấp hơn so với **L2 cache** & tất nhiên thấp hơn nhiều so với **L1** nhưng nó vẫn nhanh hơn tốc độ truy xuất vào **RAM** .
### **2.6) Dung lượng và loại bộ nhớ ( DDR2 , DDR3 , DDR4 ) lắp trên mainboard mà CPU hỗ trợ**
### **2.7) Công nghệ tính toán mà CPU có thể sử dụng** :
- Có 2 công nghệ nổi tiếng nhất được sử dụng cho **CPU** là :
    - ***Hyper-Threading** ( siêu phân luồng )* của Intel .
    - ***Hyper-Transport** ( siêu truyền dẫn )* của AMD .
- Cả 2 công nghệ cho mỗi **CPU** logic điều khiển 1 **thread** ( luồng ) độc lập , song song với các luồng khác được điều khiển bởi các **CPU** khác trong cùng hộp .
### **2.8) Điện áp và điện năng tiêu thụ của CPU** :
- **CPU** ngày nay được áp dụng những công nghệ giúp đưa **CPU** vào trạng thái tạm nghỉ , khi chúng không làm việc và giảm tải điện áp tiêu thụ cùng với tần số **CPU** tùy thuộc vào nhu cầu .
    - **Intel** gọi công nghệ này là ***Enhanced Intel SpeedStep Technology ( EIST )***
    - **AMD** sử dụng công nghệ ***PowerNow!***
## **3) Thành phần của CPU**