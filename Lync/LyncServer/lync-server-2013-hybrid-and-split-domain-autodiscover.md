---
title: 'Lync Server 2013: ibrido e Split-Domain-individuazione automatica'
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
ms.openlocfilehash: 3fca0097f6ad0264755dd9d0a80a296e9ebf60b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Ambiente ibrido e Split-Domain-individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-14_

Uno spazio di indirizzi SIP condiviso, noto anche come distribuzione di *domini intermedi* o una distribuzione *ibrida* , è una configurazione in cui gli utenti vengono distribuiti in una distribuzione locale e in un ambiente online. L'esito desiderato consiste nel fatto che un utente, indipendentemente dal luogo in cui si trova il server Home (locale o online), acceda alla distribuzione e venga reindirizzato al percorso del server principale. A tale scopo, la caratteristica di individuazione automatica di Lync Server 2013 viene utilizzata per reindirizzare l'utente online alla topologia online. È possibile eseguire questa operazione configurando l'URL (Uniform Resource Locator) di individuazione automatica utilizzando Lync Server Management Shell, il cmdlet **Get-CsHostingProvider** e il cmdlet **Set-CsHostingProvider** .

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>Mobilità per la distribuzione del dominio diviso

Sarà necessario raccogliere e prendere nota degli attributi distribuiti seguenti:

  - Da Lync Server Management Shell, digitare
    
        Get-CsHostingProvider

  - Nei risultati, individuare il provider online con l'attributo **ProxyFQDN**. Ad esempio, sipfed.online.lync.com.

  - Registrare il valore di ProxyFQDN.

  - Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online.

  - Abilitare la federazione per il provider online. Per impostazione predefinita, tutti gli utenti online sono abilitati per la Federazione dei domini e possono comunicare con tutti i domini.

  - Se si definiscono domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati in modo esplicito.

  - Per la Federazione online, è necessario pianificare le eccezioni del firewall, i certificati e i record host DNS (A o AAAA, se si utilizza IPv6). È inoltre necessario configurare i criteri di federazione. Per informazioni dettagliate, vedere [Planning for Lync Server 2013 e Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

