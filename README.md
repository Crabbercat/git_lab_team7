# Git Lab Team 7 — Merge Conflict Practice

## 🎯 Mục tiêu

Bài thực hành này giúp các thành viên làm quen với quy trình làm việc nhóm trên GitHub:

* Clone repository về máy local.
* Tạo branch riêng.
* Thực hiện thay đổi trên branch.
* Commit và push lên GitHub.
* Tạo Pull Request.
* Review Pull Request.
* Thực hành xử lý **Merge Conflict**.

> **Lưu ý:** Đây là bài thực hành tạo conflict có chủ đích. Không tự ý sửa các phần khác của README.

---

## 1. Clone repository

Clone repository về máy:

```bash
git clone https://github.com/Crabbercat/git_lab_team7.git
```

Di chuyển vào thư mục project:

```bash
cd git_lab_team7
```

Kiểm tra repository:

```bash
git status
```

---

## 2. Tạo branch riêng

Mỗi thành viên phải tạo **một branch riêng theo tên của mình**.

Ví dụ:

```bash
git switch -c nguyen-van-a
```

Hoặc:

```bash
git checkout -b nguyen-van-a
```

Kiểm tra branch hiện tại:

```bash
git branch
```

Branch đang làm việc sẽ có dấu `*`.

Ví dụ:

```text
* nguyen-van-a
  main
```

> Không được thực hiện bài thực hành trực tiếp trên branch `main`.

---

## 3. Tạo Merge Conflict

## ⚠️ QUAN TRỌNG

Hai thành viên **KHÔNG được sửa các phần khác nhau**.

Cả hai phải sửa **cùng một dòng bên dưới**.

### 🔥 KHU VỰC TẠO CONFLICT

Thay đổi dòng sau:

```text
CONFLICT_AREA: YOUR_NAME - YOUR_STUDENT_ID
```

Mỗi thành viên thay `YOUR_NAME - YOUR_STUDENT_ID` bằng:

```text
HỌ VÀ TÊN - MSSV
```

Ví dụ:

```text
CONFLICT_AREA: Nguyen Van A - 123456
```

và thành viên còn lại:

```text
CONFLICT_AREA: Tran Van B - 654321
```

### ❗ Không được sửa dòng `CONFLICT_AREA` thành các dòng khác

Mục đích là để hai branch cùng thay đổi **một vị trí trong cùng một file**, từ đó tạo ra Merge Conflict.

---

## 4. Commit thay đổi

Sau khi chỉnh sửa README:

Kiểm tra thay đổi:

```bash
git status
```

Xem nội dung thay đổi:

```bash
git diff
```

Sau đó commit với **đúng nội dung commit sau**:

```bash
git add README.md
git commit -m "test: create merge conflict"
```

> Không sử dụng commit message khác.

---

## 5. Push branch lên GitHub

Push branch:

```bash
git push -u origin <ten-branch-cua-ban>
```

Ví dụ:

```bash
git push -u origin nguyen-van-a
```

---

## 6. Tạo Pull Request

Sau khi push branch lên GitHub:

1. Mở repository trên GitHub.
2. Chọn **Compare & pull request**.
3. Tạo Pull Request từ branch của bạn vào `main`.
4. Đặt tiêu đề:

```text
test: practice merge conflict
```

1. Trong phần **Reviewers**, thêm:

```text
Crabbercat
```

1. Tạo Pull Request.

---

## 7. KHÔNG tự resolve conflict

Sau khi tạo Pull Request:

> 🛑 **DỪNG LẠI.**

Không tự merge.

Không tự resolve conflict.

Không rebase.

Không sửa branch để tránh conflict.

Không đóng Pull Request.

Hãy để Pull Request ở trạng thái hiện tại để thành viên phụ trách xử lý Merge Conflict.

---

## 8. Quy trình xử lý của người phụ trách

Người phụ trách sẽ thực hiện:

```text
Member 1
   │
   ├── Create branch
   ├── Modify README
   ├── Commit
   ├── Push
   └── Pull Request
             │
             ▼
           main
             │
             │ Merge
             ▼
        Member 1 merged


Member 2
   │
   ├── Create branch từ main cũ
   ├── Modify cùng dòng
   ├── Commit
   ├── Push
   └── Pull Request
             │
             ▼
       ⚠️ CONFLICT
             │
             ▼
       Người phụ trách
       resolve conflict
```

Sau khi conflict được resolve, người phụ trách sẽ hoàn tất Pull Request.

---

## 9. Kết quả mong muốn

Sau bài thực hành, repository phải thể hiện được:

* Có nhiều branch.
* Có nhiều Pull Request.
* Có Pull Request xảy ra Merge Conflict.
* Conflict được giải quyết thủ công.
* Thành viên hiểu được quy trình:

```text
Clone
  ↓
Create Branch
  ↓
Modify
  ↓
Commit
  ↓
Push
  ↓
Pull Request
  ↓
Review
  ↓
Merge Conflict
  ↓
Resolve Conflict
  ↓
Merge
```

---

## 📌 Quy tắc

| Quy tắc | Yêu cầu |
| --- | --- |
| Làm việc trên `main` | ❌ Không |
| Tạo branch riêng | ✅ Bắt buộc |
| Sửa `README.md` | ✅ Bắt buộc |
| Sửa dòng `CONFLICT_AREA` | ✅ Bắt buộc |
| Commit message | `test: create merge conflict` |
| Push lên GitHub | ✅ Bắt buộc |
| Tạo Pull Request | ✅ Bắt buộc |
| Thêm `Crabbercat` làm Reviewer | ✅ Bắt buộc |
| Tự resolve conflict | ❌ Không |
| Tự merge PR | ❌ Không |
| Sửa các phần khác của README | ❌ Không |

---

## 🧪 Conflict Area

```text
CONFLICT_AREA: YOUR_NAME - YOUR_STUDENT_ID
```

**Chỉ chỉnh sửa dòng này.**
