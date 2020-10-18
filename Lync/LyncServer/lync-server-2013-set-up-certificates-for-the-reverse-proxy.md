---
title: 'Lync Server 2013: configurare i certificati per il proxy inverso'
description: 'Lync Server 2013: configurare i certificati per il proxy inverso.'
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
ms.openlocfilehash: f4b84241775bb3594840b68551048c01ff5faba2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575372"
---
# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="1fa14-103">Configurare i certificati per il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fa14-103">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fa14-104">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1fa14-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1fa14-p101">Ogni server proxy inverso richiede un certificato per server Web server che deve essere utilizzato dal servizio di attesa. Questo certificato deve essere emesso da un'Autorità di certificazione (CA) pubblica.</span><span class="sxs-lookup"><span data-stu-id="1fa14-p101">Each reverse proxy server requires a web server certificate for use by the listening service. The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="1fa14-107">Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti dei certificati per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1fa14-107">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="1fa14-108">Per impostare un certificato dei servizi Web per il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="1fa14-108">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="1fa14-109">È necessario avere già configurato il proxy inverso, inclusa l'installazione del certificato dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="1fa14-109">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="1fa14-110">Se non è stato possibile eseguire questa operazione prima di iniziare la distribuzione dei server perimetrali, utilizzare le procedure illustrate in configurare i [server proxy inversi per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) per creare la richiesta e installare il certificato dei servizi Web e quindi creare ogni regola di pubblicazione Web e configurarla per l'utilizzo del certificato.</span><span class="sxs-lookup"><span data-stu-id="1fa14-110">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

