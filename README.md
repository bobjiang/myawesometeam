# myawesometeam

# installation

## remote retro tool

Parabol

## hardware
hard disk - 20G (tmp)

Preparation for docker deploymentn:

- docker
- docker-compose

## install docker
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
```

## install docker-compose

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

## clone
```
git clone https://github.com/ParabolInc/parabol.git  
cd parabol  
cp .env.example .env  
```

## install with docker-compose
```
sudo docker-compose up -d
```

Preparation for local deployment

----- optional, only for local install -----
## install node

https://github.com/nodesource/distributions/blob/master/README.md

```
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
```

## install nvm

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
source ~/.bashrc
nvm list-remote
nvm install v14.10.0
```

----- optional end -----

## redis.conf
comment "bind 127.0.0.1"

## install rethinkdb on ubuntu

```
source /etc/lsb-release && echo "deb https://download.rethinkdb.com/repository/ubuntu-$DISTRIB_CODENAME $DISTRIB_CODENAME main" | sudo tee /etc/apt/sources.list.d/rethinkdb.list
wget -qO- https://download.rethinkdb.com/repository/raw/pubkey.gpg | sudo apt-key add -
sudo apt-get update -y
sudo apt-get upgrade -y
sudo apt-get install rethinkdb -y

sudo apt install redis-server

redis-server &
rethinkdb &
```

## install app

```
sudo apt install cmdtest

sudo apt remove yarn
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
yarn && yarn dev -i
```
