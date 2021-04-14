# docker-yandex-tank
**[Official docs](https://yandextank.readthedocs.io/en/latest/install.html)**  
Checked on macOS system with docker installed  
  
![report](https://github.com/p-12s/docker-yandex-tank/blob/main/overload-report.png?raw=true)

## Installation
1. Clone repo and change load-config file:
```
git clone https://github.com/p-12s/docker-yandex-tank.git
cd docker-yandex-tank
vi load.yaml
```

2. Change site-url in 'load.yaml'.  
3. Get your token from https://overload.yandex.net and put them into 'token.txt'-file.  
4. Run docker-command:
```
docker run \
    -v $(pwd):/var/loadtest \
    -v $SSH_AUTH_SOCK:/ssh-agent -e SSH_AUTH_SOCK=/ssh-agent \
    --net host \
    -it direvius/yandex-tank
```
or as interactive-mode:
```
docker run \
    -v $(pwd):/var/loadtest \
    -v $SSH_AUTH_SOCK:/ssh-agent -e SSH_AUTH_SOCK=/ssh-agent \
    --net host \
    -it \
    --entrypoint /bin/bash \
    direvius/yandex-tank
```
5. Get web link from output: https://overload.yandex.net/№######
