# minio-nginx-proxy-directlink-streaming

docker-compose up 
#Set alias for a deployment name  
docker exec -it share-minio-1 mc alias set 'myminio' 'http://127.0.0.1:9000' admin 11111111  

#Create Bucket:  
docker exec -it share-minio-1 mc mb myminio/mydata  

#Share all public bucket mydata  
docker exec -it share-minio-1 mc anonymous set download myminio/mydata  

Upload one image file, for ex: 01.jpg in this url:  
http://10.0.0.18/browser/mydata  
![image](https://github.com/dungla2011/minio-nginx-proxy-directlink-streaming/assets/7878963/76348ee4-5cd9-4e21-b4ee-60f60e78a664)



Access to show image: http://10.0.0.18:81/mydata/01.jpg   
![image](https://github.com/dungla2011/minio-nginx-proxy-directlink-streaming/assets/7878963/716b9473-9167-4931-a0eb-dbb0a315dbba)

