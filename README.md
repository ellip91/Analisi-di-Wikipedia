***Descrizione del Progetto***
Wikidata Insights, un'azienda leader nella gestione di contenuti digitali, è stata incaricata da Wikimedia per ottimizzare l'analisi e la categorizzazione dei contenuti di Wikipedia. Per supportare la loro continua espansione e migliorare l'organizzazione delle informazioni, Wikidata Insights ha deciso di condurre un progetto avanzato di data analysis e machine learning. L'obiettivo principale è comprendere meglio il vasto patrimonio di contenuti informativi offerti da Wikipedia e sviluppare un sistema di classificazione automatica che consenta di categorizzare efficacemente i nuovi articoli futuri.
Il progetto verrà svolto su databricks mediante l'uso di libreria pyspark.

***Obiettivi***
**1. Analisi Descrittiva dei Contenuti**
   
Il primo obiettivo del progetto è condurre un'analisi esplorativa dei dati (EDA) per capire le caratteristiche dei contenuti di Wikipedia suddivisi in diverse categorie tematiche, come ad esempio: - Cultura, Economia, Medicina, Tecnologia, Politica, Scienza, e altre.

L'analisi esplorativa prevede: - Il conteggio degli articoli presenti per ogni categoria. - Il numero medio di parole per articolo. - La lunghezza dell'articolo più lungo e di quello più corto per ciascuna categoria. - La creazione di nuvole di parole rappresentative per ogni categoria, per identificare i termini più frequenti e rilevanti.

Per fare questo è stato effettuato un preprocessing, con rimozione dei valori mancanti e dei duplicati. Viene effettuata la tokenizzazione e la rimozione delle stopwords. Tramite spark.sql si risponde alle richieste di questo primo punto. Per la nuvola di parole ho prima aggregato documents e summary per categoria e poi ho creato la funzione che utilizza wordcloud. 

**2. Sviluppo di un Classificatore Automatico**

Il secondo obiettivo è creare un modello di machine learning capace di classificare automaticamente gli articoli in base alla loro categoria. Il sistema di classificazione verrà addestrato utilizzando dati di testo presenti nelle seguenti colonne del dataset: - Sommario (summary): Introduzione breve dell'articolo. - Testo Completo (documents): Contenuto completo dell'articolo.

Testo un modello di Logistic Regression creando una pipeline contenente indexer (per indicizzare le categorie), countvectorizer, standardizzaizone e PCA. Le metriche del modello sono intono all'80%.
Si è testato anche un modello Naive bayes multinomial per vedere le metriche potessero migliorare ma il primo modello era migliore.


