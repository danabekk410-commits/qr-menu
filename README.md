# QR-меню для кафе и ресторанов

Электронное меню, которое гость открывает с телефона по QR-коду на столе:
фото блюд, поиск, фильтры, корзина и экран «Показать официанту». Без приложения,
без регистрации; при смене цен ничего не нужно перепечатывать.

В репозитории два демо на вымышленных заведениях:

- `restaurant/` — **Alma Kitchen**, ресторан казахской и европейской кухни;
- `coffee/` — **Honey Coffee**, кофейня.

Цены вымышленные, фото блюд сгенерированы нейросетью.

## Что умеет

- Три языка интерфейса: RU / KZ / EN.
- Категории с липкой навигацией, поиск по названию и описанию, фильтры по меткам
  («острое», «без мяса», «хит»), вид «плитка / список».
- Карточка блюда шторкой: описание, вес, состав и аллергены, варианты, количество.
- «Мой заказ»: итог с обслуживанием 10%, экран «Показать официанту» крупным шрифтом.
- Кнопки «Официант», «Счёт», копирование пароля Wi-Fi.
- Номер стола из ссылки: `?table=12` (QR-код на каждом столе свой).
- Баннер акции («счастливые часы»).
- Корзина сохраняется в localStorage и проверяется при загрузке.

В демо заказ и вызов официанта на кухню не уходят — показывается подсказка.
В рабочей версии заказ приходит официанту в Telegram.

## Стек

Один статический `index.html` на заведение: HTML, CSS, чистый JavaScript,
данные меню — массив в коде. Без сборки и зависимостей, хостинг — любой
статический (nginx, GitHub Pages).

## Как запустить

```bash
python3 -m http.server 8000
# http://localhost:8000/restaurant/?table=7
```

Чтобы адаптировать под своё заведение: поменять название, массив блюд, фото в
`img/` и номер WhatsApp в константе `WA` (сейчас там заглушка `77000000000`).

## Скриншоты

<!-- TODO: главный экран, карточка блюда, корзина, экран «Показать официанту» (390 px) -->

## Живое демо

- Ресторан: https://densites.ru/qr-menu/
- Кофейня: https://densites.ru/qr-menu-coffee/

---

## English summary

A mobile QR-code menu for cafes and restaurants: guests scan the code on the
table and get a trilingual (RU/KZ/EN) menu with photos, search, tag filters,
dish details, a cart with 10% service charge and a large "show to the waiter"
screen, plus waiter-call, bill and Wi-Fi buttons. Two demos for fictional venues
(a restaurant and a coffee shop). Plain static HTML/CSS/JS, no build step.
Live demos: https://densites.ru/qr-menu/ and https://densites.ru/qr-menu-coffee/.

## Лицензия

MIT — см. [LICENSE](LICENSE). Фото блюд в `img/` сгенерированы нейросетью.
