---
title: Spostare gli utenti restanti
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'È possibile spostare gli utenti nella nuova distribuzione di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione agevole a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere Configure clients for Migration. Per la procedura dettagliata relativa allo spostamento degli utenti, vedere la fase 4: spostare gli utenti di test nel pool pilota.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753714"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="744f8-106">Spostare gli utenti rimanenti in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="744f8-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="744f8-107">È possibile spostare gli utenti nella nuova distribuzione di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="744f8-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="744f8-108">È necessario soddisfare alcuni requisiti per garantire una transizione agevole a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="744f8-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="744f8-109">Per informazioni dettagliate sui prerequisiti per il completamento delle procedure descritte in questo argomento, vedere [configure clients for Migration](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="744f8-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="744f8-110">Per la procedura dettagliata relativa allo spostamento degli utenti, vedere [la fase 4: spostare gli utenti di test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="744f8-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="744f8-111">Non è possibile utilizzare lo snap-in utenti e computer di Active Directory o gli strumenti di amministrazione legacy per spostare gli utenti dall'ambiente legacy a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="744f8-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="744f8-112">Quando si sposta un utente in un pool di Skype for Business Server 2019, i dati dell'utente vengono spostati nel database back-end associato al nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="744f8-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="744f8-113">In questi dati sono incluse le riunioni attive create dall'utente legacy.</span><span class="sxs-lookup"><span data-stu-id="744f8-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="744f8-114">Ad esempio, se un utente legacy ha configurato una conferenza **My Meeting** , la conferenza sarà ancora disponibile nel nuovo pool di Skype for Business Server 2019 dopo lo spostamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="744f8-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="744f8-115">I dettagli per l'accesso alla riunione continueranno a essere gli stessi URL\*\*\*\* e ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="744f8-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="744f8-116">L'unica differenza è che la conferenza è ora ospitata nel pool di Skype for Business Server 2019 e non nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="744f8-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="744f8-117">Gli utenti homing su Skype for Business Server 2019 non richiedono la distribuzione contemporanea di client aggiornati.</span><span class="sxs-lookup"><span data-stu-id="744f8-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="744f8-118">Le nuove funzionalità degli utenti saranno disponibili per gli utenti solo quando eseguono l'aggiornamento al nuovo software client.</span><span class="sxs-lookup"><span data-stu-id="744f8-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="744f8-119">Attività di post-migrazione</span><span class="sxs-lookup"><span data-stu-id="744f8-119">Post migration task</span></span>

1. <span data-ttu-id="744f8-120">Dopo aver spostato gli utenti, verificare i criteri di conferenza loro assegnati.</span><span class="sxs-lookup"><span data-stu-id="744f8-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="744f8-121">Per garantire che le riunioni organizzate dagli utenti ospitati su Skype for Business Server 2019 funzionino perfettamente con gli utenti federati ospitati nell'installazione legacy, il criterio di conferenza assegnato agli utenti migrati dovrebbe consentire ai partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="744f8-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="744f8-122">I criteri di conferenza che consentono ai partecipanti anonimi **consentono ai partecipanti di invitare utenti anonimi** selezionati nel pannello di controllo di Skype for business server 2019 e di disporre di **AllowAnonymousParticipantsInMeetings** impostato su **true** nell'output del cmdlet **Get-CsConferencingPolicy** in Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="744f8-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

