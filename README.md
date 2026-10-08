# BÁO CÁO KIỂM THỬ API

**Tên Dự Án:** Hieu - REST API Testing

**Ngày Kiểm Thử:** 10/2026

**Người Kiểm Thử:** Phạm Văn Hiếu - 23010185

## 1. Mục Tiêu Kiểm Thử

Sử dụng Postman để kiểm thử một REST API thực tế.

Bài kiểm thử nhằm kiểm tra khả năng gửi request, nhận response và xử lý các phương thức HTTP phổ biến gồm GET, POST, PUT và DELETE.

## 2. Môi Trường Kiểm Thử

- Công cụ kiểm thử: Postman
- API sử dụng: JSONPlaceholder
- Kiểu API: REST API
- Định dạng dữ liệu: JSON
- Hệ điều hành: Windows

## 3. Phương Pháp Kiểm Thử

Kiểm thử thủ công trên phần mềm Postman.

Các request được tạo trong Collection `Long - REST API Testing`. Sau khi gửi request, tiến hành kiểm tra Status Code, Response Body và đối chiếu kết quả thực tế với kết quả mong đợi.

---

## 4. Kịch Bản Kiểm Thử Lần 1

- **Tên Kịch Bản:** Kiểm thử lấy danh sách tất cả bài viết

- **Mục Đích:** Kiểm tra khả năng hoạt động của API khi lấy danh sách bài viết.

- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET

- **URL:** `https://jsonplaceholder.typicode.com/posts`

- **Tham Số:** Không có

- **Kết Quả Mong Đợi:** Gửi yêu cầu thành công và nhận được danh sách bài viết với Status Code `200 OK`.

- **Kết Quả Thực Tế:** API trả về danh sách bài viết dưới dạng JSON với Status Code `200 OK`.

- **Trạng Thái:** Thành công

- **Kết quả sau khi kiểm thử:**

![TC01 - Get All Posts](./images/TC01-get-all-posts.png)



---

## 5. Kịch Bản Kiểm Thử Lần 2

- **Tên Kịch Bản:** Kiểm thử lấy bài viết theo ID

- **Mục Đích:** Kiểm tra khả năng lấy thông tin một bài viết thông qua ID.

- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET

- **URL:** `https://jsonplaceholder.typicode.com/posts/1`

- **Tham Số:** `id = 1`

- **Kết Quả Mong Đợi:** Gửi yêu cầu thành công và nhận được thông tin bài viết có ID bằng `1`.

- **Kết Quả Thực Tế:** API trả về thông tin bài viết có ID `1` với Status Code `200 OK`.

- **Trạng Thái:** Thành công

- **Kết quả sau khi kiểm thử:**

![TC02 - Get Post By ID](./images/TC02-get-post-by-id.png)



---

## 6. Kịch Bản Kiểm Thử Lần 3

- **Tên Kịch Bản:** Kiểm thử lấy bài viết không tồn tại

- **Mục Đích:** Kiểm tra khả năng xử lý của API khi yêu cầu một bài viết không tồn tại.

- **Phương Thức HTTP (GET/POST/PUT/DELETE):** GET

- **URL:** `https://jsonplaceholder.typicode.com/posts/9999`

- **Tham Số:** `id = 9999`

- **Kết Quả Mong Đợi:** API trả về phản hồi phù hợp khi bài viết với ID được yêu cầu không tồn tại.

- **Kết Quả Thực Tế:** API trả về Status Code `404 Not Found` và Response Body là `{}`.

- **Trạng Thái:** Thành công

- **Kết quả sau khi kiểm thử:**

![TC03 - Invalid Post](./images/TC03-invalid-post.png)

---

## 7. Kịch Bản Kiểm Thử Lần 4

- **Tên Kịch Bản:** Kiểm thử tạo bài viết mới

- **Mục Đích:** Kiểm tra khả năng của API trong việc tiếp nhận request tạo một bài viết mới.

- **Phương Thức HTTP (GET/POST/PUT/DELETE):** POST

- **URL:** `https://jsonplaceholder.typicode.com/posts`

- **Tham Số:** Không có

- **Dữ Liệu Gửi Đi:**

```json
{
    "title": "Postman API Testing",
    "body": "This is a test post created with Postman.",
    "userId": 1
}
```

- **Kết Quả Mong Đợi:** API tiếp nhận request thành công và trả về thông tin bài viết được gửi trong request.

- **Kết Quả Thực Tế:** API trả về response chứa dữ liệu bài viết được gửi trong request với Status Code `201 Created`.

- **Trạng Thái:** Thành công

- **Kết quả sau khi kiểm thử:**

![TC04 - Create Post](./images/TC04-create-post.png)


---

## 8. Kịch Bản Kiểm Thử Lần 5

- **Tên Kịch Bản:** Kiểm thử cập nhật bài viết

- **Mục Đích:** Kiểm tra khả năng cập nhật thông tin bài viết bằng phương thức PUT.

- **Phương Thức HTTP (GET/POST/PUT/DELETE):** PUT

- **URL:** `https://jsonplaceholder.typicode.com/posts/1`

- **Tham Số:** `id = 1`

- **Dữ Liệu Gửi Đi:**

```json
{
    "id": 1,
    "title": "Updated Postman Testing",
    "body": "The post has been updated using PUT.",
    "userId": 1
}
```

- **Kết Quả Mong Đợi:** API tiếp nhận request cập nhật thành công và trả về thông tin bài viết sau khi cập nhật.

- **Kết Quả Thực Tế:** API trả về response chứa dữ liệu bài viết sau khi thực hiện request PUT với Status Code `200 OK`.

- **Trạng Thái:** Thành công

- **Kết quả sau khi kiểm thử:**

![TC05 - Update Post](./images/TC05-update-post.png)


---

## 9. Kịch Bản Kiểm Thử Lần 6

- **Tên Kịch Bản:** Kiểm thử xóa bài viết

- **Mục Đích:** Kiểm tra khả năng xử lý request xóa một bài viết.

- **Phương Thức HTTP (GET/POST/PUT/DELETE):** DELETE

- **URL:** `https://jsonplaceholder.typicode.com/posts/1`

- **Tham Số:** `id = 1`

- **Kết Quả Mong Đợi:** API tiếp nhận yêu cầu DELETE và trả về response thành công.

- **Kết Quả Thực Tế:** API xử lý request DELETE thành công với Status Code `200 OK`.

- **Trạng Thái:** Thành công

- **Kết quả sau khi kiểm thử:**

![TC06 - Delete Post](./images/TC06-delete-post.png)

---

## 10. Kết Quả Kiểm Thử

Tóm tắt kết quả kiểm thử:

- **Số lượng kịch bản đã kiểm thử:** 6
- **Số lần thành công:** 6
- **Số lần thất bại:** 0
- **Tỉ lệ thành công:** 100%

| Kịch bản | Phương thức | Nội dung | Trạng thái |
|---|---|---|---|
| TC01 | GET | Lấy danh sách tất cả bài viết | Thành công |
| TC02 | GET | Lấy bài viết theo ID | Thành công |
| TC03 | GET | Lấy bài viết không tồn tại | Thành công |
| TC04 | POST | Tạo bài viết mới | Thành công |
| TC05 | PUT | Cập nhật bài viết | Thành công |
| TC06 | DELETE | Xóa bài viết | Thành công |

---

## 11. Phát Hiện Lỗi

### TC03 - 404 Not Found

- **ID Lỗi:** 404 Not Found
- **Mô Tả Lỗi:** API không tìm thấy bài viết với ID `9999`.
- **Mức Độ Ảnh Hưởng:** Không ảnh hưởng đến các API khác.
- **Ghi Chú/Đề Xuất:** Đây là trường hợp được xây dựng để kiểm tra việc API xử lý khi yêu cầu dữ liệu không tồn tại.

---

## 12. Kết Luận

Thông qua bài thực hành, em đã sử dụng Postman để kiểm thử REST API với các phương thức GET, POST, PUT và DELETE.

Các kịch bản kiểm thử bao gồm trường hợp lấy dữ liệu hợp lệ, tạo dữ liệu, cập nhật dữ liệu, xóa dữ liệu và xử lý trường hợp dữ liệu không tồn tại.

Kết quả kiểm thử cho thấy các request được thực hiện và phản hồi phù hợp với mục đích của từng kịch bản.

Bài thực hành giúp em hiểu rõ hơn về cách gửi HTTP Request, kiểm tra HTTP Response và đánh giá kết quả khi kiểm thử API bằng Postman.
