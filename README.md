# Điều khiển Máy Lạnh từ Web

Dự án này cung cấp giao diện web đơn giản để điều khiển máy lạnh thông qua MQTT. Trang web cho phép bạn bật/tắt máy lạnh, bật/tắt chế độ tự động, điều chỉnh nhiệt độ và xem trạng thái hiện tại.

## Chức năng chính

* **Trạng thái kết nối:** Hiển thị trạng thái kết nối với broker MQTT cục bộ và internet.
* **Trạng thái máy lạnh:** Hiển thị nhiệt độ hiện tại, trạng thái bật/tắt và trạng thái chế độ tự động của máy lạnh.
* **Điều khiển:** Các nút để bật/tắt máy lạnh, bật/tắt chế độ tự động, tăng/giảm nhiệt độ.
* **Cài đặt ngưỡng tự động:** Cho phép người dùng đặt ngưỡng nhiệt độ cao và thấp để tự động bật/tắt máy lạnh.
* **Trạng thái gửi lệnh IR:** Hiển thị trạng thái thành công hay thất bại khi gửi lệnh hồng ngoại (IR) đến máy lạnh.

## Yêu cầu

* Một máy chủ MQTT đang chạy (cục bộ và/hoặc internet).
* Một thiết bị (ví dụ: ESP8266) được cấu hình để kết nối với máy chủ MQTT và điều khiển máy lạnh.
* Trình duyệt web để truy cập giao diện điều khiển.

## Cài đặt

1.  **Sao chép (Clone) repository này (nếu có):**
    ```bash
    git clone <địa_chỉ_repository>
    cd <tên_repository>
    ```
2.  **Mở file `index.html`** bằng trình duyệt web của bạn.
3.  **Cấu hình địa chỉ MQTT broker:** Chỉnh sửa các dòng sau trong file `index.html` để phù hợp với địa chỉ và cổng của MQTT broker bạn đang sử dụng:
    ```javascript
    const clientLocal = new Paho.MQTT.Client('192.168.0.107', 9001, 'webClientLocal-' + parseInt(Math.random() * 100, 10));
    const clientInternet = new Paho.MQTT.Client('192.168.0.108', 9001, 'webClientInternet-' + parseInt(Math.random() * 100, 10));
    ```
    Thay `'192.168.0.107'` và `'192.168.0.108'` bằng địa chỉ IP hoặc hostname của broker cục bộ và internet tương ứng. Thay `9001` nếu broker của bạn sử dụng cổng khác.

## Sử dụng

1.  Đảm bảo thiết bị điều khiển máy lạnh của bạn đang kết nối với MQTT broker.
2.  Mở file `index.html` trên trình duyệt web.
3.  Kiểm tra trạng thái kết nối MQTT. Nếu "Đã kết nối" hiển thị màu xanh lá cây, bạn có thể bắt đầu điều khiển máy lạnh.
4.  Sử dụng các nút để bật/tắt, điều chỉnh nhiệt độ và bật/tắt chế độ tự động.
5.  Nhập ngưỡng nhiệt độ cao và thấp mong muốn và nhấn nút "Áp Dụng Ngưỡng" để cấu hình chế độ tự động.
6.  Theo dõi trạng thái gửi lệnh IR để biết lệnh đã được gửi thành công đến máy lạnh hay chưa.

## Đóng góp

Mọi đóng góp đều được hoan nghênh! Bạn có thể mở issue để báo cáo lỗi hoặc đề xuất tính năng mới, hoặc gửi pull request với các thay đổi của bạn.

## Tác giả

[Tên của bạn (nếu muốn)]

## Bản quyền

[Thông tin bản quyền (nếu có)]
