# goldratt

Для компиляции и запуска сервиса используется джава 16. 
Чтобы работало, нужно:
1. Установить 16-ю джаву себе на машину (можно через идею - File - Project settings 
- SDKs - нажать +)
2. Установить на машину свежий грэдл (не меньше 7)
3. Установить для грэдла, чтобы он для самого себя использовал 16-ю джаву (File - Settings - Build, Exec...
- Build Tools - Gradle - внизу страницы)
4. Для виндоус - установить переменную окружения JAVA_HOME на установленную джаву

Для запуска приложения в докере:
1. Настроить работу с докером в идее - Сделать все, что есть в этом видео 
- https://www.youtube.com/watch?v=ck6xQqSOlpw
2. Запустить в терминале (alt - F12) команду 'gradle bootBuildImage'
3. После этого в плагине докера в идее должен появиться имидж с сервисом goldratt
4. Его можно запустить, создав для него контейнер. Надо забиндить порт 8080 докер-контейнера на какой-то локальный
порт (port bindings), например localhost 8080
5. Проверить сервис, послав гет-запрос на порт, на который забиндили в п. 4 (GET http://localhost:8080)