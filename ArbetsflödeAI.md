# **Arbetsflödet för AI-projekt**
Christopher Seander - IT-Högskolan 2021

## **Datainsamling**
### **Web Scraping**
En metod för att samla in data är web scraping [^1] där man "skrapar nätet" genom att hämta hem data som är tillgängligt  publikt på olika hemsidor. Du kan till exempel samla in kommentarer från politiska YouTube-klipp eller personers jobbtitlar på Linkedin. Ett sätt jag hittade för att göra detta är WebScarpingAPI [^2] som kan användas med python för att hämta data från vilken hemsida som helst. 

[^1]: https://dan-suciu.medium.com/how-to-collect-data-for-machine-learning-in-6-steps-via-web-scraping-85eb4fbaca95
[^2]: https://www.webscrapingapi.com/

### **Sensor Data**
Det går också att samla in data via olika typer av sensorer från exempelvis IoT enheter [^3], där ingår till exempel  platsdata som talar om var en enhet befinner sig via GPS. En vanlig typ av data som IoT enheter använder sig av är statusdata som meddelar om en enhet är påslagen, om en lagerplats är ledig eller liknande.

[^3]: https://www.digiteum.com/iot-data-collection/

### **Vilka format och var sparas datan?**
Det finns en mängd olika format som använda för att spara datan, om man har en stor mängd data bör man spara den i ett binärt filformat då dessa tar mindre palts och tar mindre tid att läsa från en hårddisk. 
- Kolumnbaserad data används .parquet, .orc och .petastorm och denna  data nås oftast av SQL. Man använder kolumnbaserad data när man vill ha låg latens och högt dataflöde. 
- Tabellbaserad data sparas som .csv och .xslx och denna typ av data är textbaserad och åtskilt med kommatecken. En nackdel är att prestandan sänks när storleken ökar.
- Kapslade filformat används där datan kan ha "barn" och föräldrar", tänk familjeträd, och dessa kan byggas ut det krävs. Är datan textbaserad sparas den oftast som .json eller .xml och är datan binär används .avro eller .pb. 
- Numpy är ett arraybaserat format (.npy) som har hög prestanda och en Numpy array har element av samma typ som är tätt packade. 
- Hierarkiska dataformat används för stora mängder data med många dimensioner, medicinsk utrustning sparar ofta data i det här formatet.

Beroende på vad för typ av data det är och mängden så sparas den på olika sätt, mindre mängder sparas till exempel på en lokal hårddisk eller ssd medans större mängder kan vara utspridda över många olika servrar. [^4]

[^4]: https://towardsdatascience.com/guide-to-file-formats-for-machine-learning-columnar-training-inferencing-and-the-feature-store-2e0c3d18d4f9

## **Datavisualisering**
Det finns många olika sätt att visualisera data, tre vanliga är linjediagram, stapeldiagram och tårtdiagram. Linjediagram brukar används ofta för att visa förändring över en tidsperiod. Stapeldiagram kan göras både horisontellt och vertikalt, och används ofta när man har flera olika data att visa samtidigt sida vid sida. Tårtdiagram används främst när man vill visa relationen mellan olika mängder, till exempel hur stor del av ens försäljning som är från en viss produkt. [^5]

[^5]: https://www.glew.io/articles/5-powerful-examples-of-data-visualization

För att visualisera data med hjälp av Python används bland annat Matplotlib, Pandas, Seaborn, ggplot och Plotly. Matplotlib är ett lågnivåbibliotek och man har mer frihet med hur man vill visualisera sin data men det kommer att behövas mer kod för att få fram ett specifikt resultat. Pandas är liknande Matplotlib men är ett hög-prestanda bibliotek som används med dess egna datastrukturer "dataframes" och "series" och kräver därmed mindre kod för att få samma resultat. [^6]

[^6]: https://towardsdatascience.com/introduction-to-data-visualization-in-python-89a54c97fbed

## Bearbeta data
När man har rå data kan den innehålla outliers, dubbletter eller saknad data, detta går man igenom och rättar till för att inte stöta på problem när man senare använder datan. Man kan också ändra format på exempelvis tid eller datum så att det blir lättare att använda. [^7]

[^7]: https://www.talend.com/resources/what-is-data-processing/

## Linjär Regression
Linjär regression används för att kunna göra prediktioner man ännu inte har data för, genom att hitta ett linjärt samband för datan man redan har. Detta linjära samband ska avvika så lite som möjligt från ens datapunkter.

## Driftsätta en modell
När man har en modell som fungerar på ens egna dator och man tycker den är redo att driftsättas så bör man "containerize" sin kod, med detta menas det att koden ska kunna köras från var som helst och inte bara på ens egna dator.

Därefter kan man skapa en hemsida eller en app, samt ett API så modellen kan kopplas ihop med hemsidan eller appen. När det är gjort kan man driftsätta sin modell i molnet och de tre största leverantörerna för detta är Amazon AWS, Google Cloud eller Microsoft Azure. [^8]

[^8]: https://towardsdatascience.com/how-to-deploy-machine-learning-models-ec50d3daf365

## Teknologier som används i maskininlärningsprocessen
De vanligaste biblioteken för Python som används i maskininlärning är Numpy, Scipy, Scikit-learn, Theano, TensorFlow, Keras, PyTorch, Pandas och Matplotlib. [^9]

[^9 https://www.upgrad.com/blog/top-python-libraries-for-machine-learning/]

