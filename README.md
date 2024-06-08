# Analog

Truy cập container
```
docker exec -it b811a608df3f0b4408a2234d65ff0cee9ad2a06b735c2491e4eea9066767abd5 /bin/bash
```

```
docker run -d -p 9944:9944 -p 30403:30303 analoglabs/timechain --base-path /data --rpc-external --rpc-methods=Unsafe --unsafe-rpc-external --name JosephTran --telemetry-url 'wss://telemetry.analog.one/submit'
```

```
docker run -d -p 9944:9944 -p 30403:30303 --name JosephTran analoglabs/timechain --base-path /data --rpc-external --rpc-methods=Unsafe --unsafe-rpc-external --name JosephTran --telemetry-url 'wss://telemetry.analog.one/submit 0'
```
