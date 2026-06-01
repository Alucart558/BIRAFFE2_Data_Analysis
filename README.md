# BIRAFFE2 Data Analysis

Analiza zależności pomiędzy reakcją fizjologiczną (EDA) a odczuwanymi emocjami (arousal) w ramach projektu BIRAFFE2.

## 📋 Opis Projektu

Projekt bada związek między:
- **Pobudzeniem emocjonalnym (Arousal)** - subiektywnym odczuciem nasilenia emocji na skali 1-9
- **Elektrodermalną aktywnością (EDA)** - obiektywnym pomiarem fizjologicznym (liczba peaków w sygnale EDA)

Badanie przeprowadzono na grupie **5 uczestników** przy użyciu urządzenia BITalino do rejestracji sygnałów fizjologicznych.

## 📁 Struktura Repozytorium

```
BIRAFFE2_Data_Analysis/
├── Analiza_BIRAFFE.ipynb    # Główny notebook z analizą
├── data/
│   ├── biosigs/             # Sygnały biologiczne (CSV)
│   │   ├── SUB103-BioSigs.csv
│   │   ├── SUB119-BioSigs.csv
│   │   ├── SUB120-BioSigs.csv
│   │   ├── SUB136-BioSigs.csv
│   │   └── SUB141-BioSigs.csv
│   └── procedure/           # Dane z procedury eksperymentalnej (CSV)
│       ├── SUB103-Procedure.csv
│       ├── SUB119-Procedure.csv
│       ├── SUB120-Procedure.csv
│       ├── SUB136-Procedure.csv
│       └── SUB141-Procedure.csv
└── README.md
```

## 🔬 Metodologia

### Zbiór Danych
- **Liczba uczestników:** 5 osób
- **Pobieranie próbek:** 1000 Hz (standard dla BITalino)
- **Format danych:** CSV

### Zmienne Analizowane
- **ANS_AROUSAL:** Subiektywne poczucie pobudzenia (skala 1-9)
- **EDA_Peaks_Count:** Liczba rejestrowanych peaków w sygnale EDA
- Dane treningowe zostały wyłączone z analizy

### Metoda Statystyczna
Wykorzystano **korelację Spearmana** do zbadania zależności między zmiennymi.

## 📊 Główne Wyniki

| ID Uczestnika | Średnie Pobudzenie (Arousal) | Liczba Peaków EDA |
|---------------|------------------------------|------------------|
| 103           | 5.28                        | 66                |
| 119           | 5.98                        | 10                |
| 120           | 5.92                        | 20                |
| 136           | 5.49                        | 6                 |
| 141           | 6.09                        | 20                |

### Wnioski
- **Współczynnik korelacji Spearmana:** -0.205
- **P-value:** 0.741
- **Interpretacja:** Brak statystycznie istotnej zależności między odczuwanym pobudzeniem a liczbą peaków EDA (p > 0.05)
  - Wynik jest normalny dla tak małej próby (n=5)
  - Sugeruje, że indywidualne różnice mogą być duże

## 🛠️ Wymagane Biblioteki

```python
pandas
neurokit2
scipy
matplotlib
seaborn
```

### Instalacja Zależności
```bash
pip install pandas neurokit2 scipy matplotlib seaborn
```

## 📓 Uruchomienie Analizy

1. Upewnij się, że pliki danych znajdują się w folderze `data/` (struktura jak wyżej)
2. Otwórz notebook w Jupyter:
   ```bash
   jupyter notebook Analiza_BIRAFFE.ipynb
   ```
3. Uruchom komórki kodu sekwencyjnie (Shift + Enter)

## 📈 Wizualizacje

Notebook zawiera:
- Tabelę średniego pobudzenia dla każdego uczestnika
- Tabelę liczby peaków EDA dla każdego uczestnika
- Wykres regresji pokazujący relację między Arousal a EDA Peaks
- Statystyki i wnioski

## ⚙️ Uwagi Techniczne

- **Sampling Rate:** Domyślnie 1000 Hz - zmień w kodzie jeśli dane mają inną częstotliwość
- **Nazwa kolumny EDA:** Kod zakłada kolumnę o nazwie 'EDA' - sprawdź dokładną nazwę w pliku CSV
- **Optymalizacja pamięci:** Kod wczytuje tylko kolumny niezbędne do analizy, aby oszczędzać RAM

## 📝 Autor

**Alucart558**

## 📄 Licencja

Projekt jest dostępny bez specjalnej licencji - swobodny do użytku.

## 🔗 Dodatkowe Informacje

- Dataset pochodzi z projektu BIRAFFE2 (badania emocji i pobudzenia fizjologicznego)
- Analiza wykorzystuje bibliotekę NeuroKit2 do przetwarzania sygnałów EDA
- Możliwe rozszerzenia: analiza innych sygnałów biologicznych (HR, respiration), segmentacja danych czasowych
