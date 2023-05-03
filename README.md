# Карта объектов культурного наследия в Великом Новгороде
## Состав команды
Антон Березанский  
Арина Деева  
Арина Демиденко  
Оля Попова

## Источники данных
Команда работала над картографированным перечнем объектов культурного наследия в городе Великий Новгород Новгородской области.
В рамках работы были использованы [открытые данные Министерства культуры Российской Федерации](https://opendata.mkrf.ru/opendata/7705851331-egrkn/), [данные OpenStreetMap](https://www.openstreetmap.org/relation/2417529), данные об объектах исторического наследия ([например](https://gpvn.ru/34374/vn08209)), а также фотографии и панорамы [сервиса Яндекс.Карты](https://yandex.ru/maps/24/veliky-novgorod/?ll=31.275132%2C58.520913&z=17.97).


## Краткая справка о городе
Великий Новгород расположен на северо-западе России, является столицей Новгородской области и одним из древнейших городов России (первое упоминание — 859 год).  
Сочетание подобных факторов привело к существованию большого числа объектов культурного наследия в городе.  
Население городского округа Великий Новгород составляет 224286 человек (по данным ВПН-2020).

## Работа над проектом
### Методы
К основным методам, использованным в проекте, можно отнести геокодирование, пространственная обработка, генерализация. Проект выполнен с использованием геоинформационной системы QGIS, а также языка программирования Python с использованием библиотек pandas, geopandas и folium. Для облегчения командной работы был использован сервис Google Collab и, как следствие, библиотека google.colab

### Сложности при разработке
Одной из наиболее сложных частей работы являлось сопоставление объектов из перечня ОКН Минкульта РФ и реальных зданий. Например, в реестре указаны не только отдельные здания, но и их части. Координаты многих ОКН, которые были в составе какого-либо архитектурного комплекса (например, Кремля или бывшего монастыря) были одинаковыми, поэтому потребовалось вручную размещать точки ОКН на нужных полигонах зданий или наоборот вне их, если здание утрачено (т.е. ОКН считаются его остатки)  
Чтобы получить корректные полигоны зданий-ОКН некоторые из них пришлось делить на 2–3 части (например, если есть ОКН-стена и ОКН-башня, а в OSM здание представлено как единый полигон). Например, объекты культурного наследия «Дом Марфы Посадницы» и «Остатки жилого дома во дворе Большой Московской 32/12», фактически, представляют из себя один и тот же объект. 

### Итог работы
В итоге был сформирован очищенный реестр объектов культурного наследия с актуальной геопривязкой. На основе данных из этого реестра была разработана web-картосхема с разделением по уровням генерализации, возможностью просмотра на карте-врезке, просмотра информации об объекте, а также с возможностью поиска по реестру. От прочих подобных реестров наш отличается сочетанием различных типов геометрии объектов и точностью информации.
