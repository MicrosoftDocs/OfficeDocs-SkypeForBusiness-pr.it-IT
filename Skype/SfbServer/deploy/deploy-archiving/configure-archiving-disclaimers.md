---
title: Configurare le esclusioni di archiviazione per utenti esterni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: "Riepilogo: leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: d6c08b6fe2eaa6c74231b96346661488c3f8e2b0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001056"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="507a0-103">Configurare le esclusioni di archiviazione per utenti esterni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="507a0-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="507a0-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità per l'archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="507a0-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="507a0-105">Se l'organizzazione comunica con partner esterni, è necessario comunicare loro di archiviare le comunicazioni.</span><span class="sxs-lookup"><span data-stu-id="507a0-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="507a0-106">Quando si distribuisce un server perimetrale e si Abilita la Federazione per l'organizzazione, viene chiesto se si vuole inviare automaticamente una dichiarazione di non responsabilità per l'archiviazione a partner esterni.</span><span class="sxs-lookup"><span data-stu-id="507a0-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="507a0-107">Se è necessario modificare questa configurazione, è possibile usare il pannello di controllo di Skype for Business Server o il cmdlet **Set-CsAccessEdgeConfiguration** di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="507a0-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="507a0-108">I cmdlet possono essere eseguiti da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="507a0-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="507a0-109">Per consentire agli utenti esterni di collaborare con gli utenti nella distribuzione di Skype for Business Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="507a0-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="507a0-110">Per informazioni dettagliate, vedere gestire partner federativi XMPP per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="507a0-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="507a0-111">Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere controllare l'accesso in base a singoli domini federati.</span><span class="sxs-lookup"><span data-stu-id="507a0-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="507a0-112">Abilitare o disabilitare l'archiviazione della dichiarazione di non responsabilità tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="507a0-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="507a0-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="507a0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="507a0-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="507a0-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="507a0-115">Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**e quindi su **configurazione bordo di Access**.</span><span class="sxs-lookup"><span data-stu-id="507a0-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="507a0-116">Nella scheda **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="507a0-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="507a0-117">In **modifica configurazione di Access Edge**selezionare o deselezionare la casella di controllo **Invia dichiarazione di non responsabilità per i partner federati** in **Abilita**o Disabilita l'invio automatico della dichiarazione di non responsabilità per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="507a0-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="507a0-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="507a0-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="507a0-119">Abilitare o disabilitare l'archiviazione della dichiarazione di non responsabilità tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="507a0-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="507a0-120">Per abilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su True ($true):</span><span class="sxs-lookup"><span data-stu-id="507a0-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="507a0-121">Per disabilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su False ($false):</span><span class="sxs-lookup"><span data-stu-id="507a0-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


