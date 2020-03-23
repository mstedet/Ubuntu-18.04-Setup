## Setup Git SSH :
Video : [Opret SSH login on Github](https://youtu.be/HfTXHrWMGVY?t=144)
```bash
# Check for SSH Key
ls ~/.ssh

# Creaate an SSH Key
ssh-keygen -t rsa -b 4096 -C "me@mydomain.com" -f ~/.ssh/id_rsa_MyGithub
```
Video : [Opret SSH login on Github - Copy SSH-Key](https://youtu.be/HfTXHrWMGVY?t=219)
```bash
# Copy the SSH Key
sudo apt install -y xclip
xclip -sel clip < ~/.ssh/id_rsa_MyGithub.pub
```
Video : [Opret SSH login on Github - Test SSH-Key](https://youtu.be/HfTXHrWMGVY?t=245)

```bash
# test SSH
ssh -T git@github.com

# Responce somthing like this is fine 
# Hi sekt1953! You've successfully authenticated, but GitHub does not provide shell access.
```
