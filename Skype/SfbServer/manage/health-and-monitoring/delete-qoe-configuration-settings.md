---
title: Eliminare le impostazioni di configurazione della qualità delle esperienze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Riepilogo: informazioni su come eliminare le impostazioni di qualità delle esperienze (QoE) in Skype for Business Server.'
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992423"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9403a-103">Eliminare le impostazioni di configurazione della qualità delle esperienze in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9403a-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9403a-104">**Riepilogo:** Informazioni su come eliminare le impostazioni di qualità delle esperienze (QoE) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9403a-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9403a-105">Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto).</span><span class="sxs-lookup"><span data-stu-id="9403a-105">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="9403a-106">Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="9403a-106">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="9403a-107">Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="9403a-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9403a-108">Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti.</span><span class="sxs-lookup"><span data-stu-id="9403a-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="9403a-109">In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="9403a-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="9403a-110">Se si eliminano le impostazioni con ambito sito, QoE verrà gestito in tale sito utilizzando le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="9403a-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="9403a-111">Tieni presente che puoi anche "eliminare" le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="9403a-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="9403a-112">Tuttavia, le impostazioni globali non verranno effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="9403a-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="9403a-113">Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9403a-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="9403a-114">Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="9403a-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="9403a-115">Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata.</span><span class="sxs-lookup"><span data-stu-id="9403a-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="9403a-116">Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9403a-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="9403a-117">In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.</span><span class="sxs-lookup"><span data-stu-id="9403a-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="9403a-118">Puoi rimuovere le impostazioni di configurazione QoE usando il pannello di controllo di Skype for Business Server o usando il cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9403a-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9403a-119">Per eliminare le impostazioni di configurazione QoE usando il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9403a-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9403a-120">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9403a-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9403a-121">Per informazioni dettagliate, vedere **delegare le autorizzazioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="9403a-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="9403a-122">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9403a-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9403a-123">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="9403a-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="9403a-124">Nella pagina **qualità di dati esperienza** fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9403a-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="9403a-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9403a-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9403a-126">Rimozione delle impostazioni di configurazione QoE con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9403a-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9403a-127">Puoi eliminare le impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9403a-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9403a-128">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9403a-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9403a-129">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9403a-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9403a-130">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9403a-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9403a-131">Per rimuovere una raccolta specificata di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="9403a-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="9403a-132">Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="9403a-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="9403a-133">Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="9403a-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="9403a-134">Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="9403a-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9403a-135">Per rimuovere tutte le impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="9403a-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="9403a-136">Questo comando rimuove tutte le impostazioni di configurazione QoE in cui è stato disabilitato il monitoraggio QoE:</span><span class="sxs-lookup"><span data-stu-id="9403a-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="9403a-137">Per informazioni dettagliate, vedere [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="9403a-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9403a-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9403a-138">See also</span></span>

[<span data-ttu-id="9403a-139">Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9403a-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

