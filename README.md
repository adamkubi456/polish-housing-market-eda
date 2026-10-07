# Analiza Polskiego Rynku Nieruchomości (EDA)
Eksploracyjna analiza danych (EDA) rynku mieszkaniowego w największych miastach Polski, zrealizowana na bazie danych z platformy Kaggle. 

Projekt identyfikuje kluczowe determinanty cen lokali mieszkalnych. Repozytorium obejmuje pełen proces inżynierii danych: standaryzację i czyszczenie surowego zbioru, weryfikację anomalii i wartości odstających, inżynierię cech (feature engineering) oraz empiryczną weryfikację 4 hipotez rynkowych.

### Hipotezy biznesowe:

1. **Premia za pakiet udogodnień (Amenities Premium):**  
   Zwiększenie liczby udogodnień w lokalu (winda, miejsce parkingowe, balkon, ochrona, komórka lokatorska) przekłada się na nieliniowy wzrost ceny za m², przy czym istnieje punkt nasycenia, powyżej którego kolejne udogodnienia nie generują istotnej statystycznie nadwyżki rynkowej.

2. **Premia za mikrometraż (Efekt skali vs kawalerki):**  
   Cena za metr kwadratowy maleje nieliniowo wraz ze wzrostem powierzchni lokalu – małe mieszkania (do 35 m²) uzyskują najwyższą wycenę jednostkową na rynku ze względu na wysoką płynność i popyt inwestycyjny.

3. **Optymalizacja układu („Upakowanie” pokoi):**  
   W ramach tego samego przedziału metrażowego (segment 45–65 m²) lokale o większej liczbie pokoi (mniejsza średnia powierzchnia pojedynczego pokoju) osiągają wyższą cenę za m² niż mieszkania o układzie przestronnym, co wynika z premii za potencjał wynajmu na pokoje.

4. **Segment studencki a tolerancja standardu technicznego:**  
   Bliskość uczelni wyższych (do 1,5 km) neutralizuje dyskonto wynikające ze słabszego stanu technicznego nieruchomości – popyt akademicki utrzymuje wysokie stawki za m² nawet dla mieszkań wymagających remontu.

## 📊 Weryfikacja Hipotez Rynkowych

### 1. Premia za udogodnienia i punkt nasycenia (Amenities Score)
![Hipoteza 1](assets/h1_amenities_premium.png)
* **Efekt schodkowy:** Mieszkania z 1–2 udogodnieniami uzyskują umiarkowaną premię (+6,7% do +7,8%), podczas gdy zestaw 3 elementów powoduje skok wyceny do poziomu 15 000 zł/m² (+15,4% względem oferty bazowej).
* **Punkt nasycenia:** Przejście z 3 do 4 udogodnień podnosi medianę o zaledwie 148 zł/m², co wskazuje na malejące korzyści krańcowe z dodatkowych cech standardowych.
* **Segment premium:** Maksymalny pakiet (5 udogodnień) stanowi jedynie 0,8% rynku i osiąga wycenę wyższą o 23%, reprezentując wąski segment apartamentów luksusowych.

---

### 2. Premia za mikrometraż i krzywa U-kształtna
![Hipoteza 2](assets/h2_micro_apartments.png)
* **Przewaga kawalerek:** Lokale o powierzchni do 35 m² osiągają medianę 17 313 zł/m² – to aż o **23,7% wyższa stawka jednostkowa** niż w segmencie mieszkań średnich (35–65 m²).
* **Wyczerpanie efektu skali:** Różnica cen między segmentem średnim (14 000 zł/m²) a rodzinnym (13 810 zł/m²) wynosi zaledwie 1,4%, co dowodzi stabilizacji cen po przekroczeniu progu kawalerki.
* **Odbicie dla apartamentów (>100 m²):** Wykres trendu rynkowego (LOWESS) ujawnia charakterystykę U-kształtną – ponowny wzrost stawek za metr w największych metrażach wynika z obecności luksusowych apartamentów w centrach metropolii.

---

### 3. Liczba pokoi w segmencie popularnym (45–65 m²)
![Hipoteza 3](assets/h3_room_density.png)
* **Obalenie hipotezy o zagęszczeniu:** Lokale 2-pokojowe osiągają najwyższą wycenę jednostkową (14 000 zł/m²), przewyższając układy 3-pokojowe o 5,7% oraz 4-pokojowe o 8,9%.
* **Preferencja przestrzeni dziennej:** Zjawisko to występuje najsilniej w **nowym budownictwie** (+10,2% na korzyść 2 pokoi), co pokazuje, że nabywcy wyżej cenią przestronne strefy dzienne (salon z aneksem) niż ciasne sypialnie.
* **Wyjątek kamienic:** W budownictwie przedwojennym trend ulega odwróceniu – układy 3-pokojowe uzyskują wycenę wyższą o 12,8% ze względu na specyfikę adaptacji historycznych przestrzeni pod kancelarie i najem premium.

---

### 4. Segment studencki a stan lokalu (Condition vs Proximity)
![Hipoteza 4](assets/h4_student_condition.png)
* **Karygodny stan na peryferiach:** W odległości powyżej 3,5 km od uczelni zły stan techniczny (`low`) oznacza drastyczny spadek wyceny do 9 204 zł/m² (**dyskonto rzędu 37,5%** względem mieszkań premium).
* **Poduszka cenowa wokół kampusów:** W promieniu 1,5 km od uczelni wycena lokali do remontu wzrasta do 12 488 zł/m², redukując dyskonto jakościowe niemal o połowę (do 19,3%). Stały popyt ze strony studentów i inwestorów chroni wartość lokali o niskim standardzie.
* **Reporting Bias:** Wykazano, że 80% braków deklaracji stanu technicznego zachowuje się jak nieruchomości o standardzie przeciętnym (mediana 13,8–14,9 tys. zł/m²).
---

# Polish Housing Market Analysis (EDA)

An exploratory data analysis (EDA) of the residential property market across Poland's major metropolitan areas, based on data sourced from Kaggle.

This project investigates the primary drivers behind housing valuations. The repository details the end-to-end analytical pipeline: data preprocessing and cleaning, domain-aware outlier detection, feature engineering, and empirical hypothesis testing.

### Business Hypotheses:

1. **Amenities Premium & Saturation:**  
   A higher composite amenities score (elevator, parking space, balcony, security, storage) drives a non-linear increase in price per square meter, with a detectable point of diminishing returns beyond which additional features yield marginal value.

2. **Micro-Apartment Premium (Economy of Scale):**  
   Price per square meter decreases non-linearly with total area – compact apartments (under 35 m²) command the highest unit prices due to strong rental investor demand and higher transaction liquidity.

3. **Room Density & Layout Efficiency:**  
   Within an identical size tier (45–65 m²), properties configured with more rooms (lower average room area) achieve higher prices per square meter than spacious layouts, capturing a premium driven by room-by-room rental strategies.

4. **Student Market Resilience to Property Condition:**  
   Close proximity to universities (under 1.5 km) mitigates pricing discounts associated with lower property condition ratings – student-driven demand supports stable per-square-meter prices even for properties requiring renovation.

```
