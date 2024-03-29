# 1. Thiết lập tài khoản người sử dụng

**Thiết lập tên người dùng**

```zsh
git config --global user.name "user name"
```

**Thiết lập email người dùng**

```zsh
git config --global user.email "user email"
```

# 2. Các bước tạo ssh key

https://blog.nguyenary.dev/cach-tao-ssh-key-va-su-dung-no-voi-gitlab-va-github.html

# 3. Các thuật ngữ quan trọng

**Working directory**: Khu vực chứa dự án mà chúng ta đang làm việc.

**Staging area**: khu vực chứa thông tin thay đổi của các file.

**Repository**: Kho lưu trữ để lưu trữ dữ liệu của git, lịch sử các phiên bản.

[**Git Flow**](https://i.stack.imgur.com/1ijIQ.png): Quá trình thực thi của Git

# 4. Một số lệnh Git cơ bản trên terminal

**git --version**

```zsh
git --version : Xem phiên bản hiện tại đang được cài trên máy tính.
git version 2.43.0.windows.1
```

**git --help**

```zsh
git --help : Xem hướng dẫn các câu lệnh của git
```

**ls**

```zsh
ls : Hiển dị danh sách các file
```

**clear**

```zsh
clear : Xóa hiển thị terminal
```

# 5. Các lệnh cơ bản

**git init**

```zsh
git init
```

Khởi tạo 1 git `repository` (kho lưu trữ) trong một dự án mới hoặc dự án đã có (Dùng trong thư mục gốc của dự án).

Khi khởi tạo xong, trong thư mục gốc (dự án đang làm) sẽ sinh ra một thư mục tên là .git, thư mục này sẽ lưu toàn bộ thông tin lịch sử của dự án mà bạn làm. Chúng ta không cần quan tâm bên trong thư mục này chứa gì.

**git status**

```zsh
git status
```

Để xem trạng thái của những file đã được thay đổi (bao gồm: thêm, sửa, xóa) trong dự án.

**git add `file`**

```zsh
git add file
```

Thêm từng file vào Stage Changes, tại đây sẽ sắp xếp lại các file đã được thêm vào

**git add .**

```zsh
git add .
```

Đưa toàn bộ thay đổi vào Stage Changes

**git commit -m `message`**

```zsh
git commit -m "message"
```

Đưa các sự thay đổi ở vùng Staging area chuyển sang Repository mục đích là tạo ra 1 phiên bản mới và lưu vào lịch sử của Repository.

**git push**

```zsh
git push
```

Đẩy toàn bộ lên github

**git log**

```zsh
git log
```

Giúp bạn xem lại thông tin lịch sử commit, nhằm giám sát sự thay đổi của dự án. Commit mới sẽ hiện bên trên, commit cũ sẽ hiện bên dưới (Nếu gặp chữ END thì nhấn phím q để thoát).

**git show `ID của commit`**

```zsh
git show <ID của commit>
```

Dùng để xem chi tiết một commit

**git diff**

```zsh
git diff
```

Xem sự thay đổi của một file sau khi chúng ta chỉnh sửa (File đó vẫn đang ở khu vực Working directory).

**gitk**

```zsh
gitk
```

Mở dashboard xem trực quan hơn các lịch sử commit cũng như các thông tin trên git

**git pull**

```zsh
git pull
```

Lấy toàn bộ từ nhánh trên github về

# 6. Git checkout và Git branch

**git checkout -b `branch`**

```zsh
git checkout -b <branch name>
```

Tạo nhánh mới và chuyển sang nhánh đó

**git checkout `branch`**

```zsh
git checkout <branch name>
```

Chuyển sang nhánh khác

**git checkout -- `file name`**

```zsh
git checkout -- <file name>
```

Bỏ đi những thay đổi của file, để file đó trở về như lúc ban đầu. Áp dụng cho file đang ở vùng Working directory.

**git branch**

```zsh
git branch
```

Xem danh sách các nhánh.

Các branch (nhánh) đại diện cho các phiên bản cụ thể của một kho lưu trữ tách ra từ project chính của bạn.

Nhánh master là nhánh chính, để sau này deploy lên server.

**git branch -D `branch`**

```zsh
git branch -D <branch name>
```

Xóa nhánh

**git rebase `branch`**

```zsh
git rebase <branch name>
```

Đảm bảo code luôn mới nhất trên nhánh `branch`

**git merge `branch name`**

```zsh
git merge <branch name>
```

Để merge nhánh **`branch name`** vào trong nhánh hiện tại.

Ví dụ: Ta có 2 nhánh A và B, để hợp nhất nhánh B vào trong nhánh A ta làm như sau:

-   Dùng lệnh git checkout A để chuyển sang nhánh A

-   Sau đó chạy lệnh git merge B để hợp nhất nhánh B vào nhánh A.

# 7. Git reset

**git reset --soft `HEAD(Commit trước đó)/ID của commit`**

```zsh
git reset --soft <HEAD(Commit trước đó)/ID của commit>
```

-   Lệnh này chỉ đơn giản khi chúng ta quên add một file nào đó và chỉ muốn add thêm vào sau khi reset
-   Dùng để chuyển từ trạng thái đã commit về trạng thái trước lúc chạy lệnh git commit.
-   Tức là từ Repository về lại Staging area. Trong đó `ID của commit` là mã của nhánh mà ta muốn quay lại.
-   Reset commit nhưng code vẫn ở trong stage, sẵn sàng cho bạn commit lại.

**git reset --mixed `HEAD(Commit trước đó)/ID của commit`** (mặc định)

```zsh
git reset --mixed <HEAD(Commit trước đó)/ID của commit>
```

-   Sẽ reset những commit trước đó và những Stage Changes
-   Dùng để chuyển từ trạng thái đã commit về trạng thái trước lúc chạy lệnh git add.
-   Tức là từ Repository về lại Working directory. Trong đó `ID của commit` là mã của nhánh mà ta muốn quay lại.
-   Reset commit và đẩy code ra khỏi stage. Bạn cần dùng git add trước khi có thể commit lại.

**git reset `file name`**

```zsh
git reset <file name>
```

Chuyển file đó từ vùng Staging area trở lại vùng Working directory.

**git reset --hard `HEAD(Commit trước đó)/ID của commit`**

```zsh
git reset --hard <HEAD(Commit trước đó)/ID của commit>
```

Reset commit và xóa toàn bộ code bạn đã làm.

# 8. Các thao tác giữa Git và Github

**git clone `ssh_link_in_github/http_link_in_github`**

```zsh
git clone <ssh_link_in_github/http_link_in_github>
```

Dùng để clone repository từ `Github` về máy.

**Đẩy lên Github khi thư mục đã có Git**

```zsh
git remote add origin `http_link_in_github`
git branch -M main
git push -u origin main
```

**Đẩy code lần đầu lên Github khi project chưa có Git**

```zsh
git init
git add .
git commit -m "Nội dung commit"
git branch -M main
git remote add origin url_github_https
git push -u origin main

```

# 9. Git Flow

# 10. Quy trình làm việc với github trong thực tế

## 10.1 Bắt đầu một dự án

Khi bắt đầu một dự án, hoặc tham gia vào một dự án bất kì, bạn cần phải đảm bảo trên thư mục của bạn đã có được toàn bộ dữ liệu của dự án thông qua câu lệnh

```zsh
git clone <url>
```

Thêm 1 típ nhỏ, là nếu bạn muốn tên folder sau khi clone về khác tên project trên remote thì hãy đặt tên folder ở cuối lệnh:

```zsh
git clone <url> folder_name
```

## 10.2 Giai đoạn xuyên suốt dự án

Khi được giao một nhiệm vụ xử lý một chức năng hay một yêu cầu nào đó bạn cần phải đảm bảo soucre trên máy của mình đã hoàn toàn trùng với source trên nhánh của dự án

**Bước 1**: Bạn cần di chuyển về nhánh `master / main` là nhánh chính của toàn bộ dự án

```zsh
git checkout <master/main>
```

**Bước 2**: Lấy toàn bộ source mới nhất về máy

```zsh
git pull
```

**Bước 3**: Kiểm tra source trên máy local đã cập nhật mới nhất so với trên nhánh chưa

```zsh
git log --oneline
```

**Bước 4**: Di chuyển đồng thời tạo một nhánh mới để thực hiện phần chức năng của bạn

```zsh
git checkout -b feature_branch
```

**Bước 5**: Thêm các thay đổi vào stage change

```zsh
git add .
```

**Bước 6**: Commit toàn bộ những thay đổi lên nhánh

```zsh
git commit -m "Nội dung"
```

**Bước 7**: Đây toàn bộ thay đổi lên repository

```zsh
git push origin feature_branch
```

**Bước 8**: Di chuyển hoặc truy cập vào repository, tạo merge request và chờ xử lý

**Lưu ý**

Nếu branch của bạn có nhiều người làm chung, bạn chưa kịp push code thì đã có người khác push trước. Vậy thì trước khi push thì hãy pull theo cách này

```zsh
git pull --rebase
```

Commit của bạn sẽ được đẩy lên trên commit của đồng nghiệp trong log.

Trong trường hợp bạn muốn lấy code về nhưng chưa muốn merge thì hãy dùng lệnh:

```zsh
git fetch
```

# 11. Git stash

Bạn có thể dùng cái này để lưu tạm code trước khi thực hiện các lệnh rebase hay checkout sang branch khác mà bị conflict.

Bạn cứ tưởng tượng nó như một tờ giấy nháp lưu theo cấu trúc stack vậy.

Khi muốn **lưu tất cả những thay đổi hiện tại vào stash**

```zsh
git stash
```

Khi muốn **apply stash cuối cùng vừa lưu**

```zsh
git stash pop
```
