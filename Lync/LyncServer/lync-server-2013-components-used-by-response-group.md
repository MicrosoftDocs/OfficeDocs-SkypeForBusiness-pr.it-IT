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
ms.openlocfilehash: 508b5f22c2f56c5ce6a4bbb4afaacef10ba714e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="9a95f-102">Componenti utilizzati da Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a95f-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a95f-103">_**Ultimo argomento modificato:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="9a95f-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="9a95f-104">L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9a95f-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9a95f-105">In questa sezione vengono descritti i componenti che supportano l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="9a95f-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="9a95f-106">Componenti di Response Group</span><span class="sxs-lookup"><span data-stu-id="9a95f-106">Response Group Components</span></span>

<span data-ttu-id="9a95f-107">I componenti di Microsoft Lync Server 2013 seguenti supportano l'applicazione Response Group:</span><span class="sxs-lookup"><span data-stu-id="9a95f-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="9a95f-108">**Application Service**   Application Service fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di comunicazione unificata, ad esempio Response Group.</span><span class="sxs-lookup"><span data-stu-id="9a95f-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="9a95f-109">Il servizio applicazione viene installato automaticamente in tutti i front end server in un pool Front end e in tutti i server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9a95f-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="9a95f-110">**Response Group**   Application l'applicazione Response Group è una delle applicazioni di comunicazione unificate ospitate dal servizio applicazione.</span><span class="sxs-lookup"><span data-stu-id="9a95f-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="9a95f-111">Viene incluso automaticamente quando si distribuisce Response Group.</span><span class="sxs-lookup"><span data-stu-id="9a95f-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="9a95f-112">L'applicazione Response Group consente di instradare e accodare le chiamate in arrivo a gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="9a95f-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="9a95f-113">**Language Pack**   è necessario un Language Pack per il supporto del riconoscimento vocale e del testo.</span><span class="sxs-lookup"><span data-stu-id="9a95f-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="9a95f-114">Queste tecnologie vocali vengono usate quando si configurano messaggi, ad esempio messaggi di benvenuto o di altro tipo, nonché domande e risposte IVR (Interactive Voice Response).</span><span class="sxs-lookup"><span data-stu-id="9a95f-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="9a95f-115">Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a95f-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="9a95f-116">**I file audio vengono**utilizzati per i messaggi e la musica di attesa.   </span><span class="sxs-lookup"><span data-stu-id="9a95f-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="9a95f-117">\*\*\*\*   Il gruppo di risposta dell'archivio file utilizza l'archivio file per archiviare i file audio.</span><span class="sxs-lookup"><span data-stu-id="9a95f-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="9a95f-118">Più pool di Response Group possono utilizzare la stessa istanza dell'archivio file.</span><span class="sxs-lookup"><span data-stu-id="9a95f-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="9a95f-119">**Strumento di configurazione di Response Group**   lo strumento di configurazione di Response Group è uno strumento basato sul Web che viene utilizzato per creare e configurare i Response Group.</span><span class="sxs-lookup"><span data-stu-id="9a95f-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="9a95f-120">Lo strumento di configurazione di Response Group è incluso quando si installano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="9a95f-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="9a95f-121">**Pannello di controllo di Microsoft Lync Server 2013**   è possibile utilizzare il pannello di controllo di Lync Server per installare e configurare gruppi di agenti e code per i Response Group.</span><span class="sxs-lookup"><span data-stu-id="9a95f-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="9a95f-122">**Lync Server Management Shell**   tutte le impostazioni di Response Group possono essere configurate utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9a95f-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="9a95f-123">**Microsoft Lync 2013**   agenti formali (gli agenti necessari per accedere al gruppo prima che possano accettare le chiamate per il gruppo) utilizzano Lync 2013 per accedere e disconnettersi dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="9a95f-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="9a95f-124">Se un gruppo di agenti è configurato per gli agenti formali, gli agenti fanno clic su una voce di menu in Lync 2013 per aprire Internet Explorer e visualizzare una console di pagina Web per l'accesso e la disconnessione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="9a95f-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="9a95f-125">\*\*\*\*   I servizi Web dei servizi Web sono necessari per lo strumento di configurazione di Response Group, la console di accesso e disconnessione degli agenti, il pannello di controllo di Lync Server e il servizio Web client di Response Group.</span><span class="sxs-lookup"><span data-stu-id="9a95f-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="9a95f-126">**Response Group client Web**   Response Group Application fornisce un servizio Web client, che può essere utilizzato da applicazioni di terze parti per recuperare informazioni sugli agenti, l'appartenenza a un gruppo di agenti, lo stato di accesso dell'agente, lo stato delle chiamate per i gruppi e i gruppi che supportano le chiamate anonime.</span><span class="sxs-lookup"><span data-stu-id="9a95f-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="9a95f-127">Lync 2013 e Lync 2010 Attendant utilizzano il servizio Web client di Response Group per recuperare l'elenco dei Response Group che gli agenti possono utilizzare per effettuare chiamate anonime.</span><span class="sxs-lookup"><span data-stu-id="9a95f-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="9a95f-128">Il servizio Web client viene incluso quando si installano i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="9a95f-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

