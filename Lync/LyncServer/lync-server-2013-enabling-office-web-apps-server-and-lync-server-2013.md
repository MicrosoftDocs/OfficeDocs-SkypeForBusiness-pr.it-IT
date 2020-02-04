---
title: 'Lync Server 2013: Abilitazione di Office Web Apps Server e Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="8f25b-102">Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f25b-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f25b-103">_**Argomento Ultima modifica:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="8f25b-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="8f25b-104">Lync Server 2013 impiega Office Web Apps Server per gestire le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="8f25b-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="8f25b-105">Per informazioni sui vantaggi di questo approccio, vedere [Panoramica delle conferenze Web in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8f25b-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="8f25b-106">Per usare questi nuovi amministratori delle funzionalità, è necessario installare Office Web Apps Server e configurare Lync Server 2013 per la comunicazione con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="8f25b-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="8f25b-107">Questa documentazione contiene informazioni su come configurare Lync Server 2013 per l'utilizzo con Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="8f25b-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="8f25b-108">La documentazione non fornita contiene informazioni su come installare Office Web Apps Server stesso; per queste informazioni, vedere il sito Web Microsoft Office Web Apps Deployment <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span><span class="sxs-lookup"><span data-stu-id="8f25b-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="8f25b-109">Questa guida include informazioni complete sui prerequisiti per Office Web Apps Server; Tieni presente che il server Office Web Apps deve essere installato in un computer autonomo che non è in grado di eseguire Lync Server, Microsoft SQL Server o qualsiasi altra applicazione server.</span><span class="sxs-lookup"><span data-stu-id="8f25b-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="8f25b-110">Non è necessario che nel computer sia installata una versione di Microsoft Office. Qualsiasi computer usato per eseguire Office Web Apps Server deve avere anche un set di software specifico installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0); questi requisiti, oltre a informazioni sulla configurazione di certificati e Internet Information Services (IIS), vengono descritti in dettaglio nel sito Web Microsoft Office Web Apps Deployment <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span><span class="sxs-lookup"><span data-stu-id="8f25b-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8f25b-111">L'iterazione più recente di Office Web Apps Server è denominata Office Online Server, supportata da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8f25b-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="8f25b-112">Per altre informazioni, vedere la <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">documentazione del server Office Online</A>.</span><span class="sxs-lookup"><span data-stu-id="8f25b-112">For more detail, refer to the <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="8f25b-113">Questo documento illustra le aree tematiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f25b-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="8f25b-114">Configurazione di Lync Server 2013 per l'utilizzo con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="8f25b-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="8f25b-115">Pubblicazione di Office Web Apps Server in Lync Server 2013 con un server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="8f25b-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="8f25b-116">Convalida della configurazione di Office Web Apps Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f25b-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="8f25b-117">Configurazione dei client di Lync Server 2013 per l'uso con Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="8f25b-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

