---
title: Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Riepilogo: informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827996"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="43595-103">Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43595-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="43595-104">**Riepilogo:** Informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43595-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="43595-105">È possibile modificare le impostazioni di configurazione delle riunioni utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="43595-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="43595-106">Modificare le impostazioni di configurazione delle riunioni utilizzando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43595-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="43595-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="43595-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="43595-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43595-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="43595-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="43595-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="43595-110">Nell'elenco delle configurazioni delle riunioni, fare clic sulla configurazione che si desidera modificare, fare clic su **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="43595-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="43595-111">In **Modifica configurazione riunione** modificare qualsiasi impostazione di configurazione, tranne il nome della configurazione, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="43595-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="43595-112">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="43595-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="43595-113">Modificare le impostazioni di configurazione delle riunioni utilizzando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="43595-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="43595-114">Per modificare le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **Set-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="43595-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="43595-115">Il comando riportato nell'esempio seguente consente di modificare le impostazioni di configurazione delle riunioni assegnate al sito di Redmond (-Identity site: Redmond).</span><span class="sxs-lookup"><span data-stu-id="43595-115">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond).</span></span> <span data-ttu-id="43595-116">In questo caso, il valore della proprietà DesignateAsPresenter è impostato su tutti:</span><span class="sxs-lookup"><span data-stu-id="43595-116">In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="43595-117">Per ulteriori informazioni, incluso un elenco completo dei parametri, vedere [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="43595-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

