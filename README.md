# Сайт EASY TPL

## Stack / Технологии сайта

Первая версия сайта является статической, чистый html. Сборка осуществляется через вебпак, для 
стилизации используется BS4.

###### Шаблонизация
- Для склейки используется html-loader. Использовать команду <%= _.template(require('html-loader!./../includes/name.html'))(data) %> можно только во внешних файлах. Во внутренних (в папке includes) работать не будет. Через объект data можно прокинуть параметры во внутренние страницы-шаблоны. 

###### JS
- Единстванная существующая функция следит за скроллом юзеров и добавляет классы к body и мобильному меню

###### SVG
- Для удобства шаблонизации все SVG переведены в html-шаблоны. Так же удалены лишние теги (оставлено только минимально-необходимое)
- Для удаления всех id внутри svg, используется regexp: ' (id=".+?")'. Это позволит быстро найти все id и заменить их на пустое место.

**Подробнее:**
1. Открываем SVG файл
2. Удаляем xmlns:xlink в тэге svg
3. Удаляем комментарии графического редактора
4. Удаляем теги  title, desc, defs
5. Тег style оставляем
6. Удаляем все id с помощью regexp (замена на пустое место)
7. У первого дочернего тега внутри svg - задаём класс с имегем svg__iconName (его потом можно будет использовать в цсс)
8. Иконка готова. Теперь скопируйте содержимое в html-шаблон и удалить верхнюю строчку \xml version="1.0" encoding="UTF-8"\
9. Полученный хтмл-шаблон можно вставлять внутрь страниц


## Поддержка старых браузеров
Настраивается через файл .browserslistrc, варианты настроек можно прочесть здесь:
https://github.com/browserslist/browserslist#full-list

