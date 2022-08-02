run ansible script

```
ansible-playbook playbook.yaml --ask-become-pass
```

Set up runner 

# Download the binary for your system
sudo curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64

# Give it permission to execute
sudo chmod +x /usr/local/bin/gitlab-runner

# add user gitlab-runner

```
sudo adduser gitlab-runner

sudo passwd gitlab-runner

sudo usermod -aG wheel gitlab-runner
```
Than edit visudo
```
sudo visudo
```
add 
gitlab-runner ALL=(ALL) NOPASSWD: ALL

## Allow root to run any commands anywhere
root    ALL=(ALL)       ALL
gitlab-runner ALL=(ALL) ALL

Uncomment this

## Same thing without a password
%wheel  ALL=(ALL)       NOPASSWD: ALL



# Install and run as a service
sudo gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner
sudo gitlab-runner start


add in /etc/hosts
<containme ip> gitlab-service.default 

than 

gitlab-runner register

gitlab-runer register 

