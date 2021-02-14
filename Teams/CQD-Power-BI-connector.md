---
title: Installare Power BI Connector per usare i modelli di query di CQD
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
description: Installare Power BI Connector per usare i modelli di query call quality dashboard (CQD)
ms.openlocfilehash: c3812032f385a3428feec7f1126663e815af1b52
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611580"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Installare Power BI Connector per usare i modelli di query di CQD

Prima di poter usare i modelli di Query di Power BI (file PBIX) per Microsoft Teams Call Quality Dashboard (CQD), è necessario installare Power BI Connector per Microsoft CQD usando il file *MicrosoftCallQuality.pqx* incluso nel [download.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Leggere [l'uso di Power BI per analizzare i dati di CQD per Teams](CQD-Power-BI-query-templates.md) per ottenere informazioni su questi modelli.

Assicurarsi di avere il ruolo di [accesso di CQD giusto](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) per accedere ai report di Power BI.

> [!NOTE]
> CQD Power BI Connector supporta solo DirectQuery in Power BI; La modalità di importazione non è supportata. 

## <a name="installation"></a>Installazione

La procedura per l'installazione di un connettore personalizzato e la modifica della sicurezza per abilitare l'uso del connettore è descritta in dettaglio nella documentazione [di Power BI.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility) Ai fini della semplicità, ecco una breve spiegazione:

1. Verificare che nel computer in uso sia già presente una cartella Documenti dei connettori *\[ \] \\ personalizzati \\ di Power BI Desktop.* In caso contrario, creare questa cartella. <sup>1</sup>

2. Scaricare il file del connettore (file con estensione *\* mez* o *\* pqx)* e posizionarlo nella directory *Custom Connectors.*

3. **Se il file del connettore è un file con estensione *\* mez,*** sarà necessario modificare anche le impostazioni di sicurezza come descritto nella documentazione di configurazione [del connettore personalizzato.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)

Se viene rilasciata una nuova versione di Power BI Connector per Microsoft Teams, è sufficiente sostituire il vecchio file di connettore nella directory *dei* connettori personalizzati con il nuovo file.

## <a name="setup"></a>Configurazione

Per creare un report ed eseguire query, è prima necessario connettersi all'origine dati di CQD. Seguire questa procedura per connettersi:

1. Nella scheda Home di Power BI Desktop fare clic *su Ottieni dati.*

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector1-resize.png)

2. A *questo punto dovrebbe* comparire la finestra Ottieni dati. Passa ai *Servizi online,* quindi seleziona Qualità chiamata *Microsoft (beta)* e premi *Connetti.*

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector2-resize.png)

3. Verrà richiesto di eseguire l'accesso. Usare le stesse credenziali usate per CQD. <sup>2</sup>

4. La richiesta successiva ti darà l'opzione tra due modalità *di connettività dei dati.* Selezionare *DirectQuery* e fare clic su *OK.*

5. Infine, verrà visualizzata una richiesta finale che mostra l'intero modello di dati per CQD. A questo punto non saranno visibili dati, ma solo il modello di dati per CQD. Selezionare *Carica per* completare il processo di configurazione.

6. A questo punto, Power BI carica il modello di dati sul lato destro della finestra. La pagina rimarrà altrimenti vuota e non verranno caricate query per impostazione predefinita. Procedere con **la creazione di query** seguenti per creare una query e restituire dati.

Se uno o più passaggi del processo di configurazione non sono stati del tutto chiari, una spiegazione più dettagliata del processo è disponibile nella Guida introduttiva: Connettersi ai dati [in Power BI Desktop.](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)

## <a name="building-queries"></a>Creazione di query

Al termine dell'installazione, i nomi di diverse centinaia di dimensioni e misure dovrebbero essere caricati nel *riquadro* Campi. Creare query effettive da qui è semplice, basta selezionare le dimensioni e le misure desiderate per la query, quindi trascinarle nella pagina. Ecco una spiegazione più dettagliata, con un semplice esempio:

1. Selezionare la visualizzazione da usare nel *riquadro* Visualizzazioni. Nella pagina dovrebbe essere visualizzata una versione vuota della visualizzazione. Ai fini di questo esempio verrà utilizzata la *visualizzazione* Tabella.

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector3-resize.png)

2. Determinare le dimensioni e le misure (con un simbolo di aggregazione in base al nome) da usare per la query, quindi selezionarle manualmente e trascinarle nella visualizzazione nera. In alternativa, trascinarli nel campo *Valori* sotto le opzioni di visualizzazione.

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > Call Quality Dashboard richiede una misura per l'esecuzione di qualsiasi query. Se non si aggiunge una misura a una query, la query non riesce.

3. Quindi, selezionare le dimensioni in base a cui filtrare e trascinarle nel campo Filtri per questo *campo* visivo nel *riquadro* Filtri. Attualmente CQD Power BI Connector supporta i filtri di base, ovvero i valori selezionati da un elenco di valori delle dimensioni possibili, i filtri avanzati, che  specificano manualmente i valori e gli operandi in base a cui filtrare, in modo simile a Advanced CQD, e il filtro delle date relative *(disponibile* solo per le dimensioni Ora fine e Ora inizio).    Il filtro in *base alla prima N* non è supportato da CQD.

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector5-resize.png)

4. Infine, selezionare la *scheda Formato* nel riquadro *Visualizzazioni* per formattare e formattare la query.

    > [!NOTE]
    > Le query di CQD richiedono almeno una misura per l'esecuzione. Se la query non viene caricata, verificare di aver incluso una misura nella query.

## <a name="creating-a-drillthrough-report"></a>Creazione di un report drill-through

[Il drill-through in Power BI](https://docs.microsoft.com/power-bi/desktop-drillthrough) consente di creare report mirati che è possibile filtrare rapidamente usando i valori di altri report come contesto. Una volta che si è in grado di creare la prima query con CQD Connector, la creazione di un drill-through è ancora più semplice.

1. Creare un'altra pagina per il report attivo e quindi aggiungere le query a tale pagina.

2. Selezionare la dimensione da usare come filtro drill-through e trascinarla nel campo *Drill-through* nel *riquadro* Visualizzazioni.

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector6-resize.png)

3. **Questo è tutto\!** Qualsiasi altra query in un'altra pagina che usa la dimensione può ora eseguire il drill-through in quella pagina, applicando automaticamente il valore della dimensione drill-through come filtro.

    ![Screenshot: Connettore di Power BI](media/CQD-power-bi-connector7-resize.png)

A differenza di Advanced CQD, Power BI supporta il drill-through non sequenziale. Se una query include la dimensione necessaria, può eseguire il drill-through in qualsiasi altra pagina.

### <a name="best-practice"></a>Procedura consigliata

Le query del connettore Call Quality devono essere progettate appositamente per la funzionalità drill-through. Invece di provare a caricare tutti i dati contemporaneamente e quindi affettare i filtri, iniziare con query più ampie e con bassa cardinalità ed eseguire il drill-down fino a query ad alta cardinalità. Ad esempio, quando si tenta di diagnosticare quali subnet contribuiscono maggiormente ai problemi di qualità, è utile identificare prima le aree geografiche e i paesi che contribuiscono al problema, quindi eseguire il drill-down fino alle subnet di tale area geografica o paese. I modelli dei connettori Call Quality sono stati progettati in questo modo per fungere da esempio.

## <a name="limitations"></a>Limitazioni

Nonostante l'uso di Power BI, non tutte le funzionalità di Power BI sono supportate dal connettore CQD, a causa di limitazioni nel modello di dati di CQD o sui connettori DirectQuery in generale. L'elenco seguente annota alcune limitazioni più degne di nota di Connector, ma questo elenco non deve essere considerato esaustivo:

1. **Colonne calcolate :** I connettori DirectQuery in generale hanno un supporto limitato per le colonne calcolate in Power BI. Anche se alcune colonne calcolate possono funzionare con il connettore, queste dovrebbero essere considerate eccezioni. Come regola generale, le colonne calcolate non funzioneranno.

2. **Aggregazioni -** Il modello di dati di CQD è basato su un modello di cubo, ovvero le aggregazioni sono già supportate sotto forma di misure. Se si prova ad aggiungere manualmente aggregazioni a dimensioni diverse o si modifica il tipo di aggregazione di una misura, il connettore non funziona e in genere viene restituito un errore.

3. **Oggetti visivi personalizzati :** Anche se CQD Connector funziona con una gamma di oggetti visivi personalizzati, non siamo in grado di garantire la compatibilità con tutti gli oggetti visivi personalizzati. Molti oggetti visivi personalizzati si basano sull'uso di colonne calcolate o dati importati, né sono supportati dai connettori DirectQuery.

4. **Riferimento ai dati memorizzati nella cache** Power BI attualmente non supporta il riferimento ai dati memorizzati nella cache da un connettore DirectQuery in alcun modo. Se si prova a fare riferimento ai risultati di una query, viene creata una nuova query.

5. **Filtro dei dati relativo** È supportato in CQD Connector, ma solo con le dimensioni *Ora* inizio *e Ora* fine. Anche se la *dimensione Data* può essere la scelta ovvia per il filtro delle date *relative,* La data non viene archiviata come oggetto data e quindi non supporta il filtro delle date relative in Power BI.

6. **Supporto per Government Community Cloud (GCC) -** Per i clienti dell'ambiente GCC, Power BI Connector di CQD funzionerà quando si usa Power BI Desktop. Il connettore CQD Power BI non è attualmente compatibile con il servizio Power BI per i clienti GCC.

La maggior parte di questi problemi è o restrizioni alla progettazione del connettore DirectQuery in Power BI o alla progettazione del modello di dati di CQD.

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Si sta provando a usare la colonna Data come filtro dei dati Data. Non appena converto il tipo di dati di questa colonna in Data, viene visualizzato questo errore

> **Non è stato possibile caricare** i dati per l'oggetto visivo: errore OLE DB o ODBC: [Expression.Error] Non è stato possibile piegare l'espressione nell'origine dati. Provare con un'espressione più semplice.

I filtri dei dati di data non sono supportati con Power BI Connector. Per specificare un intervallo di date, applicare due filtri al report specificando una data minore e maggiore di.

In alternativa, se le date da visualizzare sono recenti, applicare un filtro data relativo per visualizzare solo i dati degli ultimi N giorni/settimane/mesi.

## <a name="error-codes"></a>Codici di errore

Poiché Power BI Connector di CQD è meno limitato dell'app browser in termini di tipi di query che è possibile creare, possono verificarsi diversi errori durante la creazione delle query. Nel caso in cui venga visualizzato un messaggio di errore di tipo "CQDError. RunQuery – Query Execution Error", fare riferimento all'elenco seguente con il numero ErrorType fornito per risolvere il possibile problema con la query. Di seguito sono riportati i codici di tipo di errore più comuni che possono verificarsi con CQD Power BI Connector:

- **ErrorType 1 - Errore nella struttura della query:** Un errore nella struttura della query è in genere causato dal mancato compilazione di una query formattata correttamente da Connector. Questo problema si verifica spesso quando si usano funzionalità non supportate, come specificato nelle Limitazioni precedenti. Verificare di non usare colonne calcolate o oggetti visivi personalizzati per la query.

  - **ErrorType 2 - Errore di compilazione query:** Un errore di creazione di query è causato dal fatto che CQD Connector non riesce ad analizzare correttamente la query che si sta provando a creare. Questo problema si verifica spesso quando si usano funzionalità non supportate, come specificato nelle Limitazioni precedenti. Verificare di non usare colonne calcolate o oggetti visivi personalizzati per la query.

  - **ErrorType 5 - Timeout esecuzione:** Prima del timeout, la query ha raggiunto il runtime massimo possibile. Provare ad aggiungere altri filtri alla query per limitarne l'ambito. Restringere l'intervallo di dati è spesso il modo più efficace per raggiungere questo obiettivo.

  - **ErrorType 7 - Errore nessuna misura:** Per funzionare, le query di CQD richiedono una misura. Verificare che la query includa misure. Le misure in CQD Connector sono indicato dal simbolo di aggregazione (somma) prima del nome.

Se si verificano altri errori all'esterno di questo ambito, informare il team di Ricerca dettagli progetto in modo da poter risolvere il problema e aggiornare la documentazione nel modo appropriato.

## <a name="footnotes"></a>Note a piè di pagina

**<sup>1</sup>** Alcuni processi e app, ad esempio OneDrive, possono causare la modifica della cartella radice Documenti; verificare che la directory Dei connettori personalizzati di *Power BI Desktop \\* sia inserita nella cartella radice corrente Documenti.

**<sup>2</sup>** Le credenziali di accesso usate  per CQD non devono essere le stesse usate per accedere all'app Desktop Power BI.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Quando verrà aggiornato il connettore di Power BI dallo stato "Beta"

Nonostante il tag Beta, Call Quality Connector per Power BI è la versione finale del connettore ed è stato ufficialmente firmato dal team di Power BI per riflettere questa richiesta. Il processo di certificazione per la rimozione del tag Beta è completo e richiede l'impegno del team di Power BI a fornire supporto diretto anche al connettore. A causa dei vincoli tempori, il team di Power BI non è attualmente in grado di fornire tale supporto e una certificazione più ampia, ma è comunque pronto a testare la sicurezza, l'autenticità e le funzionalità generali del connettore Qualità chiamata Microsoft.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>Perché il connettore sembra più lento rispetto ad Advanced CQD nel browser? Cosa si può fare per migliorare le prestazioni

Le prestazioni delle query per i vari modelli sono in realtà le stesse sia nel browser che nel connettore.  Come qualsiasi altra app autonoma, Power BI aggiunge tempo di autenticazione e rendering alle prestazioni. Inoltre, la differenza riguarda il numero di query simultanee eseguite. Dato che la versione nel browser di CQD aveva opzioni di visualizzazione meno sviluppate e ad alta densità di informazioni, la maggior parte dei report si limitava al caricamento di query 2-3 alla volta. D'altra parte, i modelli di connettore spesso visualizzano più di 20 query simultanee. Se si vogliono creare report reattivi esattamente come quelli precedenti, provare a creare report con non più di 2-3 query per scheda.

Per altre informazioni, vedere gli articoli seguenti:

- [Guida all'ottimizzazione per Power BI](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [Indicazioni sul modello DirectQuery](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Trovo abitualmente il limite di 10.000 righe durante l'esecuzione di query. Come fare in modo che il connettore restituisa più di 10.000 righe

Il limite di 10.000 righe viene in realtà specificato all'estremità dell'API ed è progettato per migliorare significativamente le prestazioni e ridurre il rischio di errori di esecuzione delle query derivanti da condizioni di memoria insufficiente.

Invece di provare ad aumentare il numero di righe dei risultati, è meglio ristrutturare i report in base alle procedure consigliate per i connettori. I modelli inclusi sono progettati per illustrare queste procedure consigliate. Se possibile, iniziare esaminando gli indicatori KPI usando dimensioni più ampie e con una cardinalità inferiore, ad esempio Mese, Anno, Data, Area geografica, Paese e così via. Da qui è possibile eseguire il drill-down in dimensioni di cardinalità sempre più elevate. Entrambi i report helpdesk e Location-Enhanced offrono ottimi esempi di questo flusso di lavoro drill-down.



## <a name="related-topics"></a>Argomenti correlati

[Usare Power BI per analizzare i dati di CQD per Teams](CQD-Power-BI-query-templates.md)
