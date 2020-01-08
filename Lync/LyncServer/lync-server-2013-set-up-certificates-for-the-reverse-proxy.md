---
title: 'Lync Server 2013: Configurare i certificati per il proxy inverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the reverse proxy
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412938(v=OCS.15)
ms:contentKeyID: 48185291
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be12aabd8c4d7aa026e6c7e1ab6f1d5189a596c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="560d5-102">Configurare i certificati per il proxy inverso in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="560d5-102">Set up certificates for the reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="560d5-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="560d5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="560d5-104">Ogni server proxy inverso richiede un certificato del server Web per l'uso da parte del servizio di ascolto.</span><span class="sxs-lookup"><span data-stu-id="560d5-104">Each reverse proxy server requires a web server certificate for use by the listening service.</span></span> <span data-ttu-id="560d5-105">Il certificato del server Web deve essere emesso da un'autorità di certificazione pubblica (CA).</span><span class="sxs-lookup"><span data-stu-id="560d5-105">The web server certificate must be issued by a public certification authority (CA).</span></span>

<span data-ttu-id="560d5-106">Per informazioni dettagliate su questo e altri requisiti per i certificati, vedere [requisiti di certificato per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="560d5-106">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>

## <a name="to-set-up-a-web-services-certificate-for-the-reverse-proxy"></a><span data-ttu-id="560d5-107">Per configurare un certificato di servizi Web per il proxy inverso</span><span class="sxs-lookup"><span data-stu-id="560d5-107">To set up a Web Services certificate for the reverse proxy</span></span>

  - <span data-ttu-id="560d5-108">È necessario avere già configurato il proxy inverso, inclusa la configurazione del certificato dei servizi Web.</span><span class="sxs-lookup"><span data-stu-id="560d5-108">You should have already set up your reverse proxy, including setting up the Web Services certificate.</span></span> <span data-ttu-id="560d5-109">In caso contrario, prima di iniziare la distribuzione di Edge Server, seguire le procedure descritte in configurare i [server proxy inverso per Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) per creare richieste e installare il certificato dei servizi Web e quindi creare ogni regola di pubblicazione Web e configurarla in modo da usare il certificato.</span><span class="sxs-lookup"><span data-stu-id="560d5-109">If you did not do so before starting your deployment of your Edge Servers, use the procedures in [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) to create request and install the Web Services certificate, and then create each web publishing rule and configure it to use the certificate.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

