

Ubutnu Docker Install:



```
sudo apt install gnome-terminal
```



Install Docker Desktop:

```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```


```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


```
Download Docker Desktop software
https://docs.docker.com/desktop/install/ubuntu/

after download run command where file downloaded
sudo dpkg -i <name.deb>
```



Signing in with Docker Desktop for Linux
```
gpg --generate-key

Enter name,email.
You can see public key in your terminal like this

pub   ---- YYYY-MM-DD [SC] [expires: YYYY-MM-DD]
      <your_generated_gpg-id_public_key>




pass init <your_generated_gpg-id_public_key>

```