# Tổng quan về APM
## **1) Giới thiệu**
- **APM（*Application Performance Management*)** là 1 hệ thống quản lí tình hình hoạt động của toàn bộ application thông qua việc giám sát tình trạng response của Web application hay điều tra các vấn đề về response time liên quan đến tính năng của hệ thống được các doanh nghiệp sử dụng.
- Việc đưa **APM** vào sử dụng mang lại lợi ích như nhận biết, dự đoán được các vấn đề liên quan đến việc response chậm của hệ thống, có khả năng phòng ngừa trước các vấn đề có thể xảy ra, đồng thời khi vấn đề thực sự xảy ra thì giảm được thời gian điều tra đáng kể.
## **2) Bối cảnh sử dụng**
- Một trong những lý do lớn ở đây là cùng với việc nhiều nghiệp vụ của doanh nghiệp hiện nay dần được thực hiện online dẫn đến độ lớn của transaction hệ thống tăng lên và trở nên phức tạp.
- Hơn nữa việc phát triển sử dụng cloud hay các kĩ thuật giả lập sẽ làm cho phạm vi giám sát hệ thống trở nên không rõ ràng khiến cho phía giám sát hệ thống không thể đáp ứng được những yêu cầu mà khách hàng đưa ra cũng là một lý do giải thích cho nhu cầu sử dụng APM dần tăng cao.
- Việc phức tạp hóa các hệ thống do sự phát triển của IT chính là bối cảnh khiến cho nhu cầu sử dụng APM của các doanh nghiệp tăng cao.
- Những năm gần đây những web system, network mà các doanh nghiệp sử dụng, hay những thiết bị dùng để tiếp cận thông tin mà các doanh nghiệp cung cấp ngày càng trở nên phức tạp, do đó việc duy trì sự ổn định của response ngày càng trở nên khó khăn hơn.
- Đặc biệt là đối với các doanh nghiệp cung cấp dịch vụ trên nền tảng web thì response của hệ thống có liên hệ trực tiếp đến với độ hài lòng của khách hàng, do vậy việc quản lí application performance càng trở nên quan trọng.
- Như đã giải thích phía trên, việc hệ thống đang sử dụng có performance kém sẽ gây ra không ít ảnh hưởng cho việc vận hành của các doanh nghiệp.
- Từ trước đến nay khi vận hành 1 hệ thống thì thường quản lí riêng biệt các loại web system và network, nên nhiều trường hợp phía quản lí thấy rằng không có vấn đề gì nhưng phía end user thì nhận thấy rõ ràng đang có vấn đề về performance.
- Chính bởi vì hiện nay cần phải vận hành hệ thống trong môi trường IT ngày càng trở nên phức tạp nên việc quản lí tính năng của hệ thống nhìn từ quan điểm của end user ngày càng trở nên cần thiết. APM là 1 hệ thống được sinh ra để đáp ứng những nhu cầu đó.
## **3) Các APM Tool**
### **3.1) AppDynamics**
- Trang chủ: https://www.appdynamics.com/
- AppDynamics là software giám sát real time tính năng của nhiều loại web application như Java hay .NET…
- Nó là một hệ thống giám sát hầu như không gây ảnh hưởng đến môi trường hệ thống được giám sát đang hoạt động và đồng thời cũng có thể giám sát được cả tình trạng xử lí của các service liên kết bên ngoài.
- Màn hình console được thiết kế trực quan dễ hiểu, đồng thời từ các dữ liệu thống kê tool này cũng tự động tạo ra map về tình trạng sử dụng của hệ thống nên khi có vấn đề gì của hệ thống có thể dễ dàng xử lí một cách nhanh chóng.
    <img src=https://i.imgur.com/KDmtink.png>
### **3.2) Dynatrace**
- Trang chủ: https://www.dynatrace.com/
- DynaTrace 1 APM tool của thời đại mới, có thể giúp phát triển ra nguyên nhân trực tiếp và nguyên nhân sâu xa của các vấn đề phát sinh trong hệ thống trong thời gian ngắn. Việc đưa vào sử dụng cũng rất đơn giản, không cần thiết phải thêm gì vào program sẵn có.
- Tool này sẽ lưu lại xử lí của transaction từ khi bắt đầu đến khi kết thúc và giám sát tình trạng performance. Nhờ đó có thể nhanh chóng tìm ra những vấn đề của hệ thống và nguyên nhân để giải quyết.
    <img src=https://i.imgur.com/uFhUsHD.png>
### **3.3) CA Application Performance Management（CA APM)**
- Trang chủ: https://www.broadcom.com/products/software/aiops/application-performance-management
- CA APM là một monitoring solution mang tính bao quát, giám sát từ user mobile đến main frame.
- Tool này sẽ giúp phát hiện nhanh chóng những vấn đề gây chậm tính năng của application hay network trước khi các vấn đề gây hại cho khách hàng xảy ra.
- Những vấn đề này và nguyên nhân của chúng được gửi tới người quản lí real time, đồng thời chỉ ra một cách rõ ràng những điểm cần phải sửa theo tình hình thực tế của hệ thống.
    <img src=https://i.imgur.com/wWKPFwe.png>
### **3.4) New Relic**
- Trang chủ: https://newrelic.com/
- New Relic là một dịch vụ cung cấp môi trường giám sát application và network như một cloud service. Nó không cần setup mà có thể ngay lập tức giám sát hệ thống.
- Những dữ liệu thu thập được sẽ tự động được hiển thị và có thể nhanh chóng xác định được những điểm có vấn đề trong hệ thống.
- Bằng việc sử dụng tool này chúng ta có thể quản lí giám sát được toàn bộ môi trường application thường xuyên thay đổi, từ đó đưa ra được những xử lí hay sizing nhanh chóng và hợp lí.
    <img src=https://i.imgur.com/E2fzle2.png>
### **3.5) Jennifer**
- Trang chủ: https://jennifersoft.com/en/
- JENNIFER là 1 APM tool để giám sát web application server. Vì nó sẽ giám sát trực tiếp xử lí bên trong của từng application nên có thể phát hiện và giải quyết vấn đề một cách nhanh chóng.
- Bằng việc giám sát thời gian response của page request cũng như cuat DB đối với query, tool này giúp cho chúng ta nhận biế được vấn đề và nguyên nhân của nó ở giai đoạn sớm cũng như nắm được xu hướng độ tại của service một cách cụ thể.
    <img src=https://i.imgur.com/0EUrlsu.png>

