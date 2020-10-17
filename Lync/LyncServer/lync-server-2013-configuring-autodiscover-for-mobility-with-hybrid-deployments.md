---
title: Configurazione dell'individuazione automatica per i dispositivi mobili con distribuzioni ibride
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3b0617094c9dcab6b6eee0cf634440fea63cf16
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502163"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Configurazione dell'individuazione automatica in Lync Server 2013 per dispositivi mobili con distribuzioni ibride

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-18_

Le distribuzioni ibride sono configurazioni che utilizzano sia il servizio cloud di Microsoft Lync Online sia la distribuzione locale. In questo tipo di configurazione, il servizio di individuazione automatica deve essere in grado di individuare l'effettiva posizione dell'utente. Vale a dire che gli aiuti di individuazione automatica nella ricerca dell'account utente e in cui il server che ospita l'account dell'utente sono, indipendentemente dal modo in cui si trova nella distribuzione locale o nella distribuzione di Lync Online.

Ad esempio, se l'account di un utente è ospitato in un server di Lync Online, il tentativo di individuare l'utente avverrà come indicato di seguito, in un processo noto come *individuabilità*:

  - L'utente avvia un tentativo di connessione alla distribuzione locale, **contoso.com**.

  - Il tentativo viene inviato a lyncdiscover.contoso.com, il nome DNS associato al servizio di individuazione automatica.

  - Il servizio di individuazione automatica si riferisce al pool di registrazione presunto nella distribuzione di contoso.com in locale e vengono fornite informazioni sul server principale effettivo dell'utente ospitato in Lync Online. A questo punto, il servizio di individuazione automatica invia all'utente una segnalazione al servizio di individuazione automatica online **lync.com**.

  - L'utente avvia un tentativo di connessione ai servizio di individuazione automatica online lync.com ed è in grado di individuare l'account utente e il server principale dell'utente.

Per abilitare i client mobili per l'individuazione della distribuzione in cui si trova il server principale dell'utente, configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator). Eseguire la procedura seguente per configurare il servizio di configurazione automatica.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configurazione del servizio di individuazione automatica per le distribuzione ibride

1.  Utilizzare Get-CsHostingProvider per recuperare il valore dell'attributo ProxyFQDN.

2.  Da Lync Server Management Shell, digitare
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Dove \[ Identity \] viene sostituita con il nome di dominio dello spazio di indirizzi SIP condiviso.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

