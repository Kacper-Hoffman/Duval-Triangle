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
# Dissolved Gas Analysis - Duval Method 🇬🇧
## Introduction
The main goal of my master's thesis was the creation of a program for DGA analysis of transformer oil gas. Using this program you can quickly determine the state of the transformer. The program is capable of analising many transformers simultaneously, or one transformer in many steps of time. Of course, you have to remember that Duval method works best when the safe limits are only exceeded by the main five gases: hydrogen, methane, acetylene, ethylene and ethane.
## DGA
Dissolved Gas Analysis allows determining the state of transformer based on the concentrations of gas in its oil. This method starts with electrochemical processes. Transformer oil is composed of many hydrocarbons. The changing electric field causes rise in temperature. Temperature then causes base elements of oil to dissolve. This proces is not linear. Different gases dissolve at different temperatures. First, hydrogen is dissolved. Then, as temperature increases, the other gases start dissolving in order: ethane, methane, etylene and finally acethylene. The order is based on the strength of bonds. For example, acethylene has a triple bond bethween carbon and hydrogen, meaning that it can only dissolve at high temperatures.

![Electrochemical Processes](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/1_1.png)

![Order of Dissolution](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/3_1.png)

Concentrations are obtained through chromatography of the oil. Then the concentrations are analised. There are multiple methods, but here we use the Duval method. Duval method is based on Duval triangles - ternary plots where relative concentration points are. Relative concentrations are calculated as precentage ratios of one gas to the sum of all others.

![Relative Concentrations](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/i2.png)

Those concentrations are displayed inside the triangles. Michel Duval created multiple triangles based on the type of oil and type of device analised. For transformers with mineral oil we use triangles number 1, 4 i 5. Triangle 1 contains relative concentrations of methane, etylene and acethylene. Triangle 4 oses the concentrations of hydrogen, ethane and methane. Triangle 5 is based on ethane, methane and etylene.

![Triangle 1](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/t1.png)

Triangle 1 is the first test. The triangle is divided into 7 regions. The result of analysis is based on which region contains the relative concentrations point. Regions D1 and D2 reflect low and high energy discharges. DT is the region where both discharges and overheating is possible. Regions T1, T2 i T3 represent overheating of low (T < 300 °C), medium (300 °C < T < 700 °C) and high (T > 700 °C) temperatures. Region PD represents partial discharges. If the relative concentration point is in regions D1, D2, DT this means tht they are the final result of the analysis. If the test shows partial discharges or low temperature overheating, we use triangle 4. If medium of high temperature overheating is detected, we then use trangle 5.

![Triangle 4](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/t2.png)

Triangle 4 uses hydrogen, ethane and methane. Because these gases easly dissolve within oil, this triangle determines the cause of transformer damage in low temperatures. It contains 5 regions. Region PD of partial discharges is present here. Region S represents stray gassing due to leaking. Region C is carbonization of cellulose isolation. Region O represents low temperature overheating without carbonization. The final region, without label, means that the result of triangle 1 was correct.

![Triangle 5](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/t3.png)

Triangle 5 contains ethane, methane and etylene. The goal of this triangle is determining the cause of damage in higher temperatures. It contains 9 regions. Here we can detect partial discharges PD, overheating of medium and high temperature T2, T3. The cause can also be stray gassing S, carbonization C and low temperature overheating O. The final region, as mentioned before, means that the result of analysis with triangle 1 was correct.

## Duval Program
To automate analysis the Duval program was created. It's a window application written by me in C#. It contains three pages. In the first page you choose the number of transformers and input their data. After pressing the "Oblicz" button in the second pages you can view the results of analysis. Concentration points are visible on the triangles as well as written with text below. The third page contains basic information about Dissolved Gas Analysis.

![Duval 1](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/5_1.png)

![Duval 2](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/5_2.png)

![Duval 3](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/4_3.png)

Preforming comparative tests with actual chromatographic results confirms that the program works correct. Deeper analysis of the topic, full analysis of code and the tests are available in my ![master's thesis (🇵🇱 only)](https://github.com/Kacper-Hoffman/Duval-Triangle/blob/main/RE000000-95009-MGR.pdf).
