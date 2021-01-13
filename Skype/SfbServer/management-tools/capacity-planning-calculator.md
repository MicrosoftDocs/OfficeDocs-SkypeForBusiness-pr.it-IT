---
title: Calcolatore di pianificazione della capacità di Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 'Riepilogo: informazioni su come utilizzare lo strumento di calcolo della capacità.'
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802996"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Calcolatore di pianificazione della capacità di Skype for Business Server
 
**Riepilogo:** Come utilizzare lo strumento di calcolo della capacità.

> [!NOTE]
> Questo articolo fa riferimento ai download di Skype for Business Server 2015, ma si applica a:
> - Skype for Business Server 2019.
> - Skype for Business Server 2015.
  
[Skype for Business server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196) e [Skype for Business Server 2019 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=57509) incrementare lo [strumento di pianificazione di Skype for business](https://www.microsoft.com/download/details.aspx?id=50357) e la documentazione relativa alla distribuzione (pianificare la distribuzione di Skype for[Business Server 2015](../plan-your-deployment/plan-your-deployment.md) e pianificare la distribuzione [di Skype for Business Server 2019](../../SfBServer2019/plan/plan-your-deployment-2019.md) ). Utilizzare la calcolatrice dopo aver esaminato la guida e aver creato una topologia consigliata tramite lo strumento di pianificazione.
  
Il calcolatore di capacità del server Skype for business consente di determinare i requisiti del server in base al numero di utenti e agli strumenti di comunicazione utilizzati dall'organizzazione. Dopo aver determinato il profilo utente e le funzioni che si desidera abilitare per gli utenti, utilizzare la calcolatrice per determinare il numero di server, la memoria e la larghezza di banda necessaria. Questa versione della calcolatrice non fornisce indicazioni per I requisiti di I/O su disco.
  
Se si dispone di informazioni accurate e dettagliate sul profilo utente specifico, è possibile trarre vantaggio dalla calcolatrice. Ad esempio, la percentuale di utenti abilitati per la voce, le chiamate medie per utente all'ora, la durata delle chiamate e la percentuale di utenti simultanei nelle conferenze possono fare una differenza enorme nei requisiti del server. L'accuratezza dei suggerimenti creati dalla calcolatrice dipende dall'accuratezza delle informazioni fornite.
  
Dopo aver utilizzato lo strumento di pianificazione e la calcolatrice per la pianificazione della capacità, è consigliabile simulare il carico proposto e pianificato per garantire che Skype for Business Server sia adeguatamente eseguito il provisioning. Per eseguire il test di stress con un carico simulato, utilizzare lo [strumento per lo stress e le prestazioni di Skype for Business Server](https://www.microsoft.com/download/details.aspx?id=50367) documentato in [Skype for Business Server Stress and Performance Tool](https://technet.microsoft.com/library/mt631400.aspx).
  
## <a name="using-the-capacity-calculator"></a>Utilizzo del calcolatore capacità

La calcolatrice è un foglio di calcolo di Microsoft Excel. Le celle di input sono colorate in arancione. I valori predefiniti vengono immessi nelle celle (per Skype for Business Server 2015, 80.000 utenti in un pool con dodici front end server, mentre per Skype for Business Server 2019, 106.000 utenti in un pool con sedici Front End Server), ma è necessario modificare questi valori in base alle esigenze dell'organizzazione.
  
Il modello di utilizzo contiene le sezioni seguenti. Per calcolare i requisiti di capacità, immettere i dati come descritto a partire dalla parte superiore del foglio e lavorare verso il basso riga per riga: 
  
 **Messaggistica istantanea e presenza**
  
- In **numero di utenti** Digitare il numero di utenti a cui verrà effettuato l'accesso contemporaneamente. Questo numero è in genere 80% del numero totale di utenti di cui è stato effettuato il provisioning. Nella maggior parte dei casi, il 100% degli utenti simultanei verrà abilitato per la messaggistica istantanea e la presenza. Il valore predefinito è 80.000 per Skype for Business Server 2015 e 106.000 per gli utenti di Skype for Business Server 2019.
    
- **Numero medio di contatti nell'elenco contatti** indica il numero di contatti utilizzati per convalidare i requisiti di sistema. Questo numero è fisso e non è necessario modificarlo.
    
  **VoIP aziendale**
  
- In **utenti abilitati per VoIP aziendale**, digitare la percentuale di utenti abilitati per VoIP aziendale. Il valore predefinito è 60%. 
    
- In **media il numero di chiamate per utente all'ora (picco)**, digitare il numero di chiamate all'ora in cui si prevede che l'utente medio partecipi in periodi di carico di picco. Il valore predefinito è 4. 
    
- In **percentuale delle chiamate che utilizzano il bypass multimediale**, digitare la percentuale di chiamate effettuate dagli utenti che ignoreranno il Mediation Server. Il valore predefinito è 65%, ma potrebbe essere più basso se si è distribuiti geograficamente o si dispone di una percentuale elevata di utenti che lavorano da casa.
    
- In **percentuale degli utenti vocali coinvolti nelle chiamate di messaggistica unificata PSTN**, digitare la percentuale delle chiamate dell'organizzazione che sono chiamate telefoniche UC-PSTN. Il valore predefinito è 60%.
    
- La **percentuale di utenti vocali coinvolti nelle chiamate UC-UC** Visualizza la percentuale di utenti abilitati per VoIP aziendale che verranno abilitati solo per le chiamate UC-UC. Questo numero viene calcolato in base all'input per la **percentuale di utenti vocali abilitati per le chiamate UC-PSTN**. 
    
  **Conferenze**
  
- In **percentuale degli utenti nelle conferenze simultanee**, digitare la percentuale di utenti che parteciperanno contemporaneamente a conferenze. Il valore predefinito è 5%. 
    
- In **percentuale delle conferenze con solo gruppo messaggistica istantanea (nessuna voce)**, digitare la percentuale di conferenze che comporterà solo la messaggistica istantanea e non includere l'audio. Il valore predefinito è 10%
    
- In **percentuale di utenti che utilizzano** le conferenze telefoniche con accesso esterno, digitare la percentuale di partecipanti alle conferenze che utilizzeranno le conferenze telefoniche con accesso esterno in una sola volta. Il valore predefinito è 15%.
    
- In **percentuale delle conferenze che utilizzano la voce**, digitare la percentuale di conferenze che includerà l'audio. 
    
  - Se il 20% delle conferenze vocali includerà anche un video normale, selezionare la casella di controllo **Includi video (nessuna visualizzazione multipla)** .
    
  - Se il 20% delle conferenze includerà anche video con più visualizzazioni, selezionare la casella di controllo **Includi Multi View** .
    
  - Se il 50% delle conferenze vocali includerà anche la condivisione di applicazioni, selezionare la casella di controllo **Includi la condivisione di applicazioni** .
    
  - Se il 20% delle conferenze vocali include i caricamenti di dati, ad esempio le presentazioni di PowerPoint, selezionare la casella di controllo **Includi Web Conferencing** .
    
  **Mobilità**
  
- In **percentuale degli utenti abilitati per la mobilità**, digitare la percentuale di utenti che saranno abilitati per la connessione a Skype for Business Server tramite dispositivi mobili. Il valore predefinito è 40%. 
    
Dopo aver immesso tutte le informazioni necessarie, la calcolatrice della capacità stima i propri requisiti. Le celle gialle mostrano i valori calcolati per i requisiti di CPU, memoria e larghezza di banda in base ai test eseguiti nei laboratori di prestazioni di Skype for Business Server. I numeri sono forniti come linee guida, non ogni singola variante viene testata e convalidata. Vengono calcolati i valori seguenti: 
  
- **CPU front-end**: percentuale di utilizzo della CPU se l'intero carico veniva gestito da un server front-end delle stesse specifiche del server utilizzato per il testing (vedere la descrizione alla fine di questo articolo).
    
- **Rete in Mbps**: requisiti di larghezza di banda in megabit al secondo (Mbps) per il carico di lavoro corrispondente.
    
- **Memoria in GB**: memoria necessaria in gigabyte (GB) per il carico di lavoro corrispondente.
    
Le celle verdi mostrano suggerimenti per il modello di utilizzo immesso. 
  
- **Total front end server**: il numero di server fisici necessari si basa su server dedicati che eseguono Skype for Business Server 2015 con doppio processore, hex-core, con 2.260 megacicli o Skype for Business Server 2019 con Intel Xeon E5-2673 V3, Dual Processor, hex-core.
    
    Si noti che è consigliabile abilitare l'Hyper-Threading ed è stato dimostrato che è possibile migliorare le prestazioni per i server che supportano audio/video.
    
- **Server perimetrali**: il numero di server perimetrali necessari, in base al 30% di tutti gli utenti simultanei che comunicano con i server perimetrali. Questa percentuale non può essere modificata nella calcolatrice. 
    
- **Archiviazione/registrazione dettagli chiamata/archivio qualità dei servizi di esperienza**: il numero di archivi necessari per le funzionalità di archiviazione o di monitoraggio, se sono abilitati nell'organizzazione.
    
- **Server database back-end necessario (pool necessari)**: il numero di server di database back-end necessari per il supporto del carico di lavoro selezionato.
    
Inoltre, nella riga accanto a Total front end server, vengono fornite ulteriori informazioni sul carico sui server e sulla rete per tutti i carichi di lavoro pianificati combinati.
  
- **Carico medio** della CPU: l'utilizzo medio della CPU per Front End Server.
    
- **Rete in Mbps**: l'allocazione di larghezza di banda necessaria per supportare il modello di utilizzo immesso.
    
- **Memoria in GB**: memoria, in gigabyte, obbligatoria per ogni Front End Server.
    
### <a name="adjusting-for-your-processors"></a>Adattamento delle cifre ai processori disponibili

Tutte le figure di utilizzo della CPU del foglio di calcolo presuppongono che ogni server di Skype for Business Server 2015 disponga di un processore duale, un hex-core con 2,26 GHz, almeno 32 GB di memoria e 8 o più unità disco rigido da 10.000-RPM con almeno 72 GB di spazio libero su disco. Per ogni server Skype for Business Server 2019, tutte le figure di utilizzo della CPU del foglio di calcolo presumono che ogni server disponga di un processore duale, hex-core con Intel Xeon E5-2673 V3, almeno 64 GB di memoria e 8 o più unità disco rigido a 10.000-RPM con almeno 72 GB di spazio libero su disco.
  
Se nei server sono disponibili processori diversi, è possibile modificare le figure in modo che corrispondano all'hardware.
  
