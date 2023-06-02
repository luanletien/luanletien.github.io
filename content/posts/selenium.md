---
title: "Tất tần tật về Selenium"
date: 2023-06-02T15:26:48+07:00
draft: false
---

# Toàn bộ về Selenium

## Tạo một đối tượng WebDriver
- Tùy thuộc vào trình duyệt (Chrome, Firefox, etc.), sử dụng lớp tương ứng trong `selenium.webdriver`
  - Chrome
    - `from selenium.webdriver import Chrome`
    - `driver = Chrome(executable_path='đường_dẫn_đến_chrome_driver')`
      - Sử dụng `executable_path` để chỉ định đường dẫn tới Chrome Driver
  - Firefox
    - `from selenium.webdriver import Firefox`
    - `driver = Firefox(executable_path='đường_dẫn_đến_geckodriver')`
      - Sử dụng `executable_path` để chỉ định đường dẫn tới GeckoDriver
  - Edge
    - `from selenium.webdriver import Edge`
    - `driver = Edge(executable_path='đường_dẫn_đến_edge_driver')`
      - Sử dụng `executable_path` để chỉ định đường dẫn tới Edge Driver
  - Safari
    - `from selenium.webdriver import Safari`
    - `driver = Safari()`
      - Safari Driver được tích hợp sẵn trong hệ điều hành macOS và không yêu cầu đường dẫn đến driver
  - Opera
    - `from selenium.webdriver import Opera`
    - `driver = Opera(executable_path='đường_dẫn_đến_opera_driver')`
      - Sử dụng `executable_path` để chỉ định đường dẫn tới Opera Driver
  - ...
- Khởi tạo đối tượng WebDriver
  - Đối tượng WebDriver sẽ mở trình duyệt tương ứng


## Truy cập URL
- Sử dụng phương thức `get(url)` của đối tượng WebDriver để truy cập một trang web

## Xác định phần tử trên trang
- Sử dụng các phương thức tìm kiếm để xác định phần tử trên trang
  - `find_element_by_id(id)`
  - `find_element_by_name(name)`
  - `find_element_by_class_name(class_name)`
  - `find_element_by_tag_name(tag_name)`
  - `find_element_by_link_text(link_text)`
  - `find_element_by_partial_link_text(partial_link_text)`
  - `find_element_by_xpath(xpath)`
  - `find_element_by_css_selector(css_selector)`
- Trả về đối tượng WebElement
  - Sử dụng để truy cập và tương tác với phần tử
  
## Truy cập và tương tác với phần tử
- Sử dụng các phương thức của đối tượng WebElement để truy cập và tương tác với phần tử
  - `click()`: Nhấp vào phần tử
  - `send_keys(keys)`: Gửi các phím vào phần tử
  - `clear()`: Xóa nội dung của phần tử
  - `text`: Lấy nội dung văn bản của phần tử
  - `get_attribute(attribute_name)`: Lấy giá trị của thuộc tính của phần tử
  - `is_displayed()`: Kiểm tra xem phần tử có hiển thị trên trang hay không
  - `is_enabled()`: Kiểm tra xem phần tử có khả dụng để tương tác hay không
  - `is_selected()`: Kiểm tra xem phần tử đã được chọn hay không
  - ...

## Xử lý cửa sổ và khung (window and frame)
- Chuyển đổi giữa các cửa sổ
  - `window_handles`: Lấy danh sách các cửa sổ trình duyệt hiện tại
  - `switch_to.window(window_handle)`: Chuyển đổi sang cửa sổ trình duyệt được chỉ định
  - `close()`: Đóng cửa sổ trình duyệt hiện tại
  - `current_window_handle`: Lấy cửa sổ trình duyệt hiện tại
  - ...

- Chuyển đổi giữa các khung (frames)
  - `switch_to.frame(frame_reference)`: Chuyển đổi sang khung được chỉ định
  - `switch_to.default_content()`: Quay lại khung gốc của trang
  - `switch_to.parent_frame()`: Chuyển đổi đến khung cha của khung hiện tại
  - `frame(index)`: Chuyển đổi sang khung theo chỉ mục
  - `frame(name_or_id)`: Chuyển đổi sang khung theo tên hoặc id
  - ...

- Xử lý các tab trình duyệt
  - `window_handles`: Lấy danh sách các cửa sổ trình duyệt hiện tại
  - `switch_to.window(window_handle)`: Chuyển đổi sang cửa sổ trình duyệt được chỉ định
  - `current_window_handle`: Lấy cửa sổ trình duyệt hiện tại
  - `close()`: Đóng cửa sổ trình duyệt hiện tại
  - ...

## Thao tác với trình duyệt
- Điều hướng trình duyệt
  - `back()`: Quay lại trang trước đó
  - `forward()`: Tiến tới trang tiếp theo
  - `refresh()`: Làm mới trang hiện tại
  - `to(url)`: Điều hướng đến một URL cụ thể
  - `to(URL)`: Điều hướng đến một URL cụ thể
  - ...

- Xử lý cửa sổ trình duyệt
  - `window_handles`: Lấy danh sách các cửa sổ trình duyệt hiện tại
  - `switch_to.window(window_handle)`: Chuyển đổi sang cửa sổ trình duyệt được chỉ định
  - `current_window_handle`: Lấy cửa sổ trình duyệt hiện tại
  - `close()`: Đóng cửa sổ trình duyệt hiện tại
  - `maximize_window()`: Phóng to cửa sổ trình duyệt
  - `set_window_size(width, height)`: Đặt kích thước cửa sổ trình duyệt
  - ...

## Xử lý dữ liệu trên trang web
- Trích xuất dữ liệu từ các phần tử trên trang
  - `text`: Lấy nội dung văn bản của phần tử
  - `get_attribute(attribute_name)`: Lấy giá trị của thuộc tính của phần tử
  - `get_property(property_name)`: Lấy giá trị của thuộc tính DOM của phần tử
  - `get_css_value(property_name)`: Lấy giá trị của thuộc tính CSS của phần tử
  - ...

- Gửi dữ liệu vào các trường nhập liệu
  - `send_keys(keys)`: Gửi dữ liệu vào phần tử đầu vào
  - `clear()`: Xóa nội dung của phần tử
  - `submit()`: Gửi biểu mẫu (form) chứa phần tử
  - ...

- Xử lý checkbox và radio button
  - `is_selected()`: Kiểm tra xem checkbox hoặc radio button đã được chọn hay chưa
  - `click()`: Chọn hoặc bỏ chọn checkbox hoặc radio button

- Xử lý dropdown
  - `select_by_visible_text(text)`: Chọn tùy chọn từ dropdown bằng văn bản hiển thị
  - `select_by_value(value)`: Chọn tùy chọn từ dropdown bằng giá trị
  - `select_by_index(index)`: Chọn tùy chọn từ dropdown bằng chỉ mục
  - `deselect_all()`: Bỏ chọn tất cả các tùy chọn đã chọn trước đó
  - `deselect_by_visible_text(text)`: Bỏ chọn tùy chọn từ dropdown bằng văn bản hiển thị
  - `deselect_by_value(value)`: Bỏ chọn tùy chọn từ dropdown bằng giá trị
  - `deselect_by_index(index)`: Bỏ chọn tùy chọn từ dropdown bằng chỉ mục
  - ...

- Xử lý iframe
  - `switch_to.frame(frame_reference)`: Chuyển sang iframe được chỉ định để thao tác với các phần tử bên trong
  - `switch_to.default_content()`: Quay lại khung mặc định của trang
  - ...

- Xử lý cửa sổ trình duyệt
  - `window_handles`: Lấy danh sách các cửa sổ trình duyệt hiện tại
  - `switch_to.window(window_handle)`: Chuyển đổi sang cửa sổ trình duyệt được chỉ định
  - `close()`: Đóng cửa sổ trình duyệt hiện tại
  - ...

- Xử lý alert.
  - `switch_to.alert`: Chuyển đổi sang cửa sổ cảnh báo
  - `accept()`: Chấp nhận cảnh báo (bấm nút OK)
  - `dismiss()`: Từ chối cảnh báo (bấm nút Cancel)
  - `text`: Lấy văn bản cảnh báo
  - `send_keys(keys)`: Gửi dữ liệu vào cảnh báo

- Xử lý khung bật lên (popup)
  - `switch_to.window(window_handle)`: Chuyển đổi sang khung bật lên
  - `switch_to.default_content()`: Quay lại khung gốc của trang
  - `switch_to.frame(frame_reference)`: Chuyển đổi sang khung bên trong khung bật lên
  - ...

- Xử lý trạng thái phần tử
  - `is_enabled()`: Kiểm tra xem phần tử có khả dụng để tương tác hay không
  - `is_displayed()`: Kiểm tra xem phần tử có hiển thị trên trang hay không
  - `is_selected()`: Kiểm tra xem phần tử đã được chọn hay chưa
  - ...

- Xử lý múi giờ (Timezone)
  - `execute_script(script, args)`: Chạy mã JavaScript để xử lý múi giờ trên trang web
  - ...

- Xử lý trình điều hướng (Navigation)
  - `back()`: Quay lại trang trước đó
  - `forward()`: Tiến tới trang tiếp theo
  - `refresh()`: Làm mới trang hiện tại
  - `to(url)`: Điều hướng đến một URL cụ thể
  - ...

## Xử lý biểu mẫu (forms)
- Điền dữ liệu vào các trường biểu mẫu
  - `send_keys(keys)`: Điền dữ liệu vào các trường biểu mẫu bằng cách gửi phím hoặc chuỗi ký tự

- Gửi biểu mẫu
  - `submit()`: Gửi biểu mẫu bằng cách click vào nút `submit`
  - `click()`: Click vào nút `submit` hoặc các phần tử tương tự để gửi biểu mẫu

- Xử lý biểu mẫu (forms)
  - `send_keys(keys)`: Điền dữ liệu vào các trường biểu mẫu bằng cách gửi phím hoặc chuỗi ký tự
  - `submit()`: Gửi biểu mẫu bằng cách click vào nút `submit`
  - `click()`: Click vào nút `submit` hoặc các phần tử tương tự để gửi biểu mẫu


## Kiểm tra và xác nhận
- Kiểm tra thông tin trên trang
  - `text`: Lấy nội dung văn bản của một phần tử
  - `get_attribute(attribute_name)`: Lấy giá trị của thuộc tính của một phần tử
  - Câu lệnh điều kiện: Sử dụng câu lệnh `if` để kiểm tra và xác nhận thông tin trên trang

- So sánh thông tin
  - `assert`: Sử dụng phương thức `assert` để kiểm tra điều kiện và thông báo lỗi nếu điều kiện không đúng
  - Câu lệnh điều kiện: Sử dụng câu lệnh `if` và các phương thức so sánh (`==`, `!=`, `<`, `>`, `<=`, `>=`) để so sánh thông tin

- Xác nhận thông tin
  - In ra thông tin: Sử dụng hàm `print()` để in ra thông tin cần xác nhận trên trang
  - Log lại thông tin: Sử dụng các công cụ log để lưu trữ và xác nhận thông tin

- Kiểm tra và xác nhận
  - `text`: Lấy nội dung văn bản của một phần tử
  - `get_attribute(attribute_name)`: Lấy giá trị của thuộc tính của một phần tử
  - Câu lệnh điều kiện: Sử dụng câu lệnh `if` để kiểm tra và xác nhận thông tin trên trang
  - `assert`: Sử dụng phương thức `assert` để kiểm tra điều kiện và thông báo lỗi nếu điều kiện không đúng
  - In ra thông tin: Sử dụng hàm `print()` để in ra thông tin cần xác nhận trên trang
  - Log lại thông tin: Sử dụng các công cụ log để lưu trữ và xác nhận thông tin


## Đóng trình duyệt
- Đóng trình duyệt hiện tại
  - `close()`: Đóng cửa sổ trình duyệt hiện tại

- Đóng tất cả các cửa sổ trình duyệt và kết thúc phiên làm việc
  - `quit()`: Đóng tất cả các cửa sổ trình duyệt và kết thúc phiên làm việc
