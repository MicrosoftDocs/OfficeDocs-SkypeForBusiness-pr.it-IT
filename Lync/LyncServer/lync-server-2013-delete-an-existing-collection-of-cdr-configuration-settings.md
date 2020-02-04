---
title: 'Lync Server 2013: eliminare una raccolta esistente di impostazioni di configurazione CDR'
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
ms.openlocfilehash: c50df73d59c588094693009ab4c84f2a7809ba5f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="98839-102">Eliminare una raccolta esistente di impostazioni di configurazione CDR in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98839-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98839-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="98839-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="98839-104">La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza.</span><span class="sxs-lookup"><span data-stu-id="98839-104">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="98839-105">Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.</span><span class="sxs-lookup"><span data-stu-id="98839-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="98839-106">Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="98839-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="98839-107">Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti.</span><span class="sxs-lookup"><span data-stu-id="98839-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="98839-108">In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="98839-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="98839-109">Se si eliminano le impostazioni con ambito sito, il CDR verrà gestito in tale sito usando le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="98839-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="98839-110">Tieni presente che puoi anche "eliminare" le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="98839-110">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="98839-111">Tuttavia, le impostazioni globali non verranno effettivamente rimosse.</span><span class="sxs-lookup"><span data-stu-id="98839-111">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="98839-112">Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="98839-112">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="98839-113">Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione CDR.</span><span class="sxs-lookup"><span data-stu-id="98839-113">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="98839-114">Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata.</span><span class="sxs-lookup"><span data-stu-id="98839-114">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="98839-115">Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="98839-115">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="98839-116">In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.</span><span class="sxs-lookup"><span data-stu-id="98839-116">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="98839-117">È possibile rimuovere le impostazioni di configurazione CDR usando il pannello di controllo di Lync Server o il cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="98839-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="98839-118">Per rimuovere le impostazioni di configurazione CDR con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="98839-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="98839-119">Nel pannello di controllo di Lync Server fare clic su **monitoraggio e archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="98839-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="98839-120">Nella scheda **registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni CDR da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="98839-120">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="98839-121">Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic su altre raccolte.</span><span class="sxs-lookup"><span data-stu-id="98839-121">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="98839-122">Fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="98839-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="98839-123">Nella finestra di dialogo Pannello di controllo di Lync Server fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="98839-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="98839-124">Rimozione delle impostazioni di configurazione CDR con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98839-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="98839-125">Puoi eliminare le impostazioni di configurazione della registrazione dei dettagli delle chiamate usando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="98839-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="98839-126">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98839-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="98839-127">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="98839-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="98839-128">Per rimuovere una raccolta specificata di impostazioni di configurazione CDR</span><span class="sxs-lookup"><span data-stu-id="98839-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="98839-129">Questo comando rimuove le impostazioni di configurazione CDR applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="98839-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="98839-130">Per rimuovere tutte le impostazioni di configurazione CDR applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="98839-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="98839-131">Questo comando rimuove tutte le impostazioni di configurazione CDR applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="98839-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="98839-132">Per rimuovere tutte le impostazioni di configurazione CDR che disabilitano la registrazione dei dettagli delle chiamate</span><span class="sxs-lookup"><span data-stu-id="98839-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="98839-133">Questo comando rimuove tutte le impostazioni di configurazione CDR in cui la registrazione dei dettagli delle chiamate è stata disattivata:</span><span class="sxs-lookup"><span data-stu-id="98839-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="98839-134">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="98839-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

