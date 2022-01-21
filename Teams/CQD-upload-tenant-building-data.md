---
title: Upload tenant e edificio in Call Quality Dashboard (CQD)
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Informazioni su come caricare i dati del tenant e della creazione in Call Quality Dashboard (CQD).
ms.openlocfilehash: c3da64a66ec2e78165bd0ee9dcb50acbe7739ee4
ms.sourcegitcommit: 0486ca906fc7f66460e54e400541e5d5cbfc6dde
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2022
ms.locfileid: "62160975"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Upload tenant e edificio in Call Quality Dashboard (CQD)


Per ottenere il massimo da Call Quality Dashboard (CQD), è consigliabile caricare i dati del tenant e dell'edificio. Esistono 2 tipi di file di dati del tenant, [Edificio](#upload-building-data-file) ed [Endpoint.](#endpoint-data-file)

È possibile scaricare un modello di dati tenant di esempio [qui.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true) Per assistenza con la mappatura dell'edificio, vedere [Creare una mappa dell'edificio per CQD.](CQD-building-mapping.md)

Nel dashboard Report di riepilogo CQD selezionare Tenant **Data Upload** dal menu CQD Impostazioni (un'icona **a** forma di ingranaggio nella parte superiore di CQD). Da qui, gli amministratori possono caricare le informazioni sull'edificio e sull'endpoint dell'organizzazione, ad esempio la mappatura di indirizzi IP e informazioni geografiche, il mapping di ogni punto di accesso wireless e del relativo indirizzo MAC e così via.

1. Aprire CQD (nell'interfaccia di amministrazione di Teams o in ), quindi selezionare l'icona a forma di ingranaggio nell'angolo in alto a destra e scegliere Tenant Data Upload dalla pagina [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) **Report di** riepilogo. 

   ![Screenshot della finestra di dialogo visualizzata durante il caricamento dei dati.](media/qerguide-image-tenantdataupload.png)
    
2. In alternativa, se è la prima volta che visiti CQD, ti verrà chiesto di caricare i dati dell'edificio. È possibile selezionare **Upload ora** per passare rapidamente alla **pagina** Upload tenant.

   ![Screenshot del banner che notifica a un utente di caricare i dati dell'edificio.](media/qerguide-image-buildingdatauploadbanner.png)

3. Nella pagina **Tenant Data Upload** selezionare **Browse** per scegliere un file di dati.

4. Dopo aver selezionato un file di dati, specificare **data di inizio** e, facoltativamente, una data di fine.

5. Dopo aver **selezionato Data di** inizio, selezionare **Upload** per caricare il file in CQD. <br><br>Prima del caricamento, il file viene convalidato. Se la convalida non riesce, viene visualizzato un messaggio di errore che richiede di correggere il file. La figura seguente mostra un errore che si verifica quando il numero di colonne nel file di dati non è corretto.

   ![Esempio di finestra di dialogo che mostra un errore di caricamento dei dati dell'edificio.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se durante la convalida non si verificano errori, il caricamento del file avrà esito positivo. È quindi possibile visualizzare il file  di dati caricato nella tabella Caricamenti personali, che mostra l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.

> [!NOTE]
> L'elaborazione del file di edificio può richiedere fino a quattro ore. <br><br> Se è già stato caricato un file di edificio ed è necessario aggiungere subnet che potrebbero essere state perse o escluse, modificare il file originale aggiungendo le nuove subnet, rimuovere il file corrente e ricaricare il file appena modificato. In CQD può essere presente un solo file di dati dell'edificio attivo. 


## <a name="upload-building-data-file"></a>Upload file di dati di creazione

Il primo tipo di file di dati del tenant in CQD è il file di dati **Building.** La colonna Subnet viene derivata espandendo la colonna Network+NetworkRange e quindi unendo la colonna Subnet alla colonna First Subnet o Second Subnet del record di chiamata per visualizzare le informazioni su Building, City, Country o Region. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:
  
- Il file deve essere un file TSV (le colonne sono separate da tab) o un file .csv (le colonne sono separate da una virgola).

- Il file di dati non include una riga di intestazione di tabella. La prima riga del file di dati dovrebbe essere dati reali, non etichette di intestazione come "Rete".

- I tipi di dati nel file possono essere solo String, Integer o Boolean. Per il tipo di dati Integer, il valore deve essere un valore numerico. I valori booleani devono essere 0 o 1.

- Se una colonna usa il tipo di dati Stringa, un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore String vuoto.

- Esiste un limite di 1.000.000 righe espanse per ogni file di dati del tenant.

- Per ogni riga devono essere presenti 15 colonne, ogni colonna deve avere il tipo di dati appropriato e le colonne devono essere nell'ordine indicato nella tabella seguente (delimitato da virgole o tabulazioni):

  **Creazione di un formato di file di dati**
  
  | Nome colonna        | Tipo di dati | Esempio                   | Linee guida              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Stringa    | 192.168.1.0               | Obbligatorio              |
  | NetworkName        | Stringa    | USA/Seattle/SEATTLE-SEA-1 | Obbligatorio<sup>1</sup>  |
  | NetworkRange       | Numero    | 26                        | Obbligatorio              |
  | BuildingName       | Stringa    | SEATTLE-SEA-1             | Obbligatorio<sup>1</sup>  |
  | OwnershipType      | Stringa    | Contoso                   | Facoltativo              |
  | BuildingType       | Stringa    | Terminazione IT            | Facoltativo              |
  | BuildingOfficeType | Stringa    | Progettazione               | Facoltativo              |
  | Città               | Stringa    | Seattle                   | Consigliata           |
  | ZipCode            | Stringa    | 98001                     | Consigliata           |
  | Paese            | Stringa    | Stati Uniti                        | Consigliata           |
  | Stato              | Stringa    | WA                        | Consigliata           |
  | Area geografica             | Stringa    | MSUS                      | Consigliata           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obbligatorio              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obbligatorio              |
  | VPN                | Bool      | 0                         | Facoltativo              |

  <sup>1</sup> Anche se non è richiesto da CQD, i modelli sono configurati per visualizzare nome edificio e rete.

  <sup>2</sup> Questa impostazione può essere usata per indicare se la subnet si trova o meno all'interno della rete aziendale. È possibile personalizzare l'utilizzo per altri scopi.

  <sup>3</sup> Questa impostazione può essere usata per indicare se la rete usa o meno Azure ExpressRoute. È possibile personalizzare l'utilizzo per altri scopi.  

  **Riga di esempio:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi caricamenti di edifici verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di edificio, è consigliabile scaricare il file corrente e ricaricarlo per identificare eventuali sovrapposizioni e risolvere il problema prima di caricarlo di nuovo. Qualsiasi sovrapposizione nei file caricati in precedenza può comportare il mapping errato delle subnet agli edifici nei report. Alcune implementazioni VPN non riportano in modo accurato le informazioni sulla subnet. 
>
> La colonna VPN è facoltativa e il valore predefinito è 0. Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da tale riga verrà completamente espansa in modo che corrisponda a tutti gli indirizzi IP all'interno della subnet. Usare questa opzione con parsimonio e solo per le subnet VPN, in quanto l'espansione completa di queste subnet avrà un impatto negativo sui tempi delle query per le query che implicano la creazione di dati. Se l'espansione della subnet comporta il superamento del limite di 1.000.000 righe di espansione, il file di edificio non verrà accettato.


### <a name="supernetting"></a>Supernetting

È possibile usare la supernetting, comunemente chiamata Classless Inter-Domain Routing (CIDR, Classless Inter-Domain Routing), al posto della definizione di ogni subnet. Una *supernet* è una combinazione di diverse subnet che condividono un singolo prefisso di routing. Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo sovrapposto. Il supernetting è supportato, ma non è consigliabile usarlo.

Ad esempio, l'edificio di marketing di Contoso è costituito da subnet seguenti:

-   10.1.0.0/24— primo piano
-   10.1.1.0/24— secondo piano
-   10.1.2.0/24— terzo piano
-   10.1.3.0/24— quarto piano

Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo sovrapposto, in questo esempio 10.1.0.0/22.

-   Rete = 10.1.0.0
-   Intervallo di rete = 22

Ecco alcuni aspetti da considerare prima di implementare la supernetting:

-   La supernetting può essere usata solo in un mapping di subnet con una maschera da 8 bit a 28 bit.

-   Il supernetting richiede meno tempo, ma ha il costo di ridurre la ricchezza dei dati. Supponiamo che ci sia un problema di qualità che riguarda la subnet 10.1.2.0. Se è stata implementata la supernetting, non si saprà dove si trova la subnet dell'edificio o quale tipo di rete si trovi, ad esempio un lab. Se si sono definite tutte le subnet per un edificio e sono stati caricati dati sulla posizione del piano, sarà possibile vedere questa distinzione.

-   È importante assicurarsi che l'indirizzo supernetto sia corretto e che non rileva subnet indesiderate.

-   È abbastanza comune trovare 192.168.0.0 nei dati. Per molte organizzazioni, questo indica che l'utente è a casa. Per altri, si tratta dello schema di indirizzi IP per un ufficio satellitare. Se l'organizzazione ha uffici che usano questa configurazione, non includerla nel file di edificio perché è difficile distinguere tra reti domestiche e interne usando [subnet comuni.](quality-of-experience-review-guide.md#common-subnets) 

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet. Tutti i nuovi caricamenti di file di dati dell'edificio verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di edificio, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e risolvere il problema. Qualsiasi sovrapposizione nei file caricati in precedenza potrebbe comportare il mapping errato delle subnet agli edifici nei report.

### <a name="vpn"></a>VPN

I dati di qualità dell'esperienza (QoE) che i client inviano a Microsoft 365 o Office 365, ovvero da dove vengono provenienti i dati CQD, include un flag VPN. CQD lo vede come la prima VPN e la seconda dimensione VPN. Tuttavia, questo flag si basa sulla segnalazione dei fornitori vpn Windows che la scheda di rete VPN registrata è una scheda di accesso remoto. Non tutti i fornitori vpn registrano correttamente gli adattatori di accesso remoto. Per questo, potrebbe non essere possibile usare i filtri di query VPN predefiniti. Usare la colonna VPN descritta sopra per contrassegnare e identificare con precisione le subnet VPN. È anche buona norma etichettare le reti VPN per identificarsi facilmente nei report. Di seguito sono riportati due esempi di come etichettare le subnet VPN:

- Definire un **nome di** rete immettendo "VPN" in questo campo per le subnet VPN.

  ![Screenshot del report QCD che mostra una VPN con il nome di rete.](media/qerguide-image-vpnnetworkname.png)

- Definire un **nome edificio** immettendo "VPN" in questo campo per le subnet VPN.

  ![Screenshot del report QCD che mostra una VPN con il nome dell'edificio.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> È noto che le connessioni VPN identificano il tipo di connessione di rete come cablato quando la connessione sottostante è wireless. Quando si esamina la qualità delle connessioni VPN, non è possibile presupporre che il tipo di connessione sia stato identificato in modo accurato.

## <a name="endpoint-data-file"></a>File di dati dell'endpoint

L'altro tipo di file di dati del tenant CQD è il file di dati **endpoint.** I valori di colonna vengono usati nella colonna First Client Endpoint Name o Second Client Endpoint Name del record di chiamata per visualizzare le informazioni su Endpoint Make, Model o Type. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:

- Il file deve essere un file TSV (le colonne sono separate da tab) o un file .csv (le colonne sono separate da una virgola).

- Il contenuto del file di dati non include intestazioni di tabella. La prima riga del file di dati dovrebbe essere dati reali, non un'etichetta di intestazione come "EndpointName".

- Tutte e sette le colonne usano solo il tipo di dati Stringa. La lunghezza massima consentita è di 64 caratteri.

- Per le voci viene fatto distinzione tra maiuscole e minuscole. EndpointName **ABC123** verrà considerato univoco da EndpointName **abc123**.

- Un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore String vuoto.

- EndpointName deve essere univoco, altrimenti il caricamento non riesce. Se è presente una riga duplicata o due righe che usano lo stesso EndpointName, il conflitto causerà un join non corretto.

- EndpointLabel1, EndpointLabel2 ed EndpointLabel3 sono etichette personalizzabili. Possono essere stringhe vuote o valori come "Reparto IT designato 2018 Laptop" o "Asset Tag 5678".

- Per ogni riga devono essere presenti sette colonne e le colonne devono essere nell'ordine seguente:

  **Ordine dei campi:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Riga di esempio:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Aggiornare un file di edificio

Durante la raccolta di informazioni sull'edificio e la subnet, gli amministratori spesso caricano il file dell'edificio in più iterazioni nel tempo, aggiungendo nuove subnet e le relative informazioni di edificio non appena diventano disponibili. In questo caso, sarà necessario caricare di nuovo il file di edificio. Questo processo è simile al caricamento iniziale come descritto nella sezione precedente, con alcune eccezioni come indicato nella sezione seguente.

> [!Important]
> Può essere attivo un solo file di edificio alla volta. Più file di edificio non sono cumulativi.

## <a name="add-net-new-subnets"></a>Aggiungere nuove subnet nette

A volte è necessario aggiungere nuove subnet nette a CQD che in origine non fanno parte della topologia di rete. Per aggiungere nuove subnet nette, eseguire le operazioni seguenti dalla **pagina** Upload tenant in CQD:

1.  Scaricare il file originale, se non si dispone già di una copia aggiornata.

1.  Rimuovere il file corrente in CQD.

1.  Modificare il file dell'edificio originale e specificare una data di fine che si verifica almeno un giorno prima dell'acquisizione delle nuove subnet nette.

1.  Accodare le nuove subnet nette al file di edificio originale.

1.  Upload il file di edificio appena modificato e impostare la data di inizio per un giorno dopo la fine del file di edificio precedente.

## <a name="add-missing-subnets"></a>Aggiungere subnet mancanti

Dopo aver caricato le informazioni sull'edificio per le reti gestite, ogni rete gestita deve avere un'associazione di edificio. Tuttavia, questo non è sempre il caso. in genere, alcune subnet vengono perse. Per trovare queste reti mancanti, esaminare il **report subnet** mancante nella pagina **Report** sulla qualità dell'esperienza in CQD. Vengono presentate tutte le subnet con 10 o più flussi audio non definiti nel file di dati dell'edificio e contrassegnati come esterni. Verificare che nell'elenco non siano presenti reti gestite. Se mancano subnet, usare la procedura seguente per aggiornare il file di dati dell'edificio originale e caricarlo di nuovo in CQD.

1. Passare alla pagina **Tenant Data Upload** in CQD.

1. Scaricare il file originale, se non si dispone già di una copia aggiornata.

1. Rimuovere il file corrente in CQD.

1. Accodare le nuove subnet al file originale.

1. Upload file di edificio. Assicurarsi di impostare la data di inizio su almeno otto mesi prima, in modo che CQD eelaborare i dati cronologici.


> [!IMPORTANT]
> È necessario aggiungere l'ID tenant come filtro di query per il secondo **ID tenant** a questo report per filtrare il report in modo da visualizzare solo i dati del tenant dell'organizzazione. In caso contrario, il report mostrerà subnet federate.

> [!NOTE] 
> Assicurarsi di modificare il filtro del report Anno mese sul mese corrente. Selezionare **Modifica** e modificare il filtro del report **Anno** mese per salvare il nuovo mese predefinito.


## <a name="related-topics"></a>Argomenti correlati

[Creare una mappa dell'edificio per CQD](CQD-building-mapping.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dati e report CQD](CQD-data-and-reports.md)

[Usare CQD per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione dei flussi in CQD](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati CQD](CQD-Power-BI-query-templates.md)
