---
title: Rapporto distribuzione errori in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
description: 'Riepilogo: informazioni sul Rapporto distribuzione errori in Skype for Business Server.'
ms.openlocfilehash: e8ebf3ccbb14b46c862d03f328fdbb327af51992
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847239"
---
# <a name="failure-distribution-report-in-skype-for-business-server"></a>Rapporto distribuzione errori in Skype for Business Server
 
**Riepilogo:** Informazioni sul Rapporto distribuzione errori in Skype for Business Server.
  
Il Rapporto distribuzione errori classifica le sessioni non riuscite nelle categorie seguenti:
  
- Motivi diagnostica principali
    
- Modalità principali
    
- Pool principali
    
- Origini principali
    
- Componenti principali
    
- Utenti di origine principali
    
- Utenti di destinazione principali
    
- Agenti utenti di origine principali
    
Queste categorie possono essere utilizzate per localizzare con precisione il problema e, in alcuni casi, stabilirne la causa. Si supponga ad esempio di aver registrato 242 sessioni audio/video non riuscite in un giorno specifico. Analizzando il Rapporto distribuzione errori, si può riscontrare che 237 di queste sessioni non riuscite hanno avuto luogo nel pool Dublin. Questa informazione rappresenta un punto di partenza valido nell'individuazione e nella diagnosi delle cause che sono alla base degli errori. Facendo clic sul pool Dublin nella categoria **Pool principali**, verrà visualizzato un Rapporto distribuzione errori per il pool specifico. A questo punto è possibile iniziare ad analizzare le cause dei problemi che hanno interessato il pool Dublin.
  
## <a name="viewing-the-failure-distribution-report"></a>Visualizzazione del Rapporto distribuzione errori

È possibile accedere al Rapporto distribuzione errori da uno qualsiasi dei rapporti seguenti facendo clic sulla metrica **Errore previsto** o **Errore imprevisto**:
  
- [Rapporto errori principali in Skype for Business Server](top-failures-report.md)
    
- [Rapporto di diagnostica conferenze in Skype for Business Server](conference-diagnostic-report.md)
    
- [Rapporto di diagnostica attività peer-to-peer in Skype for Business Server](peer-to-peer-activity-diagnostic-report.md)
    
Nel Rapporto distribuzione errori è possibile fare clic su una delle metriche seguenti per visualizzare il Rapporto elenco errori [in Skype for Business Server](failure-list-report.md):
  
- Motivi diagnostica principali (sessioni)
    
- Modalità principali (sessioni)
    
- Pool principali (sessioni)
    
- Origini principali (sessioni)
    
- Componenti principali (sessioni)
    
- Utenti di origine principali (sessioni)
    
- Utenti di destinazione principali (sessioni)
    
- Agenti utenti di origine principali (sessioni)
    
## <a name="using-the-failure-distribution-report"></a>Uso del Rapporto distribuzione errori

A seconda delle dimensioni del monitor e della risoluzione dello schermo, è possibile che alcuni dei dati mostrati nel Rapporto distribuzione errori vengano troncati quando vengono visualizzati. Ciò accade soprattutto nel caso di metriche come gli agenti utente che possono avere etichette particolarmente lunghe. Ad esempio un agente utente con un nome come "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" può essere visualizzato solo parzialmente: 
  
UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...
  
Fortunatamente, è possibile visualizzare l'intera etichetta semplicemente posizionando il mouse sul valore troncato.
  
Una metrica interessante in base alla quale è possibile filtrare usando il Rapporto distribuzione errori è ID diagnostica. Se lo stesso valore di ID diagnostica viene fuori in altri rapporti, è possibile applicare il filtro in base all'ID nel Rapporto distribuzione errori e ottenere informazioni estremamente dettagliate su dove e con che frequenza l'ID è stato segnalato durante una sessione non riuscita.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un insieme di dati più circoscritto o di visualizzare in modi diversi i dati restituiti. Il Rapporto distribuzione errori ad esempio consente di applicare filtri in base a elementi come il tipo di attività (sessione peer-to-peer o di conferenza) o l'ID diagnostica associato a ogni sessione non riuscita.
  
Nella tabella riportata di seguito vengono elencati i filtri che è possibile utilizzare con il Rapporto distribuzione errori.
  
**Filtri del Rapporto distribuzione errori**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**From** <br/> |Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**To** <br/> |Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:  <br/> 07/07/2015 13.00  <br/> Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane vanno sempre dal lunedì alla domenica.  <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool o fare clic su **[Tutti]** per visualizzare dati per tutti i pool. Questo elenco a discesa viene popolato automaticamente in base ai record del database.<br/> |
|**Tipo di attività** <br/> | Tipo di attività in base al quale applicare il filtro. Selezionare uno dei valori seguenti: <br/>  [All] <br/>  Peer-to-peer <br/>  Conferenza <br/> |
|**Categoria sessione** <br/> | Indica l'esito dell'attività in questione. Selezionare uno dei valori seguenti: <br/>  [All] <br/>  Completato <br/>  Errore previsto <br/>  Errore imprevisto <br/>  Per "errore previsto" si intende un errore che si prevede si verificherà. Se ad esempio un utente ha impostato il proprio stato su Non disturbare, è previsto che le chiamate effettuate per tale utente abbiano esito negativo. Per "errore imprevisto" si intende un errore che si verifica in un sistema considerato integro. Una chiamata ad esempio non dovrebbe interrompersi quando il chiamante viene messo in attesa. Se la chiamata si interrompe, l'evento verrà contrassegnato come errore imprevisto. <br/> |
|**ID diagnostica** <br/> |Identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi. Le intestazioni di diagnostica sono facoltative (è possibile che in alcune sessioni SIP non siano incluse queste intestazioni) e gli ID diagnostica sono spesso indicati solo per sessioni in cui si sono verificati problemi di un determinato tipo.  <br/> |
   
## <a name="metrics-for-top-diagnostic-reasons"></a>Metrica dei motivi di diagnostica principali

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base all'ID diagnostica segnalato con maggiore frequenza.
  
**Metrica dei motivi di diagnostica principali**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa di sessioni non riuscite in base agli ID diagnostica. L'ID diagnostica è un identificatore univoco nel formato di un'intestazione ms-diagnostics associato a un messaggio SIP in cui spesso vengono fornite informazioni utili per la risoluzione dei problemi.  <br/> |
|**Motivi diagnostica** <br/> |No  <br/> |ID diagnostica generato in una sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite in cui è stato generato l'ID diagnostica specificato.  <br/> |
   
## <a name="metrics-for-top-modalities"></a>Metrica delle modalità principali

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base alle modalità di sessione in cui si sono verificati più errori.
  
**Metrica delle modalità principali**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa di sessioni non riuscite in base al tipo di sessione, ad esempio un trasferimento file peer-to-peer o di conferenza audio/video.  <br/> |
|**Modalità** <br/> |No  <br/> |Tipo di sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite con la modalità specificata.  <br/> |
   
## <a name="metrics-for-top-pools"></a>Metrica dei pool principali

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai pool in cui si sono verificati più errori.
  
**Metrica dei pool principali**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base al pool di registrazione o al server perimetrale in cui è stata eseguita la sessione.  <br/> |
|**Pool** <br/> |No  <br/> |Nome del pool di registrazione o del server perimetrale.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per pool di registrazione o server perimetrali.  <br/> |
   
## <a name="metrics-for-top-sources"></a>Metrica delle origini principali

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai computer in cui si sono verificati più errori.
  
**Metrica delle origini principali**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa di sessioni non riuscite per computer.  <br/> |
|**Origini** <br/> |No  <br/> |Nome del computer associato alla sessione non riuscita.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per computer.  <br/> |
   
## <a name="metrics-for-top-components"></a>Metrica dei componenti principali

Nella tabella seguente sono elencate le informazioni fornite nel Rapporto distribuzione errori in base ai componenti che hanno riscontrato il maggior numero di errori.
  
**Metrica dei componenti principali**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa delle sessioni non riuscite in base al componente (ad esempio, ExumRouting, GroupChat o MediationServer).  <br/> |
|**Componenti** <br/> |No  <br/> |Nome del componente associato alla sessione non riuscita.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per componente.  <br/> |
   
## <a name="metrics-for-top-from-users"></a>Metrica degli utenti di origine delle chiamate

Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base agli utenti per cui si sono verificati più errori quando hanno tentato di chiamare un altro utente (utenti "Da").
  
**Metrica degli utenti di origine delle chiamate**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa di sessioni non riuscite in base all'utente invitato a partecipare alla sessione.  <br/> |
|**Da utenti** <br/> |No  <br/> |Indirizzo SIP dell'utente invitato a partecipare alla sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per utente.  <br/> |
   
## <a name="metrics-for-top-to-users"></a>Metrica degli utenti destinatari delle chiamate

Nella tabella seguente vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base agli utenti per cui si sono verificati più errori quando un altro utente ha tentato di chiamarli (utenti "A").
  
|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa di sessioni non riuscite in base all'utente che ha avviato la sessione.  <br/> |
|**A utenti** <br/> |No  <br/> |Indirizzo SIP dell'utente che ha avviato la sessione.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per utente.  <br/> |
   
## <a name="metrics-for-top-user-agents"></a>Metrica degli agenti utente

Nella tabella riportata di seguito vengono elencate le informazioni fornite nel Rapporto distribuzione errori in base al software endpoint in cui si sono verificati più errori.
  
**Metrica degli agenti utente**

|**Nome**|**Elemento utilizzabile per eseguire l'ordinamento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Classificazione** <br/> |No  <br/> |Classificazione relativa di sessioni non riuscite in base all'agente utente (software) associato alla sessione, ad esempio RTCC/4.0.0.0 Routing in ingresso/4.0.0.0.  <br/> |
|**Da agenti utente** <br/> |No  <br/> |Nome dell'agente utente coinvolto nella sessione non riuscita.  <br/> |
|**Sessioni** <br/> |No  <br/> |Numero totale di sessioni non riuscite per agente.  <br/> |
   

