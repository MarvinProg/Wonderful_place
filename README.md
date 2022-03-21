# Wonderful_place

О регистрации и входе:
Присутствует стандартная регистрация.

### О создании события:
Пользователь может создавать событие, удалять и редактировать. Так же пользователь может ставить пин-код на событие. При подписке на событие создатель получает увидомления на почту, которую он указал. Если же пользователь оставляет комментарий, добавляет фото, то рассылка почты об обновлении в собитии идет всем, кто подписан на событие.

### Как пользоваться:
Для того чтобы попробовать приложение у себя на локальной машине, вам нужно:
1. Склонировать приложение к себе на компьютер. (`git clone git@github.com:MarvinProg/Wonderful_place.git`)
2. Сделать `bundle` всех гемов (перед тем как делать, нужно перейти в папку приложения) 
3. Далее вам нужно прогнать все миграции командой: `rails db:migrate`
4. Чтобы приложение работало, вам нужно создать файлы `database.yml` и `secrets.yml`
- В файле `database.yml` нужно прописать следующий код:
  
  ```yml
  default: &default
    adapter: sqlite3
    encoding: unicode
    pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>

  development:
    «: *default
    database: `name`
  
  test:
    «: *default
    database: `name`

  production:
    adapter: postgresql
    user: `user vps`
    password: `password database`
    database: `name`
    host: localhost
    port: `port`
  ```

5. В корневой папке Wonderful_place создать файл `.env`
  ```yml
  MAILJET_API_KEY = ''
  MAILJET_SECRET_KEY = ''
  MAILJET_SENDER = ''
  YANDEX_API = ''
  S3_ACCESS_KEY = ''
  S3_SECRET_KEY = ''
  S3_BUCKET_NAME = ''
  ```
6. Теперь осталось просто написать команду: `rails s`\
7. И запустить `bin/webpack-dev-server` webpack сервер.

## О версии Ruby - 2.7.2


