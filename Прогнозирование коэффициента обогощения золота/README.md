# Проект. Предсказание коэффициента восстановления золота из золотосодержащей руды.

# Описание проекта

Необходимо подготовить прототип модели машинного обучения для «Цифры». Компания разрабатывает решения для эффективной работы промышленных предприятий.

Модель должна предсказать коэффициент восстановления золота из золотосодержащей руды. В вашем распоряжении данные с параметрами добычи и очистки.

Модель поможет оптимизировать производство, чтобы не запускать предприятие с убыточными характеристиками.

## Необходимо:

1. Подготовить данные;
2. Провести исследовательский анализ данных;
3. Построить и обучить модель.

### Нужно спрогнозировать сразу две величины:

1. эффективность обогащения чернового концентрата `rougher.output.recovery`
2. эффективность обогащения финального концентрата `final.output.recovery`

## Описание данных:

`floatbank` - флотационная установка  `ag, pb, sol, au` - Серебро, Свинц, Соль, Золото

Этап Флотации - Rougher
`rougher.input.feed_ag(pb, sol, au)` - концентрация исходного сырье ag, pb, sol, au
`rougher.input.feed_rate` - скорость подачи сырья
`rougher.input.feed_size` - размер гранул сырья
`rougher.input.floatbank_10_sulfate(xanthate)` - подача флотационных реагентов sulfate, xanthate
`rougher.output.concentrate_ag(pb, sol, au)` - концентрация на выходе ag, pb, sol, au
`rougher.output.tail_ag` - отвальные хвосты ag, pb, sol, au после флотации
`rougher.output.recovery` - Эффективность обогащения после флотации
`rougher.state.floatbank10_a_air(level)` - параметры объема воздуха и уровня жидкости, характеризующие текущее состояние этапа
`rougher.calculation` - расчётные характеристики

Этап Первичной очистки - Primary_cleaner
`primary_cleaner.input.sulfate(depressant, xanthate)` - подача реагентов sulfate, depressant, xanthate
`primary_cleaner.input.feed_size` - размер гранул сырья на входе
`primary_cleaner.output.concentrate_ag(pb, sol, au)` - концентрация на выходе ag, pb, sol, au
`primary_cleaner.output.tail_ag(pb, sol, au)` - отвальные хвосты ag, pb, sol, au после первичной очистки
`primary_cleaner.state.floatbank8_a_air(level)` - параметры объема воздуха и уровня жидкости, характеризующие текущее состояние этапа

Этап Вторичной очистки - Secondary_cleaner
`secondary_cleaner.output.tail_ag` - отвальные хвосты ag, pb, sol, au после вторичной очистки
`secondary_cleaner.state.floatbank2_a_air(level)` - параметры объема воздуха и уровня жидкости, характеризующие текущее состояние этапа

Финальный концентрат - Final
`final.output.recovery` - Эффективность обогащения финального концентрата
`final.output.concentrate_ag(pb, sol, au)` - финальный концентрат ag, pb, sol, au
`final.output.tail_ag(pb, sol, au)` - финальные отвальные хвосты ag, pb, sol, au
