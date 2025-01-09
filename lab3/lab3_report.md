University: ITMO University  
Faculty: FICT   
Course: Introduction to distributed technologies  
Year: 2024/2025  
Group: K4112c  
Author: Tiurina Oksana Dmitrievna    
Lab: Lab3   
Date of create: 07.12.2024   
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
Screenshot 1      
Рисунок 1 - Создание манифеста для configMap      
Применяем созданный манифест с помощью команды minikube kubectl -- apply -f config.map.yaml. (Рис. 2)   
![2](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab3/picture/2.jpg)  
Screenshot 2      
Рисунок 2 - Применение созданного манифеста        
Проверяем, что манифест применен. (Рис. 3)  
Screenshot 3  
Риснок 3 - Проверка применения манифеста  
Создаем replicaSet с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и, используя ранее созданный configMap, передаем переменные REACT_APP_USERNAME, REACT_APP_COMPANY_NAME. (Рис. 4, 5)  
Screenshot   
Рисунок 4 - Написание манифеста для ReplicaSet  
Screenshot 5  
Рисунок 5 - Применение написанного манифеста  
Проверяем с помощью команды minikube kubectl -- get replicasets, что написанный манифест применен. (Рис. 6)   
Screenshot 6  
Рисунок 6 - Проверка применения манифеста   
Далее используем команду minikube addons enable ingress, которая позволит использовать Ingress. (Рис. 7)  
Screenshot 7  
Рисунок 7 - Использование команды minikube addons enable ingress   
Создаем Service с названием frontend-service. (Рис. 8)  
Screenshot 8  
Рисунок 8 - Создание Service   
Применяем написанный манифест и проверяем, что он успешно применен. (Рис. 9)  
Screenshot 9  
Рисунок 9 - Прменение манифеста и его проверка   
Устанавливаем OpenSSL версии 3.4.0 и генерируем TLS-сертификат. (Рис. 10)  
Screenshot 10  
Рисунок 10 - Генерирование TLS-сертификата   
Импортируем данный сертификат в minikube. (Рис. 11)   
Screenshot 11   
Рисунок 11 - Импорт TLS-сертификата  
Далее используем команду minikube addons configure ingress. (Рис. 12)  
Screenshot 12  
Рисунок 12 - Выполнение команды minikube addons configure ingress   
Созданием манифест для Ingress. (Рис. 13)   
Screenshot 13  
Рисунок 13 - Написание манифеста   
Создаем объект Ingress с использованием написанного ранее манифеста. (Рис. 14)   
Screenshot 14  
Рисунок 14 - Создание объекта Ingress с использованием написанного ранее манифеста  
Далее запускаем команду minikube tunnel. (Рис. 15)  
Screenshot 15   
Рисунок 15 - Запуск команды minikube tunnel  
В браузере переходим по FQDN-имени. (Рис. 16)   
Screenshot 16   
Рисунок 16 - Применение FQDN-имени в браузере   
Проверяем наличие сертификата. (Рис. 17)   
Screenshot 17   
Рисунок 17 - Проверка наличия сертификата   
Схема организации контейнеров и сервисов представлена на рисунке 18.   
Screenshot 18   
Рисунок 18 - Схема организации контейнеров и сервисов  
  
Результаты лабораторной работы.  
  
Файлы с разработанными манифестами с расширением .yaml.    
Схема организации контейеров и сервисов, нарисованная в draw.io.   
Скриншоты c результатами работы.  
  
