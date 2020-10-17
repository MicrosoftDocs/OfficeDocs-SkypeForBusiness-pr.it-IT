---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione per la qualità delle esperienze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ab6d90109d177fde84f8693cb4d14b5d8a6fdb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525543"
---
# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1459b-102">Eliminare le impostazioni di configurazione per la qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1459b-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1459b-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1459b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1459b-p101">La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="1459b-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="1459b-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="1459b-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="1459b-107">Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali.</span><span class="sxs-lookup"><span data-stu-id="1459b-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="1459b-108">Per impostazione predefinita, le impostazioni configurate in ambito sito hanno la precedenza sulle impostazioni configurate in ambito globale.</span><span class="sxs-lookup"><span data-stu-id="1459b-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="1459b-109">Se si eliminano le impostazioni in ambito sito, le metriche QoE verranno gestite nel sito utilizzando le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="1459b-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="1459b-p103">Si noti che è inoltre possibile "eliminare" le impostazioni globali. Tuttavia, le impostazioni non verranno realmente rimosse: per tutte le proprietà della raccolta verranno ripristinati i valori predefiniti. Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE. Si supponga di modificare la raccolta globale e disabilitare l'eliminazione. Se successivamente si eliminano le impostazioni globali, per tutte le proprietà verranno ripristinati i valori predefiniti. In tal caso, l'eliminazione verrà di nuovo abilitata.</span><span class="sxs-lookup"><span data-stu-id="1459b-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of QoE configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="1459b-117">È possibile rimuovere le impostazioni di configurazione QoE utilizzando il pannello di controllo di Lync Server o utilizzando il cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1459b-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="1459b-118">Per eliminare le impostazioni di configurazione QoE utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="1459b-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1459b-119">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1459b-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1459b-120">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1459b-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="1459b-121">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1459b-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1459b-122">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1459b-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1459b-123">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="1459b-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="1459b-124">Nella pagina **Dati QoE** fare clic sul criterio desiderato, selezionare **Modifica** e quindi fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1459b-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="1459b-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1459b-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1459b-126">Rimozione delle impostazioni di configurazione QoE tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1459b-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1459b-127">È possibile eliminare le impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1459b-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="1459b-128">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1459b-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1459b-129">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1459b-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="1459b-130">Per rimuovere una raccolta specificata di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="1459b-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="1459b-131">Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="1459b-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="1459b-132">Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito sito</span><span class="sxs-lookup"><span data-stu-id="1459b-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="1459b-133">Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito sito.</span><span class="sxs-lookup"><span data-stu-id="1459b-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="1459b-134">Per rimuovere tutte le impostazioni di configurazione QoE dove il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="1459b-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="1459b-135">Questo comando rimuove tutte le impostazioni di configurazione QoE dove il monitoraggio QoE è stato disabilitato</span><span class="sxs-lookup"><span data-stu-id="1459b-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="1459b-136">Per informazioni dettagliate, vedere [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1459b-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

