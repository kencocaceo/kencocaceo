Mọi người chạy lệnh dưới để cài đặt nhé commitlint nhé.

```
npm install
npm run prepare
```

Sau đó mỗi lần commit thì mọi người commit theo rule sau: `type(scope): subject`
Trong đó:
- type bao gồm:
  - fix: dành cho các task fix bugs
  - feat: dành cho các task mới
  - style: dành cho các task chỉ chỉnh sửa giao diện
  - refactor: dành cho các task refactor hệ thống.
  
- sope: được định nghĩa như sau. ds_{id của issue}|no_{id tài liệu}
- subject: là nội dung của task mà bạn cần làm. có về viết nhiều dòng

**Example:**
```
feat(ds_32|no_16): confirm affiliates screen (mô tả chung)
<new_line>
(Mô tả chi tiết task ở dưới)
- coding screen confirm
- handle email sending.
```

*Lưu ý: khi mọi người tạo pull request thì chỉ chứa 1 commit với cú pháp như trên nhé.*

**Gitflow:**
Khi mọi người đang làm thì có thể tạo nhiều commit để lưu vết trong quá trình làm.

Sau khi implement task xong thì mọi người phải gộp nhiều commit thành 1 commit duy nhất bằng lệnh `git rebase -i HEAD~n (n  là số commit bạn muốn gộp)`. 
Như vậy quá trình review sẽ dễ dàng nắm bắt được commit bạn muốn làm gì thay vì ngồi đọc 10 commit trong đó có cả commit merge ngược develop vào branch :)).

Tiếp theo đó pull rebase với nhánh develop để đưa commit của mọi người lên đầu tiên.
`git pull --rebase origin develop`
Nếu có conflict thì sửa push lại lên nhánh của mọi người nhé.

*Lưu ý: Sau khi branch đã được merge thì không được làm tiếp trên branch đó nữa mà sẽ tạo 1 branch khác với suffix nhé.*
