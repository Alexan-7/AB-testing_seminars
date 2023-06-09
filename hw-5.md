# Урок 5. Применение математической статистики для проверки гипотез в реальной жизни для популярных метрик
## 1. Вы провели эксперимент c упрощением формы заказа в магазине «Утконос» и получили результаты по метрике конверсий в покупку. Выберите метод оценки и оцените есть ли стат. значимые различия между конверсиями в двух группах при alpha = 5%. Дайте краткие рекомендации команде.
## Результаты: 1) Число юзеров в группах, которые заходили на сайт в период эксперимента: n1 = 15550 и n2 = 15550. 2) Число юзеров в группах, которые совершили хотя бы одну покупку за период эксперимента: n1 = 164 и n2 = 228. 3) Конверсии: conv1 = 1.05% conv2 = 1.47%.
### _**Спойлер с похожей задачей в лекции https://gb.ru/lessons/328105 на 46:45 мин, слайд 35😊.**_
**Нулевая гипотеза** – Между конверсией в двух группах нет статистически значимых различий;

**Альтернативная гипотеза** – Между конверсией в двух группах есть статистически значимые различия.

| Группа | Посетители | Кликнувшие посетители | Конверсия |
|:-------|:----------:|:---------------------:|----------:|
| Тестовая группа | n1 = 15550 | 164 | conv1 = 1.05% |
| Контрольная группа | n2 = 15550 | 228 | conv2 = 1.47%|

Для α = 5%   z = 1.96. Что показывает 1.96? Это показывает в скольких стандартных ошибках (так называется стандартное отклонение для среднего выборочного) лежит среднее по выборке от истинного среднего.
Найдем доверительный интервал для групп:

![image](https://github.com/Alexan-7/AB-testing_seminars/assets/112006440/19b000a9-67bd-4248-9e2d-9c8cde606147)

Ноль не входит в интервал, поэтому на основе собранных данных принимаем альтернативную гипотезу о наличии статистически значимых различий между конверсией в двух группах. Все ОК, развиваемся в том же духе!
Калькулятор для А/В: https://www.evanmiller.org/ab-testing/sample-size.html
Калькулятор для А/В: https://www.statulator.com/SampleSize/ss2M.html

## 2. Сравниваем метрику «конверсия в покупку». Размер выборки - 10000 элементов в каждой группе. Какой статистический критерий тут лучше всего подойдёт и почему?
Работаем с количественными данными. Если мы имеем дело с суммами большого числа случайных величин, то можно использовать нормальный закон. Выборки независимые. Сравниваем 3 и более группы.
Согласно таблице ниже, такому случаю соответствует использование однофакторного дисперсионного анализа. 

![image](https://github.com/Alexan-7/AB-testing_seminars/assets/112006440/91f9c63b-9519-46c7-814e-b04eac51777d)
