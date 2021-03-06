# Построение RESTful API для Yatube
## Стек технологий: Django, Django Rest Framework (DRF)

## Для чего этот проект?
Нужно иметь понимание, что такое запросы, каких видов бывают запросы, зачем они нужны!
В данном проекте рассматриваются все виды: GET, POST, PATCH, PUT, DELETE

## Особенности реализации
Все view-classes наследуются от ModelViewSet (по факту generic класс), что очень упрощает работу.
В идеале прописать через APIView каждый класс, чтобы лучше понимать устройство запросов, но в данном проекте это было бы дольше)
Для каждого view-класса используются свои сериализаторы, а возвращается Response(serializer.data) + status.
Также есть permissions для Comment и Post моделей, т.к. мы обрабатываем все типы запросов, то менять посты и комменты, может только автор и аутентифицированный пользователь.
В проекте настроена фильтрация по following.username (SearchFilter) (для FollowViewSet), а также для всех полей модели Post (DjangoFilterBackend)

## Что умеет данный проект?
Этот проект продолжение проекта Yatube - простого блога, теперь к нему прикрутили API, у нас появилась возможность обращаться к апи и делать различные запросы к нему
* Обработка всех видов запросов для постов (получить, изменить, удалить, создать (CRUD)), однако на последние 3 требуются специальные permissions
* Обработка запросов для комментариев
* Обработка запросов для отслеживаемых авторов конкретного пользователя
* Обработка запросов для групп

## К данному проекту прикручена документация в пакете static, при запуске проекта (runserver), можно перейти на /redoc, чтобы ознакомиться с документацией
## Данный проект выполнен в учебных целях ©️ max_bstr
