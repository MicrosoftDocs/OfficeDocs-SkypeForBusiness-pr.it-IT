---
title: Report di registrazione degli utenti in Skype for Business Server
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
ms.assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
description: 'Riepilogo: informazioni sul report di registrazione degli utenti in Skype for Business Server.'
ms.openlocfilehash: 7923db1ceac936825508f438d5d0437071e89c62
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817605"
---
# <a name="user-registration-report-in-skype-for-business-server"></a>Report di registrazione degli utenti in Skype for Business Server
 
**Riepilogo:** Informazioni sul report di registrazione degli utenti in Skype for Business Server.
  
Il report registrazione utenti offre una panoramica delle attività di accesso degli utenti, in particolare informazioni sul numero di utenti che hanno effettuato l'accesso a Skype for Business Server durante un determinato periodo di tempo (ogni ora, ogni giorno, ogni settimana, ogni mese). Tieni presente che il report indica solo il numero di persone che hanno effettuato l'accesso. Non indica le persone che hanno effettuato l'accesso. I report di monitoraggio non contengono informazioni su quali utenti specifici usano Skype for Business Server (e quali no). Puoi tuttavia ottenere una stima approssimativa delle informazioni utente usando il report attività utente.
  
Quando si forniscono informazioni sugli accessi degli utenti, il report di registrazione utente estrae due distinzioni importanti. In primo luogo, interrompe gli accessi in due categorie principali: gli accessi interni e gli accessi esterni. Gli accessi interni rappresentano gli utenti che hanno effettuato l'accesso dall'interno del firewall dell'organizzazione, ovvero durante la connessione alla rete aziendale. Gli accessi esterni rappresentano gli utenti che hanno effettuato l'accesso dall'esterno del firewall tramite un server perimetrale (ad esempio, un utente che ha effettuato l'accesso da un Internet Café conta come Accounting esterno). Se è necessario conoscere il numero di utenti che accedono dall'esterno del firewall, è possibile che il report di registrazione dell'utente disponga di queste informazioni.
  
Inoltre, il report registrazione utenti rileva il numero di utenti attivi presenti durante un determinato periodo di tempo. Un utente attivo è un utente che ha preso parte a una sessione di messaggistica istantanea, ha partecipato a una riunione Skype for Business Server, ha eseguito o ricevuto una telefonata oppure ha usato Skype for Business Server in un determinato periodo di tempo. Questa operazione è diversa da quella di un utente che ha effettuato l'accesso, ma non ha mai effettivamente usato il sistema.
  
## <a name="accessing-the-user-registration-report"></a>Accesso al report di registrazione utente

È possibile accedere al report di registrazione utenti solo dalla Home page dei report di monitoraggio. Il report di registrazione utente non viene collegato ad altri report.
  
## <a name="making-the-best-use-of-the-user-registration-report"></a>Sfruttare al meglio il report di registrazione utente

Dopo aver implementato Skype for Business Server una domanda comunemente chiesta è la seguente: come faccio a sapere se i miei utenti usano effettivamente questa nuova tecnologia? Anche se ha alcune limitazioni a questo proposito, il report di registrazione dell'utente può aiutarti a rispondere a questa domanda. Per determinare se gli utenti usano Skype for Business Server o meno, è necessario eseguire due operazioni. Prima di tutto, ottenere il valore della metrica degli utenti di accesso univoco dal report di registrazione dell'utente. Questo valore indica il numero di persone distinte che hanno effettuato l'accesso a Skype for Business Server.
  
In base al confronto, la metrica totale degli accessi Mostra il numero totale di volte in cui chiunque abbia effettuato l'accesso a Skype for Business Server. Supponiamo ad esempio che Ken si sia connesso a Skype for Business Server cinque volte in un solo giorno. In questo caso, Ken si conta come cinque sessioni di accesso separate per la metrica totale degli accessi, ma solo un utente di accesso per la metrica per gli utenti di accesso univoco. Allo stesso modo, non è raro che un utente acceda da più dispositivi o più posizioni. Ad esempio, un utente può accedere usando il suo computer desktop, il suo computer portatile e può avere un telefono IP che acceda automaticamente a Skype for Business Server. In questo esempio esiste un utente univoco con tre accessi.
  
Per spiegare ulteriormente la differenza tra gli accessi totali e gli accessi univoci, prendere in considerazione gli accessi per un determinato periodo di tempo nella tabella seguente.
  
|**Utente**|**Ora di accesso**|
|:-----|:-----|
|Ken  <br/> |7/7/2015 8:45 AM  <br/> |
|Ken  <br/> |7/7/2015 8:46 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:17 AM  <br/> |
|Ken  <br/> |7/7/2015 9:22 AM  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 9:31 AM  <br/> |
   
Si noti che esiste un totale di cinque accessi; Tuttavia, esistono solo due utenti di Access univoci: Ken remario (che ha effettuato l'accesso tre volte) e Pilar Ackerman (che ha effettuato l'accesso due volte). Questa è la differenza tra gli accessi e gli utenti di accesso univoco.
  
Oltre a conoscere il numero di accessi univoci, è necessario conoscere il numero totale di utenti abilitati per Skype for Business Server. Questo valore può essere recuperato aprendo Skype for Business Server Management Shell ed eseguendo il comando di Windows PowerShell seguente:
  
```PowerShell
(Get-CsUser).Count
```

Se il comando precedente restituisce un valore di 1.236 e gli utenti di Access univoci metriche restituiscono un valore medio di 667, il che suggerisce che un po' più della metà degli utenti abilitati per Skype for business si stia effettivamente accedendo al sistema ogni giorno (ovvero , 667 diviso per 1.236, che è approssimativamente 54%).
  
> [!CAUTION]
> Tieni presente che le metriche di accesso registrano gli utenti che hanno effettivamente effettuato l'accesso durante il periodo di tempo specificato. Non tengono traccia degli utenti che hanno già effettuato l'accesso al sistema. Ad esempio, se la metrica degli utenti di accesso univoco Mostra gli accessi di 667 e si hanno utenti di 1.236, il che suggerisce che circa la metà degli utenti accedono al sistema. Supponiamo tuttavia che gli utenti di 300 abbiano già effettuato l'accesso al sistema nel momento in cui hai iniziato a controllare i dati di accesso. Ciò significherebbe che in realtà gli utenti di quasi 1.000 hanno effettuato l'accesso a Skype for Business Server, il che significherebbe che più vicino al 80% degli utenti è stato effettuato l'accesso. 
  
Devi anche confrontare il valore degli utenti di accesso univoco con il valore della metrica utenti attivi univoci. La metrica utenti attivi univoci indica il numero di utenti univoci usati in realtà Skype for Business Server: hanno effettuato una telefonata, hanno partecipato a una riunione di Skype for Business Server o sono stati partecipanti a una sessione di messaggistica istantanea. Si tratta di informazioni utili, perché Skype for Business Server può essere configurato per l'avvio automatico ogni volta che un utente avvia Windows. Per questo motivo, potresti avere un numero elevato di utenti che accedono automaticamente a Skype for business quando accedono a Windows ogni giorno, ma non usano mai realmente Skype for Business Server durante tale periodo di tempo.
  
La metrica utenti attivi univoci offre anche dati più significativi in un'organizzazione in cui gli utenti in genere non disconnettersi da Windows alla fine della giornata. Al contrario, bloccano semplicemente i loro computer e lasciano Windows e Skype for business in funzione. In una situazione simile, potresti finire con pochissimi accessi al giorno perché gli utenti hanno effettuato l'accesso diversi giorni fa e non sono mai stati disconnessi. Tuttavia, gli utenti attivi univoci indicano se gli utenti usano attivamente Skype for business o un altro client di Skype for Business Server.
  
## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Il report di registrazione utente, ad esempio, consente di visualizzare i dati per tutti i pool di registrazione e i server perimetrali o per visualizzare i dati per un singolo pool. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le registrazioni sono raggruppate per ora, giorno, settimana o mese.
  
Nella tabella seguente sono elencati i filtri che è possibile usare con il report di registrazione dell'utente.
  
**Filtri report registrazione utenti**

|**Nome**|**Descrizione**|
|:-----|:-----|
|**Da** <br/> |Data e ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**A** <br/> |Data e ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:  <br/> 7/7/2015 1:00 PM  <br/> Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:  <br/> 7/7/2015  <br/> Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):  <br/> 7/3/2015  <br/> Le settimane si eseguono sempre da domenica a sabato.  <br/> |
|**Intervallo** <br/> | Intervallo di tempo. Selezionare una delle opzioni seguenti: <br/>  Ogni ora (può essere visualizzato un massimo di 25 ore) <br/>  Giornaliera (è possibile visualizzare un massimo di 31 giorni) <br/>  Settimanale (può essere visualizzato un massimo di 12 settimane) <br/>  Mensile (può essere visualizzato un massimo di 12 mesi) <br/>  Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, vengono visualizzati solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2015 e una data di fine 2/28/2015, i dati verranno visualizzati per i giorni 8/7/2015 12:00 da AM a 9/7/2015 12:00 AM, ovvero un totale di 31 giorni di dati. <br/> |
|**Pool** <br/> |Nome di dominio completo (FQDN) del pool di registrazione o del server perimetrale. È possibile selezionare un singolo pool oppure scegliere **[tutti]** per visualizzare i dati per tutti i pool. Questo elenco a discesa viene compilato automaticamente in base ai record nel database. <br/> |
   
## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report di registrazione dell'utente. 
  
**Metriche del report di registrazione degli utenti**

|**Nome**|**Si può ordinare su questo elemento?**|**Descrizione**|
|:-----|:-----|:-----|
|**Oraria** <br/> **Quotidiana** <br/> **Settimanale** <br/> **Mensile** <br/> |No  <br/> |Indica l'intervallo di tempo selezionato sulla barra degli strumenti filtro. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2015, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.  <br/> |
|**Totale accessi** <br/> |No  <br/> |Numero totale di sessioni di accesso riuscite.  <br/> |
|**Accessi interni** <br/> |No  <br/> |Numero totale di accessi all'interno della rete interna.  <br/> |
|**Accessi esterni** <br/> |No  <br/> |Numero totale di accessi esterni alla rete interna tramite il server perimetrale.  <br/> |
|**Utenti di Access univoci** <br/> |No  <br/> |Numero totale di utenti che avevano almeno una sessione di accesso. Un utente che ha avuto più sessioni di accesso conta come un solo utente, uguale a quello che ha avuto solo una singola sessione di accesso.  <br/> |
|**Utenti attivi univoci** <br/> |No  <br/> |Numero totale di utenti che hanno partecipato a una sessione peer-to-peer o conferenza. Un utente che ha avuto più sessioni conta come un utente, lo stesso che ha avuto una sola sessione.  <br/> |
   

