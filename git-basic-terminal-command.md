# 1. Thiết lập tài khoản người sử dụng

- git config --global user.name `"user name"`

  > Ví dụ: git config --global user.name "Lê Tuấn Bình"

- git config --global user.email `"user email"`

  > Ví dụ: git config --global user.email "ltbinh@gmail.com"

# 2. Các bước tạo ssh key

https://blog.nguyenary.dev/cach-tao-ssh-key-va-su-dung-no-voi-gitlab-va-github.html

# 3. Các thuật ngữ quan trọng

- **Working directory** (Thư mục làm việc): Khu vực chứa dự án mà chúng ta đang làm việc.
- **Staging area** (Khu vực sắp xếp): khu vực chứa thông tin thay đổi của các file.
- **Repository** (Git directory - thư mục git): Kho lưu trữ để lưu trữ dữ liệu, lịch sử các phiên bản.
- [Git Flow](https://i.stack.imgur.com/1ijIQ.png): Quá trình thực thi của Git

# 4. Một số lệnh Git cơ bản trên terminal

- **git --version**: Xem phiên bản hiện tại đang được cài trên máy tính.
- **git --help**: Xem danh sách các câu lệnh Git.
- **ls** : Hiển dị danh sách các file
- **clear** : Xóa hiển thị terminal

# 5. Các lệnh cơ bản

- **git init**:
  - Khởi tạo 1 git repository (kho lưu trữ) trong một dự án mới hoặc dự án đã có (Dùng trong thư mục gốc của dự án).
  - Khi khởi tạo xong, trong thư mục gốc (dự án đang làm) sẽ sinh ra một thư mục tên là .git, thư mục này sẽ lưu toàn bộ thông tin lịch sử của dự án mà bạn làm. Chúng ta không cần quan tâm bên trong thư mục này chứa gì.
- **git status** : Để xem trạng thái của những file đã được thay đổi (bao gồm: thêm, sửa, xóa) trong dự án.
- **git add `file`**: Thêm từng file vào Stage Changes

  > Ví dụ: git add index.html

- **git add .** : Đưa toàn bộ thay đổi vào Stage Changes
  
  > Ví dụ: git add .

- **git commit -m `message`** : Đưa các sự thay đổi lên

  > Ví dụ: git commit -m 'Add index.html and app.css':

- **git push**: Đẩy lên github
- **git checkout -b `branch`** : Tạo nhánh mới

  > Ví dụ: git checkout -b TBin

- **git checkout `branch`** : Chuyển sang nhánh khác
- **git branch -D `branch`** : Xóa nhánh
- **git rebase `branch`** : Đảm bảo code luôn mới nhất trên nhánh `branch`
- **git log --oneline** : Log ra những commit

- **git pull** : Lấy toàn bộ từ nhánh về

# 6. Git reset

- **git reset --soft HEAD(`Commit trước đó/ID của commit`)**: Lệnh này chỉ đơn giản khi chúng ta quên add một file nào đó và chỉ muốn add thêm vào sau khi reset
- **git reset --mixed HEAD(`Commit trước đó/ID của commit`)** (mặc định): Sẽ reset những commit trước đó và những Stage Changes
- **git reset --hard HEAD(`Commit trước đó/ID của commit`)**: Xóa tất cả commit trước đó nếu có

# 7. Một số thứ thường thấy khi làm việc chung

- Create pull request
- Merge code to branch Master
