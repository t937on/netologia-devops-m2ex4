## Домашнее задание к занятию 4 «Оркестрация группой Docker контейнеров на примере Docker Compose»

### Задача 1
7.  
Ссылка в docker-hub: [https://hub.docker.com/repository/docker/t937on/netologia_devops_2_4_1_custom_nginx/general](https://hub.docker.com/repository/docker/t937on/netologia_devops_2_4_1_custom_nginx/general)

***
### Задача 3
3.  
Если подключиться к контейнеру через команду "attach"  то выполняется подключение к основному процессу, выполняемому в контейнере. Не создается новый процесс, а подключается стандратный ввод/вывод к уже работающему процессу.   
По нажатию Ctrl+C процесс завершается, контейнер останавливается.

10.  
В контейнере открыт порт 80,  а сервер теперь слушает порт 81, проброс портов остался с 8080 на порт контейнера 80

***
### Задача 5
1.  
Docker Compose будет использовать файл с именем compose.yaml.  
Ответ содержится в подсказке на странице [The Compose file](https://docs.docker.com/compose/intro/compose-application-model/#the-compose-file).  
Путь по умолчанию для файла Compose — compose.yaml(предпочтительно) или compose.yml, который находится в рабочем каталоге. Compose также поддерживает docker-compose.yamlи docker-compose.yml для обратной совместимости с более ранними версиями.  
Если существуют оба файла, Compose предпочитает compose.yaml.

7.
  > WARN[0000] docker-compose.yaml: the attribute `version` is obsolete, it will be ignored, please remove it to avoid potential confusion  

атрибут version больше не требуется в файлах конфигурации Docker Compose,  
он будет проигнорирован, и его наличие может вызвать путаницу.  

Рекомендации по действиям:  
Открыть файл docker-compose.yaml и удалить строку с version

  > WARN[0000] Found orphan containers ([task5-portainer-1]) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up. 

Это предупреждение говорит о том, что Docker Compose обнаружил контейнеры, которые были созданы ранее, 
но больше не определены в текущем файле конфигурации.  
Это может произойти, если были удалены или переименованы сервисы в файле.

Рекомендации по действиям:  
Очистить orphan-контейнеры, использовать  флаг --remove-orphans при выполнении команды:  
```$ docker compose up -d --remove-orphans```
