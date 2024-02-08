# README

## Практическое занятие №30

### Тема:

Репозитарий содержит материалы по практическому занятию №30, посвященному ознакомлению с хуком useEffect.

1. Вспоминаем useState. В компоненте `App`, над списком гномов, добавляем кнопку "Hide/Show dwarwes". При нажатии на нее нам нужно скрывать список гномов если он показан, и показывать - если скрыт.
2. Теперь разбираемся со связью жизненного цикла компонента и хуком `useEffect`. Работаем с компонентом `SimpleList`. Нужно, чтобы при ПЕРВОМ рендере нашего компонента, выводилось сообщение в консоль 'Dwarwes arrived!'.
3. Теперь сделаем так, чтобы при размонтировании (удалении из DOM) нашего компонента, в консоль отображалось сообщение 'Dwarwes departured!'.
4. Гномам нужно попасть к Одинокой горе точно в День Дурина. Нужны точные часы. Дорабатываем компонент `App`. Мы хотим, чтобы в нем отображались текущие время и дата с точностью до секунды. Нам нужно в компоненте `App`, добавить параграф, в котором будет отображаться время и дата. При этом, это должно обновляться каждую секунду.

Подсказка: здесь нам пригодится `setInterval`. То есть, нам нужно при монтировании компонента `App`, запустить interval, который будет каждую секунду обновлять время.
5. Усложняем работу с эффектами - работаем с массивом зависимостей. В компоненте `SimpleList`, нам нужно при КАЖДОМ изменении пропса `listSource` выводить в консоль сообщение "List source is changed".
6. Теперь поработаем с `localStorage`. В компонент `App` надо добавить кнопку, при нажатии на которую мы сохраним в localStorage данные о списке гномов. Используем ключ `dwarwes`.
7. Пора научиться извлекать данные о списке гномов из ЛС. Нужно при монтировании компонента `App`, проверять, нет ли у нас в ЛС значения по ключу `dwarwes`. Если есть - надо их оттуда доставать, и добавлять в локальный стейт (чтобы они рендерились).
8. Объединим все вместе, и сделаем так, чтобы данные о гномах сохранялись в ЛС автоматически, при изменении списка гномов. То есть, нам нужно сохранять эти данные в ЛС везде, где мы изменяем список гномов. Рекомендуется сохранение в ЛС вынести в отдельную функцию.
9. Теперь пришла пора поработать с бэком. Гномы будут идти через эльфийские земли - и туда можно отнести товары на продажу. В лесах дефицит электроники, поэтому гномы возьмут такие товары. Нужно при монтировании компонента `App` отправлять запрос списка товаров по адресу `https://dummyjson.com/products`. Результат (массив товаров) нужно будет сохранить в локальном стейте компонента, и вывести его в консоль.
10. Добавляем иконку загрузки. Нужно перед отправкой запроса показать параграф с текстом "Загружаем товары для эльфов...". А когда список товаров будет загружен - этот параграф убрать.

### Полезные ссылки по занятию:
 - [React useEffect](https://react.dev/reference/react/useEffect#updating-state-based-on-previous-state-from-an-effect) - толковая официальная документация по `useEffect`. С интерактивными примерами, поэтому настоятельно рекомендуется к просмотру. Кое-что там можно проигнорировать (например использование анимации), но в целом дает представление о том, зачем это.
 - [React useEffect](https://ru.legacy.reactjs.org/docs/hooks-effect.html) - устаревшая, зато русскоязычная документация. Она все еще актуальна, логика работы хука никак не изменилась, так что можно рассмотреть.