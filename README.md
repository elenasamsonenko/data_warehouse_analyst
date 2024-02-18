# Первое практическое занятие
# “Создание потоков данных с использованием Airbyte”

#### Цель:
• Настройка потоков данных с помощью Airbyte     
• Развертывание инфраструктуры как кода с использованием Terraform и Yandex.Cloud    
• Мгновенная разработка с использованием Github Codespaces    
• Проверка заданий с использованием Github Actions   

#### Airbyte
Airbyte - это открытый источник данных (open-source data integration platform), который используется для создания, мониторинга и управления потоками данных между различными источниками и системами. Его основная цель - упростить и ускорить процесс интеграции данных, обеспечивая эффективный обмен информацией между различными приложениями, базами данных и сервисами. Airbyte позволяет создавать конвейеры данных (data pipelines) для синхронизации и перемещения информации, что облегчает аналитику, отчетность и другие бизнес-процессы, требующие доступа к разнообразным данным.

#### Terraform
Terraform - это инструмент для управления инфраструктурой как кода (Infrastructure as Code, IaC). С его помощью можно описывать и развертывать инфраструктуру в виде конфигурационных файлов, что позволяет автоматизировать процесс создания, изменения и удаления ресурсов в облачных и других окружениях.

В рамках работы было настроено развертывание инфраструктуры на Yandex.Cloud с использованием Terraform. Были настроены data pipelines между базами данных PostgreSQL и ClickHouse, а также интеграция с хранилищем данных Amazon S3. Это позволяет эффективно передавать и обрабатывать данные между различными хранилищами, обеспечивая гибкость и масштабируемость в управлении данными в рамках проекта

## 1.	Настройка среды разработчика.

На GitHub был создан репозиторий для сохранения результатов практических уроков.   

![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/cc618ff8-dd12-47fb-8e37-8f6ba83ab96b)   

Также была создана локальная копия удаленного репозитория Git с использованием команды git clone, после чего была создана новая ветка. Этот процесс позволяет изолировать и вносить изменения в код независимо, облегчая параллельную разработку, тестирование и управление версиями проекта в системе контроля версий.

![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/b7d6fe60-1882-4264-852c-09a8390d6bd8)     
### Основные команды Git
#### Инициализация проекта как репозиторий Git
```
git init
```   
#### Отражение текущего состояния репозитория
```
git status
```   
#### Отслеживание изменений во всех файлах и включение их в следующий коммит
```
git add .     
```
#### Исключение файла из индексации, если не нужно отслеживать изменения
```
git reset
```


Установлен Docker   
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/b39ae922-6121-4eff-8c5d-c13965a510ed)   
Настроена работа в CLI c devcontainer
#### Devcontainer
Devcontainer - это концепция, предоставляющая контейнеризованные среды разработки для проектов, что обеспечивает консистентность среды разработки между различными разработчиками и облегчает управление зависимостями проекта. Установка devcontainer CLI позволяет использовать команды для создания и управления такими контейнерами. 

Был создан контейнер разработки на основе указанных конфигурационных файлов в каталоге
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/ec066982-f918-4e49-8960-1fbb69903eca)
И успешно запущен 
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/746c89a6-1fae-4ffd-be2d-13e4a7302d30)   

После инициализации контейнера разработки были выполнены команды для проверки используемых версий инструментов внутри контейнера, чтобы исключить их использования на локальном компьютере.
```
terraform -v
yc --version
dbt –version
```   
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/c02ae35d-02e8-4e4c-bef4-ec793577cb58)   

## 2. Развертывание инфраструктуры в Yandex.Cloud с использованием Terraform.

Создан аккаунт в Yandex.Cloud, с последующим ознакомлением с веб-интерфейсом платформы.

![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/a0f9fa6f-f7bd-4efb-b428-693f9d08296a)


Настроена работа в CLI c Yandex.Cloud
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/cd50e82e-3af0-4e2e-8dcd-f52e1088b2ca)

На этом этапе был создан и заполнен файл .env для безопасного хранения паролей. После этого была осуществлена настройка Terraform и запущена виртуальная машина в Yandex.Cloud.   
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/43f6525c-fa0c-4459-bbb4-79ab1f860c22)


## 3. Доступ к Airbyte
С помощью СLI был запрошен IP Airbyte

## 4. Настройка потоков данных
Настроена конфигурация источника данных Postgres с использованием учетных данных, предоставленных в конфигурационном файле.  


Произведена синхронизация данных с источника в ClickHouse и S3   
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/e88ec835-4e64-4f32-b14f-ee2df7994788)   
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/cb16edce-9439-4ce7-b5d2-91dccdb49faf)


## 5. Результаты
Данная практическая работа предоставила следующие результаты:
1. Опыт работы с Yandex.Cloud: Приобретение навыков работы с облачной платформой Yandex.Cloud, включая создание аккаунта, конфигурирование инфраструктуры.
2. Использование Terraform: Опыт использования Terraform для создания и управления инфраструктурой в облаке. Это включает в себя настройку виртуальных машин, хранилищ данных.
3. Настройка Data Pipelines: Практическое применение настройки потоков данных с использованием Airbyte, настройка источников данных (Postgres), настройка назначений данных (ClickHouse, S3), а также синхронизация данных между ними.
4. Безопасное хранение секретов: Опыт безопасного хранения паролей и ключей с использованием файла .env и переменных окружения.
5. Работа с Git и GitHub: Взаимодействие с Git для клонирования репозиториев, управления ветками и выполнения пушей.
6. Знакомство с DevOps: Опыт работы с DevOps-подходом, включая создание контейнеров разработки (devcontainer) и использование Terraform для развертывания инфраструктуры.

Эта практическая работа предоставила полезные навыки и опыт, необходимые для работы в облачных средах, управления данными и использования DevOps-инструментов.































