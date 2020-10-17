---
title: 'Lync Server 2013: configurare i certificati per il proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e5bf87e02dbcdebeb8b1bb5a7a360c2c91ab00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509873"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Configurare i certificati per il proxy inverso in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Ogni server proxy inverso richiede un certificato per server Web server che deve essere utilizzato dal servizio di attesa. Questo certificato deve essere emesso da un'Autorità di certificazione (CA) pubblica.

Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>Per impostare un certificato dei servizi Web per il proxy inverso

  - È necessario avere già configurato il proxy inverso, inclusa l'installazione del certificato dei servizi Web. Se non è stato possibile eseguire questa operazione prima di iniziare la distribuzione dei server perimetrali, utilizzare le procedure illustrate in configurare i [server proxy inversi per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) per creare la richiesta e installare il certificato dei servizi Web e quindi creare ogni regola di pubblicazione Web e configurarla per l'utilizzo del certificato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

