---
title: 'Lync Server 2013: componenti utilizzati da Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b59f96175925c427f77880012f804daf20bf751
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517773"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="63246-102">Componenti utilizzati da Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63246-102">Components used by Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63246-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="63246-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="63246-104">L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="63246-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="63246-105">In questa sezione vengono descritti i componenti che supportano l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="63246-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="63246-106">Componenti di Response Group</span><span class="sxs-lookup"><span data-stu-id="63246-106">Response Group Components</span></span>

<span data-ttu-id="63246-107">I componenti di Microsoft Lync Server 2013 seguenti supportano l'applicazione Response Group:</span><span class="sxs-lookup"><span data-stu-id="63246-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="63246-108">**Servizio applicazione**     Il servizio applicazione fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio Response Group.</span><span class="sxs-lookup"><span data-stu-id="63246-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="63246-109">Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="63246-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="63246-110">**Applicazione**     Response Group L'applicazione Response Group è una delle applicazioni di comunicazioni unificate ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="63246-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="63246-111">Viene incluso automaticamente quando si distribuisce Response Group.</span><span class="sxs-lookup"><span data-stu-id="63246-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="63246-112">L'applicazione Response Group consente di instradare e accodare le chiamate in arrivo a gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="63246-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="63246-113">**Language Pack**     È necessario un Language Pack per il supporto del riconoscimento vocale e del testo.</span><span class="sxs-lookup"><span data-stu-id="63246-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="63246-114">Queste tecnologie vocali vengono usate quando si configurano messaggi, ad esempio messaggi di benvenuto o di altro tipo, nonché domande e risposte IVR (Interactive Voice Response).</span><span class="sxs-lookup"><span data-stu-id="63246-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="63246-115">Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63246-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="63246-116">**File audio**     I file audio vengono utilizzati per i messaggi e la musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="63246-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="63246-117">**Archivio file**     Response Group utilizza l'archivio file per archiviare i file audio.</span><span class="sxs-lookup"><span data-stu-id="63246-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="63246-118">Più pool di Response Group possono utilizzare la stessa istanza dell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="63246-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="63246-119">Strumento di configurazione di **Response Group**     Lo strumento di configurazione di Response Group è uno strumento basato sul Web che viene utilizzato per creare e configurare Response Group.</span><span class="sxs-lookup"><span data-stu-id="63246-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="63246-120">Lo strumento di configurazione di Response Group è incluso quando si installano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="63246-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="63246-121">Pannello di controllo di **Microsoft Lync Server 2013**     È possibile utilizzare il pannello di controllo di Lync Server per installare e configurare gruppi di agenti e code per i Response Group.</span><span class="sxs-lookup"><span data-stu-id="63246-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="63246-122">**Lync Server Management Shell**     Tutte le impostazioni di Response Group possono essere configurate utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="63246-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="63246-123">**Microsoft Lync 2013**     Gli agenti formali (gli agenti necessari per accedere al gruppo prima che possano accettare le chiamate per il gruppo) utilizzano Lync 2013 per accedere e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="63246-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="63246-124">Se un gruppo di agenti è configurato per gli agenti formali, gli agenti fanno clic su una voce di menu in Lync 2013 per aprire Internet Explorer e visualizzare una console di pagina Web per l'accesso e la disconnessione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="63246-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="63246-125">**Servizi Web**     I servizi Web sono necessari per lo strumento di configurazione di Response Group, la console di accesso e disconnessione degli agenti, il pannello di controllo di Lync Server e il servizio Web client di Response Group.</span><span class="sxs-lookup"><span data-stu-id="63246-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="63246-126">Servizio Web client di **Response Group**     L'applicazione Response Group fornisce un servizio Web client, che può essere utilizzato da applicazioni di terze parti per recuperare informazioni sugli agenti, l'appartenenza al gruppo di agenti, lo stato di accesso dell'agente, lo stato delle chiamate per i gruppi e i gruppi che supportano le chiamate anonime.</span><span class="sxs-lookup"><span data-stu-id="63246-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="63246-127">Lync 2013 e Lync 2010 Attendant utilizzano il servizio Web client di Response Group per recuperare l'elenco dei Response Group che gli agenti possono utilizzare per effettuare chiamate anonime.</span><span class="sxs-lookup"><span data-stu-id="63246-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="63246-128">Il servizio Web client viene incluso quando si installano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="63246-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

