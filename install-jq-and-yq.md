```
sudo apt-get update && sudo apt-get install -y jq

sudo apt-get update && sudo apt-get install -y jq && \
  wget -qO /usr/local/bin/yq "https://github.com/mikefarah/yq/releases/latest/download/yq_linux_amd64" && \
  sudo chmod +x /usr/local/bin/yq
```