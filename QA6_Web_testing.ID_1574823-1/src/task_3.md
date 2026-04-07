## Выбранные элементы интерфейса для анализа

На основе анализа сайта https://21-school.ru/ были выбраны следующие 5 ключевых элементов интерфейса:

1. **Блок "Помогаем раскрыть потенциал..."** - текстовая строка с описанием.
2. **Блок "Программа обучения"** - стрелки навигации (< >).
3. **Блок "Отзывы выпускников"** - карточки отзывов.
4. **Блок с картой** - интерактивная карта.
5. **Блок "Этапы поступления"** - карточки этапов.

## Отчет о тестировании в браузерах

Тестирование проводилось в браузерах: Google Chrome, Mozilla Firefox, Microsoft Edge.

| Проверяемый элемент | Конкретное отличие (Что различается и в каких браузерах) | Предполагаемая техническая причина отличия | Номер/название скриншотов |
|----------------------|----------------------------------------------------------|---------------------------------------------|--------------------------|
| Блок "Где помогаем раскрыть потенциал" | В Firefox в строку влезает больше слов, чем в Chrome и Edge. | Различия в рендеринге шрифтов и ширины контейнера из-за разных движков (Gecko vs Blink). | screenshot1_firefox.png, screenshot1_chrome.png, screenshot1_edge.png |
| Блок "Программа обучения" | В Firefox стрелки < > чуть сдвинуты правее, в отличие от Chrome и Edge. | Различия в CSS-позиционировании или box-model (margin/padding) между браузерами. | screenshot2_firefox.png, screenshot2_chrome.png, screenshot2_edge.png |
| Блок "Отзывы выпускников" | В Edge карточки расположены более компактно, в отличие от Chrome и Firefox. | Различия в интерпретации flexbox или grid-layout в Edge (Chakra vs Blink/Gecko). | screenshot3_edge.png, screenshot3_chrome.png, screenshot3_firefox.png |
| Блок с картой | В Chrome карта не загрузилась, в Firefox и Edge все в порядке. | Проблемы с JavaScript или API карты в Chromium, возможно, блокировка или ошибка загрузки скрипта. | screenshot4_chrome.png, screenshot4_firefox.png, screenshot4_edge.png |
| Блок "Этапы поступления" | В Firefox другое расстояние между карточками-этапами, в отличие от Chrome и Edge. | Различия в CSS-свойствах gap или margin в flexbox/grid. | screenshot5_firefox.png, screenshot5_chrome.png, screenshot5_edge.png |

## Рекомендации разработчикам по обеспечению кроссбраузерной совместимости

1. **Использовать CSS-префиксы и полифилы:** Для свойств, которые по-разному интерпретируются (например, flexbox), добавлять вендорные префиксы (-webkit-, -moz-) и тестировать на всех браузерах.
2. **Тестировать на реальных устройствах и браузерах:** Регулярно проводить кроссбраузерное тестирование с помощью инструментов вроде BrowserStack или Selenium, чтобы выявлять различия на ранних этапах.
3. **Оптимизировать загрузку ресурсов:** Для элементов вроде карт проверять совместимость API и скриптов с разными браузерами, использовать fallback для случаев, когда карта не загружается.
4. **Стандартизировать CSS и JS:** Избегать зависимостей от специфических особенностей браузеров, использовать современные стандарты (CSS Grid, Flexbox) с проверкой на совместимость.

## Прикрепленные скриншоты

- screenshot1_firefox.png: <br>![fs1](misc/images/fs1.png)<br>
- screenshot1_chrome.png: <br>![gs1](misc/images/gs1.png)<br>
- screenshot1_edge.png: <br>![es1](misc/images/es1.png)<br>
- screenshot2_firefox.png: <br>![fs2](misc/images/fs2.png)<br>
- screenshot2_chrome.png: <br>![gs2](misc/images/gs2.png)<br>
- screenshot2_edge.png: <br>![es2](misc/images/es2.png)<br>
- screenshot3_edge.png: <br>![es3](misc/images/es3.png)<br>
- screenshot3_chrome.png: <br>![gs3](misc/images/gs3.png)<br>
- screenshot3_firefox.png: <br>![fs3](misc/images/fs3.png)<br>
- screenshot4_chrome.png: <br>![gs4](misc/images/gs4.png)<br>
- screenshot4_firefox.png: <br>![fs4](misc/images/fs4.png)<br>
- screenshot4_edge.png: <br>![es4](misc/images/es4.png)<br>
- screenshot5_firefox.png:<br>![fs5](misc/images/fs5.png)<br>
- screenshot5_chrome.png: <br>![gs5](misc/images/gs5.png)<br>
- screenshot5_edge.png: <br>![es5](misc/images/es5.png)<br>