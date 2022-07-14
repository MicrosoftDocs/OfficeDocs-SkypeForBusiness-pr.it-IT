---
title: Installare Power BI Connector per usare i modelli di query CQD
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Installare Power BI Connector per usare i modelli di query Call Quality Dashboard (CQD)
ms.openlocfilehash: 80d1b39c6fbe26f04998b06b22fb527b60bbb6a0
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789871"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Installare Microsoft Call Quality Connector per Power BI per usare i modelli di query di Call Quality Dashboard

Prima di usare i modelli di query Power BI (file PBIX) per Call Quality Dashboard (CQD) di Microsoft Teams, è necessario installare il connettore Microsoft Call Quality per Power BI, usando il file *MicrosoftCallQuality.pqx* incluso nel [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).

Per informazioni su questi modelli, vedere [Usare Power BI per analizzare i dati di Call Quality Dashboard per Teams](CQD-Power-BI-query-templates.md) .

Assicurarsi di avere il ruolo di accesso corretto a [Call Quality Dashboard](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) per accedere ai report di Power BI.

> [!NOTE]
> Il connettore Microsoft Call Quality supporta solo DirectQuery in Power BI; La modalità di importazione non è supportata. 

## <a name="installation"></a>Installazione

Il processo per l'installazione di un connettore personalizzato e la regolazione della sicurezza per consentire l'uso del connettore è descritto in dettaglio nella [documentazione di Power BI](/power-bi/desktop-connector-extensibility). Per semplicità, ecco una breve spiegazione:

1. Verificare se nel computer è già disponibile una *\[cartella Documenti\]\\ Power BI Desktop\\ Connettori personalizzati*. In caso contrario, creare questa cartella. <sup>1</sup>

2. Scaricare il file del connettore ( *\*file con estensione mez* o *\*pqx* ) e inserirlo nella directory *Custom Connectors* .

3. **Se il file del connettore è un *\*file con estensione mez* ,** sarà necessario modificare anche le impostazioni di sicurezza come descritto nella [documentazione sulla configurazione del connettore personalizzata](/power-bi/desktop-connector-extensibility#data-extension-security).

Se viene rilasciata una nuova versione del connettore Microsoft Call Quality, sostituire il vecchio file del connettore nella directory *Custom Connectors* con il nuovo file.

## <a name="setup"></a>Installazione

Per creare un report ed eseguire query, è necessario prima di tutto connettersi all'origine dati di Call Quality Dashboard. Segui i passaggi seguenti per connetterti:

1. Nella scheda Home di Power BI Desktop fare clic su *Recupera dati*.

    ![Recuperare dati in Power BI Connector.](media/CQD-power-bi-connector1-resize.png)

2. A questo punto dovrebbe comparire la finestra *Recupera dati* . Passa a *Servizi online*, quindi seleziona *Qualità chiamata Microsoft (Beta)* e premi *Connetti*.

    ![Qualità chiamata Microsoft nel connettore Power BI.](media/CQD-power-bi-connector2-resize.png)

3. Verrà richiesto di eseguire l'accesso successivo. Usare le stesse credenziali usate per Call Quality Dashboard. <sup>2</sup>

4. Nel prompt successivo verrà visualizzata l'opzione tra due *modalità di connettività dati*. Selezionare *DirectQuery* e fare clic su *OK*.

5. Infine, verrà visualizzata una richiesta finale che mostra l'intero modello di dati per Call Quality Dashboard. A questo punto non saranno visibili dati, ma solo il modello di dati per Call Quality Dashboard. Selezionare *Carica* per completare il processo di configurazione.

6. A questo punto, Power BI caricherà il modello di dati sul lato destro della finestra. In caso contrario, la pagina rimarrà vuota e per impostazione predefinita non verrà caricata alcuna query. Passare alla **creazione di query** seguente per creare una query e restituire i dati.

Se uno dei passaggi durante questo processo di configurazione non è stato chiaro, è possibile trovare una spiegazione più dettagliata del processo nella [Guida introduttiva: Connettersi ai dati in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Creazione di query

Al termine dell'installazione, nel riquadro *Campi* dovrebbero essere visualizzati i nomi di diverse centinaia di dimensioni e misure. Creare query effettive da qui è semplice, basta selezionare le dimensioni e le misure desiderate per la query, quindi trascinarle nella pagina. Ecco una spiegazione più dettagliata, con un semplice esempio:

1. Selezionare la visualizzazione da usare nel riquadro *Visualizzazioni* . Nella pagina dovrebbe essere visualizzata una versione vuota della visualizzazione. Ai fini di questo esempio, verrà usata la visualizzazione *Tabella* .

    ![Riquadro Visualizzazioni in Power BI Connector.](media/CQD-power-bi-connector3-resize.png)

2. Determinare le dimensioni e le misure (indicate da un simbolo di aggregazione con il relativo nome) da usare per la query, quindi selezionarle manualmente e trascinarle nella visualizzazione nera. In alternativa, trascinarli nel campo *Valori* sotto le opzioni di visualizzazione.

    ! Query di visualizzazioni in Power BI Connector.] (elementi multimediali/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Call Quality Dashboard richiede una misura per l'esecuzione di qualsiasi query. Se non si aggiunge una misura a una query, la query avrà esito negativo.

3. Selezionare quindi le dimensioni da filtrare e trascinarle nel campo *Filtri in questo campo visivo* nel riquadro *Filtri* . Il connettore Microsoft Call Quality attualmente supporta *il filtro di base* (selezionare valori da un elenco di valori di dimensione possibili), il *filtro avanzato* (specificare manualmente i valori e gli operandi in base a cui filtrare, in modo simile a Call Quality Dashboard) e il *filtro data relativo* (disponibile solo per le dimensioni *Ora fine* e *Ora inizio* ). Il filtro in base a *Top N* non è supportato da Call Quality Dashboard.

    ![Le visualizzazioni vengono filtrate in Power BI Connector.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > I filtri sono supportati solo se applicati alle dimensioni. Il filtro dei valori delle misure non è supportato in Call Quality Dashboard.

4. Infine, selezionare la scheda *Formato* nel riquadro *Visualizzazioni* per applicare stili e formattare la query.

    > [!NOTE]
    > Le query di Call Quality Dashboard richiedono almeno una misura per l'esecuzione. Se la query non viene caricata, verificare di aver incluso una misura nella query.

## <a name="creating-a-drillthrough-report"></a>Creazione di un report drill-through

[Il drill-through in Power BI](/power-bi/desktop-drillthrough) consente di creare report evidenziati che è possibile filtrare rapidamente usando i valori di altri report come contesto. Dopo aver capito come creare la prima query con il connettore Microsoft Call Quality, creare un drill-through è ancora più semplice.

1. Creare un'altra pagina per il report con lo stato attivo e quindi aggiungere le query a tale pagina.

2. Selezionare la dimensione da usare come filtro drill-through e trascinarla nel campo *Drill-through* sotto nel riquadro *Visualizzazioni* .

    ![Drill-through nel connettore di Power BI.](media/CQD-power-bi-connector6-resize.png)

3. **Questo è tutto\!** Qualsiasi altra query in un'altra pagina che usa tale dimensione può ora eseguire il drill-through alla pagina, applicando automaticamente il valore della dimensione drill-through come filtro.

    ![Filtro drill-through in Power BI Connector.](media/CQD-power-bi-connector7-resize.png)

A differenza di Call Quality Dashboard, Power BI supporta il drill-through non sequenziale. Se una query include la dimensione necessaria, può eseguire il drill-down fino a qualsiasi altra pagina.

### <a name="best-practice"></a>Procedure consigliate

Le query dei connettori Microsoft Call Quality devono essere progettate tenendo presente la funzionalità drill-through. Invece di provare a caricare tutti i dati contemporaneamente e quindi a scendere con i filtri, iniziare con query più ampie a bassa cardinalità ed eseguire il drill-down fino a query con cardinalità elevata. Ad esempio, quando tenti di diagnosticare quali subnet contribuiscono maggiormente ai problemi di qualità, è utile prima identificare le aree geografiche e i paesi che contribuiscono al problema, quindi eseguire il drill-down fino alle subnet di tale area geografica o paese. I modelli di connettore Qualità chiamata sono stati progettati in questo modo per fungere da esempio.

## <a name="limitations"></a>Limitazioni

Nonostante l'uso di Power BI, non tutte le funzionalità di Power BI sono supportate dal connettore Microsoft Call Quality, a causa di limitazioni nel modello di dati di Call Quality Dashboard o sui connettori DirectQuery in generale. Nell'elenco seguente vengono annota alcune delle limitazioni più degne di nota del Connettore, ma questo elenco non deve essere considerato esaustivo:

1. **Colonne calcolate –** I connettori DirectQuery in generale hanno un supporto limitato per le colonne calcolate in Power BI. Alcune colonne calcolate potrebbero funzionare con Il connettore, in quanto tali colonne sono eccezioni. Come regola generale, le colonne calcolate non funzionano.

2. **Aggregazioni:** Il modello di dati Call Quality Dashboard è basato su un modello cubo, ovvero le aggregazioni sono già supportate sotto forma di misure. Se si prova ad aggiungere manualmente aggregazioni a dimensioni diverse o a modificare il tipo di aggregazione di una misura, il connettore non funziona e in genere si verifica un errore.

3. **Oggetti visivi personalizzati :** Anche se il connettore Microsoft Call Quality funziona con una gamma di oggetti visivi personalizzati, non siamo in grado di garantire la compatibilità con tutti gli oggetti visivi personalizzati. Molti oggetti visivi personalizzati si basano sull'uso di colonne calcolate o dati importati, nessuno dei quali è supportato dai connettori DirectQuery.

4. **Riferimento ai dati memorizzati nella cache -** Power BI attualmente non supporta in alcun modo il riferimento ai dati memorizzati nella cache da un connettore DirectQuery. Qualsiasi tentativo di fare riferimento ai risultati di una query determinerà una nuova query.

5. **Filtro dei dati relativi -** È supportato nel connettore Microsoft Call Quality, ma solo con le dimensioni *Ora inizio* e *Ora fine* . Anche se la dimensione *Data* può essere la scelta ovvia per il filtro delle date relative, *La data* non viene archiviata come oggetto data e quindi non supporta il filtro delle date relative in Power BI.

6. **Query di sola misurazione -** Al momento non sono supportati nel connettore Microsoft Call Quality. Quando si crea una visualizzazione con tre o più misure e senza dimensioni, i dati della colonna verranno trasposti. Per evitare questo tipo di errore, includere sempre almeno una dimensione (ad esempio, Mese Anno) nelle visualizzazioni. Questo problema dovrebbe essere risolto in una prossima versione del connettore Microsoft Call Quality per Power BI.

7. **Supporto per Government Community Cloud (GCC) -** Per i clienti nell'ambiente GCC, il connettore Microsoft Call Quality funzionerà solo quando si utilizza Power BI Desktop. Il connettore Microsoft Call Quality non è attualmente compatibile con il servizio Power BI per i clienti GCC.

La maggior parte di questi problemi sono le restrizioni alla progettazione del connettore DirectQuery in Power BI o fondamentali per la progettazione del modello di dati di Call Quality Dashboard.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Si sta provando a usare la colonna Data come filtro dei dati Data. Non appena converti il tipo di dati di questa colonna in Data, viene visualizzato questo errore

> **Non è stato possibile caricare i dati per questo oggetto visivo**: errore OLE DB o ODBC: [Expression.Error] Non è stato possibile piegare l'espressione all'origine dati. Prova un'espressione più semplice.

I filtri dei dati data non sono supportati con il connettore Microsoft Call Quality. Per specificare un intervallo di date, applicare due filtri al report, specificando una data minore e maggiore di.

In alternativa, se le date da visualizzare sono recenti, applicare un filtro relativo per visualizzare solo i dati relativi agli ultimi N giorni/settimane/mesi.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Quando si aggiungono determinate dimensioni ai report, l'oggetto visivo restituisce immediatamente **"Impossibile caricare i dati per questo oggetto visivo".** La rimozione della dimensione corregge l'oggetto visivo: cosa sta accadendo?

Si tratta di un problema noto nel connettore Microsoft Call Quality; Qualsiasi dimensione esposta come numero intero verrà visualizzata in Power BI come colonna di aggregazione, dove Power BI tenterà un'azione di riepilogo predefinita (in genere 'Somma'). In alcuni casi, questo comportamento riuscirà a sommare i valori anche se il risultato non è utile, poiché la "somma" di una dimensione come Second WiFi Channel è priva di significato. In altri casi, l'azione di riepilogo avrà esito negativo e causerà errori nell'oggetto visivo.

Per ovviare a questo problema, iniziare rimuovendo la dimensione dall'oggetto visivo. Selezionare la dimensione dall'elenco "Campi", passare alla scheda "Strumenti colonna" sulla barra multifunzione, fare clic sul menu a discesa "Riepilogo" e selezionare **Non riepilogare**. La dimensione può ora essere aggiunta di nuovo all'oggetto visivo.


## <a name="error-codes"></a>Codici di errore

Poiché il connettore Microsoft Call Quality per Power BI è meno limitato rispetto all'app del browser in termini di tipi di query che è possibile creare, è possibile che si verifichino occasionalmente diversi errori durante la creazione delle query. Nel caso in cui venga visualizzato un messaggio di errore di tipo "CQDError. RunQuery – Query Execution Error", fare riferimento all'elenco seguente con il numero ErrorType fornito per risolvere il possibile problema con la query. Di seguito sono elencati i codici di tipo di errore più comuni che possono verificarsi con il connettore power BI di Call Quality Dashboard:

- **ErrorType 1 - Errore struttura query:** Un errore di struttura della query è in genere causato dal connettore che non riesce a creare una query formattata correttamente. Questa situazione si verifica più spesso quando si usano funzionalità non supportate, come specificato nelle limitazioni precedenti. Verificare di non usare colonne calcolate o oggetti visivi personalizzati per la query.

  - **ErrorType 2 - Errore di creazione query:** Un errore di creazione di query è causato dal fatto che il connettore Microsoft Call Quality non è in grado di analizzare correttamente la query che si sta tentando di creare. Questa situazione si verifica più spesso quando si usano funzionalità non supportate, come specificato nelle limitazioni precedenti. Verificare di non usare colonne calcolate o oggetti visivi personalizzati per la query.

  - **ErrorType 5 - Timeout esecuzione:** La query ha raggiunto il runtime massimo possibile prima del timeout. Provare ad aggiungere altri filtri alla query per limitarne l'ambito. Limitare l'intervallo di dati è spesso il modo più efficace per ottenere questo risultato.

  - **ErrorType 7 - Nessun errore di misura:** Le query di Call Quality Dashboard richiedono una misura per funzionare. Verificare che la query includa una misura. Le misure nel connettore Microsoft Call Quality sono indicate dal simbolo di aggregazione (somma) prima del nome.

Se si verificano altri errori al di fuori di questo ambito, inviare una notifica al team di Call Quality Dashboard in modo che possiamo contribuire alla risoluzione del problema e aggiornare la documentazione in base alle esigenze.

## <a name="footnotes"></a>Note

**<sup>1</sup>** Alcuni processi e app (ad esempio, OneDrive) possono causare la modifica della cartella radice Documenti; assicurarsi che la directory *Power BI Desktop\\ Custom Connectors* sia inserita nella cartella Documenti della cartella radice corrente.

**<sup>2</sup>** Le credenziali di accesso utilizzate per Call Quality Dashboard *non* devono necessariamente essere le stesse utilizzate per accedere all'app Power BI Desktop stessa.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando verrà aggiornato il connettore Power BI dallo stato "Beta"?

Nonostante il tag Beta, il connettore Microsoft Call Quality (Beta) per Power BI è la prima versione "release" del connettore ed è stato ufficialmente firmato dal team di Power BI per riflettere questo aspetto. Al momento del rilascio iniziale del connettore, il team di Power BI non era in grado di fornire supporto e certificazione più ampia, ma era ancora pronto a attestare la sicurezza, l'autenticità e le funzionalità generali del connettore Microsoft Call Quality. In futuro, prevediamo di investire nel connettore Microsoft Call Quality per Power BI.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>Perché il connettore sembra più lento rispetto a Call Quality Dashboard nel browser? Cosa posso fare per migliorare le prestazioni?

Le prestazioni delle query per i vari modelli sono in realtà le stesse sia nel browser che nel connettore.  Come per qualsiasi altra app autonoma, Power BI ne aggiunge l'autenticazione e il tempo di rendering alle prestazioni. Inoltre, la differenza riguarda il numero di query simultanee da eseguire. Poiché la versione nel browser di Call Quality Dashboard aveva opzioni di visualizzazione meno sviluppate e con densità di informazioni, la maggior parte dei report era limitata al caricamento di 2-3 query alla volta. D'altra parte, i modelli di connettore spesso visualizzano più di 20 query simultanee. Se si vogliono creare report che rispondano allo stesso modo di quelli precedenti, provare a creare report con non più di 2-3 query per scheda.

Per altre informazioni, vedere gli articoli seguenti:

- [Guida all'ottimizzazione per Power BI](/power-bi/guidance/power-bi-optimization)
- [Linee guida del modello DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Il limite di 10.000 righe durante l'esecuzione di query viene regolarmente gestito. Come si fa a fare in modo che il connettore restituisca più di 10.000 righe?

Il limite di 10.000 righe è in realtà specificato sul lato API ed è progettato per migliorare significativamente le prestazioni e ridurre il rischio di errori di esecuzione delle query derivanti da condizioni di memoria insufficiente.

Invece di tentare di aumentare il numero di righe dei risultati, è consigliabile ristrutturare i report in base alle procedure consigliate per i connettori. I modelli inclusi sono progettati per dimostrare queste procedure consigliate. Dove possibile, iniziare osservando gli indicatori KPI usando dimensioni più ampie e con una cardinalità inferiore, ad esempio Mese, Anno, Data, Area geografica, Paese e così via. Da qui è possibile eseguire il drill-down per visualizzare dimensioni di cardinalità sempre più elevate. Il supporto tecnico e i report di Location-Enhanced offrono entrambi esempi validi di questo flusso di lavoro di drill-down.



## <a name="related-topics"></a>Argomenti correlati

[Usare Power BI per analizzare i dati di Call Quality Dashboard per Teams](CQD-Power-BI-query-templates.md)
