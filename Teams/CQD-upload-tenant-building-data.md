---
title: Caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD)
author: CarolynRowe
ms.author: crowe
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
description: Informazioni su come caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD).
ms.openlocfilehash: d999098a2d920c8709ae1878ac94648451c00f0b
ms.sourcegitcommit: 548978550d58f8657d7035b57b736e9cf9b15984
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2022
ms.locfileid: "69163226"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Caricare i dati del tenant e dell'edificio in Call Quality Dashboard (CQD)


Per sfruttare al massimo Call Quality Dashboard (CQD), è consigliabile caricare i dati del tenant e dell'edificio. Esistono 2 tipi di file di dati tenant, [building](#upload-building-data-file) ed [endpoint](#endpoint-data-file).

È possibile scaricare un modello di dati tenant di esempio [qui](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Per informazioni sulla mappatura dell'edificio, vedere [Creare una mappa dell'edificio per Call Quality Dashboard](CQD-building-mapping.md).

Nel dashboard Report di riepilogo di Call Quality Dashboard selezionare **Caricamento dati tenant** dal menu **Impostazioni** di Call Quality Dashboard (icona a forma di ingranaggio nella parte superiore di Call Quality Dashboard). Da qui, gli amministratori possono caricare le informazioni sull'edificio e sull'endpoint dell'organizzazione, ad esempio la mappatura di indirizzi IP e informazioni geografiche, il mapping di ogni punto di accesso wireless e del relativo indirizzo MAC e così via.

1. Aprire Call Quality Dashboard (dall'interfaccia di amministrazione di Teams o in ), quindi selezionare l'icona a forma di ingranaggio nell'angolo in alto a [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)destra e scegliere **Caricamento dati tenant** dalla pagina **Report di riepilogo** .

   ![Screenshot della finestra di dialogo visualizzata durante il caricamento dei dati.](media/qerguide-image-tenantdataupload.png)
    
2. In alternativa, se è la prima volta che visiti Call Quality Dashboard, ti verrà chiesto di caricare i dati dell'edificio. È possibile selezionare **Carica ora** per passare rapidamente alla pagina **Caricamento dati tenant** .

   ![Screenshot del banner che notifica a un utente di caricare i dati dell'edificio.](media/qerguide-image-buildingdatauploadbanner.png)

3. Nella pagina **Caricamento dati tenant** selezionare **Sfoglia** per scegliere un file di dati.

4. Dopo aver selezionato un file di dati, specificare **Data inizio** e, facoltativamente, una data di fine.

5. Dopo aver selezionato **Data inizio**, selezionare **Carica** per caricare il file in Call Quality Dashboard. <br><br>Prima del caricamento, il file viene convalidato. Se la convalida non riesce, viene visualizzato un messaggio di errore che richiede la correzione del file. La figura seguente mostra un errore che si verifica quando il numero di colonne nel file di dati non è corretto.

   ![Esempio di finestra di dialogo che mostra un errore di caricamento dei dati dell'edificio.](media/qerguide-image-buildingdatauploaderror.png)
 
6. Se non si verificano errori durante la convalida, il caricamento del file avrà esito positivo. È quindi possibile visualizzare il file di dati caricato nella tabella **Caricamenti personali** , che mostra l'elenco completo di tutti i file caricati per il tenant corrente nella parte inferiore della pagina.

> [!NOTE]
> Il completamento dell'elaborazione del file dell'edificio può richiedere fino a quattro ore. <br><br> Se è già stato caricato un file dell'edificio ed è necessario aggiungere subnet che potrebbero essere state perse o escluse, modificare il file originale aggiungendo le nuove subnet, rimuovere il file corrente e ricaricare il file appena modificato. In Call Quality Dashboard può essere presente un solo file di dati di compilazione attivo. 


## <a name="upload-building-data-file"></a>Caricare un file di dati di tipo building

Il primo tipo di file di dati tenant in Call Quality Dashboard è il file **di dati building** . La colonna Subnet deriva dall'espansione della colonna Network+NetworkRange, quindi dall'aggiunta della colonna Subnet alla colonna Prima subnet o Seconda subnet del record di chiamata per visualizzare le informazioni relative a edificio, città, paese o area geografica. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:
  
- Il file deve essere un file con estensione tsv (le colonne sono separate da una TAB) o un file .csv (le colonne sono separate da una virgola).

- Il file di dati non include una riga di intestazione di tabella. Si prevede che la prima riga del file di dati sia costituita da dati reali, non da etichette di intestazione come "Network".

- I tipi di dati nel file possono essere solo String, Integer o Boolean. Per il tipo di dati Integer, il valore deve essere un valore numerico. I valori booleani devono essere 0 o 1.

- Se una colonna usa il tipo di dati Stringa, un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore Stringa vuoto.

- Esiste un limite di riga espanso di 1.000.000 per ogni file di dati tenant.

- Devono essere presenti 15 colonne per ogni riga, ogni colonna deve avere il tipo di dati appropriato e le colonne devono essere nell'ordine indicato nella tabella seguente (delimitato da virgole o tabulazioni):

  **Formato di file di dati per la creazione**
  
  | Nome colonna        | Tipo di dati | Esempio                   | Linee guida              |
  |--------------------|-----------|---------------------------|-----------------------|
  | NetworkIP          | Stringa    | 192.168.1.0               | Obbligatorio              |
  | NetworkName        | Stringa    | USA/Seattle/SEATTLE-SEA-1 | Obbligatorio<sup>1</sup>  |
  | NetworkRange       | Numero    | 26                        | Obbligatorio              |
  | Nome edificio       | Stringa    | SEATTLE-SEA-1             | Obbligatorio<sup>1</sup>  |
  | ProprietàTipo      | Stringa    | Contoso                   | Facoltativo<sup>4</sup>  |
  | BuildingType       | Stringa    | Terminazione IT            | Facoltativo<sup>4</sup>  |
  | BuildingOfficeType | Stringa    | Ingegneria               | Facoltativo<sup>4</sup>  |
  | Città               | Stringa    | Seattle                   | Consigliata           |
  | Zipcode            | Stringa    | 98001                     | Consigliata           |
  | Paese            | Stringa    | Noi                        | Consigliata           |
  | Stato              | Stringa    | WA                        | Consigliata           |
  | Regione             | Stringa    | MSUS                      | Consigliata           |
  | InsideCorp<sup>2</sup>         | Bool      | 1             | Obbligatorio              |
  | ExpressRoute<sup>3</sup>       | Bool      | 0             | Obbligatorio              |
  | Vpn                | Bool      | 0                         | Facoltativo              |

  <sup>1</sup> Anche se non richiesto da Call Quality Dashboard, i modelli sono configurati per visualizzare il nome dell'edificio e della rete.

  <sup>2</sup> Questa impostazione può essere utilizzata per indicare se la subnet è interna o meno alla rete aziendale. È possibile personalizzare l'utilizzo per altri scopi.

  <sup>3</sup> Questa impostazione può essere usata per indicare se la rete usa Azure ExpressRoute o meno. È possibile personalizzare l'utilizzo per altri scopi.  
  
  <sup>4</sup> Anche se queste colonne facoltative sono denominate per suggerire i valori con cui è possibile popolare i valori, è possibile personalizzare l'utilizzo per altri scopi. ad esempio: Priorità di rete - `Tier 1, Tier 2, Tier 3` 

  **Riga di esempio:**

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> L'intervallo di rete può essere usato per rappresentare una supernet (combinazione di più subnet con un singolo prefisso di routing). Tutti i nuovi caricamenti di edifici verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di tipo building, è consigliabile scaricare il file corrente e ricaricarlo per identificare eventuali sovrapposizioni e risolvere il problema prima di caricarlo di nuovo. Qualsiasi sovrapposizione nei file caricati in precedenza può causare la mappatura errata delle subnet agli edifici nei report. Alcune implementazioni VPN non riportano in modo accurato le informazioni sulla subnet. 
>
> La colonna VPN è facoltativa e per impostazione predefinita è 0. Se il valore della colonna VPN è impostato su 1, la subnet rappresentata da quella riga verrà completamente espansa in modo che corrisponda a tutti gli indirizzi IP all'interno della subnet. Utilizza questa opzione con moderazione e solo per le subnet VPN, poiché l'espansione completa di queste subnet avrà un impatto negativo sui tempi di query per le query che implicano la creazione di dati. Se l'espansione della subnet determina il superamento del limite della riga di espansione di 1.000.000, il file dell'edificio non verrà accettato.


### <a name="supernetting"></a>Supernetting

È possibile usare la supernetting, comunemente denominata Classless Inter-Domain Routing (CIDR, Classless Inter-Domain Routing), al posto della definizione di ogni subnet. Una *supernet* è una combinazione di diverse subnet che condividono un singolo prefisso di routing. Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo con supernette. La supernetting è supportata, ma non è consigliabile usarla.

Ad esempio, l'edificio di marketing di Contoso è costituito dalle subnet seguenti:

-   10.1.0.0/24 — primo piano
-   10.1.1.0/24 — secondo piano
-   10.1.2.0/24 — terzo piano
-   10.1.3.0/24 — quarto piano

Invece di aggiungere una voce per ogni subnet, è possibile usare l'indirizzo supernetted, in questo esempio 10.1.0.0/22.

-   Rete = 10.1.0.0
-   Intervallo di rete = 22

Ecco alcuni aspetti da considerare prima di implementare la supernetting:

-   La supernetting può essere usata solo in una mappatura subnet con maschera a 8 bit a 28 bit.

-   La supernetting richiede meno tempo in anticipo, ma ha il costo di ridurre la ricchezza dei dati. Si supponga che si sia verificato un problema di qualità relativo alla subnet 10.1.2.0. Se hai implementato la supernetting, non saprai dove si trova la subnet nell'edificio o quale tipo di rete è (ad esempio, un lab). Se hai definito tutte le subnet per un edificio e hai caricato le informazioni sulla posizione del pavimento, sarai in grado di vedere questa distinzione.

-   È importante assicurarsi che l'indirizzo supernetted sia corretto e non trovi subnet indesiderate.

-   È abbastanza comune trovare 192.168.0.0 nei dati. Per molte organizzazioni, questo indica che l'utente è a casa. Per altri, questo è lo schema di indirizzi IP per un ufficio satellitare. Se l'organizzazione ha uffici che usano questa configurazione, non includerla nel file di edificio perché è difficile distinguere tra le reti domestiche e interne usando [le subnet comuni](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> L'intervallo di rete può essere utilizzato per rappresentare una supernet. Tutti i nuovi caricamenti di file di dati dell'edificio verranno controllati per verificare la sovrapposizione degli intervalli. Se in precedenza è stato caricato un file di tipo building, è consigliabile scaricare il file corrente e caricarlo di nuovo per identificare eventuali sovrapposizioni e risolvere il problema. Qualsiasi sovrapposizione nei file caricati in precedenza potrebbe causare la mappatura errata delle subnet agli edifici nei report.

### <a name="vpn"></a>Vpn

I dati sulla qualità dell'esperienza (QoE) inviati dai client a Microsoft 365 o Office 365, da cui provengono i dati di Call Quality Dashboard, includono un contrassegno VPN. Call Quality Dashboard vedrà questo come le dimensioni Prima VPN e Seconda VPN. Tuttavia, questo flag si basa sulla segnalazione a Windows dei fornitori di VPN che la scheda di rete VPN registrata è una scheda di accesso remoto. Non tutti i fornitori di VPN registrano correttamente gli adattatori di Accesso remoto. Per questo motivo, potresti non essere in grado di usare i filtri di query VPN predefiniti. Usa la colonna VPN illustrata in precedenza per contrassegnare e identificare con precisione le subnet VPN. È anche buona norma etichettare le reti VPN per identificarle facilmente nei report. Ecco due esempi di come etichettare le subnet VPN:

- Definisci un **nome di rete** immettendo "VPN" in questo campo per le subnet VPN.

  ![Screenshot del report QCD che mostra la VPN con il nome di rete.](media/qerguide-image-vpnnetworkname.png)

- Definisci un **nome di edificio** immettendo "VPN" in questo campo per le subnet VPN.

  ![Screenshot del report QCD che mostra la VPN con il nome dell'edificio.](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> È noto che le connessioni VPN insidino il tipo di connessione di rete come cablata quando la connessione sottostante è wireless. Quando si osserva la qualità tramite connessioni VPN, non è possibile supporre che il tipo di connessione sia stato identificato in modo accurato.

## <a name="endpoint-data-file"></a>File di dati dell'endpoint

L'altro tipo di file di dati tenant CQD è il file di dati **Endpoint** . I valori della colonna vengono usati nella colonna First Client Endpoint Name o Second Client Endpoint Name del record di chiamata per visualizzare le informazioni su Make, Model o Type dell'endpoint. Il formato del file di dati caricato deve soddisfare i criteri seguenti per superare il controllo di convalida prima del caricamento:

- Il file deve essere un file con estensione tsv (le colonne sono separate da una TAB) o un file .csv (le colonne sono separate da una virgola).

- Il contenuto del file di dati non include le intestazioni di tabella. Si prevede che la prima riga del file di dati sia costituita da dati reali e non da un'etichetta di intestazione come "EndpointName".

- Tutte e sette le colonne usano solo il tipo di dati Stringa. La lunghezza massima consentita è di 64 caratteri.

- Per le voci viene fatto distinzione tra maiuscole e minuscole; EndpointName **ABC123** verrà considerato univoco da EndpointName **abc123**.

- Un campo dati può essere vuoto, ma deve comunque essere separato da una tabulazione o da una virgola. Un campo dati vuoto assegna semplicemente un valore Stringa vuoto.

- EndpointName deve essere univoco, altrimenti il caricamento non riesce. Se è presente una riga duplicata o due righe che usano lo stesso EndpointName, il conflitto causerà un join non corretto.

- EndpointLabel1, EndpointLabel2 e EndpointLabel3 sono etichette personalizzabili. Possono essere stringhe vuote o valori come "Reparto IT designato 2018 Laptop" o "Asset Tag 5678".

- Devono essere presenti sette colonne per ogni riga e le colonne devono essere nell'ordine seguente:

  **Ordine campo:**

  EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Riga di esempio:**

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a>Aggiornare un file di compilazione

Durante la raccolta di informazioni relative all'edificio e alla subnet, gli amministratori spesso caricano il file dell'edificio in più iterazioni nel corso del tempo, aggiungendo nuove subnet e le informazioni relative all'edificio non appena disponibili. In questo caso, sarà necessario caricare nuovamente il file di edificio. Questo processo è analogo al caricamento iniziale, come descritto nella sezione precedente, con alcune eccezioni come indicato nella sezione seguente.

> [!Important]
> È possibile attivare un solo file di compilazione alla volta. Più file di creazione non sono cumulativi.

## <a name="add-net-new-subnets"></a>Aggiungi nuove subnet di rete

A volte è necessario aggiungere nuove subnet di rete a Call Quality Dashboard che in origine non corrispondono alla topologia di rete. Per aggiungere nuove subnet net, eseguire le operazioni seguenti dalla pagina **Caricamento dati tenant** in Call Quality Dashboard:

1.  Scaricare il file originale, se non si ha già una copia aggiornata.

1.  Rimuovere il file corrente in Call Quality Dashboard.

1.  Modifica il file dell'edificio originale e specifica una data di fine che si verifica almeno un giorno prima dell'acquisizione delle nuove subnet di rete.

1.  Accodare la rete nuove subnet al file dell'edificio originale.

1.  Caricare il file di edificio appena modificato e impostare la data di inizio per un giorno dopo la fine del file di edificio precedente.

## <a name="add-missing-subnets"></a>Aggiungere subnet mancanti

Dopo aver caricato le informazioni di creazione per le reti gestite, ogni rete gestita deve avere un'associazione di edificio. Tuttavia, questo non sempre è il caso; in genere, alcune subnet vengono perse. Per trovare queste reti mancanti, esaminare il **report subnet mancante** nella pagina **Report sulla qualità dell'esperienza** in CQD. Vengono presentate tutte le subnet con 10 o più flussi audio non definiti nel file di dati dell'edificio e contrassegnati come esterni. Assicurarsi che nell'elenco non siano presenti reti gestite. Se le subnet non sono presenti, eseguire la procedura seguente per aggiornare il file di dati dell'edificio originale e ricaricarlo in Call Quality Dashboard.

1. Passare alla pagina **Caricamento dati tenant** in Call Quality Dashboard.

1. Scaricare il file originale, se non si ha già una copia aggiornata.

1. Rimuovere il file corrente in Call Quality Dashboard.

1. Aggiungere le nuove subnet al file originale.

1. Caricare il file dell'edificio. Assicurarsi di impostare la data di inizio almeno otto mesi prima, in modo che Call Quality Dashboard eserciti i dati cronologici.


> [!IMPORTANT]
> È necessario aggiungere l'ID tenant come filtro di query per **Second Tenant ID** al report per filtrare il report in modo da visualizzare solo i dati del tenant dell'organizzazione. In caso contrario, nel report verranno visualizzate le subnet federate.

> [!NOTE] 
> Assicurarsi di modificare il filtro del report Month Year in base al mese corrente. Selezionare **Modifica** e modificare il filtro del report **Anno mese** per salvare il nuovo mese predefinito.


## <a name="related-topics"></a>Argomenti correlati

[Creare una mappa dell'edificio per Call Quality Dashboard](CQD-building-mapping.md)

[Migliorare e monitorare la qualità delle chiamate per Teams](monitor-call-quality-qos.md)

[Che cos'è CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurare Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Call Quality Dashboard - Dati e report](CQD-data-and-reports.md)

[Usare Call Quality Dashboard per gestire la qualità delle chiamate e delle riunioni](quality-of-experience-review-guide.md)

[Dimensioni e misure disponibili in CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificazione del flusso in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md)

[Usare Power BI per analizzare i dati di Call Quality Dashboard](CQD-Power-BI-query-templates.md)
