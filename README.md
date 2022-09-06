⚠️ WIP ⚠️
# Analiza gazów rozpuszczonych DGA - Metoda Duvala 🇵🇱
## Wstęp
Głównym celem mojej pracy magisterskiej było stworzenie programu służącego do analizy koncentracji gazów w oleju metodą Duvala. Wykorzystanie tego programu pozwoli na szybkie stwierdzenie stanu transformatora bazując na jego oleju. Program ten jest w stanie przeanalizować jednocześnie dużo transformatorów naraz, albo jeden transformator w wielu okresach czasu. Należy oczywiście pamiętać o tym, że metoda Duvala sprawdza się najlepiej gdy poza granicę bezpieczeństwa wychodzą tylko gazy z głównej piątki: wodór, metan, acetylen, etylen oraz etan.
## DGA
Analiza gazów rozpuszczonych polega na przewidzeniu stanu transformatora bazując na zawartych w jego oleju gazach. Podejście to ma swój początek w procesach elektrochemicznych. Olej transformatorowy składa się z wielu węglowodanów. Pod wpływem pola elektrycznego wzrasta temperatura oleju. Temperatura z kolej powoduje wydzielanie się z oleju jego bazowych składników. Proces ten jest niejednorodny. Różne gazy rozkładają się pod różną temperaturą. Najpierw wydziela się wodór, ponieważ ma najsłabsze połączenie z resztą oleju. Potem jak temperatura wzrasta zaczynają się wydzielać etan, metan, etylen a na koniec acetylen. Kolejność wydzielania wynika z siły wiązań. Przykładowo, acetylen posiada potrójne wiązanie między węglem i wodorem, przez co potrzeba wysokiej temperatury aby go wydzielić.

![Electrochemical Processes](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/1_1.png)

![Order of Dissolution](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/3_1.png)

Same koncentracje gazów można wykryć poprzez badanie chromatograficzne. Póżniej należy te koncentracje przeanalizować. Istnieje kilka metod służących w tym celu, tutaj jednak stosujemy metodę Duvala. Metoda Duvala to sposób analizy odnoszący się do trójkątów Duvala - wykresów we współrzędnych trójkątnych gdzie znajdują się koncentracje względne. Koncentracje względne obliczany jako prosty stosunek procentowy jednego z gazów do sumy pozostałych.

![Relative Concentrations](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/i2.png)

Owe koncentracje wyświetla się wewnątrz trójkątów. Michel Duval stworzył kilka trójkątów zależnie od rodzaju oleju oraz typu urządzenia analizowanego. Dla transformatorów posiadających olej mineralny stosuje się trójkąty numer 1, 4 i 5. Trójkąt 1 zawiera koncentracje względne metanu, etylenu oraz acetylenu. Trójkąt 4 odnosi się do koncentracji wodoru, etanu i metanu. Z kolej trójkąt 5 bazuje na etanie, metanie i etylenie.

![Triangle 1](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/t1.png)

Trójkąt 1 jest testem wstępnym. Trójkąt podzielony jest na 7 rejonów. Wynik analizy zależy od tego, w którym rejonie znajdzie się punkt koncentracji względnych. Rejony D1 i D2 odpowiaadają za wyładowania nisko- i wysokoenergetyczne. DT to rejon pośredni gdzie mogą występować i wyładowania zupełne i przegrzania. Rejony T1, T2 i T3 oznaczają występowanie przegrzań o temperaturze niskiej (T < 300 °C), średniej (300 °C < T < 700 °C) oraz wysokiej (T > 700 °C). Rejon PD oznacza wyładowania niezupełne. Jeśli punkt koncentracji wypadnie w rejonach D1, D2, DT to oznacza że wynikiem końcowym analizy jest ten rejon. Jeśli badanie wykarze wyładowania niezupełne lub przegrzania niskiej temperatury to przechodzimy do trójkąta 4. Jeśli wykryto przegrzania średniej lub wysokiej temperatury bierzemy trójkąt 5.

![Triangle 4](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/t2.png)

Trójkąt 4 składa się z wodoru, etanu i metanu. Ponieważ te gazy łatwo wydzielają się z oleju, ten trójkąt odpowiada za określenie przyczyny uszkodzenia transformatora w niskich temperaturach. Zawiera on 5 rejonów. Powtarza się rejon wyładowań niezupełnych PD. Rejon S oznacza występowanie gazów pasożytniczych w wyniku nieszczelności. Rejon C to karbonizacja celulozowej izolacji transformatora. Rejon O odpowiada za przegrzanie bez karbonizacji. Ostatni rejon, bez oznaczenia, oznacza że wynik badania z trójkąta 1 był prawidłowy.

![Triangle 5](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/t3.png)

Trójkąt 5 zawiera etan, metan oraz etylen. Celem tego trójkąta jest określenie przyczyny uszkodzenia wyższej temperatury. Składa się on z 9 rejonów. Tutaj również istnieje możliwość wykrycia wyładowań niezupełnych PD, jak i potwierdzenia przegrzań średniej i wysokiej temperatury T2, T3. Przyczyną takiego uszkodzenia mogą być gazy pasożytnicze S, karbonizacja C i przegrzanie O. Ostatni rejon, tak jak wcześniej wspomniano, oznacza że wynik analizy trójkąta 1 był prawidłowy.

## Program Duval
W celu automatyzacji analizy stworzono program Duval. Jest to program oknowy napisany prze ze mnie w języku C#. Składa się on z trzech kart. W pierwszej karcie wybiera się ilość transformatorów oraz wpisuje ich dane. Po naciśnięciu przycisku "Oblicz" w karcie drugiej pokazują się wyniki obliczeń. Punkty koncentracji pokazują się na trójkątach oraz są spisane tekstowo na dole. W trzeciej karcie znajdują się podstawowe informacje o analizie DGA.

![Duval 1](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/5_1.png)

![Duval 2](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/5_2.png)

![Duval 3](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/4_3.png)

Przeprowadzenie testów porównawczych z rzeczywistymi raportami z badań chromatograficznych potwierdza, że program działa prawidłowo. Głębsza analiza tematu, pełna analiza kodu programu oraz przeprowadzone testy są dostępne w mojej ![pracy magisterskiej](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/RE000000-95009-MGR.pdf).

---
# Dissolved Gas Analisys - Duval Method 🇬🇧
