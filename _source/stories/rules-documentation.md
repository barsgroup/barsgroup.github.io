<!-- 
.. title: Правила по документированию Python и JS кода
.. slug: rules-documentation
.. date: 2014/03/19 10:34:36
.. tags: 
.. link: 
.. description: 
.. type: text
-->

## Содержание

1. [Термины и определения](#terms)
2. [Общие положения](#common-issues)
3. [Ручное документирование](#write-docs)
    - [Общее описание](#common-writes-docs)
    - [Установка](#install)
    - [Приступая к работе](#getting-started)
    - [Расширенное использование](#advanced-usage)
    - [Интерфейс взаимодействия](#api)
    - [ЧаВО](#faq)
    - [Дополнительные сведения](#other-data)
4. [Документирование python-кода](#python)
    - [Классы](#python-class)
    - [Методы и функции](#python-method-and-func)
5. [Документирование javascript-кода](#js)
    - [Структура блока документирования](#js-structure)
    - [Переменные](#js-variable)
    - [Функции](#js-func)
    - [Классы](#js-class)

## <a name="terms">Термины и определения</a>

_[reStructuredText](http://ru.wikipedia.org/wiki/ReStructuredText)_ (_ReST_) – язык разметки,
предназначенный для документирования программ непосредственно в исходном коде.

_[Sphinx](http://sphinx-doc.org/)_ – генератор документации, преобразующий файлы в формате ReST в другие форматы (HTML, PDF, EPub и др.)

_Модуль_ - набор алгоритмов, классов и других структур, имеющий имя, поставляемых как единое целое,
объединенных общей целью и вариантом использования.

## <a name="common-issues">Общие положения</a>

Следует разделять документацию модуля и документацию кода.
Цель документирования модуля - описание структуры модуля,
его вариантов использования, интерфейса взаимодействия с модулем.
Цель документирования кода - описание внутренних структур модуля и алгоритмов.

Документирование модуля предназначено для ознакомления с предназначением модуля и его частей,
особенностями его установки и использования.
Именно на основании документации к модулю разработчик принимает решение о способе и варианте использования модуля.

Документирование кода является неотъемлемой частью разработки программных продуктов.
Оно направлено на описание дополнительных аспектов того, что именно делает код.

Общие правила:

- Документация пишется на русском языке с соблюдением грамматики и пунктуации;
- Предложения разделяются пробелами;
- Комментарии пишутся на русском языке;
- Используются строки шириной не более 79 символов. Ширина в 79 знаков заполняется максимально полно;
- В строках документации и комментариях не допускается использование шуток,
сленга, ненормативной лексики, «языка паддонкаф» и пр.

Документирование кода ведется с использованием генератора документации _Sphinx_ и языка разметки _reStructuredText_.

Различаются два типа документирования:

- **Ручное документирование** – в этом случае создается отдельный файл документации,
в котором формируется текст в соответствии с языком разметки _reStructuredText_;

- **Документирование кода** – в этом случае разработчик делает соответствующую разметку непосредственно в коде.
После чего такая документация может использовать различными IDE или при автоматической сборке в режиме ручного
документирования.


## <a name="write-docs">Ручное документирование</a>

Обычно, документация к модулю состоит из следующих разделов:

- Общее описание (About, Introduction, Overview)
- Установка (Installation, Setup, Requirements, Dependencies)
- Приступая к работе (Tutorial, Basic usage, First steps, Quickstart, Getting started)

Дополнительными разделами могут быть:

- Расширенное использование (Advanced usage, Tips&Tricks)
- Интерфейс взаимодействия (API, Command reference, Integration)
- ЧаВО (FAQ, Common issues)
- Дополнительные сведения (Resources, Community, Links)

### <a name="common-writes-docs">Общее описание</a>

- Назначение модуля и основной функционал
- Состав и структура
- История, предпосылки
- Лицензия

Из общего описания должно быть понятно предназначение модуля, его основные функции и состав.
Можно описать варианты использования со ссылками на примеры из остальных пунктов.

### <a name="install">Установка</a>

- Необходимые библиотеки и другие модули
- Процесс установки
- Описание настроек
- Установка должна описывать зависимости и особенности выполнения установки модуля.
Возможные варианты установки. Также должно содержаться описание всех настроек,
которые необходимо выполнить при и после установки.

### <a name="getting-started">Приступая к работе</a>

- Описание необходимых условий
- Простые примеры использования модуля
- В этом разделе должны описываться самые простые варианты использования модуля с указанием выполняемых действий и кода.
Должны содержаться результаты выполнения примеров. Примеров должно быть максимально много, чтобы разобрать все простые варианты использования модуля.
- Примеры должны показать основные функции модуля в их простом применении.
Примеры, которые требуют большей подоготовки и сложного поведения следует вынести в следующий раздел.

### <a name="advanced-usage">Расширенное использование</a>

- Специальные и критические варианты использования
- Использование различных настроек

В этом разделе могут быть описаны примеры использования при более тонкой настройке модуля,
требующие более глубокого погружения в особенности работы модуля.
Также могут быть примеры использования модуля в различных комбинациях настроек.

### <a name="api">Интерфейс взаимодействия</a>

- Описание классов и методов, api-функций, REST-интерфейса
- Описание команд
- Описание точек расширения функционала
- Примеры интеграции и расширений

В этом разделе могут описываться все объекты и функции для обеспечения взаимодействия с модулем.
Даются ссылки на автодокументацию по коду.
Приводятся примеры и способы расширения и/или изменения функционала модуля.

### <a name="faq">ЧаВО</a>

- Частозадаваемые вопросы и ответы
- Решеные и нерешенные проблемы
- Особенности и трюки
- Обработка ошибок

В этом разделе описываются ответы на типичные вопросы, возникающие при использовании модуля.
Также, рассматриваются возможные проблемы и способы их ршения (если это возможно).
Рассматриваются возможные ошибки и их обработка.

### <a name="other-data">Дополнительные сведения</a>

- Ссылки на дополнительные ресурсы, форумы, документы
- Авторы
- История версий (changelog)

В этом разделе могут содержаться любые иные сведения не описывающие использование модуля, но дополняющие его описание.


## <a name="python">Документирование Python кода</a>


Каждый новый создаваемый модуль должен предваряться директивой:

    ::python
    #coding: utf-8

или

    ::python
    # -*- coding: utf-8 -*-

После которой в тройных кавычках идет аннотация к модулю.
Аннотация может содержать в себе дату его создания, автора модуля, краткое резюме о предназначении модуля. Например:

    ::python
    u"""
    Created on 12.05.13

    @author: ivanov
    Описание моделей
    """

### <a name="python-class">Классы</a>

После строки определения класса должен следовать комментарий в тройных кавычках, о назначении этого класса.

    ::python
    class Account(BaseEnterpriseDictionaryModel):
        u"""Модель плана счетов.
        """

### <a name="python-method-and-func">Методы и функции</a>

После строки объявления функции (метода) должен следовать комментарий в тройных кавычках о назначении этой функции.
Затем указывается перечень аргументов функции, их типов, возвращаемый результат,
а также типы возможных исключений в функции. Описание функции и перечень аргументов необходимо разделять пустой строкой.
Также пустой строкой отделяется перечень аргументов с их типами и
перечень возвращаемых значений с типами возможных исключений.

Если описание элемента превышает в строке 79 символов, его необходимо перенести на новую строку с обязательным отступом.

Элементы синтаксиса документирования аргументов функций:

<table border="1" cellpadding=5>
    <tr>
        <th>Элемент</th>
        <th>Назначение</th>
    </tr>
    <tr>
        <td>:param [тип] имя:</td>
        <td>Описание параметра функции</td>
    </tr>
     <tr>
        <td>:type имя параметра: тип</td>
        <td>Тип параметра</td>
    </tr>
     <tr>
        <td>:return:</td>
        <td>Описание возвращаемого результата</td>
    </tr>
    <tr>
        <td>:rtype:</td>
        <td>Тип возвращаемого результата</td>
    </tr>
    <tr>
        <td>:raise:</td>
        <td>Тип(ы) возможных исключений</td>
    </tr>
</table>


Если тип передаваемого параметра является встроенным типом языка Python,
то он указывается с ключевым словом _param_. В противном случае, он указывается с ключевым словом _type_.
Для возможности перехода к описанию типов программного продукта рекомендуется в параметре type указывать полный путь до типа,
например:

    ::python
    web_bb.core.acc_chart.models.Account #  для классов из ядра системы,
    web_bb.plugins.ack.models.Budget #  для классов из плагинов.

Пример описания метода:

    ::python
    def create_doc(doc_model, operation, doc_params=None):
        """ Создание документа на основе полученных данных

        :param doc_model: класс модели документа
        :param operation: шаблон операции
        :type operation: web_bb.core.repos.models.DocumentOperations
        :param dict doc_params: словарь параметров, которые будут присвоены
            экземпляру документа

        :return: экземпляр на основе переданной модели документа
        :raise: KeyError

        """


Для переопределяемых методов в наследующих классах допустимо опускать описание только в случае,
если описание присутствует в классе-родителе, и в методе потомка используется вызов такого же метода родителя.


**Пример 1**

Описание метода присутствует в классе-родителе, также используется вызов метода родителя с помощью ключевого слова super.
Описание метода можно опустить

    ::python
    def get_rows(self, request, context, query_object):
            query_object.with_parents = True

            # "Соответствие капитальных вложений и счетов НМА" (НМАКапВл)
            # Заложено в фикстурах модуля acc_chart
            acc_group = 12
            acc_list = get_equivalent_accounts_from_group(acc_group)
            query_object.filter = BE(
                'id', BE.IN, acc_list) & query_object.filter

            return super(NMACapInvestAccChartPack, self).get_rows(
                request, context, query_object)

**Пример 2**

Полностью переопределяется метод родительского класса. Описание обязательно.

    ::python
    class MergeRecordsPack(RecordsPack):

        def validate_row(self, request, context, record, is_new):
            u"""Выключаем проверку базового класса
            """
            pass


## <a name="js">Документирование JavaScript кода</a>

Документирование JavaScript-кода производится с использованием синтаксиса языка [JSDoc](http://ru.wikipedia.org/wiki/JSDoc).
Строки документирования заключаются в секции /**…*/.
Все строки документирования помещаются перед определением параметров, функций, классов.

### <a name="js-structure">Структура блока документирования</a>

    ::javascript
    /**
    * Описание параметра, функции, класса и т.д.
    *
    * параметры, типы, возвращаемые результаты
    */

### <a name="js-variable">Переменные</a>

    ::javascript
    /**
     * Счетчик
     * @type {number}
     */
    var i = 0;

    /**
     * Массив
     * @type {Array}
     */
    var d = [];

С помощью ключевого слова _type_ в фигурных скобках отражаем тип переменной.

### <a name="js-func">Функции</a>

    ::javascript
    /**
     * Проверяет какое-то условие
     *
     * @param а какой-то параметр
     * @returns {boolean}
     */
    function myFunction(a) {
        if (a) {
            return true;
        } else {
            return false;
        }
    }

С помощью ключевого слова _param_ описываем аргументы функции.
С помощью ключевого слова _returns_ описываем возвращаемое значение.
В фигурных скобках можно указать типы описываемых элементов.

### <a name="js-class">Классы</a>

    ::javascript
    /**
     * Создает экземпляр класса MyClass
     *
     * @param {number} x параметр x
     * @param {number} y параметр y
     * @this {MyClass}
     * @constructor
     */
    function MyClass(x ,y) {
        this.x = x;
        this.y = y;
    }

С помощью ключевого слова _constructor_ указываем,
что данная функция является конструктором класса.
С помощью ключевого слова _this_ указываем, какого типа будет созданный объект.