# Install docker engine on Ubuntu 
### Set up the repository
1. Update the `apt ` package index and install packages to allow `apt` to use a repository over HTTPS:
```
sudo apt-get update
```
```
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
2. Add docker's official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
3. Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below.
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
### Install docker engine
1. Update the apt package index, and install the latest version of Docker Engine, containerd, and Docker Compose, or go to the next step to install a specific version:
```
sudo apt-get update
```
```
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
2. To install a specific version of Docker Engine, list the available versions in the repo, then select and install:
* List the versions available in your repo:
```
apt-cache madison docker-ce
```
* Install 
```
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io docker-compose-plugin
```
> Note: Thay <VERSION_STRING> bằng phiên bản ở trên: 
> ví dụ: 
```

sudo apt-get install docker-ce=5:20.10.14~3-0~ubuntu-hirsute docker-ce-cli=5:20.10.14~3-0~ubuntu-hirsute containerd.io docker-compose-plugin
```

3. Sau khi cài đặt, bạn có thể cho user hiện tại thuộc group docker, để khi gõ lệnh không cần xin quyền sudo
```
sudo usermod -aG docker $USER
```
4. khởi động lại máy để lệnh số 3 có hiệu lực
```
sudo reboot now
```

# Install docker-compose  
1. Update your system
```
sudo apt update 
```
2. Install curl package
```
sudo apt install curl -y
```
3. Dowload the latest docker compose version
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
4. Change File Permissions
```
sudo chmod +x /usr/local/bin/docker-compose
```
5. Check docker-compose version
```
docker-compose --version
```






