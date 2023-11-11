# minio-nginx-proxy-directlink-streaming

docker-compose up\
#Set alias for a deployment name\
docker exec -it share-minio-1 mc alias set 'myminio' 'http://127.0.0.1:9000' admin 11111111\

#Create Bucket:\
docker exec -it share-minio-1 mc mb myminio/mydata\

#Share all public bucket mydata\
docker exec -it share-minio-1 mc anonymous set download myminio/mydata\

Upload one image file, for ex: 01.jpg in this url: \
http://10.0.0.18/browser/mydata

Access to show image: http://10.0.0.18:81/mydata/01.jpg 

