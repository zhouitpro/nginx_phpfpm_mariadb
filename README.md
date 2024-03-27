```
docker network create --driver=bridge --subnet=10.10.255.0/24 --ip-range=10.10.255.0/24 --gateway=10.10.255.254 proxy
```

start proxy
```
docker-compose -f proxy/docker-compose.yml up -d
```

start mariadb
```
docker-compose -f mariadb/docker-compose.yml up -d
```

start your app

