Данные практики не идеальны и нацеленны не на оптимизацию, а на удобство. Созданны для связки MySQL + PHP + Git (как самой распространенной)
Используйте на свой страх и риск. 
Не забывайте что гвозди закручивают, а шурупы забивают)

MySQL

1. Таблицы в единственном числе
2. Кодировка **utf8_unicode_ci**
3. ``PrimaryKey`` не составной а ``AutoIncrement``
4. Вместо ``ENUM`` использовать ``TINYINT`` с суфиксом **\_enum**
5. В каждой таблице поле **added_at** ``TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP``
6. ``ForeignKey`` по умолчанию ``RESTRICTED``
7. В составных ключах сущности разделяются минусом
7. Именование ``ForeignKey`` **FK-table-table**
8. Именование ``Unique`` **U-column**
9. Название таблиц в нижнем регистре, разделитель нижнее подчеркивание
10. Пароли в базе не хранятся, только хеши с динамической солью
11. Детали кредитных карт в базе не хранятся (номер, сvv), только платежные токены и последние 4 цифры карты для идентификации
12. Цены хранятся, в типах данных без округления, либо в **DECIMAL** либо в **INT**

PHP
1. Вместо магических чисел и строк использовать константы
2. Функция возвращает только один тип данных
3. Запросы в базу данных сопровождаются документацией содержащей имена задействованных таблиц ``/**@usage table*/``
4. Функции должны быть документированны (``@return``, ``@param``, ``@throws``)
5. Необязательные параметры в функциях запрещены
6. ``error_reporting`` выставлен в **E_ALL**
7. Магические методы и свойства должны быть описанны в документации (``@property``, ``@method``)
8. Перенос строк **LF**
9. Кодировка файлов **UTF-8**
10. Работа с базой через **PDO**
11. Запрос формируется в переменной **$query** а не непосредственно в методе
12. Обрамляются пустой строкой ``if, switch, for, foreach, break, return``. За исключением вложенностей без других структур
13. По возможности не использовать тернарные условия.
14. Элементы массива с новой строки
15. Каждый элемент массива заканчивается запятой
16. Имена классов в CamelCase
17. Имена папок в CamelCase, заглавная в нижнем регистре
18. Имена функций в CamelCase, заглавная в нижнем регистре
19. Переменные в запросе к базе данных оформляются через плейсхолдеры
20. Environment делится на **prod**, **dev**, **staging**, **local**
21. Детали аутентификации добавляются в локальный файл занесённый в **.gitignore**
22. Путь к файловой системе прописывается через магическую константу **\_\_DIR\_\_**
Frontend
23. Если путь к файловой системе имеет динамические составляющие, то вконце он конкатенируется с пустой строкой.
24. Локальное окружение должно иметь возможность легко переключаться на обе базы **prod** и **dev**
25. При переключении окружения, пользователь должен залогинится снова
26. Вывод ошибок на **prod** отключен

Общие
1. Комментарии к коммиту должны содержать идентификатор таска и краткое описание

