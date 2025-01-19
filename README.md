# Template-Repo


## 1. `Pyproject.toml`
### 1.1 Định nghĩa 

Tệp `pyproject.toml` là một tệp cấu hình được giới thiệu trong PEP 518 và PEP 517, nhằm chuẩn hóa việc xây dựng và phân phối các dự án Python. Nó cung cấp một cách thống nhất để khai báo các yêu cầu và cấu hình của hệ thống xây dựng, giúp các công cụ như pip xác định và cài đặt các phụ thuộc cần thiết để xây dựng dự án.

### 1.2 Tại sao sử dụng `pyproject.toml`
***Thay thế nhiều file cấu hình*** : Trước đây, các dự án Python thường sử dụng nhiều file cấu hình khác nhau (như `setup.py`, `requirements.txt`, v.v.). `pyproject.toml` giúp hợp nhất tất cả các thông tin này vào một file duy nhất, làm cho việc quản lý dự án trở nên đơn giản hơn.

***Hỗ trợ nhiều công cụ***: File này không chỉ dùng cho việc quản lý các gói phụ thuộc mà còn có thể được sử dụng bởi nhiều công cụ khác như linter, formatter, type checker, v.v. Điều này giúp đảm bảo tính nhất quán và dễ quản lý trong toàn bộ dự án.


### 1.3 Các thành phần trong `pyproject.toml`
Trong file `pyproject.toml` có 3 thành phần chính 
    - `[build-system]` khai báo backend xây dựng mà bạn sử dụng và các phụ thuộc khác cần thiết để xây dựng dự án.
    - `[project]` là định dạng mà hầu hết các backend xây dựng sử dụng để chỉ định siêu dữ liệu cơ bản của dự án, chẳng hạn như các phụ thuộc, tên của tác giả, v.v.
    - `[tool]` chứa các bảng con cụ thể cho từng công cụ, ví dụ, `[tool.hatch]`, `[tool.black]`, `[tool.mypy]`, v.v . Nội dung của bảng này được định nghĩa bởi từng công cụ cụ thể. Hãy tham khảo tài liệu của công cụ cụ thể để biết những gì nó có thể chứa.

## 2. `uv.lock`
Tệp `uv.lock` là một phần quan trọng trong hệ thống quản lý phụ thuộc của công cụ uv, được thiết kế để khóa các phiên bản phụ thuộc của dự án Python, đảm bảo tính nhất quán và khả năng tái tạo môi trường trên nhiều nền tảng khác nhau.

### 2.1 Chức năng chính

***Khóa Phiên bản Phụ thuộc***: Tệp uv.lock ghi lại các phiên bản chính xác của các gói phụ thuộc được sử dụng trong dự án, giúp đảm bảo rằng môi trường phát triển và sản xuất đều sử dụng cùng một phiên bản, tránh các vấn đề không tương thích. 


***Hỗ Trợ Đa Nền Tảng***: Khác với tệp requirements.txt, uv.lock hỗ trợ khóa phụ thuộc cho nhiều nền tảng khác nhau, cho phép tạo ra các môi trường nhất quán trên các hệ điều hành khác nhau. 


