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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Scopri i dati e i report disponibili in Microsoft Call Quality Dashboard (CQD).
ms.openlocfilehash: 4b96f64f7f182c0d4c95796358b20b38d8c726b4
ms.sourcegitcommit: c1aaf1f81c07c0956095b5bd4cb241b1de67b189
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "46897846"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>Dati e report in Call Quality Dashboard (CQD)

Microsoft Call Quality Dashboard (CQD) usa un feed di dati NRT (Near-Real-Time). I record di chiamata sono disponibili in Call Call Call Entro 30 minuti dalla fine della chiamata. I record di chiamata dalla pipeline NRT sono disponibili solo per alcuni mesi prima di essere rimossi dal set di dati. 


## <a name="many-ways-to-access-cqd-data"></a>Molti modi per accedere ai dati di CQD

È possibile accedere ai dati di CQD da svariati viali. Scegliere quello più adatto alle proprie esigenze:

|  |  |
|---------|---------|
|Interfaccia di amministrazione di Teams [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)    | I dati di CQD sono inclusi nella pagina Utenti dell'interfaccia di amministrazione di Teams, che mostrano i dati più comuni necessari in un formato di facile lettura.  Non è possibile personalizzare i dati di CQD trovati in **Utenti.**  |
|Portale di CQD [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)     | Report dettagliati e di riepilogo efficace che soddisfano la maggior parte delle esigenze, con filtri drill-through. È anche possibile personalizzare i report nel portale di CQD. <br><br>Ottenere due [modelli di report di CQD](#import-the-cqd-report-templates) per analizzare i dati nel portale di CQD.       |
|Power BI     | Usare query dirette per visualizzare i dati di CQD in Power BI usando [i modelli di Power BI personalizzabili.](CQD-Power-BI-query-templates.md) [Scaricare i modelli di query di Power BI per CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)<br><br>È anche possibile [usare l'API REST per accedere ai dati di CQD](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) tramite Power BI. Usare questo metodo se si vogliono scaricare i dati di CQD in modo da poter lavorarvi offline. Il vantaggio di questo metodo è l'ottimizzazione delle prestazioni, particolarmente utile per grandi set di dati che non sono presenti in Power BI quando si è online.       |
|API di Microsoft Graph     | Accedi ai dati di qualità delle chiamate manualmente usando [l'API Graph.](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta) Si tratta del metodo più complesso, ma offre il maggior controllo e flessibilità nell'analisi dei dati sulla qualità delle chiamate. Ad esempio, se è necessario unirlo con altri dati per l'organizzazione, è possibile usare l'API Graph per creare un modello di dati e incorporare i dati sulla qualità delle chiamate.        |

## <a name="import-the-cqd-report-templates"></a>Importare i modelli di report di CQD

Scarica due modelli curati di [report di CQD](https://aka.ms/qertemplates) (Tutte le reti e Le reti gestite) per iniziare rapidamente a utilizzare CQD. Il modello Tutte le reti, anche se ottimizzato per l'uso con un file di dati dell'edificio, può essere usato durante la raccolta e il caricamento delle informazioni dell'edificio in CQD, come descritto nella sezione successiva.

**Per importare i modelli (. CQDX) in CQD**

1. In CQD selezionare **Detailed Reports** dal menu nella parte superiore della pagina.

2. Nel riquadro sinistro selezionare **Importa.** Passare al primo modello CQDX e selezionare **Apri.**

3. Dopo il caricamento del modello, viene visualizzata una finestra popup con il messaggio "Importazione report completata". 

4. Ripetere i passaggi 2 e 3 per il secondo modello di CQD.

   > [!NOTE]
   > Ogni utente deve importare i modelli di CQD nella propria istanza di CQD. 



## <a name="euii-data"></a>Dati EUII

Per motivi di conformità, i dati delle informazioni identificabili dall'utente finale (EUII, Personally-Identifiable Information o PII) vengono mantenuti solo per 28 giorni. Quando i dati NRT superano il contrassegno di 28 giorni, i campi che contengono euII vengono cancellati, con il risultato di dati NRT senza EUII. I campi che contengono dati UEII sono:

- Indirizzo IP completo
- Indirizzo MAC (Media Access Control)
- Identificatore del set di servizi di base (BSSID)
- URI SIP (Session Initiation Protocol) (solo Skype for Business)
- Nome entità utente (UPN)
- Nome endpoint computer
- User Verbatim Feedback
- ID oggetto (ID oggetto Active Directory dell'utente dell'endpoint)

### <a name="admin-roles-with-and-without-euii-access"></a>Ruoli di amministratore con e senza accesso euii

Questi [ruoli RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) **hanno** accesso EUII:
- Amministratore globale
- Amministratore dei servizi di Teams
- Amministratore delle comunicazioni di Teams
- Tecnico supporto comunicazioni Teams
- Lettore globale
- Amministratore di Skype for Business

Questi ruoli RBAC **non hanno accesso** EUII:
- Lettore di report
- Teams Communications Support Specialist


## <a name="date-controls"></a>Controlli data

CQD supporta i tipi di tendenza distribuzione seguenti:

- 5 giorni
- 7 giorni
- 30 giorni
- 60 giorni
- 90 giorni

Il parametro Url Date accetta un campo Day. I report dei giorni di distribuzione usano le date specificate nel formato AAAA-MM-GG come ultimo giorno della tendenza. Il parametro data URL "00" indica "oggi".

|URL| Data di fine della tendenza del giorno di distribuzione|
|:---|:---|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02/</span>   |Giorno corrente di febbraio 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /2019-02-15/</span>|15 febbraio 2019|
|<span>https:// <cqdv3> /spd/#/Dashboard/ <reportid> /00/</span>        |Giorno corrente|
|||

Per impostazione predefinita, il giorno corrente del mese viene usato come ultimo giorno della tendenza dei giorni di distribuzione.


## <a name="data-available-in-cqd-reports"></a>Dati disponibili nei report di CQD

Il riepilogo predefinito e i report dettagliati di Call Quality Quality possono essere tutto ciò che ti serve per gestire la qualità delle chiamate per la tua organizzazione. Se necessario, è possibile [creare report personalizzati.](#create-custom-detailed-reports) 

Se si vuole usare Power BI per analizzare i dati di CQD, leggere Usare Power BI per analizzare i dati di [CQD per Teams.](CQD-Power-BI-query-templates.md)

|Funzionalità|Report di riepilogo|Report dettagliati|
|:--- |:--- |:--- |
|Metrica di condivisione applicazioni | No | Sì |
|Supporto per le informazioni di tipo Building dei clienti | Sì | Sì |
|Supporto per le informazioni sull'endpoint del cliente | Solo in <span> cqd.teams.microsoft.com<span/> | Solo in <span> cqd.teams.microsoft.com<span/> |
|Supporto per l'analisi drill-down   | No   | Sì   |
|Metriche di affidabilità dei supporti multimediali   | No   | Sì   |
|Report predefiniti   | Sì   | Sì   |
|Report di panoramica   | Sì   | Sì   |
|Set di report per utente   | No   | Sì   |
|Personalizzazione del set di report (aggiunta, eliminazione, modifica di report)   | No   | Sì   |
|Metriche di condivisione dello schermo basata su video   | No   | Sì   |
|Metriche video   | No   | Sì   |
|Quantità di dati disponibili   | Ultimi 12 mesi   | Ultimi 12 mesi   |
|Dati di Microsoft Teams   | Sì   | Sì   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a>Selezionare i dati di prodotto da visualizzare nei report

Nei report Riepilogo e Location-Enhanced puoi utilizzare  l'elenco a discesa Filtro prodotti per visualizzare tutti i dati di prodotto, solo i dati di Microsoft Teams o solo i dati di Skype for Business Online.
  
![Screenshot: mostra le opzioni di controllo del filtro prodotti](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
Nei report dettagliati è possibile usare la dimensione **Is Teams** per filtrare i dati in base ai dati di Microsoft Teams o Skype for Business online.

## <a name="summary-reports"></a>Report di riepilogo

Questi sono i report che vengono visualizzati nel dashboard di CQD quando si accede a CQD per la prima volta. Consentono di esaminare a colpo d'occhio le tendenze della qualità con rapporti giornalieri, mensili e di tabella per identificare le subnet di qualità scarsa. 

| TAB | Descrizione |
|---------|---------|
|Qualità complessiva delle chiamate     | Aggregazione delle altre 3 schede.       |
|Server - Client     |Dettagli dei flussi tra endpoint server e client.        |
|Client - Client     |Dettagli dei flussi tra due endpoint client.        |
|Sla sulla qualità vocale     |Informazioni sulle chiamate incluse nel contratto di servizio sulla qualità [vocale](https://go.microsoft.com/fwlink/p/?linkid=846252)di Skype for Business.        |

### <a name="overall-call-quality-tab"></a>Scheda Overall Call Quality

Utilizza i dati in questa scheda per valutare lo stato e le tendenze della qualità delle chiamate in base al numero dei flussi e alle percentuali di qualità scarsa. La legenda nell'angolo in alto a destra mostra il colore e gli elementi visivi che rappresentano queste metriche.
  
![Screenshot: visualizzare la scheda Qualità chiamata](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
I flussi sono classificati in tre gruppi: Buono, Scarso e Non classificato. Sono inoltre disponibili valori  *calcolati*  per la percentuale di flussi classificati di qualità scarsa rispetto *al*  conteggio totale dei flussi classificati. Poiché % scarsi = flussi scarsi/ (flussi scarsi + flussi  *buoni) * 100,* la *%* scarsa non è influenzata dalla presenza di più flussi non classificati. Per informazioni su ciò che classifica un flusso come scadente o buono, fare riferimento a [Classificazione di flusso in Call Quality Dashboard.](stream-classification-in-call-quality-dashboard.md)
  
Usare la scala a sinistra per misurare i valori del conteggio dei flussi.
  
![Screenshot: mostra i valori per il conteggio dei flussi](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
Usare la scala a destra per misurare i valori di % scarsi.
  
![Screenshot: mostra i valori di % scarsi](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
È anche possibile ottenere i valori numerici effettivi posizionando il puntatore del mouse su una barra.
  
> [!NOTE]
> L'esempio seguente deriva da un set di dati di esempio molto piccolo e i valori non sono realistici per una distribuzione effettiva.
  
![Screenshot: mostra il mouse usato per accedere ai dati](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
Il volume complessivo dei flussi aiuta a determinare la pertinente percentuale di flussi calcolati. Minore è il volume complessivo dei flussi, meno affidabili sono i valori delle percentuali segnalate come scarsi.
  
### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client schede e Client-Client testo

Queste due schede forniscono dettagli sui flussi che hanno avuto luogo negli scenari endpoint-endpoint. La Server-Client video contiene quattro sezioni comprimibili che rappresentano quattro scenari in cui si scorrono i flussi multimediali.
  
- Cablata interno
- Cablata esterna
- WiFi Inside
- WiFi Outside

Allo stesso modo, la Client-Client contiene cinque sezioni comprimibile:

- Cablata interno - Cablata all'interno
- Cablata interno - Cablata all'esterno
- Cablata esterna - Cablata all'esterno
- Cablata interno - WiFi Interno
- Cablata interno - WiFi Esterno

#### <a name="inside-versus-outside"></a>Interno ed esterno

CQD classifica un flusso  come Interno *o* Esterno usando le informazioni di tipo Building, se presente. Gli endpoint di ogni flusso sono associati a un indirizzo subnet. Se la subnet è presente nell'elenco delle subnet contrassegnate come InsideCorp nelle informazioni sull'edificio caricate, viene *considerata* interna. Se le informazioni di tipo Building non sono ancora state caricate, Inside Test classifica sempre i flussi come *Outside.* 

Il test interno di uno scenario Server-Client considera solo l'endpoint client. Poiché i server sono sempre esterni al punto di vista dell'utente, questo non viene seguito nel test.
  
#### <a name="wired-versus-wifi"></a>Cablata o WiFi

Come indicano i nomi, i criteri di classificazione si basano sul tipo di connessioni client. Il server è sempre cablato e non è incluso nel calcolo. In un determinato flusso, se uno dei due endpoint è connesso a una rete WiFi, CQD lo classifica come WiFi.

> [!NOTE]
> Dato uno stream, se uno dei due endpoint è connesso a una rete WiFi, viene classificato come WiFi in CQD.
  
  
## <a name="tenant-data-information"></a>Informazioni sui dati del tenant

Il dashboard dei report di riepilogo di CQD include una pagina caricamento dati **tenant,** accessibile selezionando Caricamento dati **tenant** dal menu delle impostazioni nell'angolo in alto a destra. Questa pagina viene usata per gli amministratori per caricare le proprie informazioni, ad esempio:

- Mappa di informazioni geografiche e indirizzi IP.
- Mappa di ogni punto di accesso wireless e del relativo indirizzo MAC.
- Mappa di Endpoint - Make/Model/Type dell'endpoint e così via
  
È consigliabile caricare i dati del tenant, dell'edificio e della posizione in modo che CQD possa includere queste informazioni nei report. Se questi dati non sono già stati caricati, leggere [Caricare il tenant e creare i dati.](CQD-upload-tenant-building-data.md) 


## <a name="detailed-reports"></a>Report dettagliati

| Nome | Descrizione |
|---------|---------|
|Location-Enhanced report     |Mostra le tendenze della qualità in base alle informazioni sulla posizione. Questo report viene visualizzato solo se sono [stati caricati i dati del tenant.](CQD-upload-tenant-building-data.md)        |
|Report sull'affidabilità     |Include report audio, video, di condivisione dello schermo basata su video (VBSS) e di condivisione app.        |
|Report sulla qualità dell'esperienza     |Qualità audio e affidabilità per tutti i clienti e i dispositivi, comprese le sale riunioni. Questi report sono una versione "slimmed" dei modelli [CQD](https://aka.ms/QERtemplates)scaricabili, incentrato sulle aree chiave per l'analisi della qualità audio e dell'affidabilità.         |
|Report drill-down della qualità     | Drill-down: data per area geografica, località, subnet, ora e utenti.        |
|Report drill-down degli errori     | Drill-down: data per area geografica, località, subnet, ora e utenti.        |
|Valuta i rapporti sulle chiamate     |Analizzare le classificazioni delle chiamate degli utenti in base all'area geografica, alla località o in base all'utente. Include feedback dettagliato.         |
|Report dell'help desk     |I report dell'help desk consentono di esaminare i dati delle chiamate e delle riunioni per singoli utenti, gruppi di utenti o tutti. Incorporando i dati di edificio ed EUII, questi report aiutano a identificare i possibili problemi di sistema in base al percorso di rete, ai dettagli delle conferenze, ai dispositivi o al firmware.         |
|Report delle versioni client     |Riepilogo delle versioni client: visualizzare il conteggio di sessioni e utenti per ogni versione dell'app client<br><br>Versione client per utente: visualizzare i nomi utente per ogni versione dell'app client <br><br>I filtri predefiniti per tipo di prodotto e client consentono di concentrare le versioni su client specifici.         |
|Report endpoint     |Mostra la qualità della chiamata dagli endpoint della macchina (modellazione e make-to-computer). Questi report includono i dati di compilazione, se sono stati caricati.         |


## <a name="create-custom-detailed-reports"></a>Creare report dettagliati personalizzati

Se i report di CQD predefiniti non soddisfano le proprie esigenze, usare queste istruzioni per creare un report personalizzato. In alternativa, a partire da gennaio 2020, usare i report di Power BI per [CQD. ](cqd-power-bi-query-templates.md)

Nell'elenco a discesa dei report nella parte superiore della schermata visualizzata nella schermata di accesso ai report di riepilogo selezionare Report dettagliati \( e quindi  \) **Nuovo.**  Fare **clic su** Modifica in un report per visualizzare l'editor di query. Ogni report viene sottoposto a backup da una query nel cubo. Un report è una visualizzazione dei dati restituiti dalla query. L'editor di query consente di modificare queste query e le opzioni di visualizzazione del report.

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi caricamenti di tipo Building verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di tipo Building, è consigliabile scaricare il file corrente e ricaricarlo per identificare eventuali sovrapposizioni e risolvere il problema prima di caricarlo di nuovo. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare la mappatura errata delle subnet agli edifici nei report. Alcune implementazioni di VPN non riportano in modo accurato le informazioni sulla subnet. Quando si aggiunge una VPN al file dell'edificio, invece di una voce per la subnet, è consigliabile aggiungere voci separate per ogni indirizzo nella VPN come rete a 32 bit separata. Ogni riga può avere gli stessi metadati dell'edificio. Ad esempio, invece di una riga per 172.16.18.0/24, si dovrebbero avere 256 righe, con una riga per ogni indirizzo tra 172.16.18.0/32 e 172.16.18.255/32, incluse.
>
> La colonna VPN è facoltativa e viene impostata per impostazione predefinita su 0.  Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da quella riga sarà completamente espansa per corrispondere a tutti gli indirizzi IP all'interno della subnet.  Usare questa opzione con moderamento e solo per le VPN, perché la piena espansione di queste subnet avrà un impatto negativo sui tempi delle query per le query che implicano l'utilizzo di dati di tipo building.

Posizionare il punto sui grafici a barre e le linee di tendenza nel report per visualizzare valori dettagliati. Il report con lo stato attivo mostrerà il menu delle azioni: **Modifica,** **Clona,** Elimina, **Scarica** ed Esporta albero **report.**



## <a name="query-filters"></a>Filtri di query

I filtri di query vengono implementati usando l'editor di query in CQD. Questi filtri vengono usati per ridurre il numero di record restituiti da CQD, riducendo così al minimo le dimensioni complessive del report e i tempi delle query. Questa opzione è particolarmente utile per filtrare le reti non gestite. I filtri elencati nella tabella seguente usano espressioni regolari (RegEx).


| Filter         | Descrizione          | Esempio di filtro query di CQD      |
|----------------|----------------------|-------------------------------|
| Nessun valore vuoto   | Alcuni filtri non hanno l'opzione per filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su Uguale o Diverso da, a seconda delle esigenze.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Escludere subnet comuni | Senza un file di edificio valido da separare le reti gestite da quelle non gestite, nei report verranno incluse le reti domestiche. Queste subnet domestiche sono al di fuori dell'ambito di controllo dell'IT e possono essere rapidamente escluse da un report. Le subnet comuni, come definito in questa guida, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Visualizza solo all'interno  | Consente di filtrare un report in modo che sia gestito (all'interno) o non gestito (all'esterno). Il modello CQD gestito è già preconfigurato con questi filtri.       | Second Inside Corp = Inside        |

## <a name="report-filters"></a>Filtri rapporto

Usare i filtri di report di CQD per limitare l'interesse delle indagini. Usare i filtri rapporto aggiungendo un filtro al report con rendering nell'editor di query o direttamente nel report. I filtri rapporto seguenti vengono usati in tutti [i modelli di CQD.](https://aka.ms/QERtemplates)


| Filter     | Descrizione                            | Esempio di filtro rapporto di CQD         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Iniziare con l'anno e poi con il mese. | 2017-10                           |
| Alfabetico | Filtra per qualsiasi carattere alfabetico. | [a-z]                             |
| Numerico    | Filtra per qualsiasi carattere numerico.    | [0-9]                             |
| Percentuale | Filtra per una percentuale.              | ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) |


### <a name="drill-down-filters"></a>Filtri drill-down

I report di Call Quality Quality Report presentano diversi filtri drill-down, che sono potenti strumenti per limitare l'attenzione delle indagini sulla qualità delle chiamate. Se si seleziona un campo drill-down, il report apre automaticamente la scheda appropriata e filtra il valore selezionato. Se in questa scheda sono presenti campi drill-down propri e se ne seleziona uno, vengono applicati entrambi i set di filtri, restringendo progressivamente il set di dati risultante.

![Diagramma che illustra il flusso del report drill-down](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a>Aggiunta e modifica di campi drill-down

Quando si modifica un report, è possibile specificare campi drill-down personalizzati usando l'editor di query.

Per iniziare, fare clic **su ...** per il report da modificare, quindi seleziona **Modifica.**

![Screenshot della modifica di un campo drill-down](media/qerguide-image-addeditdrilldownfields.png)

Selezionare una dimensione nell'elenco a sinistra dell'editor di query. Quindi fare clic sull'elenco a discesa sotto l'etichetta Passa **a** e selezionare la scheda e il gruppo di espansione di cui si vuole eseguire il drill-through per la dimensione. Nota: Attualmente, la funzionalità di drill-down funziona solo passando a schede diverse. Il supporto per il drill-down a uno specifico espanditore verrà aggiunto in un secondo momento. Infine, fare **clic su Chiudi** per salvare le modifiche apportate alla dimensione, quindi fare clic su **Salva** per salvare e chiudere l'editor di query.

![Screenshot della selezione di una dimensione nell'editor di query](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>Filtri a selezione multipla

Oltre alla funzionalità di drill-down, CQD supporta anche l'impostazione di filtri con più valori (filtri OR).

Per selezionare più valori di filtro, iniziare aggiungendo un nuovo filtro al report. Fare **+** clic accanto **all'etichetta** Dei filtri, immettere il nome della dimensione da usare e fare clic su **Aggiungi.**

![Screenshot dell'aggiunta di un filtro a selezione multipla](media/qerguide-image-addmultiselectfilter.png)

Quindi, fare **clic su Cerca** (un'icona a forma di lente di ingrandimento accanto al nuovo filtro). Verranno visualizzati un campo di testo e diverse opzioni, tra cui Seleziona **tutto** e **Inverti.** Immettere un valore e fare clic **su Cerca** accanto al campo per eseguire la ricerca. In alternativa, lasciare vuoto il campo di testo e fare clic **su** Cerca per visualizzare le prime 100 opzioni.

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio:  

![Screenshot dell'aggiunta di un filtro di query](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>Filtri a livello di dashboard
In alcuni report di Dashboard Dashboard sono stati aggiunti filtri a livello di dashboard, che consentono di filtrare facilmente in base a parametri comuni. Questi filtri vengono visualizzati all'esterno delle normali schede dei report e direttamente sotto il filtro Prodotto e vengono applicati a tutti i filtri nel dashboard.

![Screenshot di un filtro del dashboard](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>Filtri URL

CQD supporta l'aggiunta di filtri all'URL. In questo modo è facile condividere o aggiungere un segnalibro a una query CQD. È possibile definire parametri nell'URL, ad esempio Mese di tendenza, ID tenant o lingua. È anche possibile aggiungere filtri a livello di prodotto o dashboard all'URL.
L'esclusione dei dati federati dai report di CQD è utile per correggere gli edifici gestiti o le reti in cui gli endpoint federati potrebbero influire sui report.

Per aggiungere un filtro, aggiungere quanto segue alla fine dell'URL:

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Esempio:  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

Per aggiungere un filtro a livello di dashboard a un URL, tale filtro deve essere in CQD come filtro a livello di prodotto o dashboard. Aggiungere questi filtri all'URL dopo il mese di tendenza e prima dei parametri dell'URL:

`filter/DATA_MODEL_NAME|VALUE`

Ad esempio, per applicare un valore di filtro Prodotto di Microsoft Teams, aggiungere quanto segue:

`filter/[AllStreams].[Is%20Teams]|[True]`

L'intero URL sarà simile al seguente:

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

Per applicare filtri URL con valori di selezione multipla, separare ogni valore con una barra verticale (| ). Ad esempio:

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

Se si specifica un nome o un valore non valido, il filtro url non verrà applicato.


È possibile usare un filtro URL per filtrare ogni report per una dimensione specifica. I filtri url più comuni vengono usati per filtrare i report per escludere la telemetria dei partecipanti federati o per concentrarsi solo su Teams o Skype for Business online. L'esclusione dei dati federati dai report di CQD è utile per correggere gli edifici gestiti o le reti in cui gli endpoint federati potrebbero influire sui report.

| Filter         | Descrizione          | Esempio di filtro query di CQD      |
|----------------|----------------------|-------------------------------|
| Nessun valore vuoto   | Alcuni filtri non hanno l'opzione per filtrare i valori vuoti. Per filtrare manualmente i valori vuoti, usare l'espressione vuota e impostare il filtro su Uguale o Diverso da, a seconda delle esigenze.      | Second Building Name \<\> \^ \\ s\*\$                       |
| Escludere subnet comuni | Senza un file di edificio valido da separare le reti gestite da quelle non gestite, nei report verranno incluse le reti domestiche. Queste subnet domestiche sono al di fuori dell'ambito di controllo dell'IT e possono essere rapidamente escluse da un report. Le subnet comuni, come definito in questo articolo, sono 10.0.0.0, 192.168.1.0 e 192.168.0.0. | Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0 |
| Visualizza solo all'interno  | Consente di filtrare un report in modo che sia gestito (all'interno) o non gestito (all'esterno). Il modello CQD gestito è già preconfigurato con questi filtri.       | Second Inside Corp = Inside        |


#### <a name="how-to-find-your-tenant-id"></a>Come trovare l'ID tenant

L'ID tenant in CQD corrisponde all'ID directory in Azure. Se non conosci il tuo ID directory, puoi trovarlo nel portale di Azure:

1.  Accedere al portale di Microsoft Azure: <https://portal.azure.com>

2.  Selezionare **Azure Active Directory.**

3.  In **Gestisci** selezionare **Proprietà.** L'ID tenant è nella **casella ID** directory.

È anche possibile trovare l'ID tenant con PowerShell: 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>Confronto tra i dati CQD di Teams e Skype for Business

Anche all'interno dell'ultimo CQD (cqd.teams.microsoft.com), vedrai le differenze nei dati tra Teams e Skype for Business. Alcuni motivi:
- Differenze nei meccanismi per garantire prestazioni e affidabilità:
  - Teams ha la riconnessione automatica e il roaming veloce. Non è così in Skype for Business.
  - Teams ha una gestione dinamica della larghezza di banda. Non è così in Skype for Business.
- Differenze negli [intervalli di indirizzi IP](Office-365-URLs-IP-address-ranges.md) tra Teams e Skype for Business. Gli intervalli IP di Teams sono più nuovi, il che potrebbe causare problemi di connettività al firewall.

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a>Aprire CQD dal portale legacy di Skype for Business

![Icona del logo Di Skype for Business ](media/sfb-logo-30x30.png) **Utilizzando il portale legacy di Skype for Business**

1. Accedere all'organizzazione di Office 365 con un  account di amministratore e quindi selezionare il riquadro Amministratore per aprire l'interfaccia di amministrazione.

2. Nel riquadro sinistro, in **Interfaccia di** amministrazione, selezionare **Microsoft Teams** per aprire l'interfaccia di amministrazione di Teams.

3. Nell'interfaccia di amministrazione di Teams, selezionare **Portale legacy** nel riquadro sinistro, selezionare **Strumenti,** quindi selezionare Call Quality Dashboard di Skype for **Business Online.**

   ![Screenshot: Selezionare Call Quality Dashboard](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. Nella pagina visualizzata accedere con l'account di amministratore globale e quindi specificare le credenziali dell'account quando richiesto.

Dopo il primo accesso, CQD inizierà a raccogliere ed elaborare i dati. 

> [!IMPORTANT]
> A partire da dicembre 2019 è ancora possibile accedere alla versione precedente di CQD (cqd.lync.com), anche se il portale legacy offre un collegamento all'ultima versione di CQD (cqd.teams.microsoft.com). Alla fine, la versione precedente di CQD verrà rimossa. A partire dal 1° luglio 2020, la versione precedente di CQD accede ai dati dal nuovo CQD ( e non è più possibile esportare i dati di edifici https://CQD.teams.microsoft.com) e report. Alla fine del 2020, il vecchio CQD verrà disattivato e non sarà più possibile accedervi.


## <a name="related-topics"></a>Argomenti correlati

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md)

[Usare Call Quality Quality Call per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md)
