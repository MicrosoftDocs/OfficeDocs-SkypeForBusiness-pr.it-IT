---
title: Caricare i dati del tenant e della creazione in dashboard qualità chiamata (Call Quality Dashboard)
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Informazioni su come caricare i dati del tenant e della creazione in dashboard qualità chiamata (Call Quality Dashboard).
ms.openlocfilehash: 86ff0cba51b5c1cb291f7b885cf5baadf9744d4a
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584065"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Caricare i dati del tenant e della creazione in dashboard qualità chiamata (Call Quality Dashboard)


Per ottenere il massimo da Dashboard di qualità delle chiamate (Call Quality Dashboard), è consigliabile caricare il tenant e creare dati. Esistono due tipi di file di dati tenant, [Building](#upload-building-data-file) e [endpoint](#endpoint-data-file).

[Qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)è possibile scaricare un modello di dati tenant di esempio. Per assistenza per la creazione di mapping, leggere [creare una mappa dell'edificio per Call Quality dashboard](CQD-building-mapping.md).

Nel dashboard report di riepilogo di Call Quality Dashboard selezionare **Carica dati tenant** dal menu **Impostazioni** di Call Quality Dashboard (icona a ingranaggio nella parte superiore di Call Quality Dashboard). Da qui gli amministratori possono caricare le informazioni relative all'edificio e all'endpoint dell'organizzazione, ad esempio mappatura di indirizzi IP e informazioni geografiche, mappatura di ogni punto di accesso wireless e relativo indirizzo MAC e così via.

1. Aprire Call Quality Dashboard (nell'interfaccia di amministrazione di teams o at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ), quindi selezionare l'icona dell'ingranaggio nell'angolo in alto a destra e scegliere **Carica dati tenant** dalla pagina **report di riepilogo** .

   ![Screenshot della finestra di dialogo visualizzata durante il caricamento dei dati](media/qerguide-image-tenantdataupload.png)
    
2. In alternativa, se è la prima volta che visiti Call Quality dashboard, ti verrà chiesto di caricare i dati dell'edificio. È possibile selezionare **carica ora** per passare rapidamente alla pagina di **caricamento dei dati del tenant** .

   ![Screenshot del banner che informa un utente di caricare i dati dell'edificio](media/qerguide-image-buildingdatauploadbanner.png)

3. Nella pagina **caricamento dati tenant** selezionare **Sfoglia** per scegliere un file di dati.

4. Dopo aver selezionato un file di dati, specificare **Data di inizio** e, facoltativamente, specificare una data di fine.

5. Dopo aver selezionato **Data inizio**, selezionare **carica** per caricare il file in Call Quality dashboard. <br><br>Prima che il file venga caricato, viene convalidato. Se la convalida non riesce, viene visualizzato un messaggio di errore che richiede di correggere il file. La figura seguente mostra un errore che si verifica quando il numero di colonne nel file di dati non è corretto.

   ![Esempio di finestra di dialogo in cui viene visualizzato un errore di caricamento dei dati dell'edificio](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se non si verificano errori durante la convalida, il caricamento del file avrà esito positivo. È quindi possibile **visualizzare il file** di dati caricati nella tabella uploads, che mostra l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.

> [!NOTE]
> Per completare l'elaborazione del file di costruzione, possono essere necessarie fino a quattro ore. <br><br> Se è già stato caricato un file di costruzione ed è necessario aggiungere subnet che potrebbero essere state perse o escluse, modificare il file originale aggiungendo le nuove subnet, rimuovere il file corrente e caricare di nuovo il file appena modificato. In Call Quality dashboard può essere presente un solo file di dati dell'edificio attivo. 


## <a name="upload-building-data-file"></a>Caricare un file di dati dell'edificio

Il primo tipo di file di dati del tenant in Call Quality dashboard è il file di dati dell' **edificio** . La colonna subnet viene derivata espandendo la colonna Network + NetworkRange, quindi unendo la colonna subnet alla prima subnet o alla seconda colonna subnet del record di chiamata per visualizzare le informazioni su edifici, città, Paesi o aree geografiche. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:
  
- Il file deve essere un file TSV (le colonne sono separate da una TABULAzione) o un file CSV (le colonne sono separate da una virgola).
- Il file di dati non include una riga di intestazione di tabella. La prima riga del file di dati dovrebbe essere dati reali, non etichette di intestazione come "rete".
- I tipi di dati nel file possono essere solo stringa, Integer o Boolean. Per il tipo di dati Integer, il valore deve essere un valore numerico. I valori booleani devono essere 0 o 1.
- Se una colonna usa il tipo di dati stringa, un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore di stringa vuoto.
- Devono essere presenti 14 colonne per ogni riga, ogni colonna deve avere il tipo di dati appropriato e le colonne devono essere nell'ordine elencato nella tabella seguente (delimitato da una tabulazione o da una scheda):

**Creare un formato di file di dati**

| Nome colonna        | Tipo di dati | Esempio                   | Linee guida              |
|--------------------|-----------|---------------------------|-----------------------|
| NetworkIP          | Stringa    | 192.168.1.0               | Obbligatorio              |
| NetworkName        | Stringa    | USA/Seattle/SEATTLE-SEA-1 | Obbligatorio<sup>1</sup>  |
| NetworkRange       | Numero    | 26                        | Obbligatorio              |
| Buildingname       | Stringa    | SEATTLE-SEA-1             | Obbligatorio<sup>1</sup>  |
| OwnershipType      | Stringa    | Contoso                   | Facoltativo              |
| BuildingType       | Stringa    | Terminazione IT            | Facoltativo              |
| BuildingOfficeType | Stringa    | Ingegneria               | Facoltativo              |
| Città               | Stringa    | Seattle                   | Consigliato           |
| ZipCode            | Stringa    | 98001                     | Consigliato           |
| Paese            | Stringa    | NOI                        | Consigliato           |
| Stato              | Stringa    | WA                        | Consigliato           |
| Area             | Stringa    | MSUS                      | Consigliato           |
| InsideCorp<sup>2</sup>         | Bool      | 1             | Obbligatorio              |
| ExpressRoute<sup>3</sup>       | Bool      | 0             | Obbligatorio              |
| VPN                | Bool      | 0                         | Facoltativo              |

<sup>1</sup> Anche se non richiesto da Call Quality dashboard, i modelli sono configurati per visualizzare il nome dell'edificio e della rete.

<sup>2</sup> Questa impostazione può essere usata per riflettere se la subnet si trova o meno all'interno della rete aziendale. È possibile personalizzare l'utilizzo per altri scopi.

<sup>3</sup> Questa impostazione può essere usata per riflettere se la rete usa Azure ExpressRoute. È possibile personalizzare l'utilizzo per altri scopi.  

**Riga di esempio:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una SuperNet (combinazione di più subnet con un unico prefisso di routing). Tutti gli upload di nuovi edifici verranno controllati per gli intervalli sovrapposti. Se in precedenza è stato caricato un file di costruzione, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e correggere il problema prima del caricamento. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare l'errata mappatura delle subnet agli edifici nei report. Alcune implementazioni VPN non segnalano in modo accurato le informazioni sulla subnet. Si consiglia di aggiungere voci separate per ogni indirizzo della subnet VPN in una rete a 32 bit separata per l'aggiunta di una subnet VPN al file di compilazione, anziché una voce per la subnet. Ogni riga può avere gli stessi metadati dell'edificio. Ad esempio, invece di una riga per 172.16.18.0/24, dovresti avere 256 righe, con una riga per ogni indirizzo compreso tra 172.16.18.0/32 e 172.16.18.255/32, incluso.
>
> La colonna VPN è facoltativa e sarà impostata su 0. Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da tale riga verrà espansa completamente in modo che corrisponda a tutti gli indirizzi IP nella subnet.  Usare questo metodo con parsimonia e solo per le subnet VPN poiché l'espansione completa di queste subnet avrà un impatto negativo sugli orari delle query per le query che coinvolgono i dati dell'edificio.


### <a name="supernetting"></a>SuperNet

Puoi usare il Supernetting, comunemente denominato CIDR (Inter-Domain Routing), al posto della definizione di ogni subnet. Un *SuperNet* è una combinazione di più subnet che condividono un unico prefisso di routing. Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo supernetted. Il Supernetting è supportato, ma non è consigliabile usarlo.

Ad esempio, l'edificio di marketing di Contoso è costituito dalle subnet seguenti:

-   10.1.0.0/24-primo piano
-   10.1.1.0/24-secondo piano
-   10.1.2.0/24-terzo piano
-   10.1.3.0/24-quarto piano

Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo supernetted, in questo esempio 10.1.0.0/22.

-   Network = 10.1.0.0
-   Intervallo di rete = 22

Ecco alcuni aspetti da considerare prima di implementare il Supernetting:

-   Il Supernetting può essere usato solo in un mapping della subnet con una maschera da 8 bit a 28 bit.

-   La Supernetting richiede meno tempo in anticipo, ma viene a scapito della riduzione della ricchezza dei dati. Supponiamo che ci sia un problema di qualità che coinvolge la subnet 10.1.2.0. Se è stata implementata la Supernetting, non si sa dove si trova l'edificio della subnet o quale tipo di rete è (ad esempio, un Lab). Se sono state definite tutte le subnet per un edificio e sono state caricate le informazioni sulla posizione del piano, è possibile vedere la distinzione.

-   È importante assicurarsi che l'indirizzo della Supernetting sia corretto e che non sia necessario intercettare subnet indesiderate.

-   È abbastanza comune trovare 192.168.0.0 nei dati. Per molte organizzazioni, questo indica che l'utente è in casa. Per altri utenti, si tratta dello schema di indirizzi IP per un ufficio satellite. Se l'organizzazione ha uffici che usano questa configurazione, non includerla nel file dell'edificio, perché è difficile distinguere tra le reti domestiche e quelle interne usando [subnet comuni](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare un SuperNet. Tutti i caricamenti dei file di dati della nuova costruzione verranno controllati per gli intervalli sovrapposti. Se in precedenza è stato caricato un file di costruzione, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e risolvere il problema. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare l'errata mappatura delle subnet agli edifici nei report.

### <a name="vpn"></a>VPN

I dati di qualità dell'esperienza (QoE) che i client inviano a Microsoft 365 o Office 365, da cui vengono provenienti i dati di Call Quality dashboard, includono un contrassegno VPN. Call Quality dashboard vedrà questo come la prima VPN e le seconde dimensioni VPN. Tuttavia, questo contrassegno si basa sulla creazione di report dei fornitori VPN in Windows che la scheda di rete VPN registrata è un adattatore di accesso remoto. Non tutti i fornitori di VPN registrano correttamente gli adapter di accesso remoto. Per questo motivo, potresti non essere in grado di usare i filtri di query VPN predefiniti. Esistono due approcci per ospitare subnet VPN nel file di informazioni sull'edificio:

- Definire un **nome di rete** immettendo "VPN" in questo campo per le subnet VPN.

  ![Schermata del report QCD che mostra la VPN tramite il nome di rete](media/qerguide-image-vpnnetworkname.png)

- Definire un **nome dell'edificio** immettendo "VPN" in questo campo per le subnet VPN.

  ![Schermata del report QCD che mostra la VPN usando il nome dell'edificio](media/qerguide-image-vpnbuildingname.png)

> [!IMPORTANT]
> Alcune implementazioni VPN non segnalano in modo accurato le informazioni sulla subnet. Se questo problema si verifica nella creazione di report, è consigliabile aggiungere voci separate per ogni indirizzo della subnet VPN in una rete separata a 32 bit quando si aggiunge una subnet VPN al file di compilazione. Ogni riga può avere gli stessi metadati dell'edificio. Ad esempio, invece di una riga per 172.16.18.0/24, hai 253 righe, con una riga per ogni indirizzo da 172.16.18.1/32 a 172.16.18.254/32, incluso.


> [!NOTE]
> Le connessioni VPN sono note per non identificare la connessione di rete come cablata quando la connessione Internet sottostante è wireless. Quando si esamina la qualità tramite connessioni VPN, non è possibile supporre che il tipo di connessione sia stato accuratamente identificato.


## <a name="endpoint-data-file"></a>File di dati endpoint

L'altro tipo di file di dati del tenant di Call Quality dashboard è il file di dati dell' **endpoint** . I valori della colonna vengono usati nel primo nome dell'endpoint client del record di chiamata o nella seconda colonna nome endpoint client per visualizzare le informazioni sul tipo, il modello o la marca dell'endpoint. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:

- Il file deve essere un file TSV (le colonne sono separate da una TABULAzione) o un file CSV (le colonne sono separate da una virgola).
- Il contenuto del file di dati non include le intestazioni di tabella. La prima riga del file di dati dovrebbe essere dati reali, non un'etichetta di intestazione come "EndpointName".
- Tutte e sei le colonne usano solo il tipo di dati stringa. La lunghezza massima consentita è di 64 caratteri.
- Un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore di stringa vuoto.
- EndpointName deve essere univoco, altrimenti il caricamento non riesce. Se è presente una riga duplicata o due righe che usano lo stesso EndpointName, il conflitto causerà l'Unione errata.
- EndpointLabel1, EndpointLabel2 e EndpointLabel3 sono etichette personalizzabili. Possono essere stringhe o valori vuoti, ad esempio "reparto IT designato 2018 laptop" o "asset tag 5678".
- Devono essere presenti sei colonne per ogni riga e le colonne devono essere nell'ordine seguente:

  **Ordine dei campi:**

EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Riga di esempio:**

`1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  



## <a name="update-a-building-file"></a>Aggiornare un file di edificio

Durante la raccolta di informazioni sulla creazione e la subnet, gli amministratori spesso caricano il file di costruzione in più iterazioni nel tempo, aggiungendo nuove subnet e le relative informazioni edilizie Man mano che diventano disponibili. Quando si verifica questo problema, è necessario ricaricare il file della costruzione. Questo processo è simile al caricamento iniziale, come descritto nella sezione precedente, con alcune eccezioni, come indicato nella sezione seguente.

> [!Important]
> Solo un file di compilazione può essere attivo alla volta. Più file di compilazione non sono cumulativi.

## <a name="add-net-new-subnets"></a>Aggiungere nuove sottoreti nette

In alcuni casi è necessario aggiungere nuove subnet a Call Quality dashboard che in origine non facevano parte della topologia di rete. Per aggiungere nuove subnet nette, eseguire le operazioni seguenti nella pagina **caricamento dati tenant** in Call Quality Dashboard:

2.  Scaricare il file originale, se non si ha già una copia aggiornata.
1.  Rimuovere il file corrente in Call Quality dashboard.
1.  Modificare il file di costruzione originale e specificare una data di fine che si verifica almeno un giorno prima dell'acquisizione delle nuove subnet nette.
1.  Aggiungere le nuove subnet nette al file di costruzione originale.
1.  Caricare il file di costruzione appena modificato e impostare la data di inizio per un giorno dopo la fine del file di costruzione precedente.

## <a name="add-missing-subnets"></a>Aggiungere subnet mancanti

Dopo aver caricato le informazioni sulla creazione per le reti gestite, ogni rete gestita dovrebbe avere un'associazione di edifici. Tuttavia, questo non è sempre il caso; in genere, vengono perse alcune subnet. Per trovare queste reti mancanti, esaminare il **report della subnet mancante** nella pagina **report sulla qualità della** relazione tra esperienze in Call Quality dashboard. In questo modo vengono presentate tutte le subnet con 10 o più flussi audio non definiti nel file di dati dell'edificio e contrassegnati come esterni. Verificare che non ci siano reti gestite in questo elenco. Se mancano sottoreti, eseguire la procedura seguente per aggiornare il file di dati della costruzione originale e caricarlo di nuovo in Call Quality dashboard.

1. Accedere alla pagina **caricamento dati tenant** in Call Quality dashboard.
1. Scaricare il file originale, se non si ha già una copia aggiornata.
1. Rimuovere il file corrente in Call Quality dashboard.
1. Aggiungere le nuove subnet al file originale.
1. Caricare il file di costruzione. Assicurati di impostare la data di inizio su almeno otto mesi prima che Call Quality dashboard elabori i dati cronologici.


> [!IMPORTANT]
> È necessario aggiungere l'ID tenant come filtro di query per il **secondo ID tenant** al report per filtrare il report per visualizzare solo i dati del tenant dell'organizzazione. In caso contrario, il report mostrerà subnet federate.

> [!NOTE] 
> Assicurarsi di regolare il filtro rapporto mese-anno nel mese corrente. Selezionare **modifica**e regolare il filtro rapporto **mese-anno** per salvare il nuovo mese predefinito.


## <a name="related-topics"></a>Argomenti correlati

[Creare una mappa dell'edificio per Call Quality dashboard](CQD-building-mapping.md)

[Migliorare e monitorare la qualità delle chiamate per i team](monitor-call-quality-qos.md)

[Che cos'è Call Quality dashboard?](CQD-what-is-call-quality-dashboard.md)

[Configurare il dashboard sulla qualità delle chiamate (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md)

[Dati e report di Call Quality dashboard](CQD-data-and-reports.md)

[Usare Call Quality dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in Call Quality dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality dashboard](CQD-Power-BI-query-templates.md)
