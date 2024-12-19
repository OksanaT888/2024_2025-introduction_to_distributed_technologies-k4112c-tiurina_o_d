University: [ITMO University](https://itmo.ru/ru/)    
Faculty: [FICT](https://fict.itmo.ru)     
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)    
Year: 2024/2025    
Group: K4112c   
Author: Tiurina Oksana Dmitrievna    
Lab: Lab1      
Date of create: 18.11.2024   
Date of finished:   
**Лабораторная работа №2. "Развертывание веб сервиса в Minikube, доступ к веб интерфейсу сервиса. Мониторинг сервиса."**    
**Описание**     
В данной лабораторной работе необходимо познакомитесь с развертыванием полноценного веб сервиса с несколькими репликами.   
**Цель работы**    
Ознакомиться с типами "контроллеров" развертывания контейнеров, ознакомится с сетевыми сервисами и развернуть свое веб приложение.    
**Ход работы**     
Скачиваем образ ifilyaninitmo/itdt-contained-frontend:master с помощью команды docker pull ifilyaninitmo/itdt-contained-frontend:master и создаем контейнер на основе скаченного образа. Далее запускаем Minikube, используя команду minikube start.   
Далее создаем deployment с 2 репликами контейнера ifilyaninitmo/itdt-contained-frontend:master и передаем переменные в эти реплики: REACT_APP_USERNAME, REACT_APP_COMPANY_NAME.   
![screen]()    
Применяем созданный манифест для создания реплик.    
![screen]()    
Проверяем, что deployment добавлен.   
![screen]()     
Реализуем сервис, через который будут доступны эти "поды".   
![screen]()    
Применяем написанный манифест.   
![screen]()   
Для доступа к контейнеру через веб браузер пробрасываем порты. Используется команда minikube kubectl -- port-forward service/front-service 3000:3000.   
![screen]()    
С помощью команды minikube kubectl get pods определяем, что у нас есть 2 пода, проверяем логи контейнеров.   
![screen]()   
Схема организации контейнеров и сервисов:    
![screen]()      
**Результаты лабораторной работы:**         
Файлы с разработанными вами манифестами с расширением .yaml.  
Схема организации контейеров и сервисов нарисованная вами в draw.io или Visio.  
Скриншоты c результатами работы.   
