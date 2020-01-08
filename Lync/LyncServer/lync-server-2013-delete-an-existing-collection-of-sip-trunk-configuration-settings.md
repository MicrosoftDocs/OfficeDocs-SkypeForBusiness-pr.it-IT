---
title: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8e5fa-102">Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e5fa-102">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e5fa-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8e5fa-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8e5fa-104">Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="8e5fa-105">Queste impostazioni eseguono operazioni come specifica:</span><span class="sxs-lookup"><span data-stu-id="8e5fa-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="8e5fa-106">Se il bypass multimediale deve essere abilitato nei trunk.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="8e5fa-107">Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="8e5fa-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="8e5fa-108">Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="8e5fa-109">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8e5fa-110">Questa raccolta globale di impostazioni non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="8e5fa-111">Tuttavia, puoi usare il pannello di controllo di Lync Server o il cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) per "reimpostare" i valori predefiniti delle proprietà della raccolta globale.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-111">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="8e5fa-112">Se ad esempio è stata impostata la proprietà Enable3pccRefer su true, quando si reimposta la raccolta globale la proprietà Enable3pccRefer restituirà il valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="8e5fa-113">Gli amministratori possono anche creare impostazioni di configurazione trunk personalizzate nell'ambito del sito o nell'ambito del servizio (per un singolo gateway PSTN); Queste impostazioni personalizzate possono essere rimosse.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="8e5fa-114">Quando si rimuovono queste impostazioni personalizzate, tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e5fa-114">When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="8e5fa-115">Se si rimuovono le impostazioni dell'ambito del servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al sito, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="8e5fa-116">Se le impostazioni del sito non esistono, i trunk verranno quindi gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="8e5fa-117">Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno ora gestiti dalla raccolta globale delle impostazioni di configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="8e5fa-118">Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8e5fa-118">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8e5fa-119">Nel pannello di controllo di Lync Server fare clic su **routing vocale** e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-119">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="8e5fa-120">Nella scheda **configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="8e5fa-121">Per eliminare più raccolte nella stessa operazione, fare clic sulla prima raccolta da eliminare, quindi tenere premuto CTRL e fare clic su eventuali raccolte aggiuntive che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="8e5fa-122">La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-122">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="8e5fa-123">Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-123">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="8e5fa-124">Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="8e5fa-125">Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-125">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="8e5fa-126">Se si cambia idea e si decide di non eliminare la raccolta, fare clic su **commit** e quindi su **Annulla tutte le modifiche non salvate**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-126">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="8e5fa-127">Quando viene visualizzata la finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** , fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-127">When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8e5fa-128">Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e5fa-128">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8e5fa-129">Puoi eliminare le impostazioni di configurazione del trunk usando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8e5fa-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="8e5fa-130">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-130">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8e5fa-131">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="8e5fa-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="8e5fa-132">Per rimuovere una raccolta di impostazioni specificata</span><span class="sxs-lookup"><span data-stu-id="8e5fa-132">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="8e5fa-133">Il comando seguente rimuove le impostazioni di configurazione trunk applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="8e5fa-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="8e5fa-134">Per rimuovere tutte le raccolte applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="8e5fa-134">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="8e5fa-135">Questo comando rimuove tutte le impostazioni di configurazione trunk applicate all'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="8e5fa-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="8e5fa-136">Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="8e5fa-136">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="8e5fa-137">Il comando seguente rimuove tutte le impostazioni di configurazione trunk in cui è stato abilitato il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="8e5fa-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="8e5fa-138">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8e5fa-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

