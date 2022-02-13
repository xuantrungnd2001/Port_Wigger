# [Lab: Basic SSRF against the local server](https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-localhost)

## Yêu cầu:

Lab này có tính năng kiểm tra kho, lấy dữ liệu từ hệ thống nội bộ. Hãy đổi URL của việc kiểm tra kho thành `http://localhost/admin` và xóa tài khoản `carlos`
![](1.png)

---

Trước hết mình sẽ tìm đến một mặt hàng và kiểm tra tính năng check stock:
![](2.png)

Mình sử dụng BurpSuite để bắt request này, thì thấy được API sử dụng để kiểm tra sản phẩm có gọi URL từ một nguồn khác:
![](3.png)

Thay đổi nguồn này thành địa chỉ `localhost` để xem cấu hình đầy đủ của trang web, và mình tìm được url của `Admin penel` là `/admin`:
![](4.png)

Thay đổi tiếp giá trị của `stockAPI` để vào được trang của admin, tại đây mình tìm được URL để xóa tài khoản `carlos`:
![](5.png)

Tiếp tục thay đổi giá trị của stockAPI, sau đó gửi đi request này:
![](6.png)

Tắt intercept là có thể hoàn thành lab:
![](7.png)
