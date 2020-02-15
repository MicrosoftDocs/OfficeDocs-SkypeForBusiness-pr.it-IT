---
title: 'Lync Server 2013: prerequisiti per la configurazione del parcheggio di chiamata e diritti utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19a677b7b1a76c0956b5edc663e8932716ce5fb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="ad01d-102">Requisiti di configurazione del parcheggio di chiamata e diritti utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad01d-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad01d-103">_**Ultimo argomento modificato:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="ad01d-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="ad01d-104">Il parcheggio di chiamata è una funzionalità di gestione delle chiamate installata per impostazione predefinita quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ad01d-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ad01d-105">In questo argomento vengono descritte le operazioni necessarie per poter configurare il parcheggio di chiamata e i diritti utente necessari per eseguire le attività di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ad01d-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad01d-106">I file musicali personalizzati per l'applicazione Parcheggio di chiamata non vengono sottoposti a backup come parte del processo di ripristino di emergenza di Lync Server 2013 e i file andranno persi se i file caricati nel pool sono danneggiati, danneggiati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="ad01d-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="ad01d-107">Mantenere sempre una copia di backup distinta dei file di musica di attesa personalizzati caricati per il parcheggio chiamate.</span><span class="sxs-lookup"><span data-stu-id="ad01d-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="ad01d-108">In questa sezione si presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al parcheggio di chiamata (vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="ad01d-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="ad01d-109">Prerequisiti per la configurazione del parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="ad01d-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="ad01d-110">Il parcheggio di chiamata richiede i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad01d-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="ad01d-111">Servizio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ad01d-111">Application service</span></span>

  - <span data-ttu-id="ad01d-112">Applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="ad01d-112">Call Park application</span></span>

<span data-ttu-id="ad01d-113">Questi componenti vengono installati automaticamente quando si distribuisce VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ad01d-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="ad01d-114">Se si desidera che i chiamanti ascoltino musica nell'intervallo di tempo in cui la chiamata è parcheggiata, sarà necessario inoltre un file di musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="ad01d-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="ad01d-115">Quando si distribuisce VoIP aziendale, viene installato automaticamente un file di musica di attesa predefinito.</span><span class="sxs-lookup"><span data-stu-id="ad01d-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="ad01d-116">È possibile sostituire il file predefinito con un proprio file di musica di attesa.</span><span class="sxs-lookup"><span data-stu-id="ad01d-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="ad01d-117">Il parcheggio di chiamata utilizza l'archivio file per contenere il file audio.</span><span class="sxs-lookup"><span data-stu-id="ad01d-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="ad01d-118">Configurazione del parcheggio di chiamata diritti utente</span><span class="sxs-lookup"><span data-stu-id="ad01d-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="ad01d-119">È possibile utilizzare gli strumenti di amministrazione seguenti per configurare il parcheggio di chiamata:</span><span class="sxs-lookup"><span data-stu-id="ad01d-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="ad01d-120">Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ad01d-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="ad01d-121">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ad01d-121">Lync Server Management Shell</span></span>

<span data-ttu-id="ad01d-122">È possibile utilizzare questi strumenti per configurare la tabella di orbit del parcheggio di chiamata e per la configurazione di altre impostazioni utilizzate dal parcheggio di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ad01d-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="ad01d-123">La configurazione del parcheggio di chiamata richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:</span><span class="sxs-lookup"><span data-stu-id="ad01d-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="ad01d-124">**CsVoiceAdministrator:** Questo ruolo di amministratore può creare, configurare e gestire tutte le impostazioni e i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="ad01d-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="ad01d-125">**CsUserAdministrator:** Questo ruolo di amministratore può abilitare il parcheggio di chiamata nel criterio vocale.</span><span class="sxs-lookup"><span data-stu-id="ad01d-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="ad01d-126">Dispone inoltre dell'accesso per la visualizzazione di sola lettura di tutte le configurazioni vocali.</span><span class="sxs-lookup"><span data-stu-id="ad01d-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="ad01d-127">**CsServerAdministrator:** Questo ruolo di amministratore può gestire, monitorare e risolvere i problemi relativi a server e servizi.</span><span class="sxs-lookup"><span data-stu-id="ad01d-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="ad01d-128">**CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator, CsServerAdministrator e CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ad01d-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad01d-129">Per informazioni dettagliate sui diritti amministrativi, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="ad01d-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad01d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad01d-130">See Also</span></span>


[<span data-ttu-id="ad01d-131">Distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad01d-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="ad01d-132">Pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad01d-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

