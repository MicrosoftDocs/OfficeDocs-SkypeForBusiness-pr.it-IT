---
title: 'Lync Server 2013: Strumenti di gestione di Windows PowerShell e Lync Server'
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
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="8858a-102">Strumenti di gestione di Windows PowerShell e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8858a-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8858a-103">_**Argomento Ultima modifica:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="8858a-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="8858a-104">In Microsoft Lync Server 2013 gli strumenti di gestione vengono implementati con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8858a-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="8858a-105">Windows PowerShell include un ambiente della riga di comando, comandi specifici del prodotto e un linguaggio di scripting completo.</span><span class="sxs-lookup"><span data-stu-id="8858a-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="8858a-106">Gli strumenti di Lync Server 2013 implementati con Windows PowerShell includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8858a-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="8858a-107">**Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="8858a-107">**Topology Builder**.</span></span> <span data-ttu-id="8858a-108">Puoi usare generatore di topologia per creare, modificare e pubblicare la topologia pianificata e convalidare la topologia prima di iniziare le installazioni del server.</span><span class="sxs-lookup"><span data-stu-id="8858a-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="8858a-109">Quando si installa Lync Server 2013 nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il programma di installazione distribuisce il server come indicato nella topologia.</span><span class="sxs-lookup"><span data-stu-id="8858a-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="8858a-110">Dopo l'installazione, le informazioni di configurazione vengono replicate automaticamente in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="8858a-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="8858a-111">I componenti possono essere aggiunti alla distribuzione solo tramite Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="8858a-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="8858a-112">**Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8858a-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="8858a-113">È possibile usare Lync Server Management Shell per la gestione completa della riga di comando della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8858a-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="8858a-114">**Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8858a-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="8858a-115">È possibile usare l'interfaccia utente del pannello di controllo di Microsoft Lync Server 2013 per gestire le attività più comuni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8858a-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="8858a-116">Questi strumenti usano i cmdlet di Windows PowerShell per la gestione della distribuzione, tra cui quasi tutti i cmdlet specifici per il prodotto 550.</span><span class="sxs-lookup"><span data-stu-id="8858a-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="8858a-117">I cmdlet di sicurezza inclusi in Lync Server 2013 vengono usati principalmente per gestire l'autenticazione e i diritti utente e le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8858a-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="8858a-118">È disponibile un'ampia varietà di cmdlet per la gestione dell'autenticazione, inclusi i cmdlet per il certificato e l'autenticazione PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="8858a-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="8858a-119">Inoltre, un certo numero di cmdlet consente di usare la nuova funzionalità controllo di accesso basato sui ruoli (RBAC) per delegare il controllo amministrativo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8858a-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="8858a-120">Per informazioni dettagliate sui cmdlet di Lync Server, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="8858a-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="8858a-121">Le funzionalità di sicurezza degli script per Windows PowerShell sono progettate in modo specifico per evitare alcuni problemi di sicurezza correlati agli script delle tecnologie meno recenti, tra cui Microsoft Visual Basic Scripting Edition (VBScript).</span><span class="sxs-lookup"><span data-stu-id="8858a-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="8858a-122">Le caratteristiche di sicurezza di Windows PowerShell sono destinate a creare un ambiente in cui gli utenti non possono eseguire facilmente o in modo inconsapevolmente gli script.</span><span class="sxs-lookup"><span data-stu-id="8858a-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="8858a-123">Per impostazione predefinita, le caratteristiche di sicurezza di Windows PowerShell sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="8858a-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="8858a-124">Puoi modificare lo stato di queste funzionalità per soddisfare le tue esigenze di scripting e diversi obiettivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8858a-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="8858a-125">Questo non significa che la Shell rende impossibile l'esecuzione di script da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8858a-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="8858a-126">La Shell rende invece difficile, per impostazione predefinita, che gli utenti eseguano gli script senza rendersene conto.</span><span class="sxs-lookup"><span data-stu-id="8858a-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="8858a-127">Per informazioni dettagliate, vedere la pagina relativa alla [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)sicurezza degli script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8858a-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

