# Cài đặt Dynatrace Managed Cluster
- Trước khi bắt đầu cài đặt, đảm bảo hệ thống đáp ứng yêu cầu về phần cứng và OS.
### **Bước 1: Download bộ cài**
- Đăng nhập vào server Linux nơi muốn cài đặt **Dynatrace Managed**.
- Copy lệnh `wget` từ email kích hoạt bạn nhận được từ hãng.
- Paste lệnh `wget` vào cửa sổ terminal. Đợi quá trình download thành công và bắt đầu bước 2.
### **Bước 2: Verify bộ cài**
- Bộ cài **Dynatrace Managed** được gán chữ ký số. File ký (signature) được gửi kèm bộ cài **Dynatrace Managed**.
- Cùng với **OpenSSL** cùng chứng chỉ gốc của **Dynatrace**, file signature có thể được sử dụng để xác minh tính toàn vẹn của bộ cài. File signature có cùng tên với bộ cài, cùng đuôi `.sig` .
- Để verify signature của bộ cài, sử dụng lệnh sau (khi file cài đặt là `dynatrace-managed.sh`):
    ```sh
    wget -qO dt-root.cert.pem https://ca.dynatrace.com/dt-root.cert.pem; wget -qO dynatrace-managed.sh.sig https://mcsvc.dynatrace.com/downloads/signature?filename=$(grep -am 1 'ARCH_FILE_NAME=' dynatrace-managed.sh | cut -d= -f2 |sed 's/.tar.gz$//'); openssl cms -inform PEM -binary -verify -CAfile dt-root.cert.pem -in dynatrace-managed.sh.sig -content dynatrace-managed.sh > /dev/null
    ```
    - Nếu xác thực thành công, kết quả sẽ trả về `Verification successful`. Nếu xác thực thất bại, kết quả sẽ trả về `Verification failure` kèm chi tiết lỗi.
### **Bước 3: Chạy bộ cài**
- Cần quyền `root` để cài đặt **Dynatrace Managed**. Có thể sử dụng `su` hoặc `sudo` để chạy script cài đặt.
- Thực hiện lệnh sau trong thư mục download script cài đặt :
    - Ubuntu Server:
        ```sh
        sudo /bin/sh dynatrace-managed.sh
        ```
    - RHEL :
        ```sh
        su -c '/bin/sh dynatrace-managed.sh'
        ```
    - Các Linux distribution khác ở session `root` :
        ```sh
        /bin/sh dynatrace-managed.sh
        ```
### **Bước 4: Kết thúc quá trình cài đặt
- Copy đường dẫn được cung cấp ở cuối quá trình cài đặt và paste lên trình duyệt để 