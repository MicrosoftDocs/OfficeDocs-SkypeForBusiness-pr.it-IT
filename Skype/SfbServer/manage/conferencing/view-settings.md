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
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827926"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0a7ea-103">Visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0a7ea-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0a7ea-104">**Riepilogo:** Informazioni su come visualizzare le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="0a7ea-105">È possibile visualizzare le impostazioni di configurazione delle riunioni utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0a7ea-106">Visualizzare le impostazioni di configurazione delle riunioni utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0a7ea-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="0a7ea-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="0a7ea-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="0a7ea-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0a7ea-109">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0a7ea-110">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="0a7ea-111">Nella pagina **Configurazione riunione** fare clic sulla configurazione di riunione che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="0a7ea-112">In **Modifica filtro file** selezionare la casella di controllo **Mostra dettagli** .</span><span class="sxs-lookup"><span data-stu-id="0a7ea-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="0a7ea-113">**Modificare la configurazione delle \<policy\> riunioni-** viene visualizzata la visualizzazione delle impostazioni per il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="0a7ea-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="0a7ea-114">Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare le impostazioni di configurazione delle riunioni in Skype for Business Server](create-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0a7ea-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0a7ea-115">Visualizzazione delle impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0a7ea-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="0a7ea-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="0a7ea-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="0a7ea-117">Per visualizzare informazioni su tutte le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **Get-CsMeetingConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="0a7ea-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="0a7ea-118">Questo comando restituirà informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a7ea-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="0a7ea-119">Per ulteriori informazioni, incluso un elenco completo dei parametri, vedere [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0a7ea-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

