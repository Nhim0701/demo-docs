## Quy tắc Font-End
### 1. VS code
 - Cài đặt eslint
     - Cài đặt "Prettier - Code formatter" và bật auto format
     - Tabspace 4
     - Bật xóa space ở cuối "Trim Auto Whitespace"

### 2. Naming Convention
 - Functions and Method    
      - Tên hàm và phương thức viết theo dạng "camelCase"
 - Constants
      - Tên biến constant viết theo dạng "SNAKE_UPPER_CASE"
 - Variables:
      - Tên biến, hàm viết theo dạng "camelCase"
      - Tên class (css, scss) viết theo dạng "kebab-case"
      - Tên biến language theo dạng "snake_case"

### 3. Assets
 - icon sử dụng svg/png
 - css sử dụng scss

### 4. Form validate
 - validate các input, select trước khi request API (các trường có ràng buộc đặc thù, tồn tại, rỗng).
 
### 5. Language
 -  Nếu label là mã lỗi hoặc sử dụng nhiều lần thì định nghĩa trong locales/*.ts 
 -  Nếu dùng chỉ trong page thì định nghĩa local trong file vue luôn

### 6. Code
 - Flow logic code xử lý > 5 dòng code nên tách ra 1 hàm riêng
 - Mỗi chức năng (Flow logic code xử lý) nên được viết hàm mới riêng biệt (tránh 1 hàm có nhiều logic code khó kiểm soát)
 - style ở các component nên thêm "scoped" vào để phạm vi sử dụng chỉ ở component đó (local styles)
 - router sử dụng Lazy loading routers (khi chuyển trang không load lại toàn bộ js, mà chỉ load các nội dung js cần thiết)

### 7. Tham khảo
 - Style scoped: https://vuejs.org/api/sfc-css-features.html#scoped-css
 - Lazy loading router: https://vueschool.io/lessons/lazy-loading-routes-vue-cli-only?friend=vuerouter