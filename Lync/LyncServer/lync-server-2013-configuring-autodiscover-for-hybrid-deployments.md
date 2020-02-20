---
title: "Lync Server 2013: configurazione dell'individuazione automatica per le distribuzioni ibride"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ec2e0653d9b9d6c8f5412c58895b7ec805c82db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Configurazione dell'individuazione automatica in Lync Server 2013 per le distribuzioni ibride

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-12-12_

Le distribuzioni ibride sono configurazioni che utilizzano sia il servizio cloud di Microsoft Lync Online sia la distribuzione locale. In questo tipo di configurazione, il servizio di individuazione automatica deve essere in grado di individuare l'effettiva posizione dell'utente. Vale a dire che gli aiuti di individuazione automatica nella ricerca dell'account utente e in cui il server che ospita l'account dell'utente sono, indipendentemente dal modo in cui si trova nella distribuzione locale o nella distribuzione di Lync Online.

Ad esempio, se l'account di un utente è ospitato in un server di Lync Online, il tentativo di individuare l'utente avverrà come indicato di seguito, in un processo noto come *individuabilità*:

  - L'utente avvia un tentativo di connessione alla distribuzione locale, **contoso.com**.

  - Il tentativo viene inviato a lyncdiscover.contoso.com, il nome DNS associato al servizio di individuazione automatica.

  - Il servizio di individuazione automatica si riferisce al pool di registrazione presunto nella distribuzione di contoso.com in locale e vengono fornite informazioni sul server principale effettivo dell'utente ospitato in Lync Online. A questo punto, il servizio di individuazione automatica invia all'utente una segnalazione al servizio di individuazione automatica online **lync.com**.

  - L'utente avvia un tentativo di connessione ai servizio di individuazione automatica online lync.com ed è in grado di individuare l'account utente e il server principale dell'utente.

Per consentire ai client di individuare la distribuzione in cui si trova il server Home dell'utente, è necessario configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator). Eseguire la procedura seguente per configurare il servizio di configurazione automatica.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configurazione del servizio di individuazione automatica per le distribuzione ibride

1.  Nell'argomento requisiti del [servizio di individuazione automatica per Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), è possibile utilizzare Get-CsHostingProvider per recuperare il valore dell'attributo ProxyFQDN.

2.  Da Lync Server Management Shell, digitare
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    Dove \[Identity\] viene sostituita con il nome di dominio dello spazio di indirizzi SIP condiviso.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

