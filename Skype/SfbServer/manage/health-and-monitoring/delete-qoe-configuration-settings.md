---
title: Eliminare le impostazioni di configurazione della qualità dell'esperienza in Skype for Business Server
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Riepilogo: informazioni su come eliminare le impostazioni QoE (Quality of Experience) in Skype for Business Server.'
ms.openlocfilehash: 45150b6aa2e6f48eedb28f180cfff8f291f58abc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816936"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="9635c-103">Eliminare le impostazioni di configurazione della qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9635c-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="9635c-104">**Riepilogo:** Informazioni su come eliminare le impostazioni QoE (Quality of Experience) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9635c-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="9635c-p101">La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="9635c-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="9635c-107">Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="9635c-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="9635c-108">Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali.</span><span class="sxs-lookup"><span data-stu-id="9635c-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="9635c-109">Per impostazione predefinita, le impostazioni configurate in ambito sito hanno la precedenza sulle impostazioni configurate in ambito globale.</span><span class="sxs-lookup"><span data-stu-id="9635c-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="9635c-110">Se si eliminano le impostazioni in ambito sito, le metriche QoE verranno gestite nel sito utilizzando le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="9635c-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="9635c-111">Si noti che è anche possibile "eliminare" le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="9635c-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="9635c-112">Tuttavia, le impostazioni globali non vengono effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="9635c-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="9635c-113">Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9635c-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="9635c-114">Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="9635c-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="9635c-115">Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione.</span><span class="sxs-lookup"><span data-stu-id="9635c-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="9635c-116">Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9635c-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="9635c-117">In questo caso, ciò significa che l'eliminazione verrà riabilitata.</span><span class="sxs-lookup"><span data-stu-id="9635c-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="9635c-118">È possibile rimuovere le impostazioni di configurazione QoE utilizzando il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9635c-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9635c-119">Per eliminare le impostazioni di configurazione QoE tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9635c-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9635c-p104">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="9635c-p104">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="9635c-122">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9635c-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9635c-123">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="9635c-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="9635c-124">Nella pagina **Dati QoE** fare clic sul criterio desiderato, selezionare **Modifica** e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="9635c-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="9635c-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9635c-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9635c-126">Rimozione delle impostazioni di configurazione QoE tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="9635c-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9635c-127">È possibile eliminare le impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="9635c-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9635c-128">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9635c-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9635c-129">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="9635c-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9635c-130">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9635c-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="9635c-131">Per rimuovere una raccolta specificata di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="9635c-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="9635c-132">Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="9635c-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="9635c-133">Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito sito</span><span class="sxs-lookup"><span data-stu-id="9635c-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="9635c-134">Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito sito.</span><span class="sxs-lookup"><span data-stu-id="9635c-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="9635c-135">Per rimuovere tutte le impostazioni di configurazione QoE dove il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="9635c-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="9635c-136">Questo comando rimuove tutte le impostazioni di configurazione QoE dove il monitoraggio QoE è stato disabilitato</span><span class="sxs-lookup"><span data-stu-id="9635c-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="9635c-137">Per informazioni dettagliate, [vedere Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="9635c-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9635c-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9635c-138">See also</span></span>

[<span data-ttu-id="9635c-139">Eliminare manualmente i database di registrazione dettagli chiamata e Qualità dell'esperienza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9635c-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

