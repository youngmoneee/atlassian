# atlassian
Jira/Confluence/Bitbucket 3종세트


## Get Started on Debian

### Uninstall Conflicting Package
```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

### Set up Docker's Apt repository
```bash
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

# Add the repository to Apt sources:
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

### Install the Docker packages
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin && sudo usermod -aG docker $USER
```

### Pull this Repository and Set Workdir
```bash
git clone https://github.com/youngmoneee/atlassian.git && cd atlassian
```

### Bootstrap
```bash
docker compose up
```

### SET .ENV
``` .env
POSTGRES_USER=${YOUR_NAME}
POSTGRES_PASSWORD=${YOUR_PASSWORD}
POSTGRES_DB=${DATABASE_NAME}
```
