# teamcity

Teamcity docker-compose configuration for GCP (e2-medium: 2 vCPU, 4 GB memory, 20 GB persistent disk, Debian GNU/Linux 10 (buster))


# installation - docker

```
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
$ echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt-get update
$ sudo sudo apt-get install docker-ce docker-ce-cli containerd.io
```

# installation - docker-compose

```
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
```

# commands

```
$ gcloud compute scp .\docker-compose.yaml teamcity:.
```
