# Cài đặt và cấu hình Dynatrace
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
#### **1.2.2) Kịch bản 2: Pure Dynatrace Managed setup**
- Nếu muốn cluster của bạn nhận được dữ liệu giám sát từ các OneAgent được cài ngoài mạng, hoặc muốn sử dụng dịch vụ **Digital Experience Monitoring (DEM)**, cần mở kết nối từ cluster ra mạng ngoài và cấu hình IP Public.
- Dịch vụ **DEM** bao gồm
    - **Synthetic Monitoring**
    - **Agentless Real User Monitoring**
    - **Mobile Real User Monitoring**
    - **Real User Monitoring qua browser extension**
    - **Communication với Dynatrace mobile app**
- Mở kết nối cluster thẳng ra mạng ngoài là không nên vì một số lý do bảo mật. Do đó, nên sử dụng 1 hoặc nhiều **Cluster ActiveGate** làm proxy trung gian để xử lý trước lưu lượng **OneAgent** và **DEM**. **Cluster ActiveGate** sẽ được nhận ra bởi cluster và có thể được cấu hình thông qua **Cluster Management Console** tương tự như các cluster node.
