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
- Quá trình làm việc của Git: [Git flow](https://i.stack.imgur.com/1ijIQ.png)

# 4. Các lệnh cơ bản

- git add `file` -> git add index.html: Thêm từng file vào Stage Changes
- git add . -> Đưa toàn bộ thay đổi vào Stage Changes
- git commit -m `message` -> git commit -m 'Add index.html and app.css': Đưa các sự thay đổi lên
- git push: Đẩy lên github
- git checkout -b `branch` -> git checkout -b TBin: Tạo nhánh mới
- git checkout `branch` -> Chuyển sang nhánh khác
- git branch -D `branch` -> Xóa nhánh
- git rebase `branch` -> Đảm bảo code luôn mới nhất trên nhánh `branch`
- git log --oneline: Log ra những commit
- git status: Kiểm tra trạng thái của các file
- ls: Hiển dị danh sách các file
- clear: Xóa hiển thị terminal
- git pull: Lấy toàn bộ từ nhánh về

# 5. Git reset

- git reset --soft HEAD(Commit trước đó/ID của commit): Lệnh này chỉ đơn giản khi chúng ta quên add một file nào đó và chỉ muốn add thêm vào sau khi reset
- git reset --mixed HEAD(Commit trước đó/ID của commit) (mặc định): Sẽ reset những commit trước đó và những Stage Changes
- git reset --hard HEAD(Commit trước đó/ID của commit): Xóa tất cả commit trước đó nếu có

# 6. Một số thứ thường thấy khi làm việc chung

- create pull request
- merge code to branch Master
