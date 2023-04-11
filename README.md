# RobotCommandAugmentation
Студенческий проект по аугментации и искуственной генерации команд (и возможно других предложений).
Нужно для более продвинутой искуственной генерации обучающих примеров для парсера команд.

Подготовка:
- [ ] Организовать репозиторий по шаблону cookiecutter https://drivendata.github.io/cookiecutter-data-science/
- [ ] Завести гуглдок для лит обзора, приложить сюда ссылку с доступом для чтения или комментирования.
- [ ] завести гуглтаблицу для сбора результатов экспериментов
- [ ] Ознакомиться с примерами команд из https://github.com/gilmoright/CommandClassifier (файлы CommandClassifier/Data/Raw/NERannontated_fixed_oldcrowd.jsonl, CommandClassifier/Data/Raw/NERannontated_crowd_2.jsonl, CommandClassifier/Data/Raw/data_v6.zip, CommandClassifier/Data/Interim/labels_names.json и документом с описанием команд.

Задачи:
- [ ] Провести литературный обзор. Нужны именно научные статьи, не хабр. Для поиска советую GoogleScholar или PapersWithCode. В обзор рекомендую включить : 
  -- [ ] Работы по аугментации данных в NLP. Какие методы применяют для этого. Какие-нибудь замены синонимами, генеративные модели, перестановки.
  -- [ ] Управляемя генерация текстовых данных с помощью генеративных моделей T5, GPT, и прочих
  -- [ ] Работы по распознаванию и парсингу команд.
  -- [ ] наши работы, которые уже опубликованы по обработке команд роботом.
  -- [ ] Какие есть методы оценки семантической близости предложений и лексического разнообразия. 
- [ ] разобраться с репозиторием https://github.com/sag111/RobotCommandAugmentation/ Изучить примеры команд, которые там есть (обратить внимание на файлы CommandClassifier/Data/Raw/NERannontated_fixed_oldcrowd.jsonl, CommandClassifier/Data/Raw/NERannontated_crowd_2.jsonl, CommandClassifier/Data/Raw/data_v6.zip, CommandClassifier/Data/Interim/labels_names.json)
- [ ] Запустить эксперимент  MyMultiTiny2_data6 (пример того, как запускать в файле train.sh). Разобраться, как запустить обучение и оценить результаты и с тем, как он вообще решает задачу. В файле Notebooks/Reports/Compare_percend_of_right_example.ipynb есть числа, которые должны получиться для этого эксперимента. После этого все эксперименты будут строится по принципу: сгенерировали новые команды, обучили на них, посмотрели точность.
- [ ] Запустить mT5 и GPT-2 на кластере не обучение и предикт, можно сначала на какую-то задачу, на которую я уже запускал (типа суммаризация).
- [ ] По результатам лит обзора предложить несколько способов аугментации команд. Варианты, которые пока есть в голове:
  -- [ ] Попробовать через mT5 или GPT-2. Попробовать подавать им классы команд, чтоб они генерировали список команд.
  -- [ ] Можно сделать какой-то ручной алгоритм с заменой синонимами и местоимениями. 
  -- [ ] Есть идея подавать в генеративную модель леммы и синтаксическую структуру, чтоб получать нормальное предложение со словоформами, но желаемой структурой. 
  -- [ ] Натренировать генеративную модель на корпусе перефраз, для того, чтобы меняла входную строку, но смысл оставался тем же.
- [ ] Расширить способ генерации до сложных команды с пропусками и кореференцией.
