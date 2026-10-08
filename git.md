# Instalasi GIT
Install melalui https://git-scm.com/install/windows

# Membuat Repository Git baru
- pergi ke https://github.com
- login menggunakan tombol `Continue with Google`
- Pada header, di bagian kanan atas, arahkan mouse ke tombol (+) > `Create New Repository`
- Pada bagian `General` isikan nama reposity pada field `Owner / {nama_repository}`, Contoh: SD_PCT_nama
- Pada bagian `Configuration` tolong buat visibility bernilai `Public`, Toggle on `Readme`, No `.gitignore`, `MIT` License.

# Mengakses repository
Untuk mengakses repository, navigate ke `https://github.com/[username]/[namarepo]`. Karena kita sudah membuat nama repo berupa `SD-PCT-Fikri` berarti URL nya adalah `https://github.com/asahfikir/SD-PCT-Fikri`

# Clone Repository / Mendownload Repository
- Cari tombol `Code`, pada dropdown, pilih Github CLI
- Jika belum ada Github CLI terinstall, click `Learn More`
- Pada halaman yang baru terbuka, pilih operating system yang sedang digunakan (misal Windows - lihat di dropdown menu `Install with Homebrew`), download Github CLI Installer
- Setelah Github CLI terinstall, software tersebut dapat diakses melalui perintah `gh`
- Login menggunakan `gh auth login`, perhatikan kode login pada layar (Lihat bagian `One-time code`), gunakan setelah browser terbuka
```
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser

///////////////// KODE OTP nya ada disini /////////////////////////////
! One-time code (FE6C-7D66) copied to clipboard 

Press Enter to open https://github.com/login/device in your browser...
Opening in existing browser session.
```
- Setelah `gh` berhasil login gunakan perintah `gh repo clone {username/namarepo}`, untuk repo kita berarti: `gh repo clone asahfikir/SD-PCT-Fikri`

# Melihat Status Perubahan
Gunakan perintah `git status`
```
 git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        git.md

no changes added to commit (use "git add" and/or "git commit -a") 
```
Dari perintah diatas terlihat bahwa ada dua perubahan, `README.md` sudah dirubah, dan ada file baru bernama `git.md`. Kita akan menambahkan 2 file tersebut ke area staging untuk dikumpulkan serta diberi deskripsi. Gunakan perintah `git add .`
Setelah menggunakan `git add`, ketika kita memanggil `git status` maka hasilnya akan seperti berikut:
```
 git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        new file:   git.md
```
Jika tidak ada lagi perubahan maka kita bisa `commit` dengan menggunakan perintah `git commit -m "Deskripsi dari perubahan yang dilakukan"`.

# Kirim Perubahan ke Github
Setelah melakukan commit, commit bisa dilihat melalui perintah `git log`:
```
 git log
commit 0a8fff68f54b6bc209605b257b12857a64f5d47e (HEAD -> main, origin/main, origin/HEAD)
Author: Rijalul Fikri <asah.fikir@gmail.com>
Date:   Thu Oct 8 20:50:48 2026 +0700

    Edit Readme, menambahkan git.md

commit ce9e02dce086955e2deb1fe90f4d0ea7e1c1e4d7
Author: Rijalul Fikri <167858775+asahfikir@users.noreply.github.com>
Date:   Thu Oct 8 19:43:04 2026 +0700

    Initial commit
```
Untuk mengirimkan ke github, gunakan perintah `git push origin main`
