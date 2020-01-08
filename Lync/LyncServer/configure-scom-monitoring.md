---
title: Configurare il monitoraggio di SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e114d3f18e482c11a8e83c9d4308f3c5712932c
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40977360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="90bf6-102">Configurare il monitoraggio di SCOM</span><span class="sxs-lookup"><span data-stu-id="90bf6-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90bf6-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="90bf6-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="90bf6-104">Dopo aver eseguito la migrazione a Microsoft Lync Server 2013, è necessario completare alcune attività per configurare Lync Server 2013 per l'utilizzo con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="90bf6-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="90bf6-105">Applicare gli aggiornamenti di Lync Server 2010 a un server scelto per gestire la logica di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="90bf6-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="90bf6-106">Aggiornare la chiave del registro di sistema del server di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="90bf6-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="90bf6-107">Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidata.</span><span class="sxs-lookup"><span data-stu-id="90bf6-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="90bf6-108">Di seguito sono riportate le istruzioni per l'esecuzione di ciascuna di queste attività.</span><span class="sxs-lookup"><span data-stu-id="90bf6-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="90bf6-109">**Applicare gli aggiornamenti di Lync Server 2010 a un server scelto per gestire la logica di individuazione centrale.**</span><span class="sxs-lookup"><span data-stu-id="90bf6-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="90bf6-110">Eleggere un server in cui sono installati i file dell'agente di System Center Operations Manager ed è configurato come nodo di individuazione candidata.</span><span class="sxs-lookup"><span data-stu-id="90bf6-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="90bf6-111">Applicare gli aggiornamenti di Lync Server 2010 al server.</span><span class="sxs-lookup"><span data-stu-id="90bf6-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="90bf6-112">Vedere l'argomento [applicare gli aggiornamenti di Lync Server 2010](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="90bf6-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="90bf6-113">**Aggiornare la chiave del registro di sistema del server di individuazione centrale.**</span><span class="sxs-lookup"><span data-stu-id="90bf6-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="90bf6-114">Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90bf6-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="90bf6-115">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="90bf6-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="90bf6-116">Ogni volta che si modifica il registro di sistema, potrebbe verificarsi un errore che indica che il comando non è riuscito se la chiave del registro di sistema esiste già.</span><span class="sxs-lookup"><span data-stu-id="90bf6-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="90bf6-117">Se si verifica questo problema, è possibile ignorare in modo sicuro l'errore.</span><span class="sxs-lookup"><span data-stu-id="90bf6-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="90bf6-118">**Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di Watcher individuazione centrale candidato.**</span><span class="sxs-lookup"><span data-stu-id="90bf6-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="90bf6-119">In un computer in cui è installata la console di System Center Operations Manager, espandere **oggetti Management Pack** e quindi selezionare individuazioni **oggetti**.</span><span class="sxs-lookup"><span data-stu-id="90bf6-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="90bf6-120">Fare clic su **Cambia ambito.** ..</span><span class="sxs-lookup"><span data-stu-id="90bf6-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="90bf6-121">Nella pagina **oggetti Management Pack di ambito** selezionare **ls Discovery candidate**.</span><span class="sxs-lookup"><span data-stu-id="90bf6-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="90bf6-122">Eseguire l'override del **valore effettivo del candidato di individuazione LS** per il nome del server candidato eletto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="90bf6-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="90bf6-123">Infine, per finalizzare le modifiche, riavviare il servizio integrità nel server di gestione radice di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="90bf6-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

