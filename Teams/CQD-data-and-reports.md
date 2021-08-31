---
title: Dati e report in Call Quality Dashboard (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Informazioni sui dati e i report disponibili in Microsoft Call Quality Dashboard (CQD).
ms.openlocfilehash: e184137c927361b1a557973d4ac8e55ea49cf1ea
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731805"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Dati e report in Call Quality Dashboard (CQD)

Microsoft Call Quality Dashboard (CQD) usa un feed di dati in tempo quasi reale (NRT). I record delle chiamate sono disponibili in CQD entro 30 minuti dalla fine di una chiamata. I record di chiamata dalla pipeline NRT sono disponibili solo per alcuni mesi prima di essere rimossi dal set di dati. 


## <a name="many-ways-to-access-cqd-data"></a>Molti modi per accedere ai dati CQD

È possibile accedere ai dati CQD in diversi modi. Scegli quello più adatto alle tue esigenze:

|  |  |
|---------|---------|
|Teams di amministrazione [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | I dati CQD  sono inclusi nella pagina Utenti dell'interfaccia di amministrazione di Teams, che mostra i dati più comuni necessari in un formato di facile lettura. Non è possibile personalizzare i dati CQD trovati in **Utenti**.  |
|Portale CQD [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Riepilogo efficace e report dettagliati che soddisfano la maggior parte delle esigenze, con filtri drill-through. È anche possibile personalizzare i report nel portale CQD. <br><br>È possibile [ottenere due modelli di report CQD](#import-the-cqd-report-templates) che consentono di analizzare i dati nel portale CQD.       |
|Power BI     | Usare query dirette per visualizzare i dati CQD in Power BI usando modelli Power BI [personalizzati.](CQD-Power-BI-query-templates.md) [Scaricare Power BI di query per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>È anche possibile [usare l'API REST per accedere ai dati CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) tramite Power BI. Usare questo metodo se si vogliono scaricare i dati CQD in modo da poterlo usare offline. L'uso di questo metodo è vantaggioso per prestazioni migliori, particolarmente utili per set di dati di grandi dimensioni che Power BI quando si è online.       |
|API di Microsoft Graph     | Accedere ai dati sulla qualità delle chiamate manualmente usando [l'API Graph chiamata](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta). Si tratta del metodo più complesso, ma offre il maggior controllo e flessibilità nell'analisi dei dati sulla qualità delle chiamate. Ad esempio, se è necessario unirsi ad altri dati per l'organizzazione, è possibile usare l'API Graph per creare un modello di dati e incorporare i dati sulla qualità delle chiamate.        |

## <a name="import-the-cqd-report-templates"></a>Importare i modelli di report CQD

Scarica [due modelli di report CQD curati](https://aka.ms/qertemplates) (Tutte le reti e Reti gestite) per aiutarti a iniziare rapidamente con CQD. Il modello Tutte le reti, anche se ottimizzato per l'uso con un file di dati dell'edificio, può essere usato durante la raccolta e il caricamento di informazioni sull'edificio in CQD, come descritto nella sezione successiva.

**Per importare i modelli (. CQDX) in CQD**

1. In CQD selezionare **Report dettagliati** dal menu nella parte superiore della pagina.

2. Nel riquadro sinistro selezionare **Importa.** Passare al primo modello CQDX e selezionare **Apri**.

3. Dopo il caricamento del modello, viene visualizzata una finestra popup con il messaggio "Importazione report completata". 

4. Ripetere i passaggi 2 e 3 per il secondo modello CQD.

   > [!NOTE]
   > Ogni utente deve importare i modelli CQD nell'istanza CQD. 



## <a name="euii-data"></a>Dati EUII

Per motivi di conformità, i dati relativi alle informazioni identificabili dell'utente finale (EUII) (noti anche come informazioni personali o informazioni personali) vengono conservati solo per 28 giorni. Quando i dati NRT attraversano il contrassegno di 28 giorni, i campi che contengono EUII vengono cancellati, con il risultato di dati NRT senza EUII. I campi che contengono dati EUII sono:

- Indirizzo IP completo
- Indirizzo MAC (Media Access Control)
- Identificatore del set di servizi di base (BSSID)
- URI SIP (Session Initiation Protocol) (Skype for Business)
- Nome entità utente (UPN)
- Nome endpoint computer
- Feedback verbale dell'utente
- ID oggetto (ID oggetto Active Directory dell'utente dell'endpoint)

### <a name="admin-roles-with-and-without-euii-access"></a>Ruoli di amministratore con e senza accesso EUII

Questi [ruoli del controllo](/azure/role-based-access-control/overview) degli **accessi in base al ruolo hanno** accesso EUII:
- Amministratore globale
- Teams Amministratore del servizio
- Teams Amministratore delle comunicazioni
- Tecnico supporto comunicazioni Teams
- Lettore globale
- Skype for Business Amministratore

Questi ruoli RBAC **non hanno accesso** EUII:
- Lettore report
- Teams Specialista del supporto per le comunicazioni


## <a name="date-controls"></a>Controlli data

CQD supporta i tipi di tendenza a rotazione seguenti:

- 5 giorni
- 7 giorni
- 30 giorni
- 60 giorni
- 90 giorni

Il parametro URL Date accetta un campo Day. I report a giornata continua usano le date specificate nel formato AAAA-MM-GG come ultimo giorno della tendenza. Il parametro URL Date "00" indica "oggi".

|URL| Data di fine della tendenza del giorno di rotazione|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Giorno corrente di febbraio 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15 febbraio 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Giorno corrente|
|||

Per impostazione predefinita, il giorno corrente del mese viene usato come ultimo giorno della tendenza del giorno.


## <a name="data-available-in-cqd-reports"></a>Dati disponibili nei report CQD

Il riepilogo predefinito e i report CQD dettagliati possono essere tutti necessari per gestire la qualità delle chiamate per l'organizzazione. Se necessario, è possibile [creare report personalizzati.](#create-custom-detailed-reports) 

Se si vuole usare Power BI per analizzare i dati CQD, vedere Usare Power BI per analizzare i dati [di CQD per](CQD-Power-BI-query-templates.md)Teams .

|Funzionalità|Report di riepilogo|Report dettagliati|
|:--- |:--- |:--- |
|Metrica di condivisione delle applicazioni | No | Sì |
|Supporto per le informazioni sull'edificio del cliente | Sì | Sì |
|Supporto per le informazioni sull'endpoint del cliente | Solo in <span> cqd.teams.microsoft.com<span/> | Solo in <span> cqd.teams.microsoft.com<span/> |
|Supporto per l'analisi drill-down   | No   | Sì   |
|Metriche sull'affidabilità dei supporti multimediali   | No   | Sì   |
|Report predefiniti   | Sì   | Sì   |
|Report di panoramica   | Sì   | Sì   |
|Set di report per utente   | No   | Sì   |
|Personalizzazione del set di report (aggiungere, eliminare, modificare report)   | No   | Sì   |
|Metriche di condivisione dello schermo basate su video   | No   | Sì   |
|Metriche video   | No   | Sì   |
|Quantità di dati disponibili   | Ultimi 12 mesi   | Ultimi 12 mesi   |
|Microsoft Teams dati   | Sì   | Sì   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Selezionare i dati di prodotto da visualizzare nei report

Nei report Riepilogo e Location-Enhanced prodotti è  possibile usare l'elenco a discesa Filtro prodotti per visualizzare tutti i dati di prodotto, solo Microsoft Teams dati o solo Skype for Business online.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra le opzioni del controllo Filtro prodotti.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Nei report dettagliati è  possibile usare la dimensione Teams per filtrare i dati Microsoft Teams o Skype for Business online.

## <a name="summary-reports"></a>Report di riepilogo

Questi sono i report che verranno visualizzati nel dashboard CQD quando si accede per la prima volta a CQD. Offrono uno sguardo a colpo d'occhio alle tendenze qualitative con report giornalieri, mensili e di tabella per facilitare l'identificazione delle subnet con qualità scarsa. 

| SCHEDA | Descrizione |
|---------|---------|
|Qualità complessiva delle chiamate     | Aggregazione delle altre 3 schede.       |
|Server- Client     |Dettagli dei flussi tra endpoint server e client.        |
|Client- Client     |Dettagli dei flussi tra due endpoint client.        |
|Contratto di servizio sulla qualità vocale     |Informazioni sulle chiamate incluse nel contratto Skype for Business qualità [vocale.](https://go.microsoft.com/fwlink/p/?linkid=846252)        |

### <a name="overall-call-quality-tab"></a>Scheda Generale Qualità chiamata

Usare i dati in questa scheda per valutare lo stato della qualità delle chiamate e le tendenze in base al numero di flussi e alle percentuali scadenti. La legenda nell'angolo in alto a destra mostra il colore e gli elementi visivi che rappresentano queste metriche.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra la scheda Qualità chiamata.](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
Flussi sono classificati in tre gruppi: Buono, Medio e Non classificato. Sono inoltre disponibili valori  *poor %*  calcolati che forniscono il rapporto tra i flussi classificati *come Poor*  e il conteggio totale dei flussi classificati. Poiché *Poor % = Poor streams/ (Poor streams+ Good streams) * 100*, poor *%*  non è interessato dalla presenza di più flussi *non*  classificati. Per vedere cosa classifica uno stream come scadente o buono, vedere Classificazione [di flusso in Call Quality Dashboard.](stream-classification-in-call-quality-dashboard.md)
  
Usare la scala a sinistra per misurare i valori del conteggio dei flussi.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra i valori del conteggio dei flussi.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Usare la scala a destra per misurare i valori di % scarsa.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra i valori di % scadente.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
È anche possibile ottenere i valori numerici effettivi posizionando il puntatore del mouse su una barra.
  
> [!NOTE]
> L'esempio seguente si trova in un set di dati di esempio molto piccolo e i valori non sono realistici per una distribuzione effettiva.

> [!div class="mx-imgBorder"]
> ![Screenshot: mostra il mouse usato per accedere ai dati.](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Il volume complessivo dello stream consente di determinare quanto sono rilevanti le percentuali di scarsa qualità calcolate. Minore è il volume dei flussi complessivi, meno affidabili sono i valori percentuali di scarsa qualità riportati.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client e Client-Client schede

Queste due schede forniscono dettagli per i flussi che hanno avuto luogo nei loro scenari da endpoint a endpoint. La Server-Client contiene quattro sezioni comprimibile che rappresentano quattro scenari in cui i flussi multimediali fluirebbero.
  
- Cablato all'interno
- Esterno cablato
- WiFi all'interno
- WiFi Esterno

Analogamente, la scheda Client-Client contiene cinque sezioni comprimibile:

- Cablato all'interno - Cablato all'interno
- Cablato all'interno - Esterno cablato
- Esterno cablato - Esterno cablato
- Cablato all'interno - WiFi Inside
- Cablato all'interno - WiFi Esterno

#### <a name="inside-versus-outside"></a>All'interno e all'esterno

CQD classifica un flusso come  *Interno* *o*  Esterno usando le informazioni sull'edificio, se esiste. Gli endpoint di ogni flusso sono associati a un indirizzo subnet. Se la subnet si trova nell'elenco delle subnet contrassegnate come InsideCorp nelle informazioni sull'edificio caricate, viene considerata *All'interno.* Se le informazioni sulla creazione non sono ancora state caricate, Inside Test classifica sempre i flussi come *Esterni.* 

Il test interno per uno scenario Server-Client considera solo l'endpoint client. Poiché i server sono sempre esterni dal punto di vista di un utente, questo non viene contabile nel test.
  
#### <a name="wired-versus-wifi"></a>Rete cablata e WiFi

Come indicano i nomi, i criteri di classificazione si basano sul tipo di connessioni client. Il server è sempre cablato e non è incluso nel calcolo. In un determinato flusso, se uno dei due endpoint è connesso a una rete WiFi, CQD lo classifica come WiFi.

> [!NOTE]
> Dato uno stream, se uno dei due endpoint è connesso a una rete WiFi, viene classificato come WiFi in CQD.
  
  
## <a name="tenant-data-information"></a>Informazioni sui dati del tenant

Il dashboard Report di riepilogo CQD include una pagina Upload dati tenant, accessibile selezionando Dati **tenant Upload** dal menu impostazioni nell'angolo in alto **a** destra. Questa pagina viene usata per gli amministratori per caricare le proprie informazioni, ad esempio:

- Mappa dell'indirizzo IP e delle informazioni geografiche.
- Mappa di ogni punto di accesso wireless e del relativo indirizzo MAC.
- Mappa di Endpoint a Endpoint Make/Model/Type e così via.
  
È consigliabile caricare i dati del tenant, dell'edificio e della posizione in modo che CQD possa includere queste informazioni nei report. Se questi dati non sono già stati caricati, leggere Upload [tenant e i dati di creazione.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Report dettagliati

| Nome | Descrizione |
|---------|---------|
|Location-Enhanced report     |Mostra le tendenze qualitative in base alle informazioni sulla posizione. Questo report viene visualizzato solo se sono stati [caricati i dati del tenant.](CQD-upload-tenant-building-data.md)        |
|Report sull'affidabilità     |Include report audio, video, condivisione dello schermo basata su video (VBSS) e condivisione di app.        |
|Report sulla qualità dell'esperienza     |Qualità audio e affidabilità per tutti i client e i dispositivi, incluse le sale riunioni. Questi report sono una versione "slimmed-down" dei modelli [CQD](https://aka.ms/QERtemplates)scaricabili, incentrata sulle aree chiave per l'analisi della qualità e dell'affidabilità audio.         |
|Report drill-down qualitativo     | Drill-down: data per area geografica, località, subnet, ora e utenti.        |
|Report drill-down degli errori     | Drill-down: data per area geografica, località, subnet, ora e utenti.        |
|Valutare i report delle chiamate     |Analizzare le classificazioni delle chiamate degli utenti per area geografica, località o per utente. Include feedback dettagliato.         |
|Report dell'Help Desk     |I report dell'Help Desk osservano i dati delle chiamate e delle riunioni per singoli utenti, gruppi di utenti o tutti. Incorporando dati di edificio e EUII, questi report consentono di identificare i possibili problemi di sistema in base alla posizione di rete, ai dettagli della conferenza, ai dispositivi o al firmware.         |
|Report versione client     |Riepilogo versione client: visualizzare il conteggio sessioni e utenti per ogni versione dell'app client<br><br>Versione client per utente: visualizzare i nomi utente per ogni versione dell'app client <br><br>I filtri predefiniti per tipo di prodotto e client consentono di concentrare le versioni su client specifici.         |
|Report degli endpoint     |Mostra la qualità delle chiamate in base agli endpoint del computer (computer make and model). Questi report includono i dati di creazione, se sono stati caricati.         |


## <a name="create-custom-detailed-reports"></a>Creare report dettagliati personalizzati

Se i report CQD predefiniti non soddisfano le proprie esigenze, usare queste istruzioni per creare un report personalizzato. Oppure (a partire da gennaio 2020) Usare [Power BI per i report CQD. ](cqd-power-bi-query-templates.md)

Nell'elenco a discesa dei report nella parte superiore della schermata visualizzata all'accesso nella schermata Report di riepilogo \( selezionare Report  \) **dettagliati** e quindi **Nuovo**. Fare **clic su** Modifica in un report per visualizzare l'editor di query. Ogni report è supportato da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor di query consente di modificare queste query e le opzioni di visualizzazione del report.

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi caricamenti di edifici verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di edificio, è consigliabile scaricare il file corrente e ricaricarlo per identificare eventuali sovrapposizioni e risolvere il problema prima di caricarlo di nuovo. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare il mapping errato delle subnet agli edifici nei report. Alcune implementazioni VPN non riportano in modo accurato le informazioni sulla subnet. Quando si aggiunge una subnet VPN al file di edificio, invece di una voce per la subnet, è consigliabile aggiungere voci separate per ogni indirizzo della subnet VPN come rete a 32 bit separata. Ogni riga può avere gli stessi metadati di compilazione. Ad esempio, invece di una riga per 172.16.18.0/24, è necessario avere 256 righe, con una riga per ogni indirizzo compreso tra 172.16.18.0/32 e 172.16.18.255/32 inclusi.
>
> La colonna VPN è facoltativa e il valore predefinito è 0.  Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da tale riga verrà completamente espansa in modo che corrisponda a tutti gli indirizzi IP all'interno della subnet.  Usare questa opzione con parsimonio e solo per le subnet VPN, in quanto l'espansione completa di queste subnet avrà un impatto negativo sui tempi delle query per le query che implicano la creazione di dati.

Posizionare il dito sui grafici a barre e le linee di tendenza nel report per visualizzare i valori dettagliati. Il report con lo stato attivo mostrerà il menu delle azioni: **Modifica**, **Clona**, **Elimina**, **Scarica** ed Esporta **albero report**.



## <a name="query-filters"></a>Filtri di query

I filtri di query vengono implementati usando l'editor di query in CQD. Questi filtri vengono usati per ridurre il numero di record restituiti da CQD, riducendo al minimo le dimensioni complessive e i tempi di query del report. Questa opzione è particolarmente utile per filtrare le reti non gestite. I filtri elencati nella tabella seguente usano espressioni regolari (RegEx).


| Filter         | Descrizione          | Esempio di filtro di query CQD      |
|----------------|----------------------|-------------------------------|
| Nessun valore vuoto   | Alcuni filtri non hanno l'opzione di filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su Uguale o Diverso da, a seconda delle esigenze.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Escludere subnet comuni | Senza un file di edificio valido per separare le reti gestite da quelle non gestite, le reti domestiche verranno incluse nei report. Queste subnet domestiche sono esterne all'ambito di controllo dell'IT e possono essere rapidamente escluse da un report. Le subnet comuni, come definito in questa guida, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Seconda subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Visualizza solo all'interno  | Consente di filtrare un report in modo che sia gestito (all'interno) o non gestito (esterno). Il modello CQD gestito è già preconfigurato con questi filtri.       | Second Inside Corp = Inside        |

## <a name="report-filters"></a>Filtri per i report

Usare i filtri dei report CQD per limitare lo stato attivo delle indagini. Usare i filtri dei report aggiungendo un filtro al report di cui è stato eseguito il rendering nell'editor di query o direttamente nel report. I filtri di report seguenti vengono usati in tutti [i modelli CQD.](https://aka.ms/QERtemplates)


| Filter     | Descrizione                            | Esempio di filtro del report CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Iniziare prima con l'anno e poi con il mese. | 2017-10                           |
| Alfabetico | Filtra per tutti i caratteri alfabetici. | [a-z]                             |
| Numerico    | Filtri per tutti i caratteri numerici.    | [0-9]                             |
| Percentuale | Filtri per una percentuale.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) |


### <a name="drill-down-filters"></a>Filtri di drill-down

I report CQD presentano diversi filtri di drill-down, che sono potenti strumenti per restringere lo stato attivo delle indagini sulla qualità delle chiamate. Se si seleziona un campo di drill-down, il report apre automaticamente la scheda appropriata e filtra il valore selezionato. Se la scheda include campi di drill-down e ne è selezionato uno, vengono applicati entrambi i set di filtri, restringendo progressivamente il set di dati risultante.

![Diagramma che illustra il flusso del report drill-down.](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Aggiunta e modifica di campi di drill-down

Quando si modifica un report, è possibile specificare campi di drill-down personalizzati usando l'editor di query.

Per iniziare, fare clic **su ...** per il report che si vuole modificare, quindi selezionare **Modifica.**

![Screenshot della modifica di un campo drill-down.](media/qerguide-image-addeditdrilldownfields.png)

Selezionare una dimensione nell'elenco sul lato sinistro dell'editor di query. Fare quindi clic sull'elenco a discesa sotto l'etichetta Passa a e selezionare la scheda e il gruppo di espansione a cui eseguire il drill-through per la dimensione.  Nota: attualmente, la funzionalità di drill-down funziona solo passando a schede diverse. Il supporto per il drill-through a uno specifico espansore verrà aggiunto in un secondo momento. Infine, fare clic **su** Chiudi per salvare le modifiche apportate alla dimensione, quindi fare clic su **Salva** per salvare e chiudere l'editor di query.

![Screenshot della selezione di una dimensione nell'editor di query.](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtri a selezione multipla

Oltre alla funzionalità di drill-down, CQD supporta anche la specifica di filtri con più valori (filtri OR).

Per selezionare più valori di filtro, iniziare aggiungendo un nuovo filtro al report. Fare **+** clic accanto **all'etichetta** Filtri, immettere il nome della dimensione da usare e fare clic su **Aggiungi.**

![Screenshot dell'aggiunta di un filtro a selezione multipla.](media/qerguide-image-addmultiselectfilter.png)

Fare quindi clic **su Cerca** (un'icona a forma di lente di ingrandimento accanto al nuovo filtro). Verranno visualizzati un campo di testo e diverse opzioni, tra cui **Seleziona tutto** e **Inverti.** Immettere un valore e fare clic **su Cerca** accanto al campo per eseguire la ricerca. In alternativa, lasciare vuoto il campo di testo e fare clic **su Cerca** per visualizzare fino alle prime 100 opzioni.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio:  

![Screenshot dell'aggiunta di un filtro di query.](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtri a livello di dashboard
In alcuni report CQD sono stati aggiunti filtri a livello di dashboard, che semplificano il filtro in base ai parametri comuni. Questi filtri vengono visualizzati all'esterno delle normali schede del report e direttamente sotto il filtro Prodotto e si applicano a tutti i filtri nel dashboard.

![Screenshot di un filtro del dashboard.](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtri URL

CQD supporta l'aggiunta di filtri all'URL. In questo modo è facile condividere o aggiungere un segnalibro a una query CQD. È possibile definire parametri nell'URL, ad esempio Mese di tendenza, ID tenant o lingua. È anche possibile aggiungere filtri a livello di prodotto o dashboard all'URL.
L'esclusione dei dati federati dai report CQD è utile per correggere gli edifici gestiti o le reti in cui gli endpoint federati potrebbero influire sui report.

Per aggiungere un filtro, aggiungere quanto segue alla fine dell'URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio:  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Per aggiungere un filtro a livello di dashboard a un URL, tale filtro deve essere presente in CQD come filtro a livello di prodotto o di dashboard. Aggiungere questi filtri all'URL dopo il mese di tendenza e prima dei parametri url:

`filter/DATA_MODEL_NAME|VALUE`

Ad esempio, per applicare un valore di filtro Prodotto di Microsoft Teams, aggiungere quanto segue:

`filter/[AllStreams].[Is%20Teams]|[True]`

L'intero URL sarà simile al seguente:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Per applicare filtri URL con valori a selezione multipla, separare ogni valore con un carattere barra verticale ( | ). Ad esempio:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Se si specifica un nome o un valore non valido, il filtro URL non verrà applicato.


È possibile usare un filtro URL per filtrare ogni report in base a una dimensione specifica. I filtri URL più comuni vengono usati per filtrare i report per escludere la telemetria dei partecipanti federati o concentrarsi solo su Teams o Skype for Business Online. L'esclusione dei dati federati dai report CQD è utile per correggere gli edifici gestiti o le reti in cui gli endpoint federati potrebbero influire sui report.

| Filter         | Descrizione          | Esempio di filtro di query CQD      |
|----------------|----------------------|-------------------------------|
| Nessun valore vuoto   | Alcuni filtri non hanno l'opzione di filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su Uguale o Diverso da, a seconda delle esigenze.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Escludere subnet comuni | Senza un file di edificio valido per separare le reti gestite da quelle non gestite, le reti domestiche verranno incluse nei report. Queste subnet domestiche sono esterne all'ambito di controllo dell'IT e possono essere rapidamente escluse da un report. Le subnet comuni, come definito in questo articolo, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Seconda subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Visualizza solo all'interno  | Consente di filtrare un report in modo che sia gestito (all'interno) o non gestito (esterno). Il modello CQD gestito è già preconfigurato con questi filtri.       | Second Inside Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Come trovare l'ID tenant

L'ID tenant in CQD corrisponde all'ID directory in Azure. Se non si conosce l'ID directory, è possibile trovarlo nel portale di Azure:

1.  Accedere al portale Microsoft Azure:<https://portal.azure.com>

2.  Selezionare **Azure Active Directory**.

3.  In **Gestisci** selezionare **Proprietà.** L'ID tenant si trova nella **casella ID** directory.

È anche possibile trovare l'ID tenant usando PowerShell: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Confronto tra Teams e Skype for Business CQD

Durante la revisione dei dati, potrebbero verificarsi differenze tra Teams e Skype for Business. Alcuni motivi:
- Differenze nei meccanismi per garantire prestazioni e affidabilità:
  - Teams la riconnessione automatica e il roaming veloce. Skype for Business non lo fa.
  - Teams gestione dinamica della larghezza di banda. Skype for Business non lo fa.
- Differenze negli [intervalli di indirizzi IP](Office-365-URLs-IP-address-ranges.md) tra Teams e Skype for Business. Gli Teams IP sono più nuovi, il che potrebbe causare problemi di connettività nel firewall.



## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload tenant e edificio](CQD-upload-tenant-building-data.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione dei flussi in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)
