# docker-compose
docker-compose.yml 파일 저장소


# mongo db 
* MONGO_INITDB_DATABASE: 사용하려는 database name 입력
* MONGO_INITDB_ROOT_PASSWORD: 사용하려는 root password입력

### 설치
```bash
sudo docker up -d
```

### monogo db 설정
* root 접속
```bash
[root@myhost mongodb]# docker exec -it mongodb bash
root@8213b68b5489:/# mongo -u "root" -p
MongoDB shell version v4.2.1
Enter password:
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("63999af8-188a-45f1-933d-c63e94bbf495") }
MongoDB server version: 4.2.1
Server has startup warnings:
2019-12-09T06:33:49.693+0000 I  CONTROL  [initandlisten]
2019-12-09T06:33:49.693+0000 I  CONTROL  [initandlisten] ** WARNING: /sys/kernel/mm/transparent_hugepage/enabled is 'always'.
2019-12-09T06:33:49.694+0000 I  CONTROL  [initandlisten] **        We suggest setting it to 'never'
2019-12-09T06:33:49.694+0000 I  CONTROL  [initandlisten]
2019-12-09T06:33:49.694+0000 I  CONTROL  [initandlisten] ** WARNING: /sys/kernel/mm/transparent_hugepage/defrag is 'always'.
2019-12-09T06:33:49.694+0000 I  CONTROL  [initandlisten] **        We suggest setting it to 'never'
2019-12-09T06:33:49.694+0000 I  CONTROL  [initandlisten]
---
Enable MongoDB's free cloud-based monitoring service, which will then receive and display
metrics about your deployment (disk utilization, CPU, operation statistics, etc).

The monitoring data will be available on a MongoDB website with a unique URL accessible to you
and anyone you share the URL with. MongoDB may use this information to make product
improvements and to suggest MongoDB products and deployment options to you.

To enable free monitoring, run the following command: db.enableFreeMonitoring()
To permanently disable this reminder, run the following command: db.disableFreeMonitoring()
---
```

* db 생성
```bash
> db
test
> use 사용할db명
switched to db vision
```

* user 생성
```bash
>  db.createUser({ user: "vision", pwd: "사용할암호", roles: [{role: "readWrite", db: "vision"}]})
Successfully added user: {
        "user" : "vision",
        "roles" : [
                {
                        "role" : "readWrite",
                        "db" : "vision"
                }
        ]
}

```
