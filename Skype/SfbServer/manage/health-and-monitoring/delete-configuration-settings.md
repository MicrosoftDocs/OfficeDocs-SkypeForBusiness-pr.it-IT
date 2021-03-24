---
title: Eliminare una raccolta esistente di impostazioni di configurazione della registrazione chiamata in Skype for Business Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Riepilogo: informazioni su come rimuovere le impostazioni di configurazione della registrazione chiamata in Skype for Business Server.'
ms.openlocfilehash: 3ac961df352f26891ece9c69b7d62b37c4c015d6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095310"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="a3264-103">Eliminare una raccolta esistente di impostazioni di configurazione della registrazione chiamata in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a3264-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="a3264-104">**Riepilogo:** Informazioni su come rimuovere le impostazioni di configurazione della registrazione chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a3264-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="a3264-p101">La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.</span><span class="sxs-lookup"><span data-stu-id="a3264-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="a3264-107">Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione della registrazione chiamata.</span><span class="sxs-lookup"><span data-stu-id="a3264-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="a3264-108">Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali.</span><span class="sxs-lookup"><span data-stu-id="a3264-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="a3264-109">Le impostazioni configurate nell'ambito del sito hanno precedenza su quelle configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="a3264-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="a3264-110">Se si eliminano le impostazioni con ambito a livello di sito, la Registrazione dettagli chiamata viene gestita nel sito in base alle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="a3264-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="a3264-111">Tieni presente che puoi anche "eliminare" le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="a3264-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="a3264-112">Tuttavia, le impostazioni globali non vengono effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="a3264-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="a3264-113">Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a3264-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="a3264-114">Ad esempio, per impostazione predefinita la rimozione è abilitata in una raccolta delle impostazioni di configurazione di Registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="a3264-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="a3264-115">Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione.</span><span class="sxs-lookup"><span data-stu-id="a3264-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="a3264-116">Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a3264-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="a3264-117">In questo caso, ciò significa che l'eliminazione verrà riabilitata.</span><span class="sxs-lookup"><span data-stu-id="a3264-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="a3264-118">È possibile rimuovere le impostazioni di configurazione della registrazione chiamata tramite il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a3264-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="a3264-119">Per rimuovere le impostazioni di configurazione della registrazione chiamata con il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a3264-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a3264-120">Nel Pannello di controllo di Skype for Business Server fare clic su **Monitoraggio e archiviazione.**</span><span class="sxs-lookup"><span data-stu-id="a3264-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="a3264-p104">Nella scheda **Registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni di Registrazione dettagli chiamata da rimuovere. Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic sulle raccolte aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="a3264-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="a3264-123">Fare clic su **Modifica** e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a3264-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="a3264-124">Nella finestra di dialogo Pannello di controllo di Skype for Business Server fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="a3264-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a3264-125">Rimozione delle impostazioni di configurazione di registrazione dei dati tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="a3264-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a3264-126">È possibile eliminare le impostazioni di configurazione della registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a3264-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="a3264-127">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3264-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a3264-128">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo di blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="a3264-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a3264-129">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a3264-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="a3264-130">Per rimuovere una raccolta specificata delle impostazioni di configurazione di Registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="a3264-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="a3264-131">Questo comando rimuove le impostazioni di configurazione di Registrazione dettagli chiamata applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="a3264-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="a3264-132">Per rimuovere tutte le impostazioni di configurazione di registrazione dei dati applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="a3264-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="a3264-133">Questo comando rimuove tutte le impostazioni di configurazione di Registrazione dettagli chiamata applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="a3264-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="a3264-134">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCdrConfiguration.](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a3264-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3264-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3264-135">See also</span></span>

[<span data-ttu-id="a3264-136">Eliminare manualmente i database di registrazione dettagli chiamata e Qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a3264-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)