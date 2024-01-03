Qui tắc API (REST API):

1. Methods:
     - GET: Trả về một Resource hoặc một danh sách Resource.
     - POST: Tạo mới một Resource.
     - PUT: Cập nhật thông tin cho Resource.
     - DELETE: Xoá một Resource.

2. Headers:
    - Authorization: Bearer + {token string}
    - timestamp: {timestamp} Ex: 1702535201
    - Content-Type: application/json

3. Status:
     - 200 OK – Trả về thành công cho những phương thức GET, POST, PUT hoặc DELETE.
     - 400 Bad Request – Request không hợp lệ
     - 401 Unauthorized – Request cần có xác thực.
     - 404 Not Found – Không tìm thấy resource từ URI
     - 429 Too Many Requests – Request bị từ chối do bị giới hạn

4. URL API Convention
    - Sử dụng Method Request để nói lên nhiệm vụ, không cần thêm các động từ create, get, update, delete nữa
    - Resource name sẽ ở dạng số nhiều (posts, categories,...)
    - Url đều là chữ viết thường (lowercase), sử dụng dấu "-" thay vì dấu "_"

5. Naming Convention
* Functions and Method
    - Tên hàm và phương thức viết theo dạng "camelCase"

* Constants
    - Tên biến constant viết theo dạng "SNAKE_UPPER_CASE"
    - Định nghĩa trong layer

* Variables
    - Tên biến viết theo dạng "camelCase"

6. Code
    - Các hàm/ variable common viết/ định nghĩa trong layer
    - Validate các param từ request (Các trường có ràng buộc đặc thù, tồn tại, rỗng)
    - Mỗi chức năng (Flow logic code xử lý) nên được viết 1 lambda 
