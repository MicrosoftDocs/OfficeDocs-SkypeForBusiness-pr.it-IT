---
title: 'Lync Server 2013: strumenti di gestione di Windows PowerShell e Lync Server'
description: 'Lync Server 2013: strumenti di gestione di Windows PowerShell e Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546042"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="21d62-103">Strumenti di gestione di Windows PowerShell e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d62-103">Windows PowerShell and Lync Server 2013 management tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d62-104">_**Ultimo argomento modificato:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="21d62-104">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="21d62-105">In Microsoft Lync Server 2013, gli strumenti di gestione vengono implementati tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21d62-105">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="21d62-106">Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di script completo.</span><span class="sxs-lookup"><span data-stu-id="21d62-106">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="21d62-107">Gli strumenti di Lync Server 2013 implementati tramite Windows PowerShell includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="21d62-107">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="21d62-108">**Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="21d62-108">**Topology Builder**.</span></span> <span data-ttu-id="21d62-109">Per creare, modificare e pubblicare la topologia pianificata, è possibile utilizzare Generatore di topologie e convalidare la topologia prima di iniziare le installazioni del server.</span><span class="sxs-lookup"><span data-stu-id="21d62-109">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="21d62-110">Quando si installa Lync Server 2013 nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il server viene distribuito come indicato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="21d62-110">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="21d62-111">Dopo l'installazione, le informazioni di configurazione vengono replicate automaticamente in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="21d62-111">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="21d62-112">I componenti possono essere aggiunti alla distribuzione solo tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="21d62-112">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="21d62-113">**Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="21d62-113">**Lync Server Management Shell**.</span></span> <span data-ttu-id="21d62-114">È possibile utilizzare Lync Server Management Shell per la gestione completa della riga di comando della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="21d62-114">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="21d62-115">**Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="21d62-115">**Lync Server Control Panel**.</span></span> <span data-ttu-id="21d62-116">È possibile utilizzare l'interfaccia utente del pannello di controllo di Microsoft Lync Server 2013 per gestire le attività più comuni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="21d62-116">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="21d62-117">Questi strumenti utilizzano i cmdlet di Windows PowerShell per la gestione della distribuzione, inclusi quasi 550 cmdlet specifici del prodotto.</span><span class="sxs-lookup"><span data-stu-id="21d62-117">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="21d62-118">I cmdlet di sicurezza inclusi in Lync Server 2013 vengono utilizzati principalmente per gestire l'autenticazione e i diritti utente e le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="21d62-118">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="21d62-119">È disponibile un'ampia gamma di cmdlet per la gestione dell'autenticazione, inclusi i cmdlet per l'autenticazione tramite certificato e PIN.</span><span class="sxs-lookup"><span data-stu-id="21d62-119">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="21d62-120">Inoltre, un certo numero di cmdlet consentono di utilizzare la nuova funzionalità di controllo di accesso Role-Based (RBAC) per delegare il controllo amministrativo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21d62-120">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="21d62-121">Per informazioni dettagliate sui cmdlet di Lync Server, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="21d62-121">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="21d62-122">Le funzionalità per la sicurezza degli script per Windows PowerShell sono progettate appositamente per evitare alcuni dei problemi di sicurezza correlati agli script di tecnologie meno recenti, incluso Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="21d62-122">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="21d62-123">Le funzionalità di sicurezza di Windows PowerShell sono pensate per creare un ambiente in cui gli utenti non possono eseguire gli script facilmente o in modo inconsapevole.</span><span class="sxs-lookup"><span data-stu-id="21d62-123">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="21d62-124">Le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="21d62-124">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="21d62-125">È possibile modificare lo stato di queste funzionalità per adattarle alle esigenze specifiche per gli script e a un'ampia gamma di obiettivi per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="21d62-125">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="21d62-126">Ciò non significa che l'esecuzione degli script sia resa impossibile dalla shell.</span><span class="sxs-lookup"><span data-stu-id="21d62-126">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="21d62-127">L'obiettivo, per impostazione predefinita, è invece quello di rendere difficile per gli utenti eseguire script senza esserne consapevoli.</span><span class="sxs-lookup"><span data-stu-id="21d62-127">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="21d62-128">Per informazioni dettagliate, vedere Windows PowerShell script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .</span><span class="sxs-lookup"><span data-stu-id="21d62-128">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

