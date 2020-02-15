---
title: Cmdlet per la creazione di report di Skype for business online e REST Web Service
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9046bb075fba832f0ba7c83697c96a285988fcf7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Cmdlet per la creazione di report di Skype for business online e REST Web Service

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-09-05_

In combinazione con le funzionalità di Reporting, Skype for business online consente di accedere a cinque cmdlet di Windows PowerShell che consentono di generare tali report e possono essere utilizzati dagli amministratori per restituire i dati di report personalizzati. Skype for business online include anche il resto (Representational State Transfer), che può essere utilizzato dagli sviluppatori per recuperare le informazioni di Reporting personalizzate.

I cmdlet per i report disponibili per gli amministratori includono:

  - Get-CsActiveUserReport, che fornisce informazioni sul numero di utenti attivi (ovvero gli utenti che hanno effettuato l'accesso a Skype for business online e hanno partecipato a almeno una conferenza o a una sessione di comunicazione peer-to-peer).

  - Get-CsAVConferenceTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) degli utenti spesi nelle conferenze audio/video.

  - Get-CsConferenceReport, che fornisce informazioni sul numero e il tipo di conferenze a cui hanno partecipato gli utenti.

  - Get-CsP2PAVTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) di utenti spesi nelle sessioni peer-to-peer che includevano audio e/o video.

  - Get-CsP2PSessionReport, che fornisce informazioni sul numero e il tipo di sessioni peer-to-peer a cui hanno partecipato gli utenti.

La maggior parte degli amministratori utilizzerà i report disponibili nell'interfaccia di amministrazione di Microsoft 365: non solo i report vengono generati automaticamente, ma forniscono anche una rappresentazione grafica dei dati che spesso è più facile interpretare rispetto ai valori dei numeri non elaborati restituiti dall' cmdlet per la creazione di report. Tuttavia, gli amministratori che hanno familiarità con Windows PowerShell possono utilizzare i cmdlet per la creazione di report per restituire dati che non sono facilmente disponibili nei report di Lync Online. Ad esempio, i cmdlet per i report restituiscono informazioni sulla durata della sessione (la quantità di tempo, espressa in minuti, in cui sono state riportate tutte le sessioni). La durata delle sessioni individuali non è disponibile con i rapporti di Lync Online. Analogamente, nella visualizzazione giornaliera dei report di Lync Online vengono visualizzate informazioni solo per i 14 giorni precedenti. Se si desidera esaminare i totali giornalieri per un giorno diverso, ad esempio una data di quattro mesi fa, è possibile utilizzare i cmdlet per la creazione di report.

Gli amministratori possono anche essere interessati all'articolo [utilizzo di Excel per recuperare i dati di report di office 365](http://msdn.microsoft.com/library/dn781442.aspx), in cui viene illustrato come utilizzare la funzionalità di query dei dati OData in Microsoft Excel per creare un report personalizzato di Office 365. I report personalizzati offrono la possibilità di dettare quali dati e quanti dati vengono restituiti dal servizio Reporting di Office 365. I report personalizzati consentono inoltre di eseguire operazioni quali la modalità di ordinamento e raggruppamento dei dati e l'accesso alle informazioni non visualizzate nell'interfaccia di amministrazione.

Gli amministratori che dispongono di uno sfondo di sviluppo possono utilizzare il servizio Web REST per ottenere informazioni non visualizzate nell'interfaccia di amministrazione di Skype for business online. Il servizio REST è simile al servizio SOAP, in quanto ogni tecnologia consente di trasferire dati XML tra un client e un server. Tuttavia, il servizio REST ha almeno due vantaggi rispetto al servizio SOAP. Per un altro, REST esegue i trasferimenti di dati XML utilizzando un formato standardizzato noto come formato di diffusione ATOM. Al contrario, SOAP utilizza un formato non standard per il trasferimento dei dati. Inoltre, REST è in grado di trasferire dati tra le reti che bloccano verbi HTTP diversi da GET e POST.

<div>

## <a name="see-also"></a>Vedere anche


[Reporting di Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))  


[Servizio Web di Reporting di Office 365](http://msdn.microsoft.com/library/office/jj984325.aspx)  
[Informazioni sul servizio Web di Reporting di Office 365](http://msdn.microsoft.com/library/office/jj984321.aspx)  
[Cmdlet per la creazione di rapporti di Exchange Online](http://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)  
[Usare Excel per recuperare dati di report Office 365](http://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

