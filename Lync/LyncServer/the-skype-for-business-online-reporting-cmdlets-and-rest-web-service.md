---
title: Cmdlet per la creazione di report di Skype for business online e servizio Web REST
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
ms.openlocfilehash: bf02e845acc35ff4381b43beb91d798ec49f58d2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a>Cmdlet per la creazione di report di Skype for business online e servizio Web REST

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-09-05_

In combinazione con le funzionalità di creazione di report, Skype for business online consente di accedere a cinque cmdlet di Windows PowerShell che consentono di generare questi report e possono essere usati anche dagli amministratori per restituire i dati di report personalizzati. Skype for business online include anche il resto (Representational State Transfer), che può essere usato dagli sviluppatori per recuperare le informazioni di Reporting personalizzate.

I cmdlet per la creazione di report disponibili per gli amministratori includono:

  - Get-CsActiveUserReport, che fornisce informazioni sul numero di utenti attivi, ovvero gli utenti che hanno effettuato l'accesso a Skype for business online e hanno partecipato ad almeno una conferenza o una sessione di comunicazione peer-to-peer.

  - Get-CsAVConferenceTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) che gli utenti hanno trascorso in conferenze audio/video.

  - Get-CsConferenceReport, che fornisce informazioni sul numero e il tipo di conferenze a cui hanno partecipato gli utenti.

  - Get-CsP2PAVTimeReport, che fornisce informazioni sulla quantità di tempo (in minuti) che gli utenti hanno trascorso nelle sessioni peer-to-peer che includevano audio e/o video.

  - Get-CsP2PSessionReport, che fornisce informazioni sul numero e il tipo di sessioni peer-to-peer a cui hanno partecipato gli utenti.

La maggior parte degli amministratori utilizzerà i report disponibili nell'interfaccia di amministrazione di Microsoft 365: non solo i report vengono generati automaticamente, ma offrono anche una rappresentazione grafica dei dati spesso più facili da interpretare rispetto ai valori numerici non elaborati restituiti dall' cmdlet per la creazione di report. Tuttavia, gli amministratori che hanno familiarità con Windows PowerShell possono usare i cmdlet per la creazione di report per restituire dati non prontamente disponibili nei report di Lync Online. Ad esempio, i cmdlet per la creazione di report restituiscono informazioni sulla durata della sessione (la quantità di tempo, in minuti, in cui è durata ogni sessione). Le singole durata della sessione non sono disponibili con i report di Lync Online. Allo stesso modo, nella visualizzazione giornaliera i report di Lync Online visualizzano le informazioni solo per i 14 giorni precedenti. Se si vuole rivedere i totali giornalieri per un giorno diverso, ad esempio una data di quattro mesi fa, è possibile usare i cmdlet per la creazione di report.

Gli amministratori potrebbero anche essere interessati all'articolo che [usa Excel per recuperare i dati di report di office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), che spiega come usare la caratteristica di query di dati OData in Microsoft Excel per creare report di Office 365 personalizzato. I report personalizzati offrono la possibilità di dettare i dati (e la quantità di dati) restituiti dal servizio Reporting di Office 365. I report personalizzati consentono inoltre di eseguire operazioni come specificare l'ordinamento e il raggruppamento dei dati e consentire l'accesso alle informazioni non visualizzate nell'interfaccia di amministrazione.

Gli amministratori con uno sfondo di sviluppo possono usare il servizio Web REST per ottenere informazioni non visualizzate nell'interfaccia di amministrazione di Skype for business online. Il servizio REST è simile al servizio SOAP, in quanto ogni tecnologia offre un modo per trasferire dati XML tra un client e un server. Tuttavia, il servizio REST ha almeno due vantaggi rispetto al servizio SOAP. Per uno, REST esegue i trasferimenti di dati XML usando un formato standardizzato noto come formato di diffusione ATOM. Al contrario, SOAP usa un formato non standard durante il trasferimento dei dati. Inoltre, REST è in grado di trasferire dati tra le reti che bloccano i verbi HTTP diversi da GET e POST.

<div>

## <a name="see-also"></a>Vedere anche


[Report di Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))  


[Servizio Web Reporting di Office 365](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[Informazioni sul servizio Web Reporting di Office 365](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Cmdlet di report di Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[Uso di Excel per recuperare i dati di report di Office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

