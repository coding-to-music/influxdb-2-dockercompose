# influxdb-2-dockercompose

# 🚀 Start InlfluxDB version 2 with the Flux language and scrape with Telegraf and view metrics 🚀

https://github.com/coding-to-music/influxdb-2-dockercompose

From / By https://github.com/devopsjourney1/influxdb-2-dockercompose

## Environment variables:

```java

```

## user interfaces:

- InfluxDB http://localhost:8086

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/influxdb-2-dockercompose.git
git push -u origin main
```

## Install Pre-requirements

```
sudo apt-get update -y
sudo apt install docker.io -y && apt install docker-compose -y
```

## Bring Up Docker

```
# run and take over the terminal:
docker-compose up

# detached mode so will run even if you log out:
docker-compose up -d
```

Open port 8086 so you can view the InfluxDB UI

- InfluxDB http://localhost:8086

Use the userid/pwd you set in the `docker-compose.yml`

Go to Load Data-->Telegraf-->Create Configuration

Configure your API Token

```java
export INFLUX_TOKEN=etc etc
```

Paste the token into the end of the file `~/.bash_aliases`

Download the Telegraf CLI

https://www.influxdata.com/downloads/

```java
docker pull telegraf
```

Or download binaries

Change the drop-down to `Ubuntu & Debian`

```java
# influxdata-archive_compat.key GPG fingerprint:
#     9D53 9D90 D332 8DC7 D6C8 D3B9 D8FF 8E1F 7DF8 B07E
wget -q https://repos.influxdata.com/influxdata-archive_compat.key
echo '393e8779c89ac8d958f81f942f9ad7fb82a25e133faddaf92e15b16e6ac9ce4c influxdata-archive_compat.key' | sha256sum -c && cat influxdata-archive_compat.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg > /dev/null
echo 'deb [signed-by=/etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg] https://repos.influxdata.com/debian stable main' | sudo tee /etc/apt/sources.list.d/influxdata.list

sudo apt-get update && sudo apt-get install telegraf
```

Set up the Telegraf config for the System Monitoring of the VM

```java
telegraf --config http://localhost:8086/api/v2/telegrafs/0c7e48639e4bf000
```

# Useful docker commands

```java
# view what is running
docker ps


```
