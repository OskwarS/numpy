
# 📘 Najważniejsze funkcje NumPy w Pythonie

**NumPy** (Numerical Python) to biblioteka do wydajnych obliczeń numerycznych na tablicach. Poniżej znajdziesz zestawienie najważniejszych funkcji i zastosowań.

---

## ✅ Podstawy

### 📥 Import
```python
import numpy as np
```

---

## 📌 Tworzenie tablic

### 🔧 Zwykłe tablice
```python
a = np.array([1, 2, 3])         # 1D
b = np.array([[1, 2], [3, 4]])  # 2D
```

### 🔧 Tablice specjalne
```python
np.zeros((2, 3))     # macierz 2x3 z zerami
np.ones((3, 3))      # macierz 3x3 z jedynkami
np.eye(3)            # macierz jednostkowa
np.full((2, 2), 7)   # wypełniona wartością 7
np.arange(0, 10, 2)  # [0 2 4 6 8]
np.linspace(0, 1, 5) # 5 wartości od 0 do 1
```

---

## 🔍 Właściwości tablic

```python
a.shape     # kształt (np. (2, 3))
a.ndim      # liczba wymiarów
a.size      # liczba elementów
a.dtype     # typ danych (np. int32, float64)
```

---

## ➕ Operacje matematyczne

```python
a + b       # dodawanie
a - b       # odejmowanie
a * b       # mnożenie (element po elemencie)
a / b       # dzielenie

np.dot(a, b)       # iloczyn macierzy
np.sum(a)          # suma
np.mean(a)         # średnia
np.std(a)          # odchylenie standardowe
np.max(a), np.min(a)  # maksimum i minimum
```

---

## 🎯 Indeksowanie i wycinanie

```python
a[0, 1]     # element z 1. wiersza, 2. kolumny
a[:, 1]     # cała druga kolumna
a[1, :]     # cały drugi wiersz
```

---

## 🔄 Zmiana kształtu

```python
a.reshape((3, 2))   # zmiana kształtu na 3x2
a.flatten()         # spłaszczenie do 1D
a.T                 # transpozycja (macierz obracana)
```

---

## 🎭 Maski i filtrowanie

```python
a = np.array([1, 2, 3, 4, 5])
a[a > 3]  # wynik: [4, 5]
```

---

## 🎲 Losowość z `np.random`

```python
np.random.rand(2, 3)        # losowe z [0, 1)
np.random.randn(2, 3)       # z rozkładu normalnego
np.random.randint(0, 10, (2, 2))  # całkowite liczby z zakresu
```

---

## 🔗 Łączenie i dzielenie tablic

```python
np.concatenate([a, b])     # łączenie 1D
np.vstack([a, b])          # łączenie pionowe
np.hstack([a, b])          # łączenie poziome
np.split(a, 2)             # dzielenie na części
```

---

## 📈 Gdzie używać NumPy?

- Analiza danych (Pandas, SciPy)
- Uczenie maszynowe (scikit-learn, TensorFlow)
- Obliczenia naukowe
- Algebra liniowa, statystyka
- Grafika i przetwarzanie obrazu

---


