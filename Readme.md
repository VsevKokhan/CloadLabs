# Cloud лаба1 - Знакомство с IaaS, PaaS, SaaS сервисами в облаке на примере Amazon Web Services (AWS). Создание сервисной модели.
## 8 вариант
## Цель работы:
Знакомство с облачными сервисами. Понимание уровней абстракции над инфраструктурой в облаке. Формирование понимания типов потребления сервисов в сервисной-модели.
## Дано:
Слепок данных биллинга от провайдера после небольшой обработки в виде SQL-параметров. Символ % в начале/конце означает, что перед/после него может стоять любой набор символов. Образец итогового соответствия, что желательно получить в конце. В этом же документе

## С чего начинаем:
Импортируем файл .csv в Excel. Далее нам нужно будет распределить потребление сервисов по иерархии, чтобы можно было провести анализ от большего к меньшему (напр. От всех вычислительных ресурсов Compute дойти до конкретного типа использования - Выделенной стойка в датацентре Dedicated host usage). Для столбцов IT Tower и Service Family значения можно выбрать из образца.Далее сохраним файл и зальем красиво его к отчету на гх.

# Ход работы
Дан слепок (в файлике слепок)
После нужно описать каждый сервисам
AI/ML
Amazon SageMaker
Amazon SageMaker предоставляет инструменты для обучения, развертывания и управления моделями машинного обучения. Это включает в себя создание ноутбуков для анализа данных, обработку данных, трансформацию, развертывание моделей и хостинг конечных точек.

Notebook: Удобные ноутбуки для анализа данных и разработки моделей.
Training: Инструменты для обучения моделей на больших наборах данных.
Processing: Возможность обработки данных через управляемые вычислительные ресурсы.
Transformation: Трансформация данных для подготовки к обучению моделей.
Model Deployment: Развертывание моделей машинного обучения в продуктивной среде.
Hosting: Хостинг конечных точек для работы обученных моделей.
Data Labeling: Услуги по маркировке данных для обучения алгоритмов.

Compute
Amazon EKS (Elastic Kubernetes Service)
Amazon EKS — это управляемый сервис Kubernetes, позволяющий запускать, управлять и масштабировать контейнерные приложения.

Fargate (vCPU и Memory Usage): Поддержка бессерверных вычислений для контейнеров, оптимизируя использование ресурсов.
Per Cluster Usage: Мониторинг и управление кластером Kubernetes.

Amazon DAX
Amazon DAX — это кэширование в памяти, которое ускоряет операции чтения для DynamoDB, обеспечивая низкие задержки и высокую производительность.

Amazon DynamoDB
Amazon DynamoDB — это полностью управляемая NoSQL база данных, которая поддерживает масштабируемость и обеспечивает предсказуемую производительность.

Write/Read Capacity: Управление емкостью записи и чтения.
Restore Operations: Восстановление данных из резервных копий.
Streams: Потоковая обработка данных DynamoDB.
Requests: Управление запросами на чтение и запись.

AWS Amplify
AWS Amplify — это платформа для разработки и хостинга веб- и мобильных приложений, предлагающая инструменты для упрощения разработки.

Build Duration: Учет времени сборки приложений.
Data Transfer Out: Управление исходящим трафиком данных.

Regional Data Transfer (Amazon FSx)
Amazon FSx позволяет управлять региональным трафиком данных и предоставляет производительные файловые системы.

Amazon GuardDuty
Amazon GuardDuty — это сервис обнаружения угроз, анализирующий потоки данных AWS для выявления подозрительной активности.

Taxation: Налогообложение использования ресурса.
Event Analysis (Free/Paid): Анализ событий в бесплатных и платных режимах.
Event Analysis (Bytes): Анализ событий с учетом объема данных.
Amazon Inspector
Amazon Inspector оценивает безопасность приложений, выявляя уязвимости и несоответствия стандартам безопасности.

Agent Assessments: Проверка безопасности запущенных агентов.
Network Assessments: Анализ уязвимостей сети.

Amazon FSx
Amazon FSx предоставляет управляемые файловые системы, такие как Windows File Server, обеспечивая высокую производительность для облачных приложений.

Throughput Capacity: Поддержка высокой пропускной способности.
Storage: Масштабируемое файловое хранилище.
Backup Usage: Управление резервными копиями.
Amazon Glacier
Amazon Glacier предоставляет надежное и доступное хранилище для архивирования данных.

Taxation: Налогообложение за использование ресурса.
Data Stored: Учет объема хранимых данных.
Provisioned Storage: Управление выделенными объемами хранения.
Timed Storage: Учёт времени хранения данных.
Request Handling: Управление запросами для различных уровней обслуживания.
Early Deletion: Штраф за раннее удаление данных.
AWS Backup
AWS Backup предоставляет централизованное управление резервным копированием для облачных ресурсов.

Cold Storage: Долговременное хранение данных с низкой стоимостью.
Warm Storage: Хранение данных для быстрого восстановления.
Restore Operations: Операции восстановления данных.
Early Deletion Penalty: Штраф за удаление данных до окончания срока хранения.

## ОТкуда инфа?

Брали преимущественно всё с:
https://clck.ru/3FUuFJ
https://clck.ru/3FUuGk
https://aws.amazon.com/pricing/
https://clck.ru/3FUuHe
https://clck.ru/3FUuJf

## Готовую таблицу можно по ссылочке:
https://drive.google.com/drive/folders/1hfpLadiyDWNRorFYM3tFAytOKVYweI4m?hl=ru
,либо в самом гх

## Вывод
вывод один - уметь вдумчиво и очень долго чиать документацю. Из самого интересного и возможно даже в будущем частого использования я считаю будут следующие срвисы и вот почему:

Если ваши данные требуют долгосрочного и дешевого хранения, например, архивов или резервных копий, Amazon Glacier станет подходящим выбором так как, он предлагает экономичное хранение данных, которые редко используются.
FSx (Windows File Server) будет актуален, если вы работаете в среде Microsoft и хотите интегрировать данные с AWS.

Если что то по моднее и вы интересуетесь анализом данных, машинным обучением или автоматизацией, сервисы Amazon SageMaker могли бы стать вашим выбором.

SageMaker позволяет легко обучать модели, развертывать их и проводить предсказания.
Вы можете использовать SageMaker для создания и настройки нейронных сетей, особенно если вам важна интеграция с другими AWS-сервисами.
Например, Notebook подходит для разработки и тестирования моделей, а Training для обработки больших объемов данных.

Вообще все перечисленные сервисы в лабе полезны, вопрос только какие именно и с какой стороны можно будет встретить эти сервисы на практике.