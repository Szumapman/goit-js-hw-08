# Zadanie domowe #8 - JavaScript

> [!NOTE]
> Do stylizacji układu twoich zadań użyj [tego](https://www.figma.com/file/m8k9NQV7qZrtYDCvxfD68B/%D0%94%D0%97-JavaScript?type=design&node-id=3-941&mode=design) szablonu.

## Zadanie — Galeria obrazków

Utwórz galerię z możliwością kliknięcia w jej elementy i przeglądania obrazu w pełnym rozmiarze w oknie modalnym. Zobacz demonstracyjne wideo działania galerii.

Tworzenie galerii to złożone zadanie, które lepiej podzielić na kilka prostszych podzadań, wykonując każde z nich, zbliżasz się do końcowego celu. Ten proces nazywa się dekompozycją zadania.

### 1 - Układ galerii

Logiczne jest zacząć od stworzenia miejsca, do którego będziemy dodawać elementy galerii. W tym celu w kodzie HTML dodaj kontener galerii - nieuporządkowaną listę z klasą `gallery`.
```
<ul class="gallery"></ul>
```

### 2 - Tablica obrazów

Do stworzenia elementów galerii będziesz potrzebować danych. Dodaj ten tablicę obiektów do swojego pliku JavaScript. Każdy obiekt reprezentuje jeden element galerii.

* `preview` — link do małej wersji obrazu dla karty galerii
* `original` — link do dużej wersji obrazu dla okna modalnego
* `description` — opis tekstowy obrazu, dla atrybutu `alt` małego obrazu i podpisu dużego obrazu w oknie modalnym.

```
  const images = [
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/14/16/43/rchids-4202820__480.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/14/16/43/rchids-4202820_1280.jpg',
    description: 'Hokkaido Flower',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/14/22/05/container-4203677__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/14/22/05/container-4203677_1280.jpg',
    description: 'Container Haulage Freight',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/16/09/47/beach-4206785__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/16/09/47/beach-4206785_1280.jpg',
    description: 'Aerial Beach View',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2016/11/18/16/19/flowers-1835619__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2016/11/18/16/19/flowers-1835619_1280.jpg',
    description: 'Flower Blooms',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2018/09/13/10/36/mountains-3674334__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2018/09/13/10/36/mountains-3674334_1280.jpg',
    description: 'Alpine Mountains',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/16/23/04/landscape-4208571__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/16/23/04/landscape-4208571_1280.jpg',
    description: 'Mountain Lake Sailing',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/17/09/27/the-alps-4209272__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/17/09/27/the-alps-4209272_1280.jpg',
    description: 'Alpine Spring Meadows',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/16/21/10/landscape-4208255__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/16/21/10/landscape-4208255_1280.jpg',
    description: 'Nature Landscape',
  },
  {
    preview:
      'https://cdn.pixabay.com/photo/2019/05/17/04/35/lighthouse-4208843__340.jpg',
    original:
      'https://cdn.pixabay.com/photo/2019/05/17/04/35/lighthouse-4208843_1280.jpg',
    description: 'Lighthouse Coast Sea',
  },
];
```

### 3 - Układ elementów galerii

Masz już kontener, do którego można dodawać elementy galerii, i dane, za pomocą których je stworzyć. Teraz czas wypełnić galerię układem.

Użyj tablicy obiektów `images` i tego szablonu HTML elementu galerii, a następnie stwórz układ elementów w kodzie JavaScript, a następnie dodaj cały układ do `ul.gallery`. Nie dodawaj innych tagów HTML poza tymi, które są zawarte w tym szablonie.

```
<li class="gallery-item">
  <a class="gallery-link" href="large-image.jpg">
    <img
      class="gallery-image"
      src="small-image.jpg"
      data-source="large-image.jpg"
      alt="Image description"
    />
  </a>
</li>
```

* W atrybucie `src` tagu `<img>` podaj link do małej wersji obrazu.
* Dla atrybutu `alt` użyj opisu obrazu.
* Link do dużego obrazu powinien być przechowywany w atrybucie danych `source` na elemencie `<img>`, a adres powinien być podany w atrybucie `href`.
* Zwróć uwagę, że obraz jest opakowany w link, którego atrybut `href` wskazuje na ścieżkę do pliku z obrazem. Kliknięcie w ten link może spowodować pobranie obrazu na komputer użytkownika. Zablokuj to zachowanie domyślnie.

### 4 - Style

Dodaj stylizację galerii zgodnie z projektem.

### 5 - Delegacja

Nadszedł czas, aby dodać funkcjonalność nasłuchiwania kliknięć na elementach galerii i uzyskiwania linku do dużego obrazu po kliknięciu. Użyj techniki delegacji na `ul.gallery`. Na razie po kliknięciu na element galerii wyświetl adres do dużego obrazu w konsoli.

### 6 - Podłączenie biblioteki

Biblioteka [basicLightbox](https://github.com/electerious/basicLightbox/tree/master) zapewnia w pełni funkcjonalne okno modalne, które doskonale nadaje się do naszego zadania. Użyj serwisu [CDN jsdelivr](https://www.jsdelivr.com/package/npm/basiclightbox?path=dist) i dodaj w pliku HTML linki do zminifikowanych plików JS i CSS biblioteki.

### 7 - Okno modalne

Rozszerz swój kod tak, aby po kliknięciu na element galerii otwierało się okno modalne podłączonej biblioteki. Aby dowiedzieć się, jak zainicjować okno modalne w swoim kodzie i jak z niego korzystać, zapoznaj się z [dokumentacją](https://github.com/electerious/basicLightbox#readme) i [przykładami](https://basiclightbox.electerious.com/).

### 8 - Duży obraz

Wykorzystaj swój kod uzyskiwania linku do dużego obrazu, aby zmienić wartość atrybutu `src` elementu `<img>` w oknie modalnym przed otwarciem. Użyj gotowego układu okna modalnego z obrazem z przykładów biblioteki [basicLightbox](https://basiclightbox.electerious.com/).

### 9 - Zamknięcie za pomocą klawiatury

Dodaj funkcjonalność zamykania okna modalnego po naciśnięciu klawisza `Escape`. Upewnij się, że nasłuchiwanie klawiatury zachodzi tylko wtedy, gdy otwarte jest okno modalne. Biblioteka [basicLightbox](https://basiclightbox.electerious.com/) zawiera metodę do programowego zamykania okna modalnego.
