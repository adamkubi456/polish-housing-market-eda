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
