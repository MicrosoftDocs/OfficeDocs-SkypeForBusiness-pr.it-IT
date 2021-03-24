---
title: Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Riepilogo: informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 81f5ef1bc0ce28c7741aa99529e7ba107ff4127f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096702"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9ab9f-103">Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ab9f-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9ab9f-104">**Riepilogo:** Informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9ab9f-105">È possibile visualizzare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9ab9f-106">Visualizzare le impostazioni di configurazione delle riunioni tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ab9f-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="9ab9f-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab9f-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="9ab9f-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="9ab9f-109">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="9ab9f-110">Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Configurazione riunione.**</span><span class="sxs-lookup"><span data-stu-id="9ab9f-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="9ab9f-111">Nella pagina **Configurazione riunione** fare clic sulla configurazione di riunione che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="9ab9f-112">In **Modifica filtro file** selezionare la casella di **controllo** Mostra dettagli.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="9ab9f-113">**Modifica configurazione \<policy\> riunione -** visualizza le impostazioni per il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="9ab9f-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="9ab9f-114">Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [Create meeting configuration settings in Skype for Business Server.](create-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9ab9f-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="9ab9f-115">Visualizzare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9ab9f-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="9ab9f-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="9ab9f-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="9ab9f-117">Per visualizzare informazioni su tutte le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **Get-CsMeetingConfiguration:**</span><span class="sxs-lookup"><span data-stu-id="9ab9f-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="9ab9f-118">Questo comando restituirà informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ab9f-118">This command will return information similar to the following:</span></span>
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

<span data-ttu-id="9ab9f-119">Per ulteriori informazioni, incluso un elenco completo di parametri, [vedere Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9ab9f-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
