---
title: 'Lync Server 2013: richiedere i certificati in anticipo (facoltativo)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7e671fe61f5d8b9e43593bf99e0ecf0e1e37109
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511963"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a><span data-ttu-id="1fe8d-102">Richiedere certificati in anticipo (facoltativo) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fe8d-102">Request certificates in advance (optional) for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fe8d-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1fe8d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1fe8d-104">I certificati sono necessari per tutti i server interni che eseguono Lync Server 2013, tra cui ogni server Enterprise Edition front-end, server Standard Edition, Director, server perimetrale e Mediation Server autonomo.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-104">Certificates are required for all internal servers that are running Lync Server 2013, including each Enterprise Edition Front End Server, Standard Edition server, Director, Edge Server and stand-alone Mediation Server.</span></span> <span data-ttu-id="1fe8d-105">Benché per i server interni sia consigliata un'autorità di certificazione (CA) globale (enterprise) interna, è inoltre possibile utilizzare una CA pubblica.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-105">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="1fe8d-106">Per informazioni dettagliate sui requisiti dei certificati e sull'utilizzo di una CA pubblica, vedere [Certificate Requirements for Internal Servers in Lync server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-106">For details about certificate requirements and about the use of a public CA, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="1fe8d-107">Nel programma di installazione di Lync Server 2013 è inclusa la procedura guidata certificate, che facilita le attività relative alla richiesta, all'assegnazione e all'installazione dei certificati durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-107">Lync Server 2013 setup includes the Certificate Wizard, which facilitates the tasks of requesting, assigning, and installing certificates during deployment.</span></span> <span data-ttu-id="1fe8d-108">Se si desidera richiedere i certificati prima di installare i server (ad esempio, per risparmiare tempo durante la distribuzione effettiva dei server), è possibile farlo utilizzando un computer in cui sono installati gli strumenti di amministrazione di Lync Server 2013 o utilizzando una procedura di richiesta di certificato definita nell'organizzazione, purché siano esportabili e contengano tutti i nomi dei soggetti alternativi richiesti.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-108">If you want to request certificates prior to installing servers (for instance, to save time during actual deployment of servers), you can do so by using a computer on which the Lync Server 2013 administrative tools are installed or by using a certificate request procedure defined in your organization, as long as you make sure that the certificates are exportable and contain all the required subject alternative names.</span></span> <span data-ttu-id="1fe8d-109">La richiesta di certificati in anticipo è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-109">Requesting certificates in advance is optional.</span></span> <span data-ttu-id="1fe8d-110">Se non vengono richiesti in anticipo, è necessario richiederli come parte del programma di installazione di ogni server che richiede un certificato.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-110">If you do not request them in advance, you must request them as part of the setup of each server that requires a certificate.</span></span>

<span data-ttu-id="1fe8d-111">In questa documentazione relativa alla distribuzione vengono fornite le procedure per l'utilizzo della creazione guidata certificati per richiedere i certificati nell'ambito del processo di installazione, come descritto in [Configure Certificates for Servers in Lync server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure Certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md)e [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-111">This Deployment documentation provides procedures for using the Certificate Wizard to request certificates as part of the setup process, as described in the [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md), [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md), and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) sections of this Deployment documentation.</span></span> <span data-ttu-id="1fe8d-112">Se si richiedono preventivamente i certificati, è necessario modificare le procedure di distribuzione dei certificati in queste sezioni, per importare e assegnare i certificati anziché richiederli al momento della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-112">If you request certificates in advance, you must modify the certificate deployment procedures in those sections as appropriate to importing and assigning the certificates instead of requesting them at the time of deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1fe8d-113">Lync Server 2013 include il supporto per i certificati SHA-256 per le connessioni dai client che eseguono i sistemi operativi Windows Vista, Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 e Windows 7 e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-113">Lync Server 2013 includes support for SHA-256 certificates for connections from clients running the Windows Vista, Windows Server&nbsp;2008, Windows Server&nbsp;2008&nbsp;R2, and Windows 7 operating systems, and Lync Phone Edition.</span></span> <span data-ttu-id="1fe8d-114">Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.</span><span class="sxs-lookup"><span data-stu-id="1fe8d-114">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

