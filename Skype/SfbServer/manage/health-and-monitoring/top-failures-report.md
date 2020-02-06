---
title: Report errori principali in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 438942e2-580a-4b67-9d42-f116111fb26a
description: 'Riepilogo: informazioni sul report errori principali in Skype for Business Server.'
ms.openlocfilehash: c1c7d5617581a004501568edc995871032e5cb5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817635"
---
# <a name="top-failures-report-in-skype-for-business-server"></a>Report errori principali in Skype for Business Server
 
**Riepilogo:** Informazioni sul report errori principali in Skype for Business Server.
  
Il report errori principali offre un'occhiata agli errori più comunemente segnalati e alle relative tendenze nel tempo. Gli errori si basano su una combinazione delle due metriche seguenti:
  
- **ID diagnostica**. Identificatore univoco (in forma di intestazione MS-Diagnostics) associato a un messaggio SIP. Gli ID di diagnostica contengono informazioni utili per la risoluzione dei problemi relativi alle chiamate.
    
- **Codice di risposta**. I codici di risposta vengono usati nelle sessioni di comunicazione SIP per rispondere alle richieste SIP. Ad esempio, supponiamo che Ken invii la richiesta di invito a Pilar Ackerman (ovvero, supponiamo che Ken si chiami Pilar Ackerman). Se le risposte di Pilar, il suo telefono invierà il codice di risposta 200 (OK), lasciando che il telefono di Ken sappia che Pilar ha risposto. Il report errori principali include solo i codici di risposta inviati in risposta a un errore di chiamata. Skype for Business Server non tiene traccia di tutti i codici di risposta emessi durante il corso di una chiamata.
    
Le informazioni vengono segnalate non solo per il numero totale di sessioni in cui si è verificato un errore, ma anche per il numero totale di utenti interessati dall'errore.
  
## <a name="accessing-the-top-failures-report"></a>Accesso al report errori principali

Il report errori principali si accede dalla Home page dei report di monitoraggio. Facendo clic sulla metrica delle sessioni segnalate si accede al [report di distribuzione dell'errore in Skype for Business Server](failure-distribution-report.md).
  
## <a name="making-the-best-use-of-the-top-failures-report"></a>Sfruttare al meglio il report errori principali

Il report errori principali è inusuale in un aspetto: consente di filtrare fino a un massimo di 5 ID di diagnostica contemporaneamente. In genere è possibile filtrare solo su un elemento, ad esempio un indirizzo SIP dell'utente, alla volta. Per filtrare su più ID di diagnostica, è sufficiente immettere ogni ID nella casella ID di diagnostica, separandoli con virgole. Se si vuole, è possibile abbandonare uno spazio vuoto dopo ogni virgola. Per esempio:
  
1011, 2412, 1033, 52116, 1008
  
A tale scopo, verranno visualizzate solo le chiamate non riuscite che segnalano almeno uno di questi cinque ID diagnostici.
  
Se si tiene premuto il mouse su un codice di risposta, viene visualizzata una descrizione comando che indica il significato del codice di risposta in questione. Ad esempio, se si tiene premuto il puntatore del mouse sul codice di risposta 486, viene visualizzato il messaggio seguente:
  
Occupato qui.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report errori principali, ad esempio, consente di filtrare i dati restituiti in base a elementi come il tipo di attività (sessione peer-to-peer o sessione di conferenza) o il codice di risposta SIP che ha accompagnato la sessione non riuscita. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report errori principali.
  
**Filtri di report errori principali**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Tipo di attività** <br/> | Tipo di attività. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Peer-to-peer <br/>  Conferenza <br/> |
|**Modalità** <br/> |In questo momento l'unica opzione disponibile è **[tutti]**.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
|**Categoria** <br/> | Tipo di errore sperimentato. Selezionare una delle opzioni seguenti: <br/>  Errore sia previsto che imprevisto <br/>  Errore imprevisto <br/>  Un "errore previsto" è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente. Un "errore imprevisto" è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto. <br/> |
|**Codice di risposta** <br/> |Codice di risposta SIP inviato quando la conferenza non è riuscita. Immettere l'intero codice di risposta, ad esempio:  <br/> 400  <br/> |
|**ID diagnostica** <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.  <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report errori principali.
  
**Principali errori di report sulle metriche**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |Sì  <br/> |Rango relativo in base al numero di sessioni segnalate.  <br/> |
|**Sessioni segnalate** <br/> |Sì  <br/> |Numero totale di sessioni non riuscite in base all'ID di diagnostica e al codice di risposta SIP.  <br/> |
|**Utenti interessati** <br/> |Sì  <br/> |Numero totale di utenti interessati dalla sessione non riuscita.  <br/> |
|**Informazioni sull'errore** <br/> |No  <br/> |Informazioni dettagliate sull'errore, incluso l'ID di diagnostica, il codice di risposta SIP e la descrizione del motivo per cui la sessione non è riuscita.  <br/> |
|**Tendenza in passato** <br/> |No  <br/> |Grafico delle sessioni non riuscite nel tempo.  <br/> |
   

