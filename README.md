<!-- Wsl -->
<!-- Danh sách wsl -->
wsl --list

<!-- Mở powershell -->
<!-- Xóa Wsl -->
wsl --unregister <Tên wsl>


<!-- Thư mục chứa source mặc định của apache -->
/var/www/html

<!-- Thư mục chứa access log mặc định của apache -->
/var/log/httpd


<!-- Docker -->
<!-- Danh sách container -->
Docker ps

<!-- Dừng container -->

<!-- Xóa container -->

<!-- Vào container -->


Cài đặt ubuntu
Cập nhật package apt-get update
Cài git apt-get -y install git

Cài thông tin git
git config --global user.name "Quan"
git config --global user.email "leovergil@gmail.com"
git config --global --list


Cài vim apt-get -y install vim
Cài composer apt-get -y install composer


thêm kho lưu trữ Docker vào hệ thống:
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Cài docker
apt-get update
apt-get -y install docker-ce docker-ce-cli containerd.io
docker --version

Cấp quyền cho toan bồ file trong docker
chmod 0777 *
Cấp quyền cho git
sudo chmod -R 777 .git
chmod 0777 .gitignore

Cấp quyền cho web/php/php.ini

Build container
docker compose build

Xóa 2 folder trong mysql là data và ibdata



Chạy web
docker compose up -d

Tạo folder htdocs
Tạo dự án cần thiết


Đối với dự án php thuần thì phải vào container của mysql import db thì mới chạy dc

Đối với laravel cần set vhost vào mục public
Cấp quyền cho log => chmod 0777 /storage/logs/
Cấp quyền cho sesstion chmod 0777 /storage/framework/sessions
Cấp quyền cho views chmod 0777 /storage/framework/views
