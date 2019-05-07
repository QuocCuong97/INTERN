# Unix - GNU - Linux và Giấy phép mã nguồn mở
> ## **UNIX** <img src=https://i.imgur.com/dcuNhVm.png width=40% align="right">

- **Unix** là một hệ điều hành vốn ra đời đã từ rất lâu , tại phòng thí nghiệm **Bell Labs** của **AT&T** . Dự án được dẫn dắt bởi **Ken Thompson** và **Dennis Ritchie** , 2 nhà khoa học máy tính nổi tiếng.

- Công việc phát triển **Unix** chính thức được bắt đầu vào mùa hè năm `1969` , và phiên bản đầu tiên của **Unix** được ra đời vào tháng `3` năm `1971` , tiếp đó là phiên bản thứ 2 ra đời năm `1972` . ( nếu gõ lệnh `date` trên một máy Linux, hay trên MacOS ... bạn sẽ nhận được một con số gọi là ***Unix Timestamp***. Con số này là số giây tính từ thời điểm `00:00:00` ngày `1` tháng `1` năm `1970` . Đó chính là thời thời điểm mà **Unix** đang nằm trong quá trình phát triển )
- **Ken Thompson** và **Dennis Ritchie** chính là 2 người đã tạo ra **B**, ngôn ngữ lập trình vốn được support ở **Unix** những phiên bản đầu. Sau đó, vào năm `1972`, **Ritchie** đã viết lại ngôn ngữ **B**, cải thiện nó tốt hơn, để trở thành ngôn ngữ lập trình **C** - ngôn ngữ lập trình còn rất phổ biến cho đến tận ngày nay. Hầu hết các components của **Unix** sau này đều được viết bằng **C**.
- Những năm sau của thập niên `70` , **AT&T** chia sẻ **Unix** cho những tổ chức giáo dục , hay tổ chức thương mại bên ngoài , từ đó dẫn đến sự ra đời của nhiều phiên bản **Unix** khác nhau . Nổi bật nhất trong số đó là phiên bản giáo dục được xây dựng bởi ***Computer Systems Research Group*** thuộc đại học ***California, Berkeley*** . Phiên bản này được biết đến rộng rãi với cái tên **Berkeley Software Distribution** , hay **BSD**.
- Ban đầu , **BSD** được xây dựng dựa trên codebase cũng như design của **Unix** , tuy nhiên càng về sau , các phiên bản của **Unix** và **BSD** càng có những điểm đặc trưng , khác biệt , dẫn đến việc xảy ra những "cuộc chiến" để trở thành "tiêu chuẩn" giữa phiên bản Unix BSD và phiên bản **Unix** của **AT&T** mang tên mã **System V** . Kết quả là phần thắng thuộc về **System V** . Các phiên bản **BSD** sau đó đã xích gần lại **System V** hơn với việc học tập và đưa vào những tiêu chuẩn chung đã được công nhận.
- Nhánh **BSD** đi đến hồi kết của quá trình phát triển lịch sử của nó, với sự ra đời và của các open source project như : **FreeBSD**, **NetBSD** và **OpenBSD** . Phiên bản cuối cùng của **BSD** được giới thiệu năm `1995` . Trong khi đó , phiên bản cuối cùng của **Unix** được phát triển bởi **Bell Laps** , phiên bản **Unix 10** , được ra mắt vào năm `1989` .
- Mặc dù phiên bản chính thức của **Unix** , **BSD** đã dừng phát triển từ lâu , thế nhưng những di sản mà chúng để lại là rất lớn cho đến ngày hôm nay . Rất nhiều hệ điều hành , từ close source cho đến open source đựa dựa trên 2 nhánh này.
- Phiên bản thương mại , *close source* nổi tiếng, thành công nhất , có lẽ chính là **MacOS** đình đám của **Apple** . **MacOS** cũng như các hệ điều hành khác của **Apple** hiện nay là **iOS** , **watchOS** , và **tvOS** đều được dựa trên nền tảng của **BSD** . Và **MacOS** cũng là một trong số ít các hệ điều hành được coi là **Unix-like** , khi có được chứng nhận ***Single UNIX Specification***. 
> ## **GNU** <img src=https://i.imgur.com/ZV3cMd1.png width=40% align="right">
- Tháng `9` năm `1983` , **Richard Stallman** thông báo về sự ra đời của dự án **GNU** ( **GNU** là viết tắt của từ **GNU's not Unix** ) .
- Mục tiêu của dự án **GNU** là tạo ra được một hệ điều hành miễn phí , giống Unix , nơi mà mọi người có quyền tự do copy , phát triển , chỉnh sửa và phân phối phần mềm , và việc tái phân phối là không bị giới hạn . ( **Unix** và các phiên bản rẽ nhánh từ **Unix** ban đầu đều là *close source* và bị ràng buộc bản quyền) .
- Năm `1985` , **Richard** thành lập tổ chức ***Free Software Foundation*** , hay **FSF** , một tổ chức phi lợi nhuận muốn thúc đẩy sự tự do trong trong phát triển phần mềm.
- Project **GNU** đã tạo ra được rất nhiều sản phẩm quan trọng như *GNU Compiler Collection (gcc) , GNU Debugger , GNU Emacs text editor (Emacs) , GNU build automator (make)* ... Ngoài ra còn phải kể đến giấy phép nổi tiếng được sử dụng rộng rãi nhất hiện nay : ***GNU General Public License (GPL)*** .
- **GNU** Project đã đạt được nhiều thành tựu lớn, tạo ra được nhiều công cụ tương tự như những gì có trên **Unix** . Tuy nhiên , **GNU** vẫn thiếu một thành phần quan trọng , mảnh ghép cuối cùng để nó trở thành một hệ điều hành hoàn chỉnh . Đó chính là **Kernel** , phần thực hiện công việc điều khiển , giao tiếp với các thiết bị phần cứng ( CPU , RAM , Devices ... ).
> ## **Linux** <img src=https://i.imgur.com/1WYvIRm.png width=30% align="right">
- Ngày `25` tháng `8` năm `1991`, một cậu sinh viên ở **Phần Lan** mang tên **Linus Torvalds** giới thiệu một sản phẩm cá nhân , sau này trở thành **Linux Kernel** .
- Project của **Linus** nhanh chóng nhận được sự chú ý cùng với đó là những đóng góp của nhiều cá nhân , tổ chức .
- Sự kết hợp giữa nhân **Linux** , với các phần mềm của **GNU** đã tạo ra một hệ điều hành hoàn chỉnh , hệ điều hành hoàn toàn miễn phí đầu tiên . Nó được mang tên **GNU/Linux** .
- Bản thân **Linux** chỉ là một **Kernel**, nó không phải là một hệ điều hành hoàn chỉnh . Hệ điều hành mà các bạn có thể vẫn đang sử dụng thực tế trên máy tính của mình có tên là **GNU/Linux** , nhưng có lẽ vì cái tên nó dài dòng nên người ta đã gọi ngắn gọn nó là **Linux** chăng . Việc lược bỏ đi **GNU** trong tên gọi hệ điều hành được cho là không công bằng , và đánh giá thấp vai trò của **GNU** . Tuy nhiên , biết sao được , nhiều người vẫn dùng cái tên **Linux** để thay cho tên gọi hệ điều hành **GNU/Linux** . Và khi nhắc đến Hệ Điều Hành **Linux** , ta cần hiểu đó là Hệ Điều Hành **GNU/Linux** .
- Hệ điều hành **Linux** hoàn toàn không sử dụng chung , hay kế thừa bất kỳ phần code nào của **Unix** , hay **BSD** . Nó được xây dựng mới hoàn toàn bởi **Linus** và **GNU Project** để có thể trở thành một phiên bản clone của **Unix** . Chính vì thế **Linux** và các hệ điều hành con cháu của **Unix** hiện nay ( như **MacOS** chẳng hạn ) có rất nhiều điểm giống nhau .
> ## **Unix-like**
- **MacOS** là một trong số ít các hệ điều hành được chứng nhận của ***Single UNIX Specification (SUS)*** , và được coi là một hệ điều hành **Unix-like** .
- Hiện thương hiệu **UNIX** thuộc bản quyền của tổ chức **The Open Group** ( chú ý là các chữ cái trong tên thương hiệu **UNIX** đều được viết hoa , trong khi để chỉ hệ điều thành thì ta có thể viết **Unix** hoặc **UNIX** ) .
- Khái niệm **Unix-like** vốn được dùng để chỉ những hệ điều hành có được chứng nhận ***SUS*** , và có thể sử dụng thương hiệu **UNIX** .
- **Linux** không phải 1 hệ điều hành **Unix-like** . Đã từng có dự án giúp **Linux** đạt được ***SUS*** , nhưng cuối cùng không đi đến đâu cả , và hiện tại các Distro **Linux** cũng không được phép sử dụng ***trademark UNIX*** .
- Có thể chia ra làm 3 loại **Unix-like** :
    - ***Genetic UNIX*** : Chỉ những hệ điều hành có liên quan trực tiếp đến codebase của phiên bản **Unix** của **Bell Labs**.
    - ***Trademark UNIX*** : Những hệ điều hành thoả mãn yêu cầu ***SUS*** và có thể sử dụng thương hiệu **UNIX**.
    - ***Functional UNIX*** : Những hệ điều hành "hoạt động giống Unix", và **Linux** có thể được xếp vào loại này.
> ## **Các loại giấy phép mã nguồn mở**
- Phần mềm nguồn mở ( **Open Source** ) là những phần mềm được cung cấp dưới cả dạng mã và nguồn , không chỉ là miễn phí về giá mua mà chủ yếu là miễn phí về bản quyền : người dùng có quyền sửa đổi , cải tiến , phát triển , nâng cấp theo một số nguyên tắc chung quy định trong giấy phép phần mềm nguồn mở mà không cần xin phép ai , điều mà họ không được phép làm đối với các phần mềm nguồn đóng ( tức là phần mềm thương mại ) .
- Trong bản mô tả chi tiết của từng “license” có thông tin về “ ***Điều khoản và điều kiện sử dụng, Tái sản xuất, Phân phối*** ” . 
    > ### **1) Apache license 2.0** <img src=https://i.imgur.com/aeHvD7d.png width=40% align="right">
    - Phát hành tháng `01-2004` .
    - Giấy phép Apache là một giấy phép phần mềm tự do của Quỹ phần mềm Apache (Apache Software Foundation – ASF). Giấy phép Apache trao cho người dùng phần mềm nguồn mở, quyền tự do sử dụng phần mềm với bất kì mục đích nào, phân phối chỉnh sửa, và phân phối bản sửa đổi của phần mềm, theo các điều khoản của giấy phép mà không lo vấn đề bàn quyền.
    - Nội dung license : http://www.apache.org/licenses/LICENSE-2.0
    - Các điều khoản của giấy phép:
        - Giấy phép Apache cho phép người dùng tự do sử dụng phần mềm với bất kì mục đích nào, tự do phân phối, tự do sửa đổi, tự do phân phối bản sửa đổi mình làm.
        - Giấy phép Apache không yêu cầu bản sửa đổi của phần mềm phải được phân phối dưới cùng giấy phép với bản gốc, cũng không yêu cầu bản sửa đổi phải được phân phối dưới dạng mã nguồn mở. Giấy phép Apache chỉ yêu cầu có một thông báo nhắc nhở người nhận rằng giấy phép Apache đã được sử dụng trong sản phẩm họ nhận được.<br>
        => Nói tóm lại người sử dụng phần mềm được quyền sử dụng chương trình và mã nguồn theo cách họ muốn, kể cả việc giữ lại mã nguồn cho riêng mình.
    - Giấy phép Apache không yêu cầu trích dẫn toàn bộ giấy phép vào sản phẩm hay tệp tin đính kèm bản phân phối, mà chỉ cần thêm vào phần thông báo có chứa đường link tới website chứa giấy phép với nội dung như sau:
        ```
        Copyright [yyyy] [name of copyright owner]

        Licensed under the Apache License, Version 2.0 (the “License”);
        you may not use this file except in compliance with the License.
        You may obtain a copy of the License at
        http://www.apache.org/licenses/LICENSE-2.0

        Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an “AS IS” BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
        See the License for the specific language governing permissions and limitations under the License.
        ```
    > ### **2) BSD 3-Clause “New” or “Revised” license** <img src=https://i.imgur.com/oVc64K7.png width=25% align="right">
    - Phát hành ngày `22-07-1999`
    - Giấy phép BSD(Berkeley Software Distribution License) có thể nói là lâu đời nhất trong các giấy phép nguồn mở, nó đã và đang tồn tại ở một số dạng kể từ những năm 1980. 
    - Giấy phép BSD 3-Clause “New” or “Revised” license là bản sửa đổi của giấy phép BSD cũ đã loại bỏ một số điều khoản mà người ta cho rằng phi thực tế .
    - Nội dung license : https://opensource.org/licenses/BSD-3-Clause
    - Điều khoản của giấy phép: Tái phân phối và sử dụng ở dạng mã nguồn và nhị phân, có hoặc không có sửa đổi mã nguồn, đều được cho phép miễn là các điều khoản sau được đáp ứng:
        - Việc phân phối lại mã nguồn phải giữ lại thông báo bản quyền, danh sách các điều kiện và tuyên bố từ chối trách nhiệm.
        - Việc phân phối lại dưới dạng nhị phân phải sao chép thông báo bản quyền, danh sách các điều kiện và tuyên bố từ chối trách nhiệm trong tài liệu và/hoặc các tài liệu khác được cung cấp bởi bản phân phối.
        - Tên của người giữ bản quyền cũng như tên của những người đóng góp của nó có thể được sử dụng để xác nhận hoặc quảng cáo các sản phẩm có nguồn gốc từ phần mềm này mà không có sự cho phép trước bằng văn bản cụ thể.
    > ### **3) BSD 2-Clause “Simplified” or “FreeBSD” license** <img src=https://i.imgur.com/oVc64K7.png width=25% align="right">
    - Phát hành tháng `04-1999`
    - Giấy phép BSD 2-Clause “Simplified” or “FreeBSD” license về cơ bản giống với giấy phép BSD 3-Clause. Nhưng BSD 2-Clause yêu cầu “Tên của những người đóng góp trước đó không được sử dụng để quảng cáo cho bất kỳ phiên bản phái sinh nào mà không có được sự cho phép bằng văn bản của họ”. BSD 3-Clause đã giảm bớt sự phiền hà khi sử dụng phần mềm nguồn mở theo giấy phép BSD.
    - Nội dung license : https://opensource.org/licenses/BSD-2-Clause
    > ### **4) GNU General Public License (GPL)** <img src=https://i.imgur.com/DJ6qZ9c.png width=28% align="right">
    - Giấy phép GNU hiện đang có 2 phiên bản được sử dụng phổ biến là GPL-2.0 và GPL-3.0.
    - Nội dung license : https://www.gnu.org/licenses/gpl.html
    - Quyền lợi khi sử dụng phần mềm áp dụng giấy phép GPL
        -  Được sao chép và phân phối chương trình, được yêu cầu trả phí cho việc phân phối đó.
        -  Được thay đổi chương trình để sử dụng cho mục đích cá nhân.
        -  Được phân phối bản đã được thay đổi đó.
    - Nghĩa vụ
        -  Khi sao chép và phân phối chương trình, phải đính kèm các thông báo về bản quyền gốc và không bảo hành( trừ trường hợp có văn bản thêm về quy định bảo hành)
        -  Khi phân phối bản đã được thay đổi bởi bản thân, phải chú thích rõ đó là bản đã được thay đổi, các thành phần được thay đổi, và áp dụng giấy phép GNU cho bản đã được thay đổi đó.
        - Khi phát hành chương trình phải công khai mã nguồn của chương trình, đồng thời phải công bố mã nguồn của chương trình trong tối thiểu 3 năm mà không được đòi một khoản phí nào từ những người yêu cầu mã nguồn trừ chi phí vận chuyển hay tương đương.
    > ### **5) GNU Library or “Lesser” General Public License (LGPL)** <img src=https://i.imgur.com/6S4KkBn.png width=32% align="right">    
    - Phiên bản mới nhất ( LGPL-3.0 ) phát hành ngày `29-06-2007` .
    - Nội dung license : https://www.gnu.org/copyleft/lesser.html
    - LGPL là một phiên bản sửa đổi của GPL. 
    - Giấy phép này thường bị hạn chế đối với các thư viện phần mềm. 
    - Cung cấp sự bảo vệ ít hơn so với GPL. 
    - Điều này cho phép các chương trình không phải là Open source có thể truy cập hoặc liên kết tới các thư viện nguồn mở mà không phải công khai mã nguồn như giấy phép GPL.
    > ### **6) MIT License** <img src=https://i.imgur.com/n2wBPHK.png width=30% align="right">
    - Được phát hành bởi Massachusetts Institute of Technology ( MIT ) .
    - Nội dung license : https://opensource.org/licenses/MIT
    - Giấy phép MIT là loại giấy phép cho phép sử dụng mã nguồn tự do nhất, nó có thể kết hợp với các mã nguồn khác và đảm bảo tương thích theo điều kiện của mọi loại giấy phép khác.
    -  Với giấy phép MIT bạn có thể sử dụng, sao chép, sửa đổi, hợp nhất, xuất bản, phân phối và/hoặc bán các bản sao của phần mềm mà không vi phạm bản quyền. Bạn chỉ cần tuân thủ điều kiện duy nhất sau:
        - Thông báo bản quyền và thông báo cho phép của phần mềm gốc sử dụng giấy phép MIT sẽ phải bao gồm trong tất cả các bản sao hoặc phần quan trọng của phần mềm.
    > ### **7) Mozilla Public License 2.0** <img src=https://i.imgur.com/n2wBPHK.png width=30% align="right">