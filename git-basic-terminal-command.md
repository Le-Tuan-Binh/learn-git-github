# 1. Thiết lập tài khoản người sử dụng

- git config --global user.name `"user name"`

  > **Ví dụ**: git config --global user.name "Lê Tuấn Bình"

- git config --global user.email `"user email"`

  > **Ví dụ**: git config --global user.email "ltbinh@gmail.com"

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
- **git add `file`**: Thêm từng file vào Stage Changes, tại đây sẽ sắp xếp lại các file đã được thêm vào

  > **Ví dụ**: git add index.html

- **git add .** : Đưa toàn bộ thay đổi vào Stage Changes

  > **Ví dụ**: git add .

- **git commit -m `message`** : Đưa các sự thay đổi ở vùng Staging area chuyển sang Repository mục đích là tạo ra 1 phiên bản mới và lưu vào lịch sử của Repository.

  > **Ví dụ**: git commit -m 'Add index.html and app.css':

- **git push**: Đẩy lên github
- **git log** : Giúp bạn xem lại thông tin lịch sử commit, nhằm giám sát sự thay đổi của dự án. Commit mới sẽ hiện bên trên, commit cũ sẽ hiện bên dưới (Nếu gặp chữ END thì nhấn phím q để thoát).
- **git show `ID của commit`**: Dùng để xem chi tiết một commit
- **git diff**: Xem sự thay đổi của một file sau khi chúng ta chỉnh sửa (File đó vẫn đang ở khu vực Working directory).
- **gitk**: Mở dashboard xem trực quan hơn.
- **git checkout -b `branch`** : Tạo nhánh mới

  > **Ví dụ**: git checkout -b TBin

- **git checkout `branch`** : Chuyển sang nhánh khác

- **git checkout -- `file name`**: Bỏ đi những thay đổi của file, để file đó trở về như lúc ban đầu. Áp dụng cho file đang ở vùng Working directory.
- **git branch -D `branch`** : Xóa nhánh
- **git rebase `branch`** : Đảm bảo code luôn mới nhất trên nhánh `branch`
- **git pull** : Lấy toàn bộ từ nhánh về

# 6. Git reset

- **git reset --soft `HEAD(Commit trước đó)/ID của commit`**:

  - Lệnh này chỉ đơn giản khi chúng ta quên add một file nào đó và chỉ muốn add thêm vào sau khi reset
  - Dùng để chuyển từ trạng thái đã commit về trạng thái trước lúc chạy lệnh git commit.
  - Tức là từ Repository về lại Staging area. Trong đó commit_id là mã của nhánh mà ta muốn quay lại.

- **git reset --mixed `HEAD(Commit trước đó)/ID của commit`** (mặc định): Sẽ reset những commit trước đó và những Stage Changes
- **git reset `file name`**: Chuyển file đó từ vùng Staging area trở lại vùng Working directory.
- **git reset --hard `HEAD(Commit trước đó)/ID của commit`**: Xóa tất cả commit trước đó nếu có

# 7. Một số thứ thường thấy khi làm việc chung

- Create pull request
- Merge code to branch Master
