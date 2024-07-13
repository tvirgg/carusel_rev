# Документация для компонента Slider

## Описание

Компонент `Slider` представляет собой слайдер с прокруткой слайдов. Поддерживает отображение на десктопе и мобильных устройствах, с различным количеством видимых слайдов и анимациями. Центральный слайд выделяется визуально.

## Основные параметры

- **visibleSlidesCount**: Количество видимых слайдов на десктопе.
- **slidesLength**: Количество оригинальных слайдов.
- **totalSlides**: Общее количество слайдов, включая клоны, чтобы обеспечить бесшовную прокрутку.
- **centralSlideIndex**: Индекс центрального слайда для выделения.

## Состояния

- **currentIndex**: Текущий индекс слайда.
- **slideWidth**: Ширина слайда.
- **currentZone**: Текущая зона курсора для навигации.
- **isAnimating**: Флаг, указывающий на то, идет ли сейчас анимация.
- **isLoading**: Флаг для отображения состояния загрузки.
- **isMobile**: Флаг, определяющий, является ли устройство мобильным.

## Реактивные хуки

1. **useEffect**: Отслеживает изменение размера окна и определяет, является ли устройство мобильным.
2. **useLayoutEffect**: Устанавливает размеры слайдов в зависимости от ширины контейнера на десктопе.

## Методы

### nextSlide(times = 1, delay = 0)

Переходит к следующему слайду. Аргументы:

- `times`: Количество переходов.
- `delay`: Задержка между переходами.

### prevSlide(times = 1, delay = 0)

Переходит к предыдущему слайду. Аргументы:

- `times`: Количество переходов.
- `delay`: Задержка между переходами.

### handleSwipeStart(e)

Обрабатывает начало свайпа на мобильных устройствах.

### handleSwipeEnd(e)

Обрабатывает окончание свайпа на мобильных устройствах. Определяет направление свайпа и вызывает соответствующий метод перехода.

### getSlideStyle(index)

Возвращает стили для слайда в зависимости от его позиции. Центральный слайд выделяется визуально.

### getSlideClass(index)

Возвращает классы для слайда в зависимости от его позиции. Центральный слайд получает класс `center`.

### getSlideClassMobile(index)

Возвращает классы для слайда на мобильных устройствах.

### renderDots()

Отображает индикаторы (точки) для мобильной версии, показывающие текущий слайд.

## Компонент Slide

Компонент для отображения каждого слайда.

### Пропсы

- `slide`: Объект с данными слайда (категория, название, год, изображение, цена).
- `className`: Классы для слайда.
- `style`: Стили для слайда.
- `isCenter`: Флаг, указывающий, является ли слайд центральным.

### Структура

- `.slide-background`: Фоновое изображение слайда.
- `.slide-content`: Содержимое слайда (категория, название, год, цена).

## CSS

### Основные стили

- **.slider-container**: Контейнер для слайдера.
- **.slider-wrapper**: Обертка для слайдера.
- **.slider**: Основная область слайдов.
- **.nav**: Кнопки навигации.
- **.slide**: Стили для слайда.
- **.slide.center**: Стили для центрального слайда.
- **.slide-background**: Фоновое изображение слайда.
- **.slide-content**: Содержимое слайда.
- **.loading-screen**: Экран загрузки.
- **.slide-dots**: Контейнер для индикаторов.
- **.dot**: Индикатор слайда.

### Адаптивные стили

Для мобильных устройств используются медиа-запросы для настройки ширины, высоты и стилей слайдов. Центральный слайд на мобильных устройствах также получает дополнительный стиль `opacity: 1`.
