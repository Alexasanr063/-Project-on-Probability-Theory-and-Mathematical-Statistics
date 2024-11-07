# -Project-on-Probability-Theory-and-Mathematical-Statistics
README для проекта по дисперсионному анализу роста спортсменов
Описание проекта
Этот проект посвящен проведению дисперсионного анализа для определения различий в среднем росте среди трех групп спортсменов: футболистов, хоккеистов и штангистов. Данные включают значения роста случайно выбранных спортсменов из каждой группы. Цель анализа — выяснить, существуют ли статистически значимые различия в росте между этими группами.

Данные
Футболисты: 173, 175, 180, 178, 177, 185, 183, 182
Хоккеисты: 177, 179, 180, 188, 177, 172, 171, 184, 180
Штангисты: 172, 173, 169, 177, 166, 180, 178, 177, 172, 166, 170
Используемые технологии
Python
SciPy
Инструкция по запуску приложения
Для того чтобы запустить проект и выполнить дисперсионный анализ, выполните следующие шаги:

Установите необходимые библиотеки:
Убедитесь, что у вас установлен Python и библиотека SciPy. Установите её с помощью pip:
pip install scipy
Запустите скрипт:
Сохраните код, представленный ниже, в файл с расширением .py, например anova_analysis.py, и выполните его:
python anova_analysis.py
from scipy.stats import f_oneway
# Данные о росте спортсменов
futbolisty = [173, 175, 180, 178, 177, 185, 183, 182]
hokkeisty = [177, 179, 180, 188, 177, 172, 171, 184, 180]
shtangisty = [172, 173, 169, 177, 166, 180, 178, 177, 172, 166, 170]
# Проведение дисперсионного анализа
anova_result = f_oneway(futbolisty, hokkeisty, shtangisty)
# Вывод результатов
print(f"Статистика F: {anova_result.statistic}")
print(f"p-значение: {anova_result.pvalue}")
# Проверка гипотезы
alpha = 0.05
if anova_result.pvalue < alpha:
    print("Принимается альтернативная гипотеза: различия в среднем росте существуют.")
else:
    print("Не хватает доказательств для принятия альтернативной гипотезы: различий в среднем росте нет.")
Заключение
В результате дисперсионного анализа было получено значение статистики F и p-значение. Если p-значение меньше уровня значимости (0.05), то принимается альтернативная гипотеза о наличии различий в среднем росте между группами спортсменов. В данном случае, p-значение составляет 0.010, что меньше 0.05, следовательно, принимается альтернативная гипотеза: различия в среднем росте между футболистами, хоккеистами и штангистами действительно существуют.
