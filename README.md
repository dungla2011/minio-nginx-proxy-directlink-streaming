# minio-nginx-proxy-directlink-streaming

Enviroment: Ubuntu, installed docker, docker-compose

**Command**

docker-compose up 

docker ps  
![image](https://github.com/dungla2011/minio-nginx-proxy-directlink-streaming/assets/7878963/734ecb1d-d3f7-436d-ae9c-24cc21c32bf9)


#Set alias for a deployment name  
(replace **share-minio-1** with **share_minio_1**, depend on your setup)

docker exec -it share-minio-1 mc alias set 'myminio' 'http://127.0.0.1:9000' admin 11111111  

#Create Bucket:  
docker exec -it share-minio-1 mc mb myminio/mydata  

#Share all public bucket mydata  
docker exec -it share-minio-1 mc anonymous set download myminio/mydata  

Upload one image file, for ex: 01.png in this url:  
http://10.0.0.18/browser/mydata  

![image](https://github.com/dungla2011/minio-nginx-proxy-directlink-streaming/assets/7878963/76348ee4-5cd9-4e21-b4ee-60f60e78a664)



Access to show directlink image: http://10.0.0.18:81/mydata/01.jpg   


![image](https://github.com/dungla2011/minio-nginx-proxy-directlink-streaming/assets/7878963/40e6f2fd-3a06-498c-b05d-9eb228175a46)


**Still problem:  
**  
When I change port Map in docker yaml file, from 80 to 8080, it's error in websocket:  
ports:
      - "8080:80"

![image](https://github.com/dungla2011/minio-nginx-proxy-directlink-streaming/assets/7878963/30968be7-a2cc-42e4-8217-92297bea450d)





