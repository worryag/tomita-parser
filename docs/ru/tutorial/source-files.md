# Исходные файлы простого проекта

Для запуска Томита-парсера необходимо создать файлы, перечисленные в следующей таблице.

**Содержание** | **Формат** | **Примечания**
----- | ----- | -----
**config.proto** — конфигурационный файл парсера. Сообщает парсеру, где искать все остальные файлы, как их интерпретировать и что делать. | Protobuf | Нужен всегда.
**dic.gzt** — корневой словарь. Содержит перечень всех используемых в проекте словарей и грамматик. | Protobuf / Gazetteer | Нужен всегда.
**mygram.cxx** — грамматика | Язык описания грамматик | Нужен, если в проекте используются грамматики. Таких файлов может быть несколько.
**facttypes.proto** — описание типов фактов | Protobuf | Нужен, если в проекте порождаются факты. Парсер запустится без него, но фактов не будет.
**kwtypes.proto** — описания типов ключевых слов | Protobuf | Нужен, если в проекте создаются новые типы ключевых слов.


Таким образом, минимальный набор файлов для запуска парсера включает конфигурационный файл и корневой словарь (см. пример **minimal**). При этом не будут использоваться грамматики и пользовательские типы ключевых слов, а также не будут порождаться факты. Типовой сценарий использования парсера подразумевает наличие всех пяти типов файлов.

**Исходные файлы проектов-примеров в этом руководстве**

Название | **файл конфигурации** | **корневой словарь** | **грамматика** | типы фактов | **типы ключевых слов** | **тексты**
----- | ----- | ----- | ----- | ----- | ----- | -----
**minimal** | config.proto | mydic.gzt |  |  |  | 
**tutorial1** | config.proto | mydic.gzt | first.cxx |  |  | test.txt
**tutorial2** | config.proto | mydic.gzt | adjperson.cxx |  |  | test1.txt, test2.txt, test3.txt
**tutorial3** | config.proto | mydic.gzt | fioborn.cxx |  |  | test.txt
**tutorial4** | config.proto | mydic.gzt | date.cxx | facttypes.proto |  | test.txt
**tutorial5** | config.proto | mydic.gzt, animals_dict.gzt, mammals.txt | main.cxx, date.cxx | facttypes.proto | kwtypes.proto | test.txt

