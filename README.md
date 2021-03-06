# Spring Study Week7

## Docker(도커)

- mysql을 직접 설치하는 것보다 docker를 사용하는게 더 쉽다
    - 남이 생성한 mysql 환경을 그대로 local에 설정이 가능하기 때문에 주로 사용함

- 배포되어질 수 있는 시스템 수준에서의 버전관리
- Rollback 등에 용이한 대처 가능



## 도커 설치



## 도커에서 MySQL의 사용

```
docker pull mysql

// 버전 지정 원한다면
docker pull mysql:(버전)
```

- local에 잘 가져왔는지 확인

```
docker images
```

- 실행하기
    - 컨테이너의 해쉬값 나오면서 실행됨

```dockerfile
docker run --name 생성 컨테이너 이름 -e MYSQL_ROOT_PASSWORD=비밀번호 -d -p host포트번호:container포트번호 다운받은 이미지이름:태그 
```

```dockerfile
docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=artineer -d -p 3306:3306 mysql:latest
```

- 가지고있는 컨테이너 정보 알아보기

```dockerfile
docket ps -a
```

- 생성되어져있는 컨테이너 제거

```dockerfile
docket rm mysql-container
```

- 컨테이너 중지시키기

```dockerfile
docker stop mysql-continer
```

- 컨테이너 실행시키기

```dockerfile
docker start mysql-container
```

- 컨테이너의 리스트 반환

```dockerfile
docker ps
```

- 실행된 컨테이너에 shell 환경으로 접근하기

```docker
docker exec -it + Container ID + /bin/bash
```

```dockerfile
docker exec -it mysql-container bashh
```



#### 의존성 주입하기

