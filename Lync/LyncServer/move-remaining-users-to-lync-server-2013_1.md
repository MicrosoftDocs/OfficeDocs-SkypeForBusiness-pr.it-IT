---
title: Spostare gli utenti rimanenti in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afb495a3500491bb85e9107770ec12f9544832b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="2d6e9-102">Spostare gli utenti rimanenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d6e9-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d6e9-103">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="2d6e9-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="2d6e9-104">È possibile spostare gli utenti nella nuova distribuzione di Lync Server 2013 utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="2d6e9-105">È necessario soddisfare alcuni requisiti per garantire una transizione agevole a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="2d6e9-106">Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere [configure clients for Migration](configure-clients-for-migration_1.md).</span><span class="sxs-lookup"><span data-stu-id="2d6e9-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="2d6e9-107">Per la procedura dettagliata relativa allo spostamento degli utenti, vedere [la fase 6: spostare gli utenti nel pool pilota](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="2d6e9-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d6e9-108">Non è possibile utilizzare lo snap-in utenti e computer di Active Directory o gli strumenti di amministrazione di Microsoft Office Communications Server 2007 R2 per spostare gli utenti dall'ambiente legacy a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d6e9-p102">Il cmdlet <STRONG>Move-CsLegacyUser</STRONG> richiede nomi utente ben formati e senza spazi iniziali o finali. Non è possibile spostare un account utente utilizzando il cmdlet <STRONG>Move-CsLegacyUser</STRONG> se contiene spazi iniziali o finali.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-p102">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces. You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="2d6e9-111">Quando si sposta un utente in un pool di Lync Server 2013, i dati dell'utente vengono spostati nel database back-end associato al nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2d6e9-112">In questi dati sono incluse le riunioni attive create dall'utente legacy.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="2d6e9-113">Ad esempio, se un utente legacy ha configurato una conferenza <STRONG>riunione personale</STRONG> , la conferenza sarà ancora disponibile nel nuovo pool di Lync Server 2013, dopo lo spostamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="2d6e9-114">I dettagli per l'accesso alla riunione continueranno a essere gli stessi URL<STRONG></STRONG>e ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="2d6e9-115">L'unica differenza è che la conferenza ora è ospitata nel pool di Lync Server 2013 e non nel pool di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2d6e9-116">Gli utenti homing su Lync Server 2013 non richiedono la distribuzione contemporanea di client aggiornati.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="2d6e9-117">Le nuove funzionalità saranno disponibili per gli utenti solo dopo l'aggiornamento al nuovo software client.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="2d6e9-118">Attività di post-migrazione</span><span class="sxs-lookup"><span data-stu-id="2d6e9-118">Post Migration Task</span></span>

1.  <span data-ttu-id="2d6e9-119">Dopo aver spostato gli utenti, verificare i criteri di conferenza loro assegnati.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="2d6e9-120">Per garantire che le riunioni organizzate dagli utenti ospitati in Lync Server 2013 funzionino perfettamente con gli utenti federati ospitati in Office Communications Server 2007 R2, i criteri di conferenza assegnati agli utenti migrati devono consentire ai partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="2d6e9-121">I criteri di conferenza che consentono ai partecipanti anonimi **consentono ai partecipanti di invitare utenti anonimi** selezionati nel pannello di controllo di Lync Server 2013 e di disporre di **AllowAnonymousParticipantsInMeetings** impostato su **true** nell'output del cmdlet **Get-CsConferencingPolicy** in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="2d6e9-122">Per informazioni dettagliate sulla configurazione dei criteri di conferenza mediante Lync Server Management Shell, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2d6e9-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

