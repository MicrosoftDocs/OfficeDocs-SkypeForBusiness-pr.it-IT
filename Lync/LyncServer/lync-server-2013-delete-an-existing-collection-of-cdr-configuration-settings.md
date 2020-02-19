---
title: 'Lync Server 2013: eliminare una raccolta esistente di impostazioni di configurazione di registrazione dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77abb8ff4d50ec19b5d689193f909b0ddc4a475e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0c6d8-102">Eliminare una raccolta esistente di impostazioni di configurazione di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c6d8-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c6d8-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0c6d8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0c6d8-p101">La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="0c6d8-106">Quando si installa Microsoft Lync Server 2013, viene creata per l'utente una singola raccolta globale di impostazioni di configurazione di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="0c6d8-107">Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="0c6d8-108">Le impostazioni configurate nell'ambito del sito hanno precedenza su quelle configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="0c6d8-109">Se si eliminano le impostazioni con ambito a livello di sito, la Registrazione dettagli chiamata viene gestita nel sito in base alle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="0c6d8-p103">Tenere presente che è anche possibile "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non vengono effettivamente rimosse. Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti. Ad esempio, per impostazione predefinita la rimozione è abilitata in una raccolta delle impostazioni di configurazione di Registrazione dettagli chiamata. Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione. Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione verrà riabilitata.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="0c6d8-117">È possibile rimuovere le impostazioni di configurazione di registrazione dettagli chiamata utilizzando il pannello di controllo di Lync Server o il cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0c6d8-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="0c6d8-118">Per rimuovere le impostazioni di configurazione di CDR con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="0c6d8-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0c6d8-119">Nel pannello di controllo di Lync Server, fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="0c6d8-p104">Nella scheda **Registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni di Registrazione dettagli chiamata da rimuovere. Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic sulle raccolte aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="0c6d8-122">Fare clic su **Modifica** e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="0c6d8-123">Nella finestra di dialogo del pannello di controllo di Lync Server fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0c6d8-124">Rimozione delle impostazioni di configurazione di registrazione dettagli chiamata tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c6d8-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0c6d8-125">È possibile eliminare le impostazioni di configurazione della registrazione dettagli chiamata utilizzando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0c6d8-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="0c6d8-126">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0c6d8-127">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="0c6d8-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="0c6d8-128">Per rimuovere una raccolta specificata delle impostazioni di configurazione di Registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="0c6d8-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="0c6d8-129">Questo comando rimuove le impostazioni di configurazione di Registrazione dettagli chiamata applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="0c6d8-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="0c6d8-130">Per rimuovere tutte le impostazioni di configurazione di registrazione dettagli chiamata applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="0c6d8-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="0c6d8-131">Questo comando rimuove tutte le impostazioni di configurazione di Registrazione dettagli chiamata applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="0c6d8-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="0c6d8-132">Per rimuovere tutte le impostazioni di configurazione della Registrazione dettagli chiamata che disabilitano la registrazione dei dettagli:</span><span class="sxs-lookup"><span data-stu-id="0c6d8-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="0c6d8-133">Questo comando rimuove tutte le impostazioni di configurazione della Registrazione dettagli chiamata per cui la registrazione dei dettagli è stata disabilitata:</span><span class="sxs-lookup"><span data-stu-id="0c6d8-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="0c6d8-134">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0c6d8-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

