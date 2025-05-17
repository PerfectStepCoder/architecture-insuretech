# architecture-insuretech

# Task2

Запуск локального кластера k8s
(не работает драйвер: minikube start --vm-driver=virtualbox)
> minikube start --driver=docker

Мониториг k8s:
> minikube dashboard
> minikube status

IP адрес кубера:
> minikube ip
Все интерфейсы сетевые у кубера
> kubectl get svc

All hpa:
> kubectl get hpa

Метрики по подам:
> kubectl top pods

Развертывание в кубере, применение манифестов в локальный кубер:
> cd ./Task2
> kubectl apply -f deployment.yaml
> kubectl apply -f service.yaml
> kubectl apply -f hpa.yaml

Проброс порта, чтобы получить доступ к веб-приложению в поде:
> minikube service scaletestapp-service

Посмотреть логи пода:
> kubectl get pods
> kubectl logs <имя-пода>

## Нагрузочное тестирование
Запуск locust
> locust
Запросы отправляю на адрес 
> minikube service scaletestapp-service --url 

Горизотнтальное масштабирование настроено на максимальную отзывчивать, как в сторону возрастанию колиечтво подов при увеличении нагрузки так и в сторону уменьшение количества подов при отсутсвии нагрузки

Статистика увеличения подов при росте нагрузки находится в папке ./hpa
