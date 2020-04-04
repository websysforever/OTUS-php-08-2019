#### Первый запуск проекта

1. Запуск контейнеров:   

        docker-compose up -d

2. Заполнение данными Redis через php-скрипт:

        localhost/redis/load_data
     
#### Проверка

1. Добавление событий реализовано через GET параметр для удобства проверки:    

        localhost/redis/add_event/?event=<{данные события}>     

add_event - принимает строку с описанием события,    
 можно вставить шаблон указанный ниже:         

    {
        "priority": 1000, 
        "conditions": {
            "param1": 1
        }, 
        "event": {
            "name": "Название события"
            }
    }

2. Удаление доступных событий:    

        localhost/redis/drop_events    

3. Ответ на запрос пользователя подходящим событием:   

        localhost/redis/query_event/?query=<{запрос}>     

query - принимает строку с параметрами,    
 можно вставить шаблон указанный ниже:     
 
    { 
        "params": {
            "param1": 1,
            "param1": 2,
            "param2": 2
        }
    }