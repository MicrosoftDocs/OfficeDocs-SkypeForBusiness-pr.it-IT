---
title: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP
description: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98acede458d34eb30202d898414b2e17076d32d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572822"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="49de1-103">Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49de1-103">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49de1-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="49de1-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="49de1-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="49de1-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="49de1-107">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="49de1-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="49de1-108">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="49de1-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="49de1-109">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="49de1-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="49de1-110">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="49de1-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="49de1-111">Questa raccolta globale di impostazioni non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="49de1-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="49de1-112">Tuttavia, è possibile utilizzare il pannello di controllo di Lync Server o il cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) per "reimpostare" le proprietà della raccolta globale sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="49de1-112">However, you can use the Lync Server Control Panel or the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="49de1-113">Ad esempio, se la proprietà Enable3pccRefer è stata impostata su true, quando si reimposta la raccolta globale, la proprietà Enable3pccRefer restituirà il valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="49de1-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="49de1-p103">Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono le impostazioni personalizzate, tenere presente che:</span><span class="sxs-lookup"><span data-stu-id="49de1-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

  - <span data-ttu-id="49de1-p104">Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.</span><span class="sxs-lookup"><span data-stu-id="49de1-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>

  - <span data-ttu-id="49de1-118">Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.</span><span class="sxs-lookup"><span data-stu-id="49de1-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="49de1-119">Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="49de1-119">To remove trunk configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="49de1-120">Nel pannello di controllo di Lync Server, fare clic su **routing vocale** e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="49de1-120">In Lync Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="49de1-p105">Nella scheda **Configurazione trunk** selezionare la raccolta di impostazioni di configurazione dei trunk SIP da eliminare, fare clic su **Modifica**, quindi su **Elimina**. Per eliminare più raccolte con una sola operazione, fare clic sulla prima raccolta da eliminare, quindi sulle altre raccolte tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="49de1-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>

3.  <span data-ttu-id="49de1-p106">La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="49de1-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

4.  <span data-ttu-id="49de1-125">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49de1-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

5.  <span data-ttu-id="49de1-126">Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49de1-126">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

6.  <span data-ttu-id="49de1-p107">Se si decide di non eliminare più la raccolta, fare clic su **Commit**, quindi su **Annulla tutte le modifiche di cui non è stato eseguito il commit**. Quando viene visualizzata la finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013**, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="49de1-p107">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**. When the **Microsoft Lync Server 2013 Control Panel** dialog box appears, click **OK**.</span></span>

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="49de1-129">Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49de1-129">Removing Trunk Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="49de1-130">È possibile eliminare le impostazioni di configurazione del trunk utilizzando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="49de1-130">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="49de1-131">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49de1-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="49de1-132">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="49de1-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="49de1-133">Per rimuovere una raccolta specificata di impostazioni</span><span class="sxs-lookup"><span data-stu-id="49de1-133">To remove a specified collection of settings</span></span>

  - <span data-ttu-id="49de1-134">Il comando seguente rimuove le impostazioni di configurazione dei trunk applicate al sito di Redmond:</span><span class="sxs-lookup"><span data-stu-id="49de1-134">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="49de1-135">Per rimuovere tutte le raccolte applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="49de1-135">To remove all the collections applied to the site scope</span></span>

  - <span data-ttu-id="49de1-136">Questo comando rimuove tutte le impostazioni di configurazione dei trunk applicate all'ambito servizio:</span><span class="sxs-lookup"><span data-stu-id="49de1-136">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="49de1-137">Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="49de1-137">To remove all the collections where media bypass is enabled</span></span>

  - <span data-ttu-id="49de1-138">Il comando seguente rimuove tutte le impostazioni di configurazione dei trunk in cui è stato abilitato il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="49de1-138">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

<span data-ttu-id="49de1-139">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="49de1-139">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

