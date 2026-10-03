# AutoStack

**Калибровка и сложение астрофотографий в одну кнопку — поверх PixInsight WBPP.**
*One-button calibration and stacking of astrophotos on top of PixInsight WBPP.* — [English below](#english)

![AutoStack](screenshot.png)

## Скачать

**[⬇ Последняя версия — Releases](../../releases/latest)** → `AutoStack-<версия>-win64.zip`, распаковать, запустить `AutoStack.exe`.

Windows может предупредить «Windows защитила компьютер» → «Подробнее» → «Выполнить в любом случае» (у программы нет платной подписи кода).

## Зачем

WBPP в PixInsight часто выбрасывает часть лайтов: мало звёзд, низкий SNR, неподходящие дарки, отсечка по весу — а подбирать настройки вручную долго. AutoStack делает это сам. Цель — сложить **все ваши лайты, по возможности 100%**, и объяснить по каждому кадру, который не вошёл, почему и что с этим делать.

Внутри работает обычный, неизменённый WBPP — AutoStack только управляет им и проверяет результат.

## Что умеет

- **Подбирает калибровку**: дарки (и флэты, биасы) по gain, offset, температуре и выдержке, а не только по выдержке, как WBPP. Ловит дарки от другой камеры или с другим gain и объясняет, почему они не подходят.
- **Сам подбирает настройки регистрации** для каждого фильтра — от стандартных до самых чувствительных, включая поля с очень малым числом звёзд (например, галактика в Hα) — и **проверяет точность совмещения по звёздам**.
- **Сам выбирает опорный кадр**, с которым совмещается больше всего кадров во всех фильтрах.
- **«Отбор кадров»**: шкала от «только лучшие» до «все кадры» и режим **«Авто»**, который для каждого фильтра выбирает, при каком отборе мастер будет самым детальным.
- Моно и цветные (OSC) камеры. Все мастера выровнены друг на друга — готовы к LRGB/SHO.
- **Подробный отчёт** (HTML с превью): что вошло, что нет, почему и что делать.
- Интерфейс на **русском и английском**.
- По желанию — **проверка результата Claude** (если установлен Claude Code; только чтение).

## Что нужно

- Windows
- PixInsight 1.9 с WBPP 3.x
- по желанию: Claude Code

## Поддержать автора

Программа бесплатная. Если она вам помогла — **[♥ поддержать автора через PayPal](https://www.paypal.com/donate/?business=shanvit1201%40gmail.com&no_recurring=0&item_name=AutoStack)** (та же кнопка есть в окне программы).

## Лицензия

Бесплатно для использования; можно передавать неизменённые копии официальных релизов. Изменять, декомпилировать и распространять изменённые версии нельзя — см. [LICENSE](LICENSE). Исходный код закрыт.

PixInsight и WBPP — продукты Pleiades Astrophoto S.L., в AutoStack не входят и используются без изменений.

---

<a name="english"></a>
## English

**AutoStack** calibrates and stacks your light frames in PixInsight automatically. WBPP often drops frames (few stars, low SNR, unsuitable darks, the weight cut-off) and finding settings by hand is slow; AutoStack's goal is to stack **all your lights, 100% where possible**, and to explain for every frame that didn't make it why and what to do.

**[⬇ Download the latest release](../../releases/latest)** → unzip → run `AutoStack.exe` (Windows may show “Windows protected your PC” → “More info” → “Run anyway”).

- matches darks/flats on gain, offset, temperature and exposure (catches darks from another camera)
- finds registration settings per filter, down to very star-poor fields, and verifies accuracy with stars
- picks the reference frame most frames register to
- **Frame selection**: slider from “best only” to “all frames”, plus **Auto** that picks the most detailed master per filter
- mono and colour (OSC) cameras; all masters aligned to each other
- detailed HTML report; Russian and English interface; optional read-only review by Claude Code

Requires Windows and PixInsight 1.9 with WBPP 3.x. Free to use; **[♥ support the author via PayPal](https://www.paypal.com/donate/?business=shanvit1201%40gmail.com&no_recurring=0&item_name=AutoStack)**. Closed source; see [LICENSE](LICENSE). PixInsight and WBPP are products of Pleiades Astrophoto S.L.
