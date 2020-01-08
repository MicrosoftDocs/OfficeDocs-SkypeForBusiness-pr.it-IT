---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione della qualità delle esperienze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9515186ab28a6d6085a01ee6785aa1d95914b1f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="eef0f-102">Eliminare le impostazioni di configurazione della qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eef0f-102">Delete Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef0f-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eef0f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eef0f-104">Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto).</span><span class="sxs-lookup"><span data-stu-id="eef0f-104">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay).</span></span> <span data-ttu-id="eef0f-105">Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.</span><span class="sxs-lookup"><span data-stu-id="eef0f-105">These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="eef0f-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="eef0f-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="eef0f-107">Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti.</span><span class="sxs-lookup"><span data-stu-id="eef0f-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="eef0f-108">In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="eef0f-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="eef0f-109">Se si eliminano le impostazioni con ambito sito, QoE verrà gestito in tale sito utilizzando le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="eef0f-109">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="eef0f-110">Tieni presente che puoi anche "eliminare" le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="eef0f-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="eef0f-111">Tuttavia, le impostazioni globali non verranno effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="eef0f-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="eef0f-112">Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="eef0f-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="eef0f-113">Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE.</span><span class="sxs-lookup"><span data-stu-id="eef0f-113">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="eef0f-114">Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata.</span><span class="sxs-lookup"><span data-stu-id="eef0f-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="eef0f-115">Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="eef0f-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="eef0f-116">In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.</span><span class="sxs-lookup"><span data-stu-id="eef0f-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="eef0f-117">È possibile rimuovere le impostazioni di configurazione QoE usando il pannello di controllo di Lync Server o usando il cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="eef0f-117">You can remove QoE configuration settings by using the Lync Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet.</span></span>

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="eef0f-118">Per eliminare le impostazioni di configurazione QoE tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="eef0f-118">To delete QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="eef0f-119">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="eef0f-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="eef0f-120">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="eef0f-120">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="eef0f-121">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eef0f-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eef0f-122">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eef0f-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eef0f-123">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="eef0f-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="eef0f-124">Nella pagina **qualità di dati esperienza** fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="eef0f-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="eef0f-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="eef0f-125">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eef0f-126">Rimozione delle impostazioni di configurazione QoE con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eef0f-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eef0f-127">Puoi eliminare le impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="eef0f-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="eef0f-128">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eef0f-128">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eef0f-129">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="eef0f-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="eef0f-130">Per rimuovere una raccolta specificata di impostazioni di configurazione QoE</span><span class="sxs-lookup"><span data-stu-id="eef0f-130">To remove a specified collection of QoE configuration settings</span></span>

  - <span data-ttu-id="eef0f-131">Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="eef0f-131">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="eef0f-132">Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="eef0f-132">To remove all of the QoE configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="eef0f-133">Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="eef0f-133">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="eef0f-134">Per rimuovere tutte le impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato</span><span class="sxs-lookup"><span data-stu-id="eef0f-134">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="eef0f-135">Questo comando rimuove tutte le impostazioni di configurazione QoE in cui è stato disabilitato il monitoraggio QoE:</span><span class="sxs-lookup"><span data-stu-id="eef0f-135">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

<span data-ttu-id="eef0f-136">Per informazioni dettagliate, vedere [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="eef0f-136">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

