
# 📷 OpenCV – Interaktywny podgląd kamery z suwakami

Ten projekt pokazuje, jak wykorzystać **OpenCV** w Pythonie do przetwarzania obrazu z kamery w czasie rzeczywistym za pomocą klas i suwaków (`cv2.createTrackbar`).

---

## 🧱 Struktura projektu

Kod zawiera klasy dziedziczące po bazowej klasie `Viewer`, która zarządza:
- uruchamianiem kamery (`cv2.VideoCapture`)
- tworzeniem okna i suwaka (`cv2.namedWindow`, `cv2.createTrackbar`)
- przechwytywaniem klatek i ich przetwarzaniem

---

## 🔧 Klasa bazowa: `Viewer`

```python
class Viewer:
    def __init__(self, slider_name, current_value, end_value)
    def get_slider_value(self)
    def process_frame(self, frame, value)
    def run(self)
```

### 🔹 `run()` – główna pętla programu:
- Pobiera klatkę z kamery
- Odwraca obraz (flip)
- Przetwarza klatkę za pomocą `process_frame`
- Wyświetla obraz w oknie
- Kończy działanie po naciśnięciu `q`

---

## ✨ Klasy pochodne (dziedziczące po Viewer)

### 💡 `BrightnessViewer`

Reguluje jasność obrazu.

```python
def process_frame(self, frame, value):
    return cv2.add(frame, value)
```

---

### 🌫️ `GaussianViewer`

Nakłada filtr rozmycia Gaussa.

```python
def process_frame(self, frame, value):
    return cv2.GaussianBlur(frame, (value, value), 0)
```

---

### 🧊 `MedianViewer`

Nakłada filtr medianowy.

```python
def process_frame(self, frame, value):
    return cv2.medianBlur(frame, value)
```

---

### 🌈 `HSVViewer`

Modyfikuje barwę (Hue) obrazu w przestrzeni kolorów HSV.

```python
def process_frame(self, frame, value):
    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
    frame[:, :, 0] = (frame[:, :, 0] + value) % 180
    return cv2.cvtColor(frame, cv2.COLOR_HSV2BGR)
```

---

## 🧪 Dodatkowe funkcje

### `ex1()`

Wczytuje i wyświetla statyczny obraz.

```python
img = cv2.imread("grzybek.png")
cv2.imshow("okno", img)
cv2.waitKey(0)
```

### `ex2()`

Przetwarzanie wideo z suwakiem jasności bez klas.

---

## 🚀 Uruchamianie

W funkcji `main()` wybierz klasę, którą chcesz testować:

```python
viewer = HSVViewer()
viewer.run()
```

---

## 📦 Wymagania

- Python 3.x
- OpenCV: `pip install opencv-python`

---

## 🏁 Skróty klawiszowe

- `q` – zakończ działanie programu

---

> Projekt edukacyjny: interaktywne przetwarzanie obrazu z kamerki w czasie rzeczywistym z użyciem suwaków w OpenCV.
