---
title: Caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD)
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
description: Scopri come caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD).
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067141"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD)


Per ottenere il massimo da Call Quality Dashboard (CQD), ti consigliamo di caricare i dati del tenant e dell'edificio. Ci sono due tipi di file di dati tenant, [Building](#upload-building-data-file) ed [Endpoint.](#endpoint-data-file)

È possibile scaricare un modello di dati tenant di [esempio qui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true) Per assistenza con la mappatura dell'edificio, [vedere Creare una mappa di edificio per CQD.](CQD-building-mapping.md)

Nel dashboard dei report di riepilogo di CQD selezionare **Caricamento** dati tenant dal **menu** Impostazioni di CQD (icona a forma di ingranaggio nella parte superiore di CQD). Da qui, gli amministratori possono caricare le informazioni sull'edificio e sull'endpoint dell'organizzazione, ad esempio il mapping di indirizzi IP e informazioni geografiche, il mapping di ogni punto di accesso wireless e del relativo indirizzo MAC e così via.

1. Aprire CQD (dall'interfaccia di amministrazione di Teams o in ), quindi selezionare l'icona a forma di ingranaggio nell'angolo in alto a destra e scegliere Caricamento dati tenant dalla pagina [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **Report di** riepilogo. 

   ![Screenshot della finestra di dialogo visualizzata durante il caricamento dei dati](media/qerguide-image-tenantdataupload.png)
    
2. In alternativa, se è la prima volta che visiti CQD, ti verrà chiesto di caricare i dati dell'edificio. È possibile selezionare **Carica ora per** passare rapidamente alla pagina caricamento dei dati **del** tenant.

   ![Screenshot del banner che notifica a un utente di caricare i dati dell'edificio](media/qerguide-image-buildingdatauploadbanner.png)

3. Nella pagina **Caricamento dati tenant** selezionare Sfoglia **per** scegliere un file di dati.

4. Dopo aver selezionato un file di dati, specificare la data **di inizio** e, facoltativamente, una data di fine.

5. Dopo aver **selezionato la data** di **inizio, seleziona Carica** per caricare il file in CQD. <br><br>Prima di essere caricato, il file viene convalidato. Se la convalida non riesce, viene visualizzato un messaggio di errore che richiede di correggere il file. La figura seguente mostra un errore che si verifica quando il numero di colonne nel file di dati non è corretto.

   ![Esempio di finestra di dialogo che mostra un errore di caricamento dei dati di un edificio](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se non si verificano errori durante la convalida, il caricamento del file avrà esito positivo. È quindi possibile visualizzare il file  di dati caricato nella tabella Caricamenti personali, che mostra l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.

> [!NOTE]
> Per completare l'elaborazione del file dell'edificio possono essere richieste fino a quattro ore. <br><br> Se hai già caricato un file di edificio e devi aggiungere subnet che potrebbero essere state perse o escluse, modifica il file originale aggiungendo le nuove subnet, rimuovi il file corrente e ricarica il file appena modificato. In CQD può essere presente un solo file di dati dell'edificio attivo. 


## <a name="upload-building-data-file"></a>Caricare un file di dati dell'edificio

Il primo tipo di file di dati del tenant in CQD è il file di dati **Building.** La colonna Subnet si deriva espandendo la colonna Network+NetworkRange e quindi unendo la colonna Subnet alla colonna First Subnet o Second Subnet del record di chiamata per visualizzare le informazioni su Building, City, Country o Region. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:
  
- Il file deve essere in formato TSV (le colonne sono separate da tabulazioni) o CSV (le colonne sono separate da una virgola).

- Il file di dati non include una riga di intestazione di tabella. È previsto che la prima riga del file di dati sia dati reali, non etichette di intestazione come "Rete".

- I tipi di dati nel file possono essere solo string, integer o booleani. Per il tipo di dati Integer, il valore deve essere un valore numerico. I valori booleani devono essere 0 o 1.

- Se in una colonna viene utilizzato il tipo di dati Stringa, un campo dati può essere vuoto ma deve comunque essere separato da tabulazioni o virgole. Un campo dati vuoto assegna semplicemente un valore Stringa vuoto.

- Esiste un limite di 1.000.000 righe espanse per file di dati tenant.

- Devono essere presenti 15 colonne per ogni riga, ogni colonna deve avere il tipo di dati appropriato e le colonne devono essere nell'ordine indicato nella tabella seguente (delimitato da virgola o tabulazione):

  **Creazione di un formato di file di dati**
  
  | Nome colonna        | Tipo di dati | Esempio                   | Linee guida              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Stringa    | 192.168.1.0               | Obbligatorio              |
  | NetworkName        | Stringa    | USA/Seattle/SEATTLE-SEA-1 | Obbligatorio<sup>1</sup>  |
  | NetworkRange       | Numero    | 26                        | Obbligatorio              |
  | BuildingName       | Stringa    | SEATTLE-SEA-1             | Obbligatorio<sup>1</sup>  |
  | OwnershipType      | Stringa    | Contoso                   | Facoltativo              |
  | BuildingType       | Stringa    | IT Termination            | Facoltativo              |
  | BuildingOfficeType | Stringa    | Progettazione               | Facoltativo              |
  | Città               | Stringa    | Seattle                   | Consigliati           |
  | ZipCode            | Stringa    | 98001                     | Consigliati           |
  | Paese            | Stringa    | Stati Uniti                        | Consigliati           |
  | Stato              | Stringa    | WA                        | Consigliati           |
  | Area geografica             | Stringa    | MSUS                      | Consigliati           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obbligatorio              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obbligatorio              |
  | VPN                | Bool      | 0                         | Facoltativo              |

  <sup>1</sup> Anche se non richiesto da CQD, i modelli sono configurati per visualizzare il nome dell'edificio e della rete.

  <sup>2</sup> Questa impostazione può essere usata per indicare se la subnet è interna o meno alla rete aziendale. È possibile personalizzare l'utilizzo per altri scopi.

  <sup>3</sup> Questa impostazione può essere usata per riflettere se la rete usa Azure ExpressRoute o meno. È possibile personalizzare l'utilizzo per altri scopi.  

  **Riga di esempio:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi caricamenti di tipo Building verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di tipo Building, è consigliabile scaricare il file corrente e ricaricarlo per identificare eventuali sovrapposizioni e risolvere il problema prima di caricarlo di nuovo. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare la mappatura errata delle subnet agli edifici nei report. Alcune implementazioni di VPN non riportano in modo accurato le informazioni sulla subnet. 
>
> La colonna VPN è facoltativa e viene impostata per impostazione predefinita su 0. Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da quella riga sarà completamente espansa per corrispondere a tutti gli indirizzi IP all'interno della subnet. Usare questa opzione con moderamento e solo per le VPN, perché la piena espansione di queste subnet avrà un impatto negativo sui tempi delle query per le query che implicano l'utilizzo di dati di tipo building. Se l'espansione della subnet comporta il superamento del limite della riga di espansione di 1.000.000, il file dell'edificio non verrà accettato.


### <a name="supernetting"></a>Supernetting

È possibile usare una rete supernetting, comunemente denominata Classless Inter-Domain Routing (CIDR), al posto della definizione di ogni subnet. Una *supernet è* una combinazione di più subnet che condividono un singolo prefisso di routing. Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo supernetteto. Il supernetting è supportato, ma non è consigliabile usarlo.

Ad esempio, l'edificio di marketing di Contoso è costituito delle subnet seguenti:

-   10.1.0.0/24 - primo piano
-   10.1.1.0/24 - secondo piano
-   10.1.2.0/24 - terzo piano
-   10.1.3.0/24 - quarto piano

Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo supernetteto, in questo esempio 10.1.0.0/22.

-   Rete = 10.1.0.0
-   Intervallo di rete = 22

Ecco alcuni aspetti da considerare prima di implementare l'apice:

-   La supernetting può essere utilizzata solo in una mappatura subnet con una maschera da 8 bit a 28 bit.

-   L'apice richiede meno tempo, ma a disminuendo le quantità di dati. Si immagini un problema di qualità che riguarda la subnet 10.1.2.0. Se è stata implementata la supernetting, non si saprà dove si trova nell'edificio la subnet o il tipo di rete (ad esempio, un laboratorio). Se si sono definite tutte le subnet per un edificio e sono stati caricati dati sulla posizione del piano, si sarà in grado di vedere questa differenza.

-   È importante assicurarsi che l'indirizzo supernetteto sia corretto e non rileva le subnet indesiderate.

-   È piuttosto comune trovare 192.168.0.0 nei dati. Per molte organizzazioni, questo indica che l'utente è a casa. Per altri, questo è lo schema di indirizzi IP per un ufficio satellitare. Se l'organizzazione ha uffici che usano questa configurazione, non includerlo nel file di tipo building perché è difficile distinguere tra reti domestiche e interne usando [subnet comuni.](quality-of-experience-review-guide.md#common-subnets) 

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet. Tutti i nuovi caricamenti di file di dati dell'edificio verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di tipo Building, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e risolvere il problema. Una sovrapposizione nei file caricati in precedenza potrebbe comportare una mappatura errata tra subnet ed edifici nei report.

### <a name="vpn"></a>VPN

I dati relativi alla qualità dell'esperienza (QoE) inviati dai client a Microsoft 365 o Office 365, che è l'origine dei dati di CQD, includono un contrassegno VPN. CQD lo scoprirà come le dimensioni First VPN e Second VPN. Tuttavia, questo contrassegno si basa sulla segnalazione dei fornitori di VPN a Windows che l'adattatore di rete VPN registrato è un adattatore di accesso remoto. Non tutti i fornitori di VPN registrano correttamente gli adattatori di accesso remoto. Per questo, potrebbe non essere possibile usare i filtri di query VPN incorporati. Usare la colonna VPN illustrata sopra per contrassegnare e identificare in modo accurato le subnet VPN. È inoltre consigliabile etichettare le reti VPN per identificarsi facilmente nei report. Di seguito sono riportati due esempi di come etichettare le subnet VPN:

- Definire un **nome di rete** immettendo "VPN" in questo campo per le vpn subnet.

  ![Schermata del report QCD che mostra la RETE VPN con il nome di rete](media/qerguide-image-vpnnetworkname.png)

- Definire un **nome di edificio** immettendo "VPN" in questo campo per le VPN subnet.

  ![Schermata del report QCD che mostra la VPN con il nome dell'edificio](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> Le connessioni VPN identificano in modo non corretto il tipo di connessione di rete come cablato quando la connessione sottostante è wireless. Quando si esamina la qualità sulle connessioni VPN, non si può presupporre che il tipo di connessione sia stato identificato in modo accurato.

## <a name="endpoint-data-file"></a>File di dati dell'endpoint

L'altro tipo di file di dati tenant di CQD è il file di dati **dell'endpoint.** I valori di colonna vengono usati nella colonna First Client Endpoint Name o Second Client Endpoint Name del record della chiamata per mostrare informazioni su Make, Model o Type del record di chiamata. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:

- Il file deve essere in formato TSV (le colonne sono separate da tabulazioni) o CSV (le colonne sono separate da una virgola).

- Il contenuto del file di dati non include le intestazioni di tabella. È previsto che la prima riga del file di dati sia dati reali, non un'etichetta di intestazione come "Nome Endpoint".

- Tutte e sette le colonne usano solo il tipo di dati Stringa. La lunghezza massima consentita è 64 caratteri.

- Un campo dati può essere vuoto ma deve comunque essere separato da tabulazioni o virgole. Un campo dati vuoto assegna semplicemente un valore Stringa vuoto.

- EndpointName deve essere univoco, altrimenti il caricamento non riesce. Se è presente una o due righe duplicate che usano lo stesso EndpointName, il conflitto causerà un'unione non corretta.

- EndpointLabel1, EndpointLabel2 ed EndpointLabel3 sono etichette personalizzabili. Possono essere stringhe vuote o valori come "It Department designated 2018 Laptop" o "Asset Tag 5678".

- Devono essere presenti sette colonne per ogni riga e le colonne devono essere nell'ordine seguente:

  **Ordine dei campi:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Riga di esempio:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Aggiornare un file di tipo Building

Durante la raccolta delle informazioni relative all'edificio e alla subnet, gli amministratori spesso caricano il file dell'edificio in più iterazioni nel corso del tempo, aggiungendo nuove subnet e le relative informazioni non appena diventano disponibili. In questo caso, è necessario ricaricare il file dell'edificio. Questo processo è simile al caricamento iniziale, come descritto nella sezione precedente, con alcune eccezioni, come indicato nella sezione seguente.

> [!Important]
> Può essere attivo un solo file di edificio alla volta. Più file di edificio non sono cumulativi.

## <a name="add-net-new-subnets"></a>Aggiungi nuove subnet nette

In alcuni casi sarà necessario aggiungere nuove subnet di rete a CQD che non erano in origine parte della topologia di rete. Per aggiungere nuove subnet di rete, eseguire le operazioni seguenti dalla pagina **Caricamento dati** tenant in CQD:

1.  Scaricare il file originale, se non si ha ancora una copia aggiornata.

1.  Rimuovere il file corrente in CQD.

1.  Modificare il file dell'edificio originale e specificare una data di fine che si verifichi almeno un giorno prima dell'acquisizione della rete delle nuove subnet.

1.  Aggiungere la rete nuova subnet al file dell'edificio originale.

1.  Caricare il file dell'edificio appena modificato e impostare la data di inizio per un giorno dopo la fine del file dell'edificio precedente.

## <a name="add-missing-subnets"></a>Aggiungi subnet mancanti

Dopo aver caricato le informazioni sugli edifici per le reti gestite, ogni rete gestita deve avere un'associazione di tipo edificio. Tuttavia, non sempre questo è il caso. in genere si persa alcune subnet. Per trovare queste reti mancanti, consultare il **report sulla subnet** mancante nella pagina **dei** report sulla qualità dell'esperienza in CQD. Tutte le subnet presentano 10 o più flussi audio non definiti nel file di dati dell'edificio e contrassegnate come esterne. Verificare che nell'elenco non siano presenti reti gestite. Se mancano subnet, usare la procedura seguente per aggiornare il file di dati dell'edificio originale e ricaricarlo in CQD.

1. Passare alla **pagina Caricamento dati tenant** in CQD.

1. Scaricare il file originale, se non si ha ancora una copia aggiornata.

1. Rimuovere il file corrente in CQD.

1. Aggiungere le nuove subnet al file originale.

1. Caricare il file dell'edificio. Assicurarsi di impostare la data di inizio su almeno otto mesi prima, in modo che CQD eelaborare i dati cronologici.


> [!IMPORTANT]
> Sarà necessario aggiungere l'ID tenant come filtro di query per il secondo **ID tenant** a questo report per filtrare il report in modo da visualizzare solo i dati del tenant dell'organizzazione. In caso contrario, il report mostrerà le subnet federate.

> [!NOTE] 
> Assicurarsi di impostare il filtro del rapporto Mese anno sul mese corrente. Selezionare **Modifica** e modificare il filtro **rapporto Mese** anno per salvare il nuovo mese predefinito.


## <a name="related-topics"></a>Argomenti correlati

[Creare una mappa di edificio per CQD](CQD-building-mapping.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dati e report di CQD](CQD-data-and-reports.md)

[Usare Call Quality Quality Call per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di CQD](CQD-Power-BI-query-templates.md)
