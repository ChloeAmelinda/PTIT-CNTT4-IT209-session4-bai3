# Bài 3: Cấu hình xác thực SSH và Đẩy dự án lên GitHub

## 1. Tạo SSH Key

Sử dụng thuật toán Ed25519 để tạo cặp khóa SSH:

```bash
ssh-keygen -t ed25519 -C "email-github"
```

SSH Key gồm:

* Private Key: `id_ed25519`
* Public Key: `id_ed25519.pub`

Private Key không được chia sẻ hoặc đưa lên GitHub.

## 2. Cấu hình SSH trên GitHub

Public Key `id_ed25519.pub` được thêm vào GitHub tại:

Settings → SSH and GPG keys → New SSH key.

## 3. Kiểm tra kết nối SSH

Sử dụng lệnh:

```bash
ssh -T git@github.com
```

Kết quả xác nhận tài khoản GitHub đã được xác thực thành công.

## 4. Cấu hình Remote Repository

Chuyển remote `origin` từ HTTPS sang SSH:

```bash
git remote set-url origin git@github.com:binlinh06/HN_KS24_CNTT4_TranNgocLinh_IT209_SS04_HW02.git
```

Kiểm tra:

```bash
git remote -v
```

Kết quả:

```text
origin  git@github.com:binlinh06/HN_KS24_CNTT4_TranNgocLinh_IT209_SS04_HW02.git (fetch)
origin  git@github.com:binlinh06/HN_KS24_CNTT4_TranNgocLinh_IT209_SS04_HW02.git (push)
```

## 5. Push dự án lên GitHub

Sử dụng:

```bash
git push -u origin main
```

Dự án và lịch sử commit đã được đẩy thành công lên GitHub thông qua giao thức SSH.

## 6. Repository

Repository GitHub:

`git@github.com:binlinh06/HN_KS24_CNTT4_TranNgocLinh_IT209_SS04_HW02.git`

## 7. Kết luận

Đã hoàn thành cấu hình xác thực SSH bằng thuật toán Ed25519, cấu hình remote bằng giao thức SSH và push dự án lên GitHub thành công.
