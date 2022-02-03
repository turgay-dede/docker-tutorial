# Docker Tutorial

### Image arama
`docker search IMAGE`
### Image Indirme
`docker pull IMAGE`

### Images Listesi
`docker images`

### Image Silme
`docker rmi REPOSITORY`

### Tüm Image Silme
`docker rmi $(docker images)`

### Container olusturma (Mysql)
`docker run -d --name benim_sql -e MYSQL_ROOT_PASSWORD=123456 mysql`

### Container Listesi
`docker ps`

### Tüm Container larin Listesi (Kapali olanlar dahil)
`docker ps -a`

### Container Silme
`docker rm -f CONTAINERID/NAMES`

### Tüm Container  lari Silme
`docker rm -f $(docker ps -a -q)`

### 2 Image ile Container olusturma
`docker run -d --link benim_sql:mysql -p 8080:80 wordpress`

### Container i durdurma
`docker stop CONTAINERID`

### Durdurulan Container i calistirma
`docker start -a -i benim_ubuntum`

### Arka planda calisan container a giris
`docker exec -i -t NAMES COMMAND`

### Container dan cikma
`exit`

### Image olusturma
`docker commit -a "Turgay Dede" NAMES turgaydede/benim_ubuntum_yeni:latest`

### Docker Hub Login
```
docker login
	username:
	password:
```
### Docker push
`docker push turgaydede/benim_ubuntum_yeni:latest`

### Docker Volume Klasor baglama (-v)
`docker run --name benim_ubuntum -i -d -v /Users/turgaydede/deneme:/home/test ubuntu`

### Docker Volume Klasor baglama (-v), aktif directory set etme (-w) ve Readonly -(ro)
`docker run -i --rm -v /Users/turgaydede/deneme:/home/test:ro -w /home/test golang go run main.go`

### Docker Volume Listeleme
`docker volume ls`

### Docker Konfigürasyon bilgilerine erişme
`docker inspect NAMES`

### Dockerfile
```
FROM golang </br>
COPY ./go_project /home/test </br>
RUN ["apt-get","update"] </br>
WORKDIR /home/test/ </br>
ENTRYPOINT ["go"] </br>
CMD ["run","main.go"] </br>
```

### Build
`docker build -t goproject:1 .`

### Run
`docker run goproject:1`

### Docker Loglama
`docker logs -f NAMES`




