# Домашнее задание к занятию «Запуск приложений в K8S»

### Цель задания

В тестовой среде для работы с Kubernetes, установленной в предыдущем ДЗ, необходимо развернуть Deployment с приложением, состоящим из нескольких контейнеров, и масштабировать его.

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключённым git-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Описание](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) Deployment и примеры манифестов.
2. [Описание](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) Init-контейнеров.
3. [Описание](https://github.com/wbitt/Network-MultiTool) Multitool.

------

### Задание 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod

1. Создать Deployment приложения, состоящего из двух контейнеров — nginx и multitool. Решить возникшую ошибку.

<img width="461" height="579" alt="image" src="https://github.com/user-attachments/assets/4e5643b1-1dd8-424e-8727-0ffb20471ba4" />

Проблемы была с портами.

2. После запуска увеличить количество реплик работающего приложения до 2.
3. Продемонстрировать количество подов до и после масштабирования.

Реплика 1  
<img width="749" height="708" alt="image" src="https://github.com/user-attachments/assets/d299aa95-1d53-4000-bbb8-72f91993a33e" />

Реплика 2  
<img width="652" height="754" alt="image" src="https://github.com/user-attachments/assets/1e17fe4b-52b1-43a1-9067-9a8748e5bb47" />


4. Создать Service, который обеспечит доступ до реплик приложений из п.1.

<img width="336" height="283" alt="image" src="https://github.com/user-attachments/assets/27faa387-ca3c-4232-9e97-2b799f475772" />

<img width="1035" height="191" alt="image" src="https://github.com/user-attachments/assets/8061079f-9c2f-4a1b-9eaa-755ca9318764" />


5. Создать отдельный Pod с приложением multitool и убедиться с помощью `curl`, что из пода есть доступ до приложений из п.1.

<img width="403" height="306" alt="image" src="https://github.com/user-attachments/assets/70963ecb-dac8-4504-b07e-fc0787164768" />


<img width="1044" height="752" alt="image" src="https://github.com/user-attachments/assets/90e5eff4-c5a2-4720-ad3b-ccdcfb9acd4f" />



------

### Задание 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий

1. Создать Deployment приложения nginx и обеспечить старт контейнера только после того, как будет запущен сервис этого приложения.
2. Убедиться, что nginx не стартует. В качестве Init-контейнера взять busybox.
3. Создать и запустить Service. Убедиться, что Init запустился.
4. Продемонстрировать состояние пода до и после запуска сервиса.

------

### Правила приема работы

1. Домашняя работа оформляется в своем Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl` и скриншоты результатов.
3. Репозиторий должен содержать файлы манифестов и ссылки на них в файле README.md.

------
