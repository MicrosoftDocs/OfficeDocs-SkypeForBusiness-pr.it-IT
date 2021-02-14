---
title: Configurare le dichiarazioni di non responsabilità relative all'archiviazione per gli utenti esterni in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: "Riepilogo: leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820666"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="c200b-103">Configurare le dichiarazioni di non responsabilità relative all'archiviazione per gli utenti esterni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c200b-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="c200b-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c200b-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="c200b-105">Se l'organizzazione comunica con partner esterni, è necessario comunicare loro che si stanno archiviando le comunicazioni con essi.</span><span class="sxs-lookup"><span data-stu-id="c200b-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="c200b-106">Quando si distribuisce un server perimetrale e si abilita la federazione per l'organizzazione, viene chiesto se si desidera inviare automaticamente una dichiarazione di non responsabilità per l'archiviazione ai partner esterni.</span><span class="sxs-lookup"><span data-stu-id="c200b-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="c200b-107">Se è necessario modificare questa configurazione, è possibile utilizzare il Pannello di controllo di Skype for Business Server o il cmdlet **Set-CsAccessEdgeConfiguration Windows PowerShell Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="c200b-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="c200b-108">I cmdlet possono essere eseguiti da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c200b-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="c200b-109">Per consentire agli utenti esterni di collaborare con gli utenti nella distribuzione di Skype for Business Server, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="c200b-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="c200b-110">Per informazioni dettagliate, vedere Manage XMPP Federated Partners for Your Organization.</span><span class="sxs-lookup"><span data-stu-id="c200b-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="c200b-111">Per informazioni dettagliate sul controllo dell'accesso per domini federati specifici, vedere Control Access by Individual Federated Domains.</span><span class="sxs-lookup"><span data-stu-id="c200b-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="c200b-112">Abilitare o disabilitare la dichiarazione di non responsabilità per l'archiviazione tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="c200b-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="c200b-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c200b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c200b-114">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c200b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c200b-115">Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Configurazione Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="c200b-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="c200b-116">Nella scheda **Configurazione Access Edge** fare clic su **Globale**, quindi su **Modifica** e infine su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c200b-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c200b-117">In Modifica configurazione **Access Edge,** in Abilita federazione e connettività per messaggistica istantanea **pubblica,** selezionare o deselezionare la casella di controllo Invia dichiarazione di non responsabilità per l'archiviazione ai **partner federati** per abilitare o disabilitare l'invio automatico della dichiarazione di non responsabilità per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c200b-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="c200b-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c200b-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="c200b-119">Abilitare o disabilitare la dichiarazione di non responsabilità per l'archiviazione Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c200b-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="c200b-120">Per abilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su True ($True):</span><span class="sxs-lookup"><span data-stu-id="c200b-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="c200b-121">Per disabilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su False ($False):</span><span class="sxs-lookup"><span data-stu-id="c200b-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


