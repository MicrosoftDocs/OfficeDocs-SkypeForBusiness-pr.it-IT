---
title: 'Lync Server 2013: Configurare i certificati per il proxy inverso'
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
ms.openlocfilehash: fe45f9e7d422da53e9dc531721d4b678685eb2b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a>Configurare i certificati per il proxy inverso in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Ogni server proxy inverso richiede un certificato del server Web per l'uso da parte del servizio di ascolto. Il certificato del server Web deve essere emesso da un'autorità di certificazione pubblica (CA).

Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a>Per configurare un certificato di servizi Web per il proxy inverso

  - È necessario avere già configurato il proxy inverso, inclusa la configurazione del certificato dei servizi Web. In caso contrario, prima di iniziare la distribuzione di Edge Server, seguire le procedure descritte in configurare i [server proxy inverso per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) per creare richieste e installare il certificato dei servizi Web e quindi creare ogni regola di pubblicazione Web e configurarla in modo da usare il certificato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

