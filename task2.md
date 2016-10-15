##1.Git 
-------
- Git là hệ thống quản lý phiên bản phân tán
Trên Git, có thể lưu trạng thái của file khi có nhu cầu dưới dạng lịch sử cập nhật. Vì thế, có thể đưa file đã chỉnh sửa một lần về trạng thái cũ hay có thể hiển thị sự khác biệt ở nơi chỉnh sửa.
Thêm nữa, khi định ghi đè (overwrite) lên file mới nhất đã chỉnh sửa của người khác bằng file đã chỉnh sửa dựa trên file cũ, thì khi đăng (upload) lên server sẽ hiện ra cảnh cáo. Vì thế, sẽ không xảy ra thất bại về việc đã ghi đè lên nội dung chỉnh sửa của người khác mà không hề hay biết.
##2.Cài đặt Git trên máy tính.
------------------------------
- Vô trang http://rogerdudler.github.io/git-guide/ để tải bản phù hợp với hệ điều hành đang dùng
- Sau khi tải về, mở file exe để cài đặt
<img src="http://i.imgur.com/4wQ8zvf.jpg">

Ấn next
<img src="http://i.imgur.com/ES2K0fm.jpg">
Chọn đường dẫn bạn muốn cài đặt Git vào.
<img src="http://i.imgur.com/dHQ93oR.jpg">
Bạn muốn tạo biểu tượng ở destop thì chọn `On the Destop` nếu không cần thì thôi. Sau đó chọn next để qua bước tiếp theo
<img src="http://i.imgur.com/hSt4lAw.jpg">
Để mặc định như hình là tốt nhất
<img src="http://i.imgur.com/wKamk52.jpg">
Chọn kiểu style thích hợp, windown hoặc unix
<img src="http://i.imgur.com/1vi2Jnn.jpg">
Đợi chạy xong là hoàn thành việc cài đặt.
##3. Sử dụng git trên cmd
-------------------------
1. **Để tạo 1 repository mới**, bạn hãy mở cửa sổ lệnh và gõ dòng lệnh sau: `git init`
Lệnh này sẽ tạo một thư mục mới có tên `.git` , thư mục này chứa tất cả các tập tin cần thiết cho kho chứa
<img src="http://i.imgur.com/YPhTDo4.jpg">
ở đây đường dẫn thư mục chứa repo là C:/Users/HT/.gits/
Sau đó add repo mà bạn muốn commit hay push `git add <đường dẫn>` ở đây là `git add Desktop/task02.md`
Commit cho lần đầu tiên này để theo dõi, dùng lệnh
`git commit -m 'ghi chú cho thư mục'`
<img src="http://i.imgur.com/vwCY97D.jpg">
Sau khi thay đổi nội dung của file mà chúng ta đã đánh dấu. Khi gõ lệnh `git status` sẽ xuất hiện thông báo tập tin nằm trong danh sách "Các thay đổi chưa được tổ chức/đánh dấu để commit" - có nghĩa là một tập tin đang được theo dõi đã bị thay đổi trong thư mục làm việc nhưng chưa được "staged"
<img src="http://i.imgur.com/m5ZKIns.jpg">
để giải quyết việc này bạn cần add lại nó một lần nữa bằng các `git add` sau đó chỉ việc commit tên lần sữa đổi này `git commit -m`
2. **Xem lại các thay đổi**
Dùng lệnh `git diff`. Nếu muốn xem lịch sử commit dùng `git log`
3.**Phục hồi lại tập tin**
`git checkout -- <đường dẫn>`
4. **Xóa tập tin không cần theo dõi nữa**
Dùng lệnh `git rm <đường dẫn>`
5. **Push  các thay đổi**
Thay đổi mới nhất của bạn hiện đang nằm ở HEAD của bản sao
Để gửi thay đổi đó đến repository remote dùng lệnh `git push <tên máy chủ> <nhánh bạn muốn dùng>`
Nếu bạn chưa clone một repo hiện có và muốn kết nối đến máy chủ remote, bận cần
`git remote add origin <máy-chủ>`
##4 Sử dụng git để commit/ push file task2 lên github
-----------------------------------------------------
đầu tiền ta phải clone đường dẫn cần push về bằng cách `git clone <đường dẫn>`
<img src="http://i.imgur.com/N3aZv6N.jpg">
Sau khi chạy xong, tất cả các thư mục trong pysthon_training được tải về ở thư mục .git
Lúc này ta chỉ cần đặt file task2 vào thư mục sau đó add 
Tiếp theo ta commit cho thay đổi này
Đặt tag theo yêu cầu của người giao ở đây là `task02_git` bằng cứ pháp `git tag task02_git`
Sau đó chỉ việc push lên là xong