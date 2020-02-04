---
title: "Lync Server 2013: Supporto dell'infrastruttura DNS (Domain Name System)"
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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Supporto dell'infrastruttura DNS (Domain Name System) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-08_

Lync Server 2013 richiede DNS (Domain Name System) e lo usa nei modi seguenti:

  - Per individuare i server o i pool interni per le comunicazioni da server a server.

  - Per consentire ai client di individuare il pool Front-end o il server Standard Edition usato per varie transazioni SIP.

  - Per associare gli URL semplici per le conferenze con i server che ospitano tali conferenze.

  - Per consentire ai server e ai client esterni di connettersi a Edge Server o al proxy inverso HTTP per la messaggistica istantanea o i servizi di conferenza.

  - Per abilitare i dispositivi Unified Communications (UC) che non hanno eseguito l'accesso per individuare il pool Front end o il server Standard Edition che esegue il servizio Web Update Device, ottenere gli aggiornamenti e inviare i log.

  - Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.

  - Per il bilanciamento del carico DNS.

<div>


> [!NOTE]  
> Lync Server 2013 non supporta i nomi di dominio internazionalizzati (IDN).



</div>

<div>


> [!IMPORTANT]  
> Il nome specificato deve essere uguale al nome del computer configurato nel server. Per impostazione predefinita, il nome del computer di un computer che non è associato a un dominio è un nome breve e non un nome di dominio completo (FQDN). Generatore di topologie usa gli FQDN e non i nomi brevi. Devi quindi configurare un suffisso DNS sul nome del computer da distribuire come server perimetrale che non è associato a un dominio. <STRONG>Usare solo caratteri standard</STRONG> (tra cui a-z, a-z, 0-9 e segni meno) durante l'assegnazione di nomi di dominio completi di Lync Server, Edge Server e pool. Non usare caratteri Unicode o carattere di sottolineatura. I caratteri non standard di un nome di dominio completo spesso non sono supportati dal DNS esterno e dalle CA pubbliche, ovvero quando il nome di dominio completo deve essere assegnato a SN nel certificato.



</div>

</div>

<span> </span>

</div>

</div>

</div>

