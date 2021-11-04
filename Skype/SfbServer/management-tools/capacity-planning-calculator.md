---
title: Calcolatore di pianificazione della capacità di Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Riepilogo: come usare lo strumento calcolatrice capacità.'
ms.openlocfilehash: bfceeb643f9043053c70670f19cbc91b325acbb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745922"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calcolatore di pianificazione della capacità di Skype for Business Server
 
**Riepilogo:** Come usare lo strumento di calcolo della capacità.

> [!NOTE]
> Questo articolo fa Skype for Business Server download 2015, ma si applica a:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
La calcolatrice della capacità [di Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=51196) e la calcolatrice della capacità di [Skype for Business Server 2019](https://www.microsoft.com/download/details.aspx?id=57509) aumentano lo strumento di pianificazione di [Skype for Business](https://www.microsoft.com/download/details.aspx?id=50357) e la documentazione relativa alla distribuzione ( Pianificare la distribuzione di[Skype for Business Server 2015](../plan-your-deployment/plan-your-deployment.md) e Pianificare rispettivamente la distribuzione [di Skype for Business Server 2019).](../../SfBServer2019/plan/plan-your-deployment-2019.md) Utilizzare il calcolatore dopo aver esaminato la guida e aver creato una topologia consigliata utilizzando lo strumento di pianificazione.
  
Il Skype for Business Server capacity calculator consente di determinare i requisiti del server in base al numero di utenti e agli strumenti di comunicazione utilizzati dall'organizzazione. Dopo aver determinato il profilo utente e le funzioni che si desidera abilitare per gli utenti, utilizzare il calcolatore per determinare il numero di server, memoria e larghezza di banda necessari. Questa versione dello strumento di calcolo non fornisce indicazioni per i requisiti di I/O su disco.
  
Se si dispone di informazioni accurate e dettagliate sul proprio profilo utente specifico, è possibile trarre vantaggio dalla calcolatrice. Ad esempio, la percentuale di utenti abilitati alla voce, la media delle chiamate per utente all'ora, la durata delle chiamate e la percentuale di utenti simultanei nelle conferenze possono fare una differenza enorme nei requisiti del server. L'accuratezza dei suggerimenti creati dal calcolatore dipende dall'accuratezza delle informazioni fornite.
  
Dopo aver utilizzato lo strumento di pianificazione e lo strumento di calcolo della pianificazione della capacità, è consigliabile simulare il carico proposto e pianificato per assicurarsi che Skype for Business Server verrà eseguito il provisioning adeguato. Per eseguire test di stress in un carico simulato, utilizzare lo strumento [Skype for Business Server Stress and Performance](https://www.microsoft.com/download/details.aspx?id=50367) documentato in Skype for Business Server Stress and Performance [Tool](./stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="using-the-capacity-calculator"></a>Utilizzo del calcolatore della capacità

La calcolatrice è un Microsoft Excel foglio di calcolo. Le celle di input sono di colore arancione. I valori predefiniti vengono immessi nelle celle (per Skype for Business Server 2015, 80.000 utenti in un pool con dodici Front End Server, mentre per Skype for Business Server 2019, 106.000 utenti in un pool con sedici Front End Server), ma è consigliabile modificare questi valori in base alle esigenze dell'organizzazione.
  
Il modello di utilizzo contiene le sezioni seguenti. Per calcolare i requisiti di capacità, immettere i dati come descritto a partire dalla parte superiore del foglio e lavorando in basso riga per riga: 
  
 **Messaggistica istantanea e presenza**
  
- In **Numero di utenti** digitare il numero di utenti che verranno connessi contemporaneamente. Questo numero è in genere l'80% del numero totale di utenti di cui è stato eseguito il provisioning. Nella maggior parte dei casi, il 100% degli utenti simultanei verrà abilitato per la messaggistica istantanea e la presenza. Il valore predefinito è 80.000 per Skype for Business Server 2015 e 106.000 utenti per Skype for Business Server 2019.
    
- **Il numero medio di contatti nell'elenco Contatti** indica il numero di contatti utilizzati per convalidare i requisiti di sistema. Questo numero è fisso e non è necessario modificarlo.
    
  **VoIP aziendale**
  
- In **Utenti abilitati per VoIP aziendale** digitare la percentuale di utenti abilitati per VoIP aziendale. Il valore predefinito è 60%. 
    
- In Numero medio di chiamate per utente **all'ora (picco)** digitare il numero di chiamate all'ora a cui si prevede che l'utente medio partecipi durante i periodi di carico di picco. Il valore predefinito è 4. 
    
- In **Percentuale di chiamate che utilizzano il bypass** multimediale digitare la percentuale di chiamate effettuate dagli utenti che bypasseranno il Mediation Server. Il valore predefinito è 65%, ma potrebbe essere inferiore se si è distribuiti geograficamente o se si dispone di una grande percentuale di utenti che lavorano da casa.
    
- In **Percentuale di utenti vocali coinvolti nelle chiamate UC-PSTN** digitare la percentuale di chiamate dell'organizzazione che sono chiamate telefoniche UC-PSTN. Il valore predefinito è 60%.
    
- **Percentuale di utenti vocali coinvolti nelle chiamate UC-UC** indica la percentuale di utenti abilitati per VoIP aziendale che verranno abilitati solo per le chiamate UC-UC. Questo numero viene calcolato in base all'input per Percentuale di utenti **vocali abilitati per le chiamate UC-PSTN.** 
    
  **Conferenze**
  
- In **Percentuale di utenti in conferenze contemporanee** digitare la percentuale di utenti che parteciperanno contemporaneamente alle conferenze. Il valore predefinito è 5%. 
    
- In Percentuale di conferenze con messaggistica istantanea di gruppo **(nessuna voce)** digitare la percentuale di conferenze che coinvolgeranno solo la messaggistica istantanea e non includeranno l'audio. Il valore predefinito è 10%
    
- In **Percentuale di utenti che utilizzano** le conferenze telefoniche con accesso esterno digitare la percentuale di partecipanti alle conferenze che utilizzano le conferenze telefoniche con accesso esterno contemporaneamente. Il valore predefinito è 15%.
    
- In **Percentuale di conferenze con voce** digitare la percentuale di conferenze che includeranno l'audio. 
    
  - Se il 20% delle conferenze vocali includerà anche video normali, selezionare la casella di controllo Includi **video (senza visualizzazione** multipla).
    
  - Se il 20% delle conferenze includerà anche video multi-visualizzazione, selezionare la **casella di** controllo Includi visualizzazione multipla.
    
  - Se il 50% delle conferenze vocali includerà anche la condivisione applicazioni, selezionare la **casella di** controllo Condivisione applicazioni inclusa.
    
  - Se il 20% delle conferenze vocali include caricamenti di dati, ad esempio PowerPoint presentazioni, selezionare la casella di controllo Includi **conferenze** Web.
    
  **Mobilità**
  
- In **Percentuale di utenti abilitati per** dispositivi mobili digitare la percentuale di utenti che saranno abilitati a connettersi Skype for Business Server dispositivi mobili. Il valore predefinito è 40%. 
    
Dopo aver immesso tutte le informazioni necessarie, il calcolatore della capacità stima i requisiti. Le celle gialle mostrano i valori calcolati per i requisiti di CPU, memoria e larghezza di banda in base ai test eseguiti nei laboratori Skype for Business Server prestazioni. I numeri vengono forniti come linea guida, non tutte le singole varianti vengono testate e convalidate. Vengono calcolati i valori seguenti: 
  
- **CPU front-end**: percentuale di utilizzo della CPU se l'intero carico viene gestito da un Front End Server delle stesse specifiche del server utilizzato per i test (vedere la descrizione alla fine di questo articolo).
    
- **Rete in Mbps:** requisiti di larghezza di banda in megabit al secondo (Mbps) per il carico di lavoro corrispondente.
    
- **Memoria in GB:** memoria necessaria in gigabyte (GB) per il carico di lavoro corrispondente.
    
Le celle verdi mostrano i suggerimenti per il modello di utilizzo immesso. 
  
- **Front End Server** totali: il numero di server fisici necessari si basa su server dedicati che eseguono Skype for Business Server 2015 con doppio processore, hex-core, con 2.260 megacicli o Skype for Business Server 2019 con Intel Xeon E5-2673 v3, doppio processore, hex-core.
    
    Si noti che l'abilitazione dell'hyperthreading è consigliata e ha dimostrato di migliorare le prestazioni per i server che supportano audio/video.
    
- **Server perimetrali**: numero di server perimetrali necessari, in base al 30% di tutti gli utenti simultanei che comunicano attraverso i server perimetrali. Questa percentuale non può essere modificata nella calcolatrice. 
    
- **Archiviazione/Registrazione dettagli chiamata/Archivio** servizi di qualità dell'esperienza: numero di archivi necessari per le funzionalità di archiviazione o monitoraggio, se abilitati nell'organizzazione.
    
- **Server database back-end necessario (pool necessari):** numero di server database back-end necessari per supportare il carico di lavoro selezionato.
    
Inoltre, nella riga accanto a Total Front End Server vengono fornite ulteriori informazioni sul carico sui server e sulla rete per tutti i carichi di lavoro pianificati combinati.
  
- **Carico medio CPU**: Utilizzo medio della CPU per server Front End.
    
- **Rete in Mbps:** allocazione della larghezza di banda necessaria per supportare il modello di utilizzo immesso.
    
- **Memoria in GB**: memoria, in gigabyte, necessaria per ogni Front End Server.
    
### <a name="adjusting-for-your-processors"></a>Adattamento delle cifre ai processori disponibili

Tutte le cifre sull'utilizzo della CPU nel foglio di calcolo presuppongono che ogni server Skype for Business Server 2015 abbia un doppio processore, un core esadecimale con 2,26 GHz, almeno 32 GB di memoria e 8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco. Per ogni server Skype for Business Server 2019, tutte le cifre sull'utilizzo della CPU nel foglio di calcolo presuppongono che ogni server abbia un doppio processore, un core esadecimale con Intel Xeon E5-2673 v3, almeno 64 GB di memoria e 8 o più unità disco rigido da 10.000 RPM con almeno 72 GB di spazio libero su disco.
  
Se i server hanno processori diversi, è possibile modificare le cifre in modo che corrispondano all'hardware.
