---
title: Configurare il monitoraggio di SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a><span data-ttu-id="39fe8-102">Configurare il monitoraggio di SCOM</span><span class="sxs-lookup"><span data-stu-id="39fe8-102">Configure SCOM monitoring</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39fe8-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="39fe8-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="39fe8-104">Dopo aver eseguito la migrazione a Microsoft Lync Server 2013, è necessario completare alcune attività per configurare Lync Server 2013 in modo che funzioni con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="39fe8-104">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="39fe8-105">Applicare gli aggiornamenti di Lync Server 2010 a un server scelto per gestire la logica di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="39fe8-105">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="39fe8-106">Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="39fe8-106">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="39fe8-107">Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidato.</span><span class="sxs-lookup"><span data-stu-id="39fe8-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="39fe8-108">Di seguito sono riportate le istruzioni per l'esecuzione di ognuna di tali attività.</span><span class="sxs-lookup"><span data-stu-id="39fe8-108">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="39fe8-109">**Applicare gli aggiornamenti di Lync Server 2010 a un server scelto per gestire la logica di individuazione centrale.**</span><span class="sxs-lookup"><span data-stu-id="39fe8-109">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="39fe8-110">Scegliere un server in cui siano installati i file dell'agente System Center Operations Manager e che sia configurato come nodo di individuazione candidato.</span><span class="sxs-lookup"><span data-stu-id="39fe8-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="39fe8-111">Applicare gli aggiornamenti di Lync Server 2010 a questo server.</span><span class="sxs-lookup"><span data-stu-id="39fe8-111">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="39fe8-112">Per ulteriori informazioni, vedere l'argomento [Apply Lync Server 2010 Updates](apply-lync-server-2010-updates.md).</span><span class="sxs-lookup"><span data-stu-id="39fe8-112">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="39fe8-113">**Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.**</span><span class="sxs-lookup"><span data-stu-id="39fe8-113">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="39fe8-114">Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39fe8-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="39fe8-115">Digitare quanto segue alla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="39fe8-115">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="39fe8-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="39fe8-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="39fe8-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="39fe8-117">If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="39fe8-118">**Configurare il server di gestione di System Center Operations Manager principale per sostituire il nodo Watcher di individuazione centrale candidato.**</span><span class="sxs-lookup"><span data-stu-id="39fe8-118">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="39fe8-119">In un computer in cui è stata installata la console System Center Operations Manager espandere **Oggetti Management Pack** e selezionare **Individuazioni oggetti**.</span><span class="sxs-lookup"><span data-stu-id="39fe8-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="39fe8-120">Fare clic su **Cambia ambito**</span><span class="sxs-lookup"><span data-stu-id="39fe8-120">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="39fe8-121">Nella pagina **Crea ambito oggetti Management Pack** selezionare **Candidato individuazione LS**.</span><span class="sxs-lookup"><span data-stu-id="39fe8-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="39fe8-122">Sostituire il **Valore effettivo candidato individuazione LS** con il nome del server candidato scelto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="39fe8-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="39fe8-123">Infine, per finalizzare le modifiche, riavviare il servizio di integrità nel server di gestione radice di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="39fe8-123">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

