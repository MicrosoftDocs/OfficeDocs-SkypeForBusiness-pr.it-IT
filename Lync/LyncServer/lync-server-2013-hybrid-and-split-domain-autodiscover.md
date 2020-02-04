---
title: 'Lync Server 2013: Hybrid e Split-Domain-individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Hybrid e Split-Domain-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-14_

Uno spazio di indirizzi SIP condiviso, noto anche come distribuzione di *domini separati* o una distribuzione *ibrida* , è una configurazione in cui gli utenti vengono distribuiti in una distribuzione locale e in un ambiente online. Il risultato desiderato consiste nell'avere un utente, indipendentemente da dove si trova il proprio Home Server (locale o online), accedere alla distribuzione ed essere reindirizzati alla posizione del proprio Home Server. A questo scopo, la funzionalità di individuazione automatica di Lync Server 2013 viene usata per reindirizzare l'utente online alla topologia online. Puoi eseguire questa operazione configurando l'URL (Uniform Resource Locator) di individuazione automatica tramite Lync Server Management Shell, il cmdlet **Get-CsHostingProvider** e il cmdlet **Set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilità per la distribuzione di domini divisi

Sarà necessario raccogliere e registrare i seguenti attributi distribuiti:

  - In Lync Server Management Shell digitare
    
        Get-CsHostingProvider

  - Nei risultati trovare il provider online con l'attributo **ProxyFqdn**. Ad esempio, sipfed.online.lync.com.

  - Registrare il valore di ProxyFQDN.

  - Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online.

  - Abilitare la Federazione per il provider online. Per impostazione predefinita, tutti gli utenti online sono abilitati per la Federazione del dominio e possono comunicare con tutti i domini.

  - Se si definiscono i domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati esplicitamente.

  - Per la Federazione online, è necessario pianificare le eccezioni, i certificati e l'host DNS (A o AAAA, se si usano i record IPv6). È inoltre necessario configurare i criteri federativi. Per informazioni dettagliate, vedere [pianificazione per Lync server 2013 e Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

