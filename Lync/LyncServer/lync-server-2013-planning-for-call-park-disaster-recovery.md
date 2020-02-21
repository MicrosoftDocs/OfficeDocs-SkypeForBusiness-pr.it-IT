---
title: 'Lync Server 2013: pianificazione per il ripristino di emergenza del parcheggio di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ae06a3d0e3e404781e2f51ef18e1ba2ca76d72b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="a786c-102">Pianificazione del ripristino di emergenza del parcheggio di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a786c-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a786c-103">_**Ultimo argomento modificato:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a786c-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a786c-104">In questa sezione vengono illustrati alcuni modi per preparare l'applicazione Parcheggio di chiamata per il ripristino di emergenza e alcune considerazioni per il processo di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="a786c-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="a786c-105">Preparazione per il ripristino di emergenza del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="a786c-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="a786c-106">Quando si preparano e si eseguono le procedure di ripristino di emergenza, tenere presenti gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a786c-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="a786c-107">Pianificare il ripristino di emergenza in fase di pianificazione della capacità.</span><span class="sxs-lookup"><span data-stu-id="a786c-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="a786c-108">Per la capacità di ripristino di emergenza, ogni pool in un pool associato dovrebbe essere in grado di gestire i carichi di lavoro dei servizi parcheggio di chiamata in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="a786c-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="a786c-109">Per informazioni dettagliate sulla pianificazione della capacità del parcheggio di chiamata, vedere [pianificazione della capacità per il parcheggio di chiamata in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="a786c-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="a786c-110">Durante il ripristino di emergenza gli utenti che sono stati reindirizzati al pool di backup durante il processo di failover, utilizzano il servizio Parcheggio di chiamata nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="a786c-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="a786c-111">Pertanto, il supporto per il parcheggio di chiamata durante il ripristino di emergenza richiede che l'applicazione Parcheggio di chiamata venga distribuita e abilitata sia nel pool primario che nel pool di backup.</span><span class="sxs-lookup"><span data-stu-id="a786c-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="a786c-112">È necessario che tutti i pool dispongano di un intervallo valido di numeri di codici orbit per gli utenti che sono ospitati nel pool da utilizzare per il parcheggio delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a786c-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="a786c-113">Mantenere sempre una copia di backup separata di qualsiasi musica personalizzata in attesa che sia stata caricata per il parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="a786c-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="a786c-114">Questi file non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="a786c-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="a786c-115">Considerazioni sul ripristino di emergenza del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="a786c-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="a786c-116">È possibile definire un solo set di impostazioni di configurazione dell'applicazione Parcheggio di chiamata e un file audio personalizzato per pool.</span><span class="sxs-lookup"><span data-stu-id="a786c-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="a786c-117">Queste impostazioni includono la soglia di timeout, la musica in attesa, il numero massimo di tentativi di risposta alle chiamate e l'URI di timeout.</span><span class="sxs-lookup"><span data-stu-id="a786c-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="a786c-118">Per visualizzare le impostazioni di configurazione, eseguire il cmdlet **Get-CsCpsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a786c-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="a786c-119">Per informazioni dettagliate sul cmdlet **Get-CsCpsConfiguration** , vedere [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="a786c-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="a786c-120">Durante il ripristino di emergenza, il parcheggio di chiamata utilizza l'applicazione Parcheggio di chiamata nel pool di backup, pertanto non è stato eseguito il backup delle impostazioni del pool primario.</span><span class="sxs-lookup"><span data-stu-id="a786c-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="a786c-121">Se il pool primario non può essere ripristinato e si distribuisce un nuovo pool per sostituire il pool primario, le impostazioni del pool primario vengono perse ed è necessario riconfigurare le impostazioni del parcheggio di chiamata e gli eventuali file audio di musica di attesa personalizzati nel nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="a786c-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="a786c-122">Se si distribuisce un nuovo pool con un nome di dominio completo (FQDN) diverso per sostituire il pool primario, è necessario riassegnare tutti gli intervalli di orbit del parcheggio di chiamata che sono stati associati al pool primario all'FQDN del nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="a786c-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="a786c-123">Per riassegnare gli intervalli di Orbit al nuovo pool, è possibile utilizzare il pannello di controllo di Lync Server o il cmdlet **set-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="a786c-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="a786c-124">Per informazioni dettagliate sul cmdlet **set-CsCallParkOrbit** , vedere [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="a786c-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

