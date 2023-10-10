# geoguide

Представьте мобильное приложение, которое расскажет вам о местности, где вы находитесь.

Это не только гид по интересным местам, достопримечательностям и истории всего, 
что вы видите или не видите вокруг себя, но и помощник, 
который подскажет как найти поблизости нужный магазин, товар, услугу или уютное кафе, чтобы передохнуть.

При этом вам не обязательно смотреть на экран, можно ехать за рулём, на велосипеде или бежать.
Гид может сам время от времени рассказывать что-то интересное вам в контексте локации. 
Свои интересы можно корректировать для него в настройках глобально или голосом здесь и сейчас, например: 

- "Нам нужно купить зубную щётку"
- "Не мешало бы уже и перекусить"
- "Давай съедим шаверму с видом на город"

Такие запросы можно делать, если у вас есть интернет, но ключевые слова и типовые потребности гид поймёт и в оффлайн-режиме,
чтобы добавить в локальный круг интересов конкретные места по пути на маршруте или в окрестностях.

---

Гид учитывает ваши предпочтения, маршрут, любимый транспорт, доступное время, график работы интересных вам мест, время в пути, погоду и степень вашего любопытсва.

Вы всегда будете в курсе локальных новостей, актуальных премьер и мероприятий, новых локаций, 
а также мест, о которых вы скорее всего не слышали, но которые вам могли бы быть интересными.

- "Гуляю в направлении Парка Горького, расскажи что тут есть интересного, и нужно кофе."
- "Еду в Тверь, запас по времени 2 часа, давай устроим перекус на природе. Еда с собой"

---

# Модель данных

## Гео-объекты
- Топонимы
  - Населенные пункты
  - Реки, каналы
  - Озёра, водохранилища, пруды
  - Побережья
  - Урочища
  - Горы
  - Улицы городов
  - Микрорайоны, локальные названия участков местности
  - Водопады
  - Балки, ущелья
  - Именованные дороги, тракты, тропы, маршруты
  - Парки
- POI
  - Источники воды
  - Памятники
  - Видовые точки, смотровые площадки
  - Исторические здания, заводы, организации, учреждения
  - Магазины
  - Остановки общественного транспорта
  - Стоянки
  - Отели и хостелы
  - Кемпинги
  - Места для пикника, беседки
  - Скамейки
  - Бары, кафе, рестораны, общепит
  - Туалеты
  - Заправки
  - СТО
  - ТЦ
  - Поместья, замки, дворцы и т.д.
- Узлы-ориентиры
  - Пересечения улиц
  - Выезды из населенных пунктов в направлении на другие крупные пункты
  - Привязки к социально значимым заметным объектам, по которым можно ориентироваться
    - рынки, поликлиники, банки, ТЦ, крупные организации, социально значимые учреждения, школы, детсады, телевышки, высотки
    - границы крупных населенных пунктов 
    - границы крупных урочищ (например леса)
    - точки открывающегося обзора на заметные урочища (горы, водоёмы, леса, ущелья, долины, населенные пункты, изолированые микрорайоны, заливы, мысы)
    - точки открывающегося обзора на заметные объекты (заводы, карьеры, трубы ТЭЦ, телевышки, радиомачты, небоскрёбы, памятники)

## Гео-карточка

Короткая информационная справка, привязанная к гео-объекту или любой гео-точке.
Может быть в составе нескольких цепочек или деревев других связанных одной темой карточек.
Снабжена набором тегов.
Опционально имеет:
- аудиальное представление, возможно в нескольких вариантах для разнообразия (перефразированные, разными голосами, разный сленг) 
- одно или несколько фото
- пиктограмма (по умолчанию на основе тегов)
- длительность восприятия
- коэффициент внимания

## Гео-триггер

Точка на карте с неким радиусом и вектором направления, участок дороги, полигон или мультиполигон, который локализует актуальность:
  - Конкретных гео-карточек (и их цепочек?)
  - Тегов (такой триггер позволяет актуализировать выборку релевантных карточек, привязанных к гео-обьектам или гео-точкам с учетом черно-белой фильтрации по набору тегов).
Триггер может учитывать направление внимания, направление движения по дороге, тропе или маршруту.

