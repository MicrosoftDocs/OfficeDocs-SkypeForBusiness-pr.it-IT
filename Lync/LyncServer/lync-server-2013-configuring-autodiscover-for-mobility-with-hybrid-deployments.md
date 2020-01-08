---
title: Configurazione dell'individuazione automatica per i dispositivi mobili con distribuzioni ibride
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>Configurazione dell'individuazione automatica in Lync Server 2013 per i dispositivi mobili con distribuzioni ibride

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-18_

Le distribuzioni ibride sono configurazioni che usano sia il servizio cloud di Microsoft Lync Online che la distribuzione locale. In questo tipo di configurazione il servizio di individuazione automatica deve essere in grado di individuare la posizione in cui si trova l'utente. Vale a dire che l'individuazione automatica aiuta a trovare l'account utente e la posizione in cui il server che ospita l'account dell'utente è, indipendentemente dal fatto che si trovi nella distribuzione locale o nella distribuzione di Lync Online.

Ad esempio, se l'account di un utente è ospitato in un server in Lync Online, il tentativo di individuare l'utente avverrà come indicato di seguito, in un processo noto come *individuabilità*:

  - L'utente avvia un tentativo di connessione alla distribuzione locale, **contoso.com**.

  - Il tentativo viene inviato a lyncdiscover.contoso.com, il nome DNS associato al servizio di individuazione automatica.

  - L'individuazione automatica si riferisce al pool di registrar assunto presso la contoso.com nella distribuzione locale e viene fornita informazioni sul server Home effettivo dell'utente ospitato in Lync Online. L'individuazione automatica invia quindi all'utente un riferimento al servizio di individuazione automatica di **Lync.com** online.

  - L'utente avvia un tentativo di connessione al servizio di individuazione automatica di lync.com online ed è in grado di individuare l'account dell'utente e il server principale dell'utente.

Per consentire ai client mobili di individuare la distribuzione in cui si trova il server Home dell'utente, è necessario configurare il servizio di individuazione automatica con un nuovo URL (Uniform Resource Locator). Per configurare il servizio di individuazione automatica, eseguire le operazioni seguenti.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>Configurazione dell'individuazione automatica per distribuzioni ibride

1.  Puoi usare Get-CsHostingProvider per recuperare il valore dell'attributo ProxyFQDN.

2.  In Lync Server Management Shell digitare
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    Dove \[identità\] viene sostituita con il nome di dominio dello spazio di indirizzi SIP condiviso.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

