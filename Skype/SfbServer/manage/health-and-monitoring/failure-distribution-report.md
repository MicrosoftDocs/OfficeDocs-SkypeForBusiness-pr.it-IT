---
title: Report di distribuzione dell'errore in Skype for Business Server
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
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: "Riepilogo: informazioni sul report di distribuzione dell'errore in Skype for Business Server."
ms.openlocfilehash: cc5f0747a5e1f1dd3be913c43fbc286bf95778a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817956"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a>Report di distribuzione dell'errore in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di distribuzione dell'errore in Skype for Business Server.
  
Il rapporto di distribuzione errori non è in grado di classificare le sessioni non riuscite nelle categorie seguenti:
  
- Principali motivi diagnostici
    
- Modalità top
    
- Pool principali
    
- Origini principali
    
- Componenti principali
    
- Inizio degli utenti
    
- Inizio per gli utenti
    
- Inizio da agenti utente
    
Puoi usare queste categorie per determinare esattamente dove si verifica un problema e, in alcuni casi, perché il problema si verifica. Ad esempio, si supponga di aver registrato 242 sessioni audio/video non riuscite durante un giorno specifico. Se si esamina il report di distribuzione degli errori, potrebbe essere necessario che 237 di tali sessioni non riuscite sia avvenuto nel pool di Dublino. Questo ti offre un buon punto di partenza per il rilevamento e la diagnosi delle cause che stanno dietro a questi errori. Se si fa clic sul pool Dublin nella categoria **Top pools** , verrà visualizzato un report di distribuzione di errore solo per il pool. È quindi possibile iniziare ad analizzare il motivo per cui il pool di Dublino stava vivendo tante difficoltà.
  
## <a name="viewing-the-failure-distribution-report"></a>Visualizzazione del report di distribuzione degli errori

È possibile accedere al report di distribuzione dell'errore da uno dei report seguenti facendo clic sul **volume di errore previsto** o sulla metrica di **volume errore imprevisto** :
  
- [Report errori principali in Skype for Business Server](top-failures-report.md)
    
- [Report di diagnostica per conferenze in Skype for Business Server](conference-diagnostic-report.md)
    
- [Report di diagnostica attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)
    
Nel report distribuzione errori è possibile fare clic su una delle metriche seguenti per visualizzare il [report elenco errori in Skype for Business Server](failure-list-report.md):
  
- Principali motivi diagnostici (sessioni)
    
- Modalità top (sessioni)
    
- Pool principali (sessioni)
    
- Origini principali (sessioni)
    
- Componenti principali (sessioni)
    
- Inizio da utenti (sessioni)
    
- Inizio per gli utenti (sessioni)
    
- Inizio da agenti utente (sessioni)
    
## <a name="using-the-failure-distribution-report"></a>Uso del report distribuzione errori

A seconda delle dimensioni del monitor e della risoluzione dello schermo, è possibile che alcuni dati visualizzati nel report di distribuzione dell'errore vengano troncati durante la visualizzazione sullo schermo. Questo vale soprattutto per le metriche, ad esempio gli agenti utente, che possono avere etichette molto lunghe. Ad esempio, un agente utente con un nome come "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" potrebbe essere visualizzato solo parzialmente sullo schermo: 
  
UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft ly...
  
Fortunatamente, è possibile visualizzare l'intera etichetta semplicemente tenendo il mouse sopra il valore troncato.
  
Una metrica interessante in cui è possibile applicare il filtro usando il report distribuzione errori è ID diagnostica. Se viene visualizzato lo stesso ID diagnostica in altri report, è possibile filtrare tale ID nel report distribuzione errori e ottenere un'analisi dettagliata precisamente dove e con quale frequenza è stato segnalato l'ID durante una sessione non riuscita.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report di distribuzione non riuscito consente di filtrare in base a elementi come il tipo di attività (sessione peer-to-peer o sessione di conferenza) o l'ID di diagnostica che ha accompagnato ogni sessione non riuscita.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di distribuzione dell'errore.
  
**Filtri dei report di distribuzione errori**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
|**Tipo di attività** <br/> | Tipo di attività su cui applicare il filtro. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Peer-to-peer <br/>  Conferenza <br/> |
|**Categoria sessione** <br/> | Indica se l'attività in questione è riuscita o meno. Selezionare una delle opzioni seguenti: <br/>  Tutti <br/>  Successo <br/>  Errore previsto <br/>  Errore imprevisto <br/>  Un "errore previsto" è un errore che dovrebbe verificarsi. Ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente. Un "errore imprevisto" è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto. <br/> |
|**ID diagnostica** <br/> |Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a>Metriche per i principali motivi diagnostici

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base all'ID di diagnostica segnalato più di frequente.
  
**Metriche per i principali motivi diagnostici**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base agli ID di diagnostica. L'ID di diagnostica è un identificatore univoco (in forma di intestazione MS-Diagnostics) associato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione degli errori.  <br/> |
|**Principali motivi diagnostici** <br/> |No  <br/> |ID di diagnostica generato in una sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite in cui è stato generato l'ID di diagnostica specificato.  <br/> |
   
## <a name="metrics-for-top-modalities"></a>Metriche per le modalità top

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base alle modalità di sessione che hanno registrato più errori.
  
**Metriche per le modalità top**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa basata sulla sessione non riuscita in base al tipo di sessione, ad esempio una conferenza audio/video o una sessione di trasferimento di file peer-to-peer.  <br/> |
|**Modalità top** <br/> |No  <br/> |Tipo di sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite che coinvolgono la modalità specificata.  <br/> |
   
## <a name="metrics-for-top-pools"></a>Metriche per i pool principali

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai pool che hanno sperimentato più errori.
  
**Metriche per i pool principali**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base al pool di registrazione o al server perimetrale in cui è stata eseguita la sessione.  <br/> |
|**Pool principali** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per ogni pool di registrar o Edge Server.  <br/> |
   
## <a name="metrics-for-top-sources"></a>Metriche per le origini principali

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai computer con più errori.
  
**Metriche per le origini principali**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite per ogni computer.  <br/> |
|**Origini principali** <br/> |No  <br/> |Nome del computer coinvolto nella sessione non riuscita.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per computer.  <br/> |
   
## <a name="metrics-for-top-components"></a>Metriche per i componenti principali

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base ai componenti che hanno sperimentato più errori.
  
**Metriche per i componenti principali**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base al componente, ad esempio ExumRouting, GroupChat o MediationServer.  <br/> |
|**Componenti principali** <br/> |No  <br/> |Nome del componente coinvolto nella sessione non riuscita.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per componente.  <br/> |
   
## <a name="metrics-for-top-from-users"></a>Metriche per l'inizio degli utenti

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base agli utenti che hanno sperimentato la maggior parte degli errori quando hanno tentato di chiamare un altro utente (detto "da" utenti).
  
**Metriche per l'inizio degli utenti**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base all'utente invitato a partecipare alla sessione.  <br/> |
|**Inizio degli utenti** <br/> |No  <br/> |Indirizzo SIP dell'utente invitato a partecipare alla sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per utente.  <br/> |
   
## <a name="metrics-for-top-to-users"></a>Metriche per i primi utenti

Nella tabella seguente sono elencate le informazioni fornite nel report di distribuzione dell'errore in base agli utenti che hanno sperimentato più errori quando un altro utente ha provato a chiamarli (detti "a" utenti).
  
|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base all'utente che ha avviato la sessione.  <br/> |
|**Inizio per gli utenti** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per utente.  <br/> |
   
## <a name="metrics-for-top-user-agents"></a>Metriche per gli agenti Top User

La tabella seguente elenca le informazioni fornite nel report di distribuzione dell'errore in base al software dell'endpoint che ha riscontrato la maggior parte degli errori.
  
**Metriche per gli agenti Top User**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Rango** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base all'agente utente (software) coinvolto nella sessione. Ad esempio: RTCC/4.0.0.0 routing in ingresso/4.0.0.0.  <br/> |
|**Agenti utente principali** <br/> |No  <br/> |Nome dell'agente utente coinvolto nella sessione non riuscita.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per agente utente.  <br/> |
   

