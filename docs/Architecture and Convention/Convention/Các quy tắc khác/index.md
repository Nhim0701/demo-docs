## Quy tắc quản lý source/git

### 1. Cách đặt tên branch
 - Tên branch" feature_{key_issues_backlog}. VD: feature_C_SEATCHART-2

### 2. Chú ý trước khi làm 
 - chuyển trạng thái thành "In Progress", 
 - điền thời gian dự kiến làm(ước lượng không cần phải đúng 100%), 
 - ngày bắt đầu làm
 - có vấn đề gì comment dưới backlog

### 3. Chú ý làm xong
 - Làm xong tạo pullrequest qua develop

## Check list code

### 1. Setting
 - Cài đặt bắt buộc Eslint và Prettier
 - Setup VS Code: auto format on save, Tabsize 2 space
 - Các hàm dùng chung thì phải có tính Global. Có nghĩa là có thể dùng ở nhiều nơi, nhiều trường hợp mà không cần thay đổi quá nhiều.
 - Khi viết hàm chung cần thảo luận với Leader trước khi làm hoặc đã được cho phép từ trước

### 2. Front-end
 - Template dùng pug template 
 - Style dùng SASS
 - KHÔNG DÙNG JQUERY.
 - KHÔNG DÙNG v-html.
 - Syntax vue ver_3 không dùng syntax vue ver_2
 - File style(sass) tạo ra 1 file riêng và import ở file .vue và PHẢI DÙNG scoped 

### 3. Back-end
 - Các function response đều phải viết Document API 
 - SQL dùng theo syntax thư viện gorm HẠN CHẾ DÙNG sql raw

### 4. Mỗi module sẽ có language riêng, menu riêng, css riêng. Những phần nào dùng chung cho nhiều module mới viết thư mục bên ngoài cùng.

### 5. Khi add 1 package mới hoặc update package hoặc add vendor mới cần xác nhận với leader trước không được tự ý thao tác nếu không rõ.

### 6. Đặt tên hàm, tên biến 
 - Back-end: 
    - Tên hàm chữ đầu viết hoa và theo quy tắc camelCase. VD: GetUser, GetUserById, ...
    - Tên biến đặt theo quy tắc camelCase. Chữ đầu có không cần viết hoa.
    - Các function dùng nội bộ trong 1 file thì theo quy định có dấu underscore ở đầu. VD: _HandleData, ...
 - Front-end
    - Cả hàm và biến cần định nghĩa type rõ ràng. Hạn chế dùng ANY.
    - Tên hàm theo quy tắc camelCase. VD: handleData, ...
    - Tên biến: có thể underscore hoặc camelCase.
