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

Установлен Docker   
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/b39ae922-6121-4eff-8c5d-c13965a510ed)   
Настроена работа в CLI c devcontainer
#### Devcontainer
Devcontainer - это концепция, предоставляющая контейнеризованные среды разработки для проектов, что обеспечивает консистентность среды разработки между различными разработчиками и облегчает управление зависимостями проекта. Установка devcontainer CLI позволяет использовать команды для создания и управления такими контейнерами. 

Был создан контейнер разработки на основе указанных конфигурационных файлов в каталоге
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/ec066982-f918-4e49-8960-1fbb69903eca)
И успешно запущен 
![image](https://github.com/elenasamsonenko/data_warehouse_analyst/assets/129121912/746c89a6-1fae-4ffd-be2d-13e4a7302d30)   

После запуска контейнера разработки, были выполнены команды 

```terraform -v
yc --version
dbt –version
```























