University: ITMO University  
Faculty: FICT   
Course: Introduction to distributed technologies  
Year: 2024/2025  
Group: K4112c  
Author: Tiurina Oksana Dmitrievna  
Lab: Lab4   
Date of create: 19.12.2024  
Date of finished:       
Лабораторная работа №4   
Сети связи в Minikube, CNI и CoreDNS.    
Описание.   
В данной работе необходимо познакомиться с сетями связи в Minikube. Особенность Kubernetes заключается в том, что у него одновременно работают underlay и overlay сети, а управление может быть организованно различными CNI.    
Цель работы.   
Познакомиться с CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.     
Ход работы.    
При запуске minikube устанавливаем плагин CNI=calico и режим работы Multi-Node Clusters одновеременно, в рамках данной лабораторной работы необходимо развернуть 2 ноды. (Рис. 1)      
![1](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/1.jpg)    
Проверяем работу CNI плагина Calico и количество нод. (Рис. 2, 3)       
![2](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/2.jpg)  
![3](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/3.jpg)  
Для проверки режима IPAM для запущеных ранее нод указываем label. (Рис. 4)  
![4](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/4.jpg)  
После этого разрабатываем манифест IPPool. (Рис. 5)  
![5](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/5.jpg)  
Применяем написанный манифест. (Рис. 6)  
![6](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/6.jpg)  
Удаляем IPPool по умолчанию. (Рис. 7)   
![7](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/7.jpg)  
На рисунке 8 видно, что IPPool'ы корректно созданы.   
![8](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/8.jpg)  
![9](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/9.jpg)  
![10](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/10.jpg)  
Далее применяем написанные манифесты и производим их проверку. (Рис. 11)  
![11](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/11.jpg)  
Осуществляем подключение к контейнерам, пробросив порты. (Рис. 12)  
![12](https://github.com/OksanaT888/2024_2025-introduction_to_distributed_technologies-k4112c-tiurina_o_d/blob/main/lab4/picture/12.jpg)  
Подключаемся к веб-сайту. (Рис. 13)  
Screenshot 13  
Рисунок 13 - Подключение к веб-сайту   
Отправляем эхо-запросы, используя команду kubectl exec deployment-977pld6b9-6b67p -- ping 10.244.117.110. (Рис. 14)   
Screenshot 14  
Рисунок 14 - Отправка эхо-запросов   
Схема организации контейнеров и сервисов представлена на рисунке 15.   
Screenshot 15   
Рисунок 15 - Схема организации контейнеров и сервисов    

Результаты лабораторной работы.   

Файлы с разработанными манифестами с расширением .yaml.   
Схема организации контейеров и сервисов, нарисованная в draw.io.   
Скриншоты c результатами работы.   
