<p align="center">
  <a href="https://github.com/lk-geimfari/mimesis">
    <img src="https://raw.githubusercontent.com/lk-geimfari/mimesis/master/.github/images/logo.png" width="300" alt="Mimesis">
  </a>
</p>

<p align="center">
    <em>Mimesis: The Fake Data Generator</em>
</p>

<p align="center">
<a href="https://github.com/lk-geimfari/mimesis/actions/workflows/test.yml?query=branch%3Amaster" target="_blank">
    <img src="https://github.com/lk-geimfari/mimesis/actions/workflows/test.yml/badge.svg?branch=master" alt="Test">
</a>
<a href="https://mimesis.name/en/latest/" target="_blank">
    <img src="https://readthedocs.org/projects/mimesis/badge/?version=latest" alt="Coverage">
</a>
<a href="https://pypi.org/project/mimesis/" target="_blank">
    <img src="https://img.shields.io/pypi/v/mimesis?color=bright-green" alt="Package version">
</a>
<a href="https://pypi.org/project/mimesis/" target="_blank">
    <img src="https://img.shields.io/pypi/dm/mimesis" alt="Package version">
</a>
<a href="https://pypi.org/project/mimesis/" target="_blank">
    <img src="https://img.shields.io/badge/python-3.10%20%7C%203.11%20%7C%203.12%20%7C%203.13%20%7C%203.14%20%7C%20pypy-brightgreen" alt="Supported Python versions">
</a>
</p>

---

**Документация**: <a href="https://mimesis.name/" target="_blank">https://mimesis.name/</a>

---

Mimesis ([/mɪˈmiːsɪs](https://mimesis.name/master/about.html#what-does-name-mean)) - это надежный генератор данных для Python, который может создавать широкий спектр поддельных данных на разных языках.

Ключевыми особенностями являются:

- **Многоязычность**: поддержка 46 различных языков.
- **Расширяемость**: Поддерживает пользовательские поставщики данных и обработчики пользовательских полей.
- **Простота использования**: Имеет простой дизайн и понятную документацию для простого создания данных.
- **Производительность**: Широко признан как самый быстрый генератор данных среди решений на Python.
- **Разнообразие данных**: Включает различные поставщики данных, предназначенные для различных случаев использования.
- **Генераторы на основе схем**: Предлагает генераторы данных на основе схем для легкого создания данных любой сложности.
- **Реляционные данные**: Поддерживает создание реляционных данных со ссылками между схемами для сложных структур данных.
- **Интуитивно понятный интерфейс**: Отличная поддержка редакторов. Полностью типизированный, что обеспечивает автоматическое заполнение практически везде.

## Установка

> [ПРЕДУПРЕЖДЕНИЕ!]
> В Mimesis 20.0.0 я собираюсь полностью переработать текущую реализацию генерации на основе схемы. Обратной совместимости с существующей реализацией не будет.

> [ВАЖНО!]
> Для работы с Mimesis на Python версий 3.8 и 3.9 последней совместимой версией является Mimesis 11.1.0. Установите именно эту версию, чтобы обеспечить совместимость.

> [ПРЕДУПРЕЖДЕНИЕ!]
> Начиная с версии 19.0.0, Mimesis прекратил поддержку встроенных поставщиков.


Чтобы установить mimesis, используйте pip:

```
~ pip install mimesis
```

## Документация

Вы можете найти полную документацию на сайте [Read the Docs](https://mimesis.name/).

Он разделен на несколько разделов:

-  [About Mimesis](https://mimesis.name/latest/about.html)
-  [Quickstart](https://mimesis.name/latest/quickstart.html)
-  [Locales](https://mimesis.name/latest/locales.html)
-  [Data Providers](https://mimesis.name/latest/providers.html)
-  [Structured Data Generation](https://mimesis.name/latest/schema.html)
-  [Random and Seed](https://mimesis.name/latest/random_and_seed.html)
-  [Integration with factory_boy](https://mimesis.name/latest/factory_plugin.html)
-  [API Reference](https://mimesis.name/latest/api.html)
-  [Changelog](https://mimesis.name/latest/index.html#changelog)

Вы можете улучшить его, отправив pull-запросы в этот репозиторий.

## Использование

Библиотека исключительно удобна в использовании, и от вас требуется только импортировать объект **Поставщик данных**,
соответствующий желаемому типу данных.

Например, поставщик услуг [Person](https://mimesis.name/latest/api.html#person) может быть импортирован для доступа к личной информации,
включая имя, фамилию, адрес электронной почты и другие связанные поля:

```python
from mimesis import Person
from mimesis.locales import Locale

person = Person(Locale.EN)

person.full_name()
# Output: 'Brande Sears'

person.email(domains=['example.com'])
# Output: 'roccelline1878@example.com'

person.email(domains=['mimesis.name'], unique=True)
# Output: 'f272a05d39ec46fdac5be4ac7be45f3f@mimesis.name'

person.telephone(mask='1-4##-8##-5##3')
# Output: '1-436-896-5213'
```

## Лицензия

Mimesis распространяется по лицензии MIT. Дополнительную информацию смотрите в разделе [LICENSE](https://github.com/lk-geimfari/mimesis/blob/master/LICENSE).
