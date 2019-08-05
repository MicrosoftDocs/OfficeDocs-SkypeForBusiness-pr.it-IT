---
title: Calcolatore di pianificazione della capacità di Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Riepilogo: come usare lo strumento Calcolatrice capacità.'
ms.openlocfilehash: 24e268c6ecc3cc48fbfb4405f1e5e6b008639944
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186836"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calcolatore di pianificazione della capacità di Skype for Business Server
 
**Riepilogo:** Come usare lo strumento di calcolo capacità.

> [!NOTE]
> Questo articolo fa riferimento ai download di Skype for Business Server 2015, ma si applica a:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
Il calcolatore di [capacità di Skype for Business server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=51196) e il calcolatore di capacità di Skype for [Business Server 2019](https://www.microsoft.com/en-us/download/details.aspx?id=57509) aumentano lo [strumento di pianificazione di Skype for business](https://www.microsoft.com/en-us/download/details.aspx?id=50357) e la documentazione di distribuzione ([piano per Skype for business Distribuzione](../plan-your-deployment/plan-your-deployment.md) e pianificazione del server 2015 [per la distribuzione di Skype for Business Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) , rispettivamente). Usare la calcolatrice dopo aver esaminato la guida e aver creato una topologia consigliata usando lo strumento pianificazione.
  
La calcolatrice della capacità di Skype for Business Server ti aiuta a determinare i requisiti del server in base al numero di utenti e agli strumenti di comunicazione usati dall'organizzazione. Dopo aver determinato il profilo utente e le funzioni che si desidera abilitare per gli utenti, usare la calcolatrice per determinare il numero di server, la memoria e la larghezza di banda necessarie. Questa versione della calcolatrice non fornisce indicazioni per I requisiti di I/O su disco.
  
Puoi trarre vantaggio dalla calcolatrice se hai informazioni accurate e dettagliate sul profilo utente specifico. Ad esempio, la percentuale di utenti abilitati per la voce, le chiamate medie per utente per ora, la durata delle chiamate e la percentuale di utenti simultanei nelle conferenze possono fare una grande differenza nei requisiti del server. La precisione delle indicazioni create dalla calcolatrice dipende dall'esattezza delle informazioni fornite.
  
Dopo aver usato lo strumento di pianificazione e il calcolatore di pianificazione della capacità, devi simulare il caricamento proposto e pianificato per verificare che Skype for Business Server venga adeguatamente provisionato. Per eseguire test di stress in un carico simulato, usare lo [strumento di stress e prestazioni di Skype for Business Server](https://www.microsoft.com/en-us/download/details.aspx?id=50367) documentato su [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/en-us/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Uso del calcolatore capacità

La calcolatrice è un foglio di calcolo di Microsoft Excel. Le celle di input sono colorate in arancione. I valori predefiniti vengono immessi nelle celle (per Skype for Business Server 2015, 80.000 utenti in un pool con dodici server front-end, mentre per Skype for Business Server 2019, 106.000 utenti in un pool con sedici server front-end), ma è necessario modificare questi valori in soddisfare le esigenze dell'organizzazione.
  
Il modello di utilizzo contiene le sezioni seguenti. Per calcolare i requisiti di capacità, immettere i dati come descritto a partire dalla parte superiore del foglio e lavorare verso il basso riga per riga: 
  
 **Messaggistica istantanea e presenza**
  
- In **numero di utenti**Digitare il numero di utenti a cui verrà eseguito l'accesso. Questo numero è in genere 80% del numero totale di utenti con provisioning. Nella maggior parte dei casi, il 100% degli utenti simultanei verrà abilitato per la messaggistica istantanea e la presenza. Il valore predefinito è 80.000 per Skype for Business Server 2015 e 106.000 utenti per Skype for Business Server 2019.
    
- Il **numero medio di contatti nell'elenco contatti** indica il numero di contatti che stiamo usando per convalidare i requisiti di sistema. Questo numero è stato risolto e non è necessario modificarlo.
    
  **VoIP aziendale**
  
- In **utenti abilitati per VoIP aziendale**Digitare la percentuale di utenti abilitati per VoIP aziendale. Il valore predefinito è 60%. 
    
- In **Media numero di chiamate per utente per ora (picco)** Digitare il numero di chiamate per ora in cui si prevede che l'utente medio partecipi durante i periodi di caricamento massimo. Il valore predefinito è 4. 
    
- In **percentuale delle chiamate che usano il bypass multimediale**Digitare la percentuale di chiamate effettuate dagli utenti che ignoreranno il server Mediation. Il valore predefinito è 65%, ma potrebbe essere inferiore se si è distribuiti geograficamente o si ha una percentuale elevata di utenti che lavorano da casa.
    
- In **percentuale degli utenti vocali coinvolti nelle chiamate UC-PSTN**Digitare la percentuale delle chiamate dell'organizzazione che sono chiamate telefoniche UC-PSTN. Il valore predefinito è 60%.
    
- La **percentuale di utenti vocali coinvolti nelle chiamate UC-UC** Mostra la percentuale di utenti abilitati per VoIP aziendale che verrà abilitata solo per le chiamate UC-UC. Questo numero viene calcolato in base all'input per la **percentuale di utenti vocali abilitati per chiamate UC-PSTN**. 
    
  **Conferenze**
  
- In **percentuale degli utenti nelle conferenze concorrenti**Digitare la percentuale di utenti che parteciperanno alle conferenze contemporaneamente. Il valore predefinito è 5%. 
    
- In **percentuale delle conferenze con messaggistica istantanea di gruppo (senza voce)** Digitare la percentuale di conferenze che coinvolgono solo la messaggistica istantanea e non includere l'audio. Il valore predefinito è 10%
    
- In **percentuale di utenti che usano i servizi di conferenza telefonica con accesso esterno**, digitare la percentuale di partecipanti alle conferenze che utilizzeranno i servizi di conferenza telefonica con accesso esterno in una sola volta. Il valore predefinito è 15%.
    
- In **percentuale delle conferenze che usano la voce**Digitare la percentuale di conferenze che includerà l'audio. 
    
  - Se il 20% delle conferenze vocali includerà anche un video normale, selezionare la casella di controllo **Includi video (senza visualizzazione multipla)** .
    
  - Se il 20% delle conferenze includerà anche il video con più visualizzazioni, selezionare la casella di controllo **Includi multi-visualizzazione** .
    
  - Se 50% delle conferenze vocali includerà anche la condivisione delle applicazioni, selezionare la casella di controllo **Includi condivisione applicazioni** .
    
  - Se il 20% delle conferenze vocali include i caricamenti dei dati, ad esempio le presentazioni di PowerPoint, selezionare la casella di controllo **Includi Web** Conferencing.
    
  **Mobilità**
  
- In **percentuale degli utenti abilitati per la mobilità**Digitare la percentuale di utenti che verranno abilitati per la connessione a Skype for Business Server tramite dispositivi mobili. Il valore predefinito è 40%. 
    
Dopo aver immesso tutte le informazioni necessarie, il calcolatore della capacità stima le proprie esigenze. Le celle gialle mostrano i valori calcolati per i requisiti di CPU, memoria e larghezza di banda in base ai test eseguiti nei laboratori di prestazioni di Skype for Business Server. I numeri sono forniti come linee guida, non ogni singola variante viene testata e convalidata. Vengono calcolati i valori seguenti: 
  
- **CPU front-end**: percentuale di utilizzo della CPU se l'intero carico veniva gestito da un server front-end con le stesse specifiche del server usato per il test (vedere la descrizione alla fine di questo articolo).
    
- **Rete in Mbps**: requisiti di larghezza di banda in megabit al secondo (Mbps) per il carico di lavoro corrispondente.
    
- **Memoria in GB**: memoria necessaria in gigabyte (GB) per il carico di lavoro corrispondente.
    
Le celle verdi mostrano le raccomandazioni per il modello di utilizzo immesso. 
  
- **Total Front End Servers**: il numero di server fisici necessari si basa su server dedicati che usano Skype for Business Server 2015 con processore duale, hex-core, con 2.260 megacicli o Skype for Business Server 2019 con Intel Xeon E5-2673 V3, Dual processore, hex-core.
    
    Tieni presente che è consigliabile abilitare l'hyperthreading ed è stato dimostrato che migliora le prestazioni per i server che supportano l'audio/video.
    
- **Edge Server**: il numero di server perimetrali necessari, in base al 30% di tutti gli utenti simultanei che comunicano tramite Edge Server. Questa percentuale non può essere modificata nella calcolatrice. 
    
- **Archiviazione/registrazione dei dettagli delle chiamate/qualità di Experience Services Store**: il numero di archivi necessari per l'archiviazione o il monitoraggio delle caratteristiche, se abilitati nell'organizzazione.
    
- **Server di database back-end obbligatorio (obbligatorio per i pool)**: numero di server di database back-end necessari per supportare il carico di lavoro selezionato.
    
Inoltre, nella riga accanto a Total Front End Servers vengono fornite ulteriori informazioni sul carico dei server e della rete per tutti i carichi di lavoro pianificati combinati.
  
- **Carico medio**della CPU: l'utilizzo medio della CPU per server front-end.
    
- **Rete in Mbps**: l'allocazione di larghezza di banda necessaria per supportare il modello di utilizzo immesso.
    
- **Memoria in GB**: memoria, in gigabyte, necessaria per ogni server front-end.
    
### <a name="adjusting-for-your-processors"></a>Regolazione per i processori

Tutte le figure di utilizzo della CPU nel foglio di calcolo presuppongono che ogni server di Skype for Business Server 2015 disponga di un processore duale, hex-core con 2,26 GHz, almeno 32 GB di memoria e 8 o più unità disco rigido da 10.000-RPM con almeno 72 GB di spazio libero su disco. Per ogni server di Skype for Business Server 2019, tutte le figure di utilizzo della CPU nel foglio di calcolo presuppongono che ogni server disponga di un processore duale, hex-core con Intel Xeon E5-2673 V3, almeno 64 GB di memoria e 8 o più unità disco rigido 10.000-RPM con almeno 72 GB di disco libero s ritmo.
  
Se i server hanno processori diversi, è possibile modificare le cifre in base all'hardware.
  
