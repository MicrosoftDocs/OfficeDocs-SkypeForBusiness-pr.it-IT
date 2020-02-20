---
title: "Lync Server 2013: supporto per l'integrazione di Exchange e SharePoint"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="0b2a0-102">Supporto per l'integrazione di Exchange e SharePoint in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b2a0-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b2a0-103">_**Ultimo argomento modificato:** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="0b2a0-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="0b2a0-104">Lync Server 2013 e Lync 2013 sono in grado di comunicare in modo sicuro e senza problemi con altre applicazioni e prodotti server, tra cui Office 2013, Exchange Server 2013, Exchange Server 2016 e SharePoint, se si integrano questi prodotti.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="0b2a0-105">L'integrazione di Lync Server 2013 e Office consente agli utenti di accedere in modo contestuale alle funzionalità di messaggistica istantanea, presenza avanzata, telefonia e conferenza di Lync.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="0b2a0-106">Gli utenti di Office possono accedere alle funzionalità di Lync dall'interno del client di messaggistica e collaborazione di Outlook 2013 e di altre applicazioni di Office o da una pagina di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="0b2a0-107">Gli utenti possono inoltre visualizzare un record delle conversazioni di Lync nella cartella Cronologia conversazioni di Outlook.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="0b2a0-108">Se integrato con Exchange 2013, Exchange 2016 o Exchange Online, Lync Server 2013 supporta anche gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b2a0-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="0b2a0-109">Archivio contatti unificato, che consente agli utenti di archiviare tutte le informazioni di contatto in Exchange o Exchange online in modo che le informazioni siano disponibili a livello globale in Lync 2013, Exchange, Outlook e Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="0b2a0-110">Cronologia conversazioni e cronologia Web Conferencing, archiviata nelle cartelle degli utenti di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="0b2a0-111">L'archiviazione di contenuto di Lync, ad esempio il contenuto di messaggistica istantanea e riunione, può essere archiviata nell'archivio di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b2a0-112">Lync Server 2013 supporta l'integrazione con le versioni precedenti di Microsoft Exchange Server e SharePoint Server, ma non tutte le funzionalità sono supportate con queste versioni precedenti, ad esempio l'integrazione dell'archiviazione di archiviazione con Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="0b2a0-113">Se si esegue la migrazione degli utenti a Exchange 2013 o Exchange 2016, è possibile utilizzare sia l'archiviazione di Exchange che l'archiviazione di Lync Server su base provvisoria, mentre si completa la migrazione.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="0b2a0-114">L'utilizzo permanente sia dell'archiviazione di Exchange che di Lync Server non è supportato.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="0b2a0-115">L'integrazione di Lync Server 2013 con Exchange Server e SharePoint Server richiede l'autenticazione da server a server tra i server che eseguono Lync Server 2013, Exchange Server e SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="0b2a0-116">Lync Server 2013 supporta il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="0b2a0-117">Per l'autenticazione server-to-server locale tra due server Microsoft, non è necessario utilizzare un server token di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="0b2a0-118">Lync Server 2013, Exchange Server e SharePoint Server dispongono di un server token incorporato che può essere utilizzato ai fini dell'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="0b2a0-119">Ad esempio, Lync Server 2013 può emettere e firmare un token di sicurezza e utilizzarlo per comunicare con Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="0b2a0-120">In questo caso, non è necessario utilizzare un server token di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="0b2a0-121">Lync Server 2013 supporta i due scenari di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="0b2a0-122">Questi includono la configurazione dell'autenticazione server-to-server tra:</span><span class="sxs-lookup"><span data-stu-id="0b2a0-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="0b2a0-123">Un'installazione locale di Lync Server 2013 e un'installazione locale di Exchange Server 2013, Exchange Server 2016 e/o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="0b2a0-124">Una coppia di componenti di Office (ad esempio, tra Microsoft Exchange 365 e Microsoft Lync Server 365 o tra Microsoft Lync Server 365 e Microsoft SharePoint 365).</span><span class="sxs-lookup"><span data-stu-id="0b2a0-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b2a0-125">L'autenticazione da server a server tra un server locale e un componente di Office 365 non è supportata in questa versione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-125">Server-to-server authentication between an on-premises server and an Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="0b2a0-126">Tra le altre cose, ciò significa che non è possibile configurare l'autenticazione da server a server tra un'installazione locale di Lync Server 2013 e Microsoft Exchange 365.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="0b2a0-127">Per informazioni dettagliate sull'autenticazione da server a server, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o alla documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="0b2a0-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

