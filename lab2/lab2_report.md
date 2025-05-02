University: ITMO University

Faculty: FICT

Course: Cloud platforms as the basis of technology entrepreneurship ADD link

Year: 2025

Group: UVB

Author: Gibadulin Timur Rashidovich

Lab: Lab2

Date of create: 27.04.2025

Date of finished: 28.04.2025

Для работы был создан cloud run с портом 8080, минимальной памятью 128 mib, ожиданием запроса в 5 минут. Из ресурсов был взят стандартный тестовый образ от google gcr.io/cloudrun/hello

![image](https://github.com/user-attachments/assets/8761e575-bded-470d-a156-69a019aee5ab)

Cloud run был запущен и протестирован. Статус запроса GET 200 говорит об отсутствии ошибок. В свою очередь метрики говорят об очень низкой нагрузке, нет данных о задержках, низкая активность.

![image](https://github.com/user-attachments/assets/79203b62-6931-472c-81d1-9cdc18f993ba)

![image](https://github.com/user-attachments/assets/3e2a73e9-e6c7-4540-869d-7a28d057c556)

Затем произведена смена порта на 8090 и задеплоена данная версия.

![image](https://github.com/user-attachments/assets/3e2c80bb-88fa-4d12-85d3-7f0df7a791c9)

После смены порта возникает ошибка, так как контейнер теперь слушает на порту 8090, а Cloud Run по умолчанию обращается к 8080

Также проведен тест на другом порте, аналогично выдет ошибки, в том числе и в логах

![image](https://github.com/user-attachments/assets/6aa4632d-9c1d-45c4-ac6b-836a3aaef042)

На основе проведенной работы можно сделать следующие выводы:

Cloud run требует строгого соответствия портов.

При каких либо ошибках логи и метрики могут помочь в поиске проблем и их решении.

Прежде чем деплоить какой либо продукт можно провести тест на тестовом образе от google
