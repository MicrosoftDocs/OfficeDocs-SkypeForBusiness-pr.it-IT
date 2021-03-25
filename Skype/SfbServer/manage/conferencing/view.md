---
title: Visualizzare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 'Riepilogo: informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: afe86f0a77e73c3fa7bf96339c4865598a7bc609
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119405"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="b7f4d-103">Visualizzare i criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7f4d-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="b7f4d-104">**Riepilogo:** Informazioni su come visualizzare i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="b7f4d-105">È possibile visualizzare i criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b7f4d-106">Visualizzare i criteri di conferenza tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7f4d-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b7f4d-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b7f4d-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b7f4d-109">Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Criteri conferenza.**</span><span class="sxs-lookup"><span data-stu-id="b7f4d-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="b7f4d-110">Nella pagina **Criteri conferenza** fare doppio clic sul criterio di conferenza che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="b7f4d-111">In **Modifica filtro file** selezionare la casella di **controllo** Mostra dettagli.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="b7f4d-112">**Modifica criteri \<policy\> conferenza -** visualizza le impostazioni per il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="b7f4d-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="b7f4d-113">Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [Create conferencing policies in Skype for Business Server.](create-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b7f4d-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b7f4d-114">Visualizzare i criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b7f4d-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b7f4d-115">Per visualizzare i criteri conferenza, utilizzare il cmdlet **Get-CsConferencingPolicy:**</span><span class="sxs-lookup"><span data-stu-id="b7f4d-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="b7f4d-116">Il cmdlet restituisce informazioni quali le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7f4d-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

<span data-ttu-id="b7f4d-117">Per ulteriori informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b7f4d-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
