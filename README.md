# minio-nginx-proxy-directlink-streaming
docker-compose up

docker exec -it share-minio-1 mc alias set 'myminio' 'http://127.0.0.1:9000' admin 11111111

docker exec -it share-minio-1 mc mb myminio/mydata

docker exec -it share-minio-1 mc anonymous set download myminio/mydata



