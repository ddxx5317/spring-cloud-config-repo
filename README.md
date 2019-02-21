# spring-cloud-config-repo
 
------对称加密
加密			  
curl -X POST http://localhost:8081/encrypt -d ddxx2018
11bd348df57a4a82fead60476ceeb1c9f1069c696f6460cf057457e574a64dfc

解密
curl -X POST http://localhost:8081/decrypt -d 11bd348df57a4a82fead60476ceeb1c9f1069c696f6460cf057457e574a64dfc



------非对称加密

生成server.jks文件
keytool -genkeypair -alias myConfigkey -keyalg RSA -dname "CN=Web Server,OU=Unit,O=Organization,L=City,S=State,C=US" -keypass ddxx2018 -keystore config_server.jks -storepass ddxx2019


加密
curl -X POST http://localhost:8088/encrypt -d ddxx2018
AQBU5wM0d4uYUvsBoUZgIALP4nC0ghEletqshuv2XCkYlJzzE1/xL2bcYwmfUhMpR2FEmPi1F0wgiUOAMk2XVTwHaAQgW3Ebi18E7keMZ3HEbwd5jlwDk1sQjRhTPhMrdT684s5Y/KpWamvW8B0po5+DDXYTgyExCpeBlRArOvAUow8Pkf1gdamkLnveq4uxSjveyfyjZbgjU6l5TE1Yd5TMxju0ya7UmaYLEDKlBWpnhCjI1bSd2N0Ue9o6Dmt6em4DeVBQOPxsFY1+EYQoQGEpEED9Nc03SjyHmZYqrhGBYQie2OOmxY3MqFuL/NM93Qs9kUomZTEfMAHKI+GBhG6vKEUGMEfV5iAWartRAfKntX75LxE53bPXAikOjAqQ4ag=

解密
curl -X POST http://localhost:8088/decrypt -d AQBU5wM0d4uYUvsBoUZgIALP4nC0ghEletqshuv2XCkYlJzzE1/xL2bcYwmfUhMpR2FEmPi1F0wgiUOAMk2XVTwHaAQgW3Ebi18E7keMZ3HEbwd5jlwDk1sQjRhTPhMrdT684s5Y/KpWamvW8B0po5+DDXYTgyExCpeBlRArOvAUow8Pkf1gdamkLnveq4uxSjveyfyjZbgjU6l5TE1Yd5TMxju0ya7UmaYLEDKlBWpnhCjI1bSd2N0Ue9o6Dmt6em4DeVBQOPxsFY1+EYQoQGEpEED9Nc03SjyHmZYqrhGBYQie2OOmxY3MqFuL/NM93Qs9kUomZTEfMAHKI+GBhG6vKEUGMEfV5iAWartRAfKntX75LxE53bPXAikOjAqQ4ag=


refresh
curl -X POST http://localhost:8082/refresh
