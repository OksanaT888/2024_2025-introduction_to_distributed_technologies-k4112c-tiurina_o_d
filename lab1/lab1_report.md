University: [ITMO University](https://itmo.ru/ru/)    
Faculty: [FICT](https://fict.itmo.ru)     
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)    
Year: 2024/2025    
Group: K4112c   
Author: Tiurina Oksana Dmitrievna    
Lab: Lab1      
Date of create: 18.11.2024   
Date of finished:   
**Лабораторная работа №1. "Установка Docker и Minikube, мой первый манифест."**    
**Описание**    
Это первая лабораторная работа, в которой необходимо протестировать Docker, установить Minikube и развернуть свой первый "под".     
**Цель работы**    
Ознакомиться с инструментами Minikube и Docker, развернуть свой первый "под".    
**Ход работы**    
Изучаем Документацию по Minikube. Устанавливаем Docker на рабочий компьютер, далее установливаем Minikube, используя оригинальную инструкцию.После установки необходимо развернуть minikube cluster, используем команду minikube start. Далее скачиваем образ hashicorp/vault. Создаем контейнер на основе образа. Создаем файл pod.yaml для развертывания пода с полученным образом.      
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/pod.jpg)      
Применяем написанный манифест.   
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/1.jpg)    
Результат создания пода представлен на рисунке.   
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/2.jpg)      
Далее создается сервис для доступа к поду.   
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/3.jpg)       
С помощью команды minikube kubectl -- logs service/vault находим Root Token.   
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/4.jpg)   
Прокидываем порт 8200 компьютера в контейнер.     
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/5.jpg)     
Открываем станицу авторизации и вводим полученный Root Token.     
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/6.jpg)    
Осуществлен успешный вход.    
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/7.jpg)    
Схема организации контейнеров и сервисов:    
![screen](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab1/picture/8.jpg)      
**Результаты данной работы:**         
Файл с разработанным манифестом для развертывания "пода" с расширением .yaml.      
Схема организации контейеров и сервисов, нарисованная в draw.io.      
Скриншоты c результатами работы.    
