# Отчёт о тестировании Приложения "Credit Card Number Validator"
## Краткое описание
20.03.2020  было проведено тестирование приложения на Java "Credit Card Number Validator" далее CCNV, которое проверяет валидность кредитных карт.

На тестирование затрачен 2 час.

В результате тестирования выявлены следующие дефекты:
* [баг репорт 1](https://github.com/DementevSlava/Java1.1-homework-2/issues/1)
* [баг репорт 2](https://github.com/DementevSlava/Java1.1-homework-2/issues/2)

## Описание процесса тестирования
### Что тестировали
1. установка IntelliJ IDEA согласно [Руководство по установке IntelliJ IDEA](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)
2. Проверка кода в том виде в которм представлен.
3. Провели Smoke-test програмы CCNV в среде IntelliJ IDEA.
### Арефакты
* тест-сьют, состоящий из 7 тест-кейсов
    * проверка валидных номера (4 кейса, позитивный сценарий)
    * проверка НЕвалидных номеров (3 кейса, негативный сценарий)
* баг-репорты;
* отчет о тестировании.

В качестве тестовых данных использовались данные из [открытых источников](https://www.getcreditcardnumbers.com/)

### Шаги тестирования
В строке ниже в " "
```
// TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
        String number = "";
```
вводились следующие данные по очереди:

Сначала валидные данные:
```
1. VISA 4556014856219267 (валидный номер из 16 цифр)
2. VISA 4130026841438 (валидный номер из 13 цифр)
3. Mastercard 5184833456136200 (валидный номер из 16 цифр)
4. American Express 378431656912004 (валидный номер из 15 цифр)
```
Затем Невалидные данные:
```
4. пустая строка ""
5. 1234123412341234 (16 цифр)
6. 5184833456136201 (В валидном номере изменил последнюю цифру с 0 на 1)
```
после каждого ввода выполнялся запук програмы и фиксируется возвращаемые результаты.

### Итоги

Предоставленный код Java-приложения CCNV прошел Smoke-test при описанных условиях. Однако выявлено, что приложение годится только для валидации номеров карт с 16-ти значным номером.

Тестирование производилось в следующем окружении:

* <версия и разрядность ОС> Windows 8.1 x64
* <версия Java> openjdk version "11.0.6" 2020-01-14
* OpenJDK Runtime Environment AdoptOpenJDK (build 11.0.6+10)
* OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11.0.6+10, mixed mode)
* git version 2.25.1.windows.1