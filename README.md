# miptAI-credit-scoring

Моё решение задачи <<Оценка кредитного риска на основе транзакционной активности>>, предложенной на форуме МФТИ по математике и ИИ летом 2022 года.

# Описание задачи

Датасет представляет из себя последовательность платежей по картам, совершенных в разных кассовых аппаратах у различных субъектов малого предпринимательства. В отдельный датасет будут вынесены отметки о целевом событии (дефолт). Для удобства транзакции агрегированы в пулы по несколько штук.

**Транзакции**

* `Transaction_id` --- Порядковый номер пула транзакций
* `Amount` --- Суммарный чек транзакций в пуле
* `Count` --- Количество транзакций в пуле
* `Std` --- Стандартное отклонение чека в пуле
* `ID_level_1` --- ID клиента
* `ID_level_2` --- ID кассового аппарата

**Таблица с целевыми значениями**

* `ID_level_1` --- ID клиента
* `Default_in_1y_flag`--- Дефолт в течение года (флаг)

Данные разбиты на обучающую и тестовую выборки. Нужно для тестовой выборки для каждого клиента определить вероятность наступления целевого события.

Метрика: `Gini_coefficient=2⋅ROC_AUC−1`
