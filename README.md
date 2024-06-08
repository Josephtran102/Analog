# Analog Node:
## 1. First, ensure you’ve installed Docker:
```
docker compose vesion
```
## 2. Next, download the latest Timechain image:
```
docker pull analoglabs/timechain:latest
```
- Check Container ID:
```
docker compose ps
```
Result:

```
ubuntu@josephtran  ~  docker ps
CONTAINER ID   IMAGE                                  COMMAND                  CREATED             STATUS             PORTS                                                                                                                                                           NAMES
a62be6b4f814   analoglabs/timechain                   "/timechain-node --b…"   About an hour ago   Up About an hour   0.0.0.0:9944->9944/tcp, :::9944->9944/tcp, 0.0.0.0:30403->30303/tcp, :::30403->30303/tcp                                                                        JosephTran
3b1b6e1fbe5f   farcasterxyz/hubble:latest             "npx pm2-runtime sta…"   23 hours ago        Up 23 hours        0.0.0.0:2281-2283->2281-2283/tcp, :::2281-2283->2281-2283/tcp                                                                                                   hubble-hubble-1
7f1d60ca8e05   grafana/grafana:10.0.3                 "/run.sh"                3 days ago          Up 23 hours        0.0.0.0:3000->3000/tcp, :::3000->3000/tcp                                                                                                                       hubble-grafana-1
409f029134b3   graphiteapp/graphite-statsd:1.1.10-5   "/entrypoint"            3 days ago          Up 23 hours        80/tcp, 2003-2004/tcp, 2013-2014/tcp, 2023-2024/tcp, 8080/tcp, 8125/tcp, 0.0.0.0:8125->8125/udp, :::8125->8125/udp, 0.0.0.0:8126->8126/tcp, :::8126->8126/tcp   hubble-statsd-1
```
- Check & Open port: 9944, 30303:
```
sudo ss -tuln | grep 9944
sudo ss -tuln | grep 30303
```
```
sudo ufw allow 9944/tcp
sudo ufw allow 30303/tcp
```

- Now run the following command:
```
docker run -d -p 9944:9944 -p 30403:30303 --name JosephTran analoglabs/timechain --base-path /data --rpc-external --rpc-methods=Unsafe --unsafe-rpc-external --name JosephTran --telemetry-url 'wss://telemetry.analog.one/submit 0'
```
Result:
```
ubuntu@josephtran  ~  docker run -d -p 9944:9944 -p 30403:30303 --name JosephTran analoglabs/timechain --base-path /data --rpc-external --rpc-methods=Unsafe --unsafe-rpc-external --name JosephTran --telemetry-url 'wss://telemetry.analog.one/submit 0'

`a62be6b4f8147e59109f8c4bcbe7503d272a27846dd9a54290e533a702349bc3`
```

