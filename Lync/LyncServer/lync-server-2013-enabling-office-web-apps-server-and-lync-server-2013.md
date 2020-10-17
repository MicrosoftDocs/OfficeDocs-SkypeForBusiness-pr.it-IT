---
title: 'Lync Server 2013: attivazione del server Office Web Apps e di Lync Server 2013'
description: 'Lync Server 2013: attivazione del server Office Web Apps e di Lync Server 2013.'
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
ms.openlocfilehash: a1bf4e09dc29bf344b78df50595258f0663cd731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546522"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="b49f0-103">Configurazione dell'integrazione con Office Web Apps Server e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b49f0-103">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b49f0-104">_**Ultimo argomento modificato:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="b49f0-104">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="b49f0-105">Lync Server 2013 utilizza il server Office Web Apps per gestire le presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="b49f0-105">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="b49f0-106">Per informazioni sui vantaggi di questo approccio, vedere [Overview of Web Conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b49f0-106">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="b49f0-107">Per poter utilizzare questi nuovi amministratori delle funzionalità, è necessario installare il server Office Web Apps e configurare Lync Server 2013 per la comunicazione con il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="b49f0-107">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="b49f0-108">In questa documentazione vengono fornite informazioni su come configurare Lync Server 2013 per l'utilizzo con il server Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="b49f0-108">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="b49f0-109">La documentazione non fornita contiene informazioni su come installare il server Office Web Apps stesso. per tali informazioni, vedere il sito Web di distribuzione di Microsoft Office Web Apps all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="b49f0-109">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="b49f0-110">Tale guida include informazioni complete sui prerequisiti per il server Office Web Apps. Si noti che il server Office Web Apps deve essere installato in un computer autonomo che non esegue Lync Server, Microsoft SQL Server o qualsiasi altra applicazione server.</span><span class="sxs-lookup"><span data-stu-id="b49f0-110">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="b49f0-111">(Non è necessario che nel computer sia installata alcuna versione di Microsoft Office). Qualsiasi computer utilizzato per eseguire il server Office Web Apps deve disporre anche di un insieme specifico di software installato (inclusi .NET Framework 4,5 e Windows PowerShell 3,0). tali requisiti, oltre alle informazioni sulla configurazione dei certificati e di Internet Information Services (IIS), vengono illustrati in dettaglio nel sito Web Microsoft Office Web Apps Deployment all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=257525> .</span><span class="sxs-lookup"><span data-stu-id="b49f0-111">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b49f0-112">L'ultima iterazione del server Office Web Apps è denominata Office Online Server, che è supportato da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b49f0-112">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="b49f0-113">Per ulteriori informazioni, fare riferimento alla <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">documentazione di Office Online Server</A>.</span><span class="sxs-lookup"><span data-stu-id="b49f0-113">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="b49f0-114">In questo documento sono riportate le aree tematiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b49f0-114">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="b49f0-115">Configurazione di Lync Server 2013 per l'utilizzo con il server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="b49f0-115">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="b49f0-116">Pubblicazione del server Office Web Apps in Lync Server 2013 utilizzando un server proxy inverso</span><span class="sxs-lookup"><span data-stu-id="b49f0-116">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="b49f0-117">Convalidare la configurazione del server Office Web Apps in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b49f0-117">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="b49f0-118">Configurazione dei client di Lync Server 2013 per l'utilizzo con il server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="b49f0-118">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

