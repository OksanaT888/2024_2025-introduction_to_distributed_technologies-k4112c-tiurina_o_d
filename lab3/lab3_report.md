University: ITMO University  
Faculty: FICT   
Course: Introduction to distributed technologies  
Year: 2024/2025  
Group: K4112c  
Author: Tiurina Oksana Dmitrievna    
Lab: Lab3   
Date of create: 19.12.2024   
Date of finished:   
**Лабораторная работа №3.**     
Сертификаты и "секреты" в Minikube, безопасное хранение данных.      
Описание.        
В данной лабораторной работе необходимо познакомитесь с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.      
Цель работы.       
Познакомиться с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.      
Ход работы.  
Создаем configMap с переменными: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME. Манифест для создания configMap записан в файле с расширением .yaml. (Рис. 1)  
![1](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/1.jpg)             
Применяем созданный манифест с помощью команды minikube kubectl -- apply -f config.map.yaml. (Рис. 2)   
![2](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/2.jpg)  
Проверяем, что манифест применен. (Рис. 3)  
![3](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/3.jpg)     
Создаем replicaSet с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и, используя ранее созданный configMap, передаем переменные REACT_APP_USERNAME, REACT_APP_COMPANY_NAME. (Рис. 4, 5)  
![4](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/4.jpg)     
![5](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/5.jpg)     
Проверяем с помощью команды minikube kubectl -- get replicasets, что написанный манифест применен. (Рис. 6)   
![6](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/6.jpg)     
Далее используем команду minikube addons enable ingress, которая позволит использовать Ingress. (Рис. 7)  
![7](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/7.jpg)     
Создаем Service с названием frontend-service. (Рис. 8)  
![8](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/8.jpg)     
Применяем написанный манифест и проверяем, что он успешно применен. (Рис. 9)  
![9](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/9.jpg)     
Устанавливаем OpenSSL версии 3.4.0 и генерируем TLS-сертификат. (Рис. 10)  
![10](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/10.jpg)     
Импортируем данный сертификат в minikube. (Рис. 11)   
![11](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/11.jpg)     
Далее используем команду minikube addons configure ingress. (Рис. 12)  
![12](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/12.jpg)     
Созданием манифест для Ingress. (Рис. 13)   
![13](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/13.jpg)     
Создаем объект Ingress с использованием написанного ранее манифеста. (Рис. 14)   
![14](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/14.jpg)     
Далее запускаем команду minikube tunnel. (Рис. 15)  
![15](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/15.jpg)     
В браузере переходим по FQDN-имени. (Рис. 16)   
![16](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/16.jpg)     
Проверяем наличие сертификата. (Рис. 17)   
![17](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/17.jpg)     
Схема организации контейнеров и сервисов представлена на рисунке 18.   
![18](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/18.jpg)     
  
Результаты лабораторной работы.  
  
Файлы с разработанными манифестами с расширением .yaml.    
Схема организации контейеров и сервисов, нарисованная в draw.io.   
Скриншоты c результатами работы.  
  
