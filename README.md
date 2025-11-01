# how-to-push-repo-to-github

## 1. Hubungkan akun github dulu
```bash
# 1. salin ssh key yang terhubung di git hub ke terminal
abim@abim23:~/.ssh$ ls
authorized_keys  finaltask

# 2. atur permision dari folder /.ssh
chmod 600 finaltask
chmod 644 finaltask.pub
chmod 700 ~/.ssh

# 3. Tambahkan key ke SSH agent
Aktifkan ssh-agent dan tambahkan key-nya:
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/finaltask

Cek apakah sudah ditambahkan:
ssh-add -l
Harus muncul fingerprint dari finaltask.

# 4. Tes koneksi ke GitHub
ssh -T git@github.com
Kalau muncul:
Hi abimsyaefulloh! You've successfully authenticated, but GitHub does not provide shell access.
Berarti koneksi SSH-mu ke GitHub sudah sukses 🎉

# 5. hubungkan github global
git config --global user.email "abimsyaefulloh2020@gmail.com"
git config --global user.name "abimsyaefulloh"

tes koneksi
git config --global --list
dan hasilnya :
user.name=abimsyaefulloh
user.email=abimsyaefulloh2020@gmail.com
```

## 2. Ubah remote pake ssh aja 
```bash
# 1. lihat remote yang terhubung
git remote -v

# 2. Hapus remote jika masih menggunakan remote https
git remote remove origin

# 3. Tambahkan remote ssh
git remote add origin git@github.com:abimsyaefulloh/fe-dumbmerch.git

# 4. Cek lagi remote nya
git  remote -v

# 5. Tes pull atau push
git fetch origin
```

## 3. Push repository
```bash
# 1. Tambahkan file yang ingin di-commit
Tambahkan semua file ke staging:
git add .

Atau kalau cuma file tertentu:
git add nama_file.js

# 2. Buat commit dengan pesan
git commit -m "pesan commit pertama"

3. Push ke GitHub
Kalau pertama kali push:
git branch -M main
git push -u origin main

4. git push
git push
```











