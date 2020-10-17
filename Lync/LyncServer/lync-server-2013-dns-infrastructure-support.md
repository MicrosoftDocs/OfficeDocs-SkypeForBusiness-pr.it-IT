---
title: "Lync Server 2013: supporto dell'infrastruttura DNS"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed40fb498b93f0c6f3b1a8d32c7642f7714998ea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528943"
---
# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Supporto dell'infrastruttura DNS in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-08_

Lync Server 2013 richiede DNS (Domain Name System) e lo utilizza nei modi seguenti:

  - Per individuare i pool o i server interni per le comunicazioni tra server.

  - Per consentire ai client di individuare il pool Front End o il server Standard Edition utilizzato per diverse transazioni SIP.

  - Per associare gli URL semplici per conferenze ai server che ospitano le conferenze.

  - Per consentire ai server e ai client esterni di connettersi ai server perimetrali o al proxy inverso HTTP per i servizi di messaggistica istantanea o conferenza.

  - Per consentire ai dispositivi per comunicazioni unificate non connessi di individuare il pool Front End o il server Standard Edition che esegue il servizio Web Aggiornamento dispositivi, ottenere gli aggiornamenti e inviare i registri.

  - Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.

  - Per il bilanciamento del carico DNS.

<div>


> [!NOTE]  
> Lync Server 2013 non supporta i nomi di dominio internazionalizzati (Internationalized Domain Name).



</div>

<div>


> [!IMPORTANT]  
> Il nome specificato deve essere uguale al nome computer configurato nel server. Per impostazione predefinita, il nome del computer di un computer che non è aggiunto a un dominio è un nome breve e non un nome di dominio completo (FQDN). Generatore di topologie utilizza gli FQDN e non i nomi brevi. Pertanto, è necessario configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale non aggiunto a un dominio. Quando si assegnano FQDN dei server Lync, server perimetrali e pool, <STRONG>utilizzare solo caratteri standard</STRONG> (tra cui a – z, a – z, 0 – 9 e segni meno). Non utilizzare caratteri Unicode o di sottolineatura. I caratteri non standard in un FQDN spesso non sono supportati dal DNS esterno e dalle CA pubbliche (ovvero, quando il nome di dominio completo deve essere assegnato a SN nel certificato).



</div>

</div>

<span> </span>

</div>

</div>

</div>

