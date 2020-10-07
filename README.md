# itsumma-frontend-test

Написать приложение для сортировки списка карточек, обладающее следующим функционалом:
* Показ "бесконечной ленты" с карточками
  * каждая карточка может быть свернутой или развернутой (сохраняется при следующем заходе)
  * каждую развернутую карточку можно смахнуть влево или в право (попадают в разные списки)
* Каджая верхняя видимая карточка влияет на hash в адресной строке строке (#id)
* Возможность просмотреть и редактировать *(удалить из списка / перенести в целевой)* списки отфильтрованных карточек


### Требования:

* Сделать пулреквест в публичный репозиторий
* Использование Angular (9+), Typescript
* Соответсвие кода правилам Tslint
* Для манипуляции с данными требуется взаимодействовать с REST API.
* Листы фильтрованных карточек с помощью всплывающих окон со списком.
* Перед удалением необходимо показать всплывающее окно для подтверждения.

### Пожелания:

* Использование state management pattern 


### Дополнительно:

https://www.figma.com/file/nJ259n4iFlgSqqiWMrgiGd/front-test?node-id=0%3A1 - условный дизан

## Directory API

Backend Host указан в environment.ts

* Получение списка карточек `GET /cards/{vote?: integer = 0}`  // vote необязательный default 0
```
Response
[] {
  id integer
  collapsed_photo string
  uncollapsed_photo string
  description string
  vote string
}
```

* Отправка голоса к карточке `Post /vote`
```
POST /vote
Body
{
  id integer
  vote integer
}

Response
{
  id integer
  collapsed_photo string
  uncollapsed_photo string
  description string
  vote string
}
```
