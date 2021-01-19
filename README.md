# myawesometeam

# installation

## remote retro tool

Parabol

## hardware
hard disk - 20G (tmp)

Preparation for docker deploymentn:

- docker
- docker-compose

### install docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker bobjiang_infinite

## install docker-compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

## clone
git clone https://github.com/ParabolInc/parabol.git
cd parabol
cp .env.example .env

## install with docker-compose
sudo docker-compose up -d

Preparation for local deployment

----- optional, only for local install -----
## install node
sudo apt install nodejs

## install nvm
nvm install v14.10.0

----- optional end -----

## redis.conf
comment "bind 127.0.0.1"

## install rethinkdb on ubuntu

```
source /etc/lsb-release && echo "deb https://download.rethinkdb.com/repository/ubuntu-$DISTRIB_CODENAME $DISTRIB_CODENAME main" | sudo tee /etc/apt/sources.list.d/rethinkdb.list
wget -qO- https://download.rethinkdb.com/repository/raw/pubkey.gpg | sudo apt-key add -
sudo apt-get update
sudo apt-get install rethinkdb
```

rethinkdb &
