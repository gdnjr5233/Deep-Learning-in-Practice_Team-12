# Требования к данным для детекции

Чтобы обеспечить эффективное и точное обучение, требуется соблюдать определенные требования к данным.

### 1. Размеченные данные:
Изображения знаков (через лобовое стекло автомобиля), на которых указаны соответствующие правила дорожного движения (классы `speed limit`, `pedestrian crossing`, `no right turn`), должны быть размечены. Это означает, что каждый объект классов на изображении должен быть выделен прямоугольником (bounding box), и этот bounding box должен быть ассоциирован с классом объекта.

### 2. Формат изображений: 
Изображения должны быть в формате png/jpg и размером не менее 480х480.

### 3. Формат координат bounding box:
Координаты bounding box должны быть в формате YOLO.

### 4. Аннотации к изображениям:
Для каждого изображения должен быть подготовлен одноименный txt-файл с аннотациями к объектам, которые находятся на изображении. Аннотации для каждого объекта записываются с новой строки в формате:
`<object-class> <x-center> <y-center> <width> <height>`

### 5. Структура данных:
Изображения и аннотации к ним должны быть структурированный следующим образом:
```
├── dataset
│ │ ├── train
│ │ │ ├── images
│ │ │ ├── labels
│ │ ├── val
│ │ │ ├── images
│ │ │ ├── labels
```

### 6. yaml-файл:
Для каждого набора данных должен быть подготовлен yaml-файд в формате:
```
train: train/images
val: val/images
nc: 3
names: ['speed limit', `pedestrian crossing`, `no right turn`]
```

### 7. Разнообразие сценариев:
Набор данных должен включать изображения с разнообразными сценариями: разные знаки, разное освещение, разные положения знаков относительно дороги, а также различные погодные условия и совокупность нескольких знаков.

### 8. Разнообразие объектов:
Объекты на изображениях должны разнообразными и находится на разных расстояниях, чтобы модель обучалась распознавать в разных контекстах.

### 9. Достаточное количество данных:
Чтобы обучить эффективную модель, требуется большой набор данных. Рекомендуется иметь не менее нескольких тысяч изображений с маркировками пешеходов.

### 10. Отсутствие повторений:
Изображения с повторяющимися сценами или одними и теми же объектами могут привести к переобучению. Старайтесь избегать дублирования данных.

### 11. Разрешение изображений:
Используйте высококачественные изображения с разрешением, достаточным для четкой видимости знаков.

### 12. Вариация освещения:
Изображения должны включать вариации освещения, чтобы обучить модель адаптироваться к разным условиям освещения.

### 13. Реальные данные:
Постарайтесь использовать реальные изображения знаков, чтобы обученная модель была применима к реальным ситуациям.

### 14. Полные сцены:
Изображения должны содержать полные сцены со знаками, чтобы модель могла корректно обучиться на их обнаружении.