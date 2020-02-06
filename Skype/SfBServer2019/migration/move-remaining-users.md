---
title: Spostare gli utenti rimanenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Puoi trasferire gli utenti nella nuova distribuzione di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell. È necessario soddisfare alcuni requisiti per garantire una transizione fluida a Skype for Business Server 2019. Per informazioni dettagliate sui prerequisiti per completare le procedure descritte in questo argomento, vedere Configurare i client per la migrazione. Per informazioni dettagliate sullo spostamento degli utenti, vedere la fase 4: spostare gli utenti del test nel pool pilota.'
ms.openlocfilehash: ac384e9f9e4aaaa534f5b646f1d847485dbb4c23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813264"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a><span data-ttu-id="452eb-106">Trasferire gli utenti rimanenti in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="452eb-106">Move remaining users to Skype for Business Server 2019</span></span>

<span data-ttu-id="452eb-107">Puoi trasferire gli utenti nella nuova distribuzione di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="452eb-107">You can move users to the new Skype for Business Server 2019 deployment by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> <span data-ttu-id="452eb-108">È necessario soddisfare alcuni requisiti per garantire una transizione fluida a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="452eb-108">You must meet some requirements to ensure a smooth transition to Skype for Business Server 2019.</span></span> <span data-ttu-id="452eb-109">Per informazioni dettagliate sui prerequisiti per completare le procedure descritte in questo argomento, vedere [configurare i client per la migrazione](configure-clients-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="452eb-109">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="452eb-110">Per informazioni dettagliate sullo spostamento degli utenti, vedere [la fase 4: spostare gli utenti del test nel pool pilota](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="452eb-110">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="452eb-111">Non è possibile usare lo snap-in utenti e computer di Active Directory o gli strumenti di amministrazione legacy per trasferire gli utenti dall'ambiente legacy a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="452eb-111">You cannot use the Active Directory Users and Computers snap-in or the legacy administrative tools to move users from your legacy environment to Skype for Business Server 2019.</span></span> 
  
<span data-ttu-id="452eb-112">Quando si sposta un utente in un pool di Skype for Business Server 2019, i dati per l'utente vengono spostati nel database back-end associato al nuovo pool.</span><span class="sxs-lookup"><span data-stu-id="452eb-112">When you move a user to a Skype for Business Server 2019 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="452eb-113">Sono incluse le riunioni attive create dall'utente legacy.</span><span class="sxs-lookup"><span data-stu-id="452eb-113">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="452eb-114">Ad esempio, se un utente legacy ha configurato una conferenza **riunioni** , la conferenza sarà ancora disponibile nel nuovo pool di Skype for Business Server 2019 dopo lo spostamento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="452eb-114">For example, if a legacy user has configured a **my meeting** conference, that conference will still be available in the new Skype for Business Server 2019 pool after the user has been moved.</span></span> <span data-ttu-id="452eb-115">I dettagli per accedere alla riunione saranno comunque lo stesso **URL conferenza e ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="452eb-115">The details to access that meeting will still be the same **conference URL and conference ID**.</span></span> <span data-ttu-id="452eb-116">L'unica differenza è che la conferenza è ora ospitata nel pool di Skype for Business Server 2019 e non nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="452eb-116">The only difference is that the conference is now hosted in the Skype for Business Server 2019 pool, and not in the legacy pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="452eb-117">Gli utenti homing in Skype for Business Server 2019 non richiedono la distribuzione di client aggiornati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="452eb-117">Homing users on Skype for Business Server 2019 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="452eb-118">Le nuove funzionalità saranno disponibili per gli utenti solo dopo aver eseguito l'aggiornamento al nuovo software client.</span><span class="sxs-lookup"><span data-stu-id="452eb-118">New functionality will be available to users only when they have upgraded to the new client software.</span></span> 
  
### <a name="post-migration-task"></a><span data-ttu-id="452eb-119">Attività post-migrazione</span><span class="sxs-lookup"><span data-stu-id="452eb-119">Post migration task</span></span>

1. <span data-ttu-id="452eb-120">Dopo aver spostato gli utenti, verificare i criteri di conferenza assegnati.</span><span class="sxs-lookup"><span data-stu-id="452eb-120">After you move users, verify the conferencing policy that is assigned to them.</span></span> 
    
2. <span data-ttu-id="452eb-121">Per fare in modo che le riunioni organizzate dagli utenti ospitati in Skype for Business Server 2019 siano perfettamente compatibili con gli utenti federati residenti nell'installazione legacy, i criteri di conferenza assegnati agli utenti migrati dovrebbero consentire ai partecipanti anonimi.</span><span class="sxs-lookup"><span data-stu-id="452eb-121">To ensure that meetings organized by users homed on Skype for Business Server 2019 work seamlessly with federated users who are homed on legacy install, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>
    
3. <span data-ttu-id="452eb-122">I criteri di conferenza che consentono ai partecipanti anonimi **di consentire ai partecipanti di invitare utenti anonimi** selezionati in Skype for business server 2019 pannello di controllo e hanno **AllowAnonymousParticipantsInMeetings** impostato su **true** nell'output del cmdlet **Get-CsConferencingPolicy** in Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="452eb-122">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Skype for Business Server 2019 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Skype for Business Server Management Shell.</span></span> 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

