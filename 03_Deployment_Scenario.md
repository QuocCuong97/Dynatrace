# Các mô hình triển khai Dynatrace
## **1) Dynatrace Managed**
### **1.1) Các thành phần**
- Các thành phần cơ bản của **Dynatrace Managed** được mô tả qua hình sau :

    <img src=https://i.imgur.com/6MoKyaK.png>

#### **1.1.1) Dynatrace Managed cluster**
- **Dynatrace Managed cluster** chịu trách nhiệm monitor một hoặc nhiều môi trường. Nó bao gồm tối thiểu 1 node được cài đặt Dynatrace Server (thường sẽ có nhiều hơn 1 node trong cluster). Mỗi **Dynatrace Managed cluster** được liên kết với một **Cluster Management Console**. Tóm lại, một **Dynatrace Managed cluster** được liên kết với :
    - Một hoặc nhiều node cài Dynatrace Server
    - Một hoặc nhiều môi trường được monitor (do đó bao gồm một hoặc nhiều host được cài đặt **Dynatrace OneAgent**)
    - Một **Cluster Management Console**
- Mỗi khi muốn setup một cluster, bạn cần [mua license](https://www.dynatrace.com/support/help/get-started/get-started-with-dynatrace-managed/). Tất cả các **Dynatrace Managed clusters** sẽ giao tiếp với **Mission Control** để được duy trì và cấp phép.
#### **1.1.2) Bộ cài đặt Dynatrace Managed**
- Bộ cài **Dynatrace Managed** cung cấp tất cả các tiện ích cung cấp bởi **Dynatrace Cloud** cho hệ thống của bạn và kích hoạt giám sát các application services, processes và insfrastructure.
- Bộ cài **Dynatrace Managed** bao gồm các thành phần sau:
    - **Dynatrace Server**
    - **Cassandra**
    - **Elasticsearch**
    - **Embedded ActiveGate**
    - **NGINX**
- Tất cả các thành phần trên sẽ được triển khai trên node đầu tiên khi cài đặt cluster, cũng như trên bất cứ node bổ sung nào.
#### **1.1.3) Cluster Management Console**
- Đối với mỗi **Dynatrace Managed cluster** mà bạn cài đặt, sẽ có một **Cluster Management Console** đi kèm.
- **Cluster Management Console** là một giao diện web hỗ trợ quản lý hiệu quả hạ tầng **Dynatrace Managed**. Từ đây bạn có thể nhìn trạng thái deployment của **Dynatrace Managed cluster** vào bất cứ lúc nào.

    <img src=https://i.imgur.com/SfusDjg.png>

- Với **Cluster Management Console**, bạn có thể :
    - Tạo user account và group
    - Thêm các cluster node
    - Thêm các monitoring environment
#### **1.1.4) Mission Control**
- **Dynatrace Mission Control** cung cấp hỗ trợ ***pro-active*** để duy trì và cấp phép.
- Với sự hỗ trợ tự động từ **Dynatrace ONE team**, bộ cài **Dynatrace Managed** của bạn sẽ tự động được cập nhật.
- Bạn có thể liên hệ **Dynatrace ONE team** để được hỗ trợ Real-time đối với sản phẩm nếu bạn cần trợ giúp hoặc gặp bất kỳ sự cố nào.
#### **1.1.5) Dynatrace OneAgent**
- **Dynatrace OneAgent** được cài đặt trên mỗi môi trường được monitor.
- **Dynatrace OneAgent** chịu trách nhiệm thu thập toàn bộ dữ liệu hoạt động của môi trường được monitor và gửi dữ liệu đó về **Dynatrace Server**.
### **1.2) Deployment**
- Có nhiều kịch bản triển khai khác nhau cho Dynatrace Managed :
#### **1.2.1) Kịch bản 1: Thiết lập cơ bản**
- Dưới đây là mô hình khi muốn cài đặt **Dynatrace Managed** và thiết lập một hoặc nhiều cluster node :

    <img src=https://i.imgur.com/o3ssA3E.png>

- Nếu không cấu hình gì thêm, 1 cluster chỉ có thể truy cập trong nội bộ và mở cổng `443` cho các REST API, traffic của **OneAgent** và **WebUI**.
- Mặc định, remote access từ **Mission Control** đã được bật sẵn. Nó cho phép **Dynatrace** thực hiện giám sát và healthcheck cụm **Dynatrace Managed Cluster**. Mỗi kết nối đều được bảo mật với **TLS**.
#### **1.2.2) Kịch bản 2: Cài đặt mới Dynatrace Managed**
- Nếu muốn cluster của bạn nhận được dữ liệu giám sát từ các OneAgent được cài ngoài mạng, hoặc muốn sử dụng dịch vụ **Digital Experience Monitoring (DEM)**, cần mở kết nối từ cluster ra mạng ngoài và cấu hình IP Public.
- Dịch vụ **DEM** bao gồm
    - **Synthetic Monitoring**
    - **Agentless Real User Monitoring**
    - **Mobile Real User Monitoring**
    - **Real User Monitoring qua browser extension**
    - **Communication với Dynatrace mobile app**
- Mở kết nối cluster thẳng ra mạng ngoài là không nên vì một số lý do bảo mật. Do đó, nên sử dụng 1 hoặc nhiều **Cluster ActiveGate** làm proxy trung gian để xử lý trước lưu lượng **OneAgent** và **DEM**. **Cluster ActiveGate** sẽ được nhận ra bởi cluster và có thể được cấu hình thông qua **Cluster Management Console** tương tự như các cluster node.
- Mô hình dưới đây thể hiện các port cần mở giữa các thành phần :

    <img src=https://i.imgur.com/LzGHiBZ.png>

- **Cluster ActiveGate** yêu cầu :
    - 1 IP Public
    - 1 domain name đi kèm SSL, bởi các kết nối ra bên ngoài chỉ hỗ trợ HTTPS (port `443`). Domain này phải khác domain của WebUI. Có thể chọn tự cung cấp domain và SSL hoặc **Dynatrace** sẽ tự làm việc đó. **Dynatrace** sẽ tự gen ra một domain đại diện và chứng chỉ SSL đi kèm.
- Đối với trường hợp hệ thống tải cao (high-load), nên setup 2 **load-balanced Cluster ActiveGate** với cùng domain name và certificate. Với trường hợp hệ thống ít tải hơn (low-load), có thể sử dụng 1 Cluster ActiveGate là được. Tuy nhiên, nên cân nhắc cài đặt các **Environment ActiveGate** riêng cho từng môi trường.
- Vì **Environment ActiveGate** bắt đầu giao tiếp với **Cluster ActiveGate** ngay sau khi cài đặt, **Cluster ActiveGate** cần sẵn sàng hoạt động qua public IP từ trước. Do đó, nếu định sử dụng **Environment ActiveGate**, cần chú ý thứ tự triển khai sau :
- Cài đặt **Dynatrace Managed Cluster**
- Cài đặt **Cluster ActiveGate** và đảm bảo nó có thể kết nối tới **Dynatrace Managed Cluster**. Ngoài ra, cần đảm bảo **Cluster ActiveGate** có IP Public và có thể truy cập từ mạng ngoài.
- Cài đặt **Environment ActiveGate** và cung cấp IP public của **Cluster ActiveGate** cho kết nối ra ngoài.
> ***Chú ý*** : Lưu lượng của WebUI - hay cluster administration (thông qua **Cluster Management Console**) phải on-premises, ở bên trong mạng nội bộ. WebUI phải được kết nối thông qua **HTTPS** (yêu cầu chứng chỉ **TLS**). Có thể sử dụng chứng chỉ self-signed, tuy nhiên sẽ không an toàn bằng cách sử dụng những tên miền và SSL hợp lệ, hoặc được gen tự động bởi **Dynatrace**. Mặc định, mỗi cluster sẽ được cấp miễn phí một subdomain với hậu tố `*.dynatrace-managed.com` với chứng chỉ hợp lệ từ **Let's Enscrypt**. Chú ý **Cluster ActiveGate** không hỗ trợ thiết lập proxy cho lưu lượng WebUI.
#### **1.2.3) Kịch bản 3: Tích hợp với môi trường IT hiện có**
- Trong kịch bản phức tạp hơn, bạn muốn nhúng **Dynatrace Managed** trong hạ tầng IT hiện có với số lượng lớn các thiết bị có sẵn, mô hình dưới đây cho thấy **load-balancer** được cung cấp từ phía khách hàng đặt trước **Cluster ActiveGate domain** và **proxy** cũng do khách hàng cung cấp cho giao tiếp bên ngoài với **Mission Control**.

    <img src=https://i.imgur.com/FUntOqT.png>

#### **1.2.4) Kịch bản 4: Môi trường High-Availability được phân bố rộng rãi với tính năng khôi phục tự động (automatic recovery)**
- **Dynatrace** cho phép bạn triển khai mô hình **high-availability** thông qua các mạng phân tán cung cấp khả năng downtime gần như bằng 0 và cho phép giám sát liên tục mà không bị mất dữ liệu trong quá trình failover. Giải pháp này giúp tiết kiệm chi phí về việc phân bổ compute và storage bằng cách loại bỏ bớt các nhu cầu về máy chủ khôi phục dự phòng riêng biệt và cơ sở hạ tầng liên quan để lưu trữ và truyền dữ liệu sao lưu. Để tính toán dung lượng cần thiết, cần coi các node trong datacenter bổ sung là dự phòng, thay vì coi noa là phần mở rộng, và có kế hoạch cân bằng cả 2 datacenter như nhau.
- [Tìm hiểu thêm mô hình **High-Availability**](https://www.dynatrace.com/support/help/setup-and-configuration/dynatrace-managed/fault-domain-awareness/premium-high-availability/)
- Để triển khai mô hình này, cần tách riêng license cho các datacenter :

    <img src=https://i.imgur.com/GE487Mp.png>

## **2) Cấu hình bắt buộc cho các trường hợp sử dụng traffic riêng biệt**
- Bảng sau đây tổng hợp cấu hình bắt buộc cho từng trường hợp sử dụng traffic riêng biệt. 

    | Traffic type | Public IP | Valid SSL certificate |
    |--------------|-----------|-----------------------|
    | OneAgent (on-premises) | | |
    | OneAgent (external) | x | |
    | RUM (on-premises) | | |
    | RUM (external) | | |
    | Agentless RUM (on-premises) | | x |
    | Agentless RUM (external) | x | x |
    | Mobile RUM (on-premises) | | x |
    | Mobile RUM (external) | x | x |
    | Synthetic | x | |
- **Real User Monitoring (RUM)**, **agentless RUM**, and **mobile RUM** thường liên quan tới traffic của user và hoạt động của trình duyệt (xảy ra ở mạng ngoài), sử dụng chung endpoint để truyền dữ liệu giám sát tới **Dynatrace**
## **3) Các đáp ứng về hệ thống khi cài đặt Dynatrace Managed Cluster**