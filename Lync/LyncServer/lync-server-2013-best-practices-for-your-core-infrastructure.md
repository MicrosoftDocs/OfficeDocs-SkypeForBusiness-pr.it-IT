---
title: "Lync Server 2013: procedure consigliate per l'infrastruttura di base"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6a8663bfae2411926fe08a497a5004def051ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Procedure consigliate per l'infrastruttura di base in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-01-27_

Probabilmente hai già adottato misure per progettare la tolleranza di errore nel sistema, usando procedure come la garanzia di ridondanza hardware, la protezione contro la perdita di corrente, l'installazione di routine degli aggiornamenti della sicurezza e delle misure antivirus e il monitoraggio delle attività del server. Queste procedure non sono utili solo per l'infrastruttura di Microsoft Lync Server 2013, ma anche per l'intera rete. Se non sono state implementate queste procedure, è consigliabile eseguire questa operazione prima di distribuire Lync Server 2013.

Per proteggere i server della distribuzione di 2013 di Lync Server da danni accidentali o intenzionali che potrebbero causare tempi di inattività, seguire le seguenti precauzioni:

  - Aggiornare i server con gli aggiornamenti della sicurezza. La sottoscrizione al servizio di notifica della sicurezza Microsoft consente di ricevere una notifica immediata dei rilasci del Bollettino della sicurezza per qualsiasi prodotto Microsoft. Per eseguire la sottoscrizione, visitare il sito Web Microsoft Technical Security [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)Notifications.

  - Verificare che i diritti di accesso siano configurati correttamente.

  - Conservare i server in un ambiente fisico che impedisce l'accesso non autorizzato. Verificare che in tutti i server sia installato un software antivirus adeguato. Tieni aggiornato il software con i file di firma del virus più recenti. Usa la funzionalità di aggiornamento automatico dell'applicazione antivirus per conservare le firme del virus aggiornate.

  - È consigliabile disabilitare i servizi di sistema operativo Windows Server che non sono necessari nei computer in cui è installato Lync Server 2013.

  - Crittografare sistemi operativi e unità disco in cui i dati vengono archiviati con un sistema di crittografia completo, a meno che non sia possibile garantire il controllo costante e completo dei server, il totale isolamento fisico e la disattivazione corretta e sicura del disco sostituito o non riuscito unità.

  - Disabilitare tutte le porte di accesso diretto alla memoria esterna (DMA) del server, a meno che non sia possibile garantire un controllo molto limitato sull'accesso fisico ai server. Gli attacchi basati su DMA, che possono essere avviati abbastanza facilmente, potrebbero esporre informazioni molto riservate, come le chiavi di crittografia private.

</div>

<span> </span>

</div>

</div>

</div>

