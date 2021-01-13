---
title: Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Skype for Business Server
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
description: 'Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. '
ms.openlocfilehash: f8e7e3576640e4c560cd620349f5c3afdaf541cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816326"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="21112-103">Eliminare una raccolta esistente di impostazioni di configurazione del trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="21112-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="21112-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="21112-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="21112-106">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="21112-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="21112-107">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="21112-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="21112-108">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="21112-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="21112-109">Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="21112-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="21112-110">Questa raccolta globale di impostazioni non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="21112-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="21112-111">Tuttavia, è possibile utilizzare il pannello di ServerControl di Skype for business o il cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) per "reimpostare" le proprietà della raccolta globale sui rispettivi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="21112-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="21112-112">Ad esempio, se la proprietà Enable3pccRefer è stata impostata su true, quando si reimposta la raccolta globale, la proprietà Enable3pccRefer restituirà il valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="21112-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="21112-p103">Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono le impostazioni personalizzate, tenere presente che:</span><span class="sxs-lookup"><span data-stu-id="21112-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="21112-p104">Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.</span><span class="sxs-lookup"><span data-stu-id="21112-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="21112-117">Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.</span><span class="sxs-lookup"><span data-stu-id="21112-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="21112-118">**Per rimuovere le impostazioni di configurazione del trunk con il pannello di controllo di Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="21112-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="21112-119">Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale** e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="21112-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="21112-120">Nella scheda **configurazione trunk** selezionare la raccolta di impostazioni di configurazione trunk SIP da eliminare, fare clic su **modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="21112-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="21112-121">Per eliminare più raccolte con una sola operazione, fare clic sulla prima raccolta da eliminare, quindi sulle altre raccolte tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="21112-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="21112-p106">La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="21112-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="21112-124">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="21112-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="21112-125">Nella finestra di dialogo del **Pannello di controllo di Skype for Business Server** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="21112-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="21112-126">Se si cambia idea e si decide di non eliminare la raccolta, fare clic su **commit** e quindi su **Annulla tutte le modifiche non salvate**.</span><span class="sxs-lookup"><span data-stu-id="21112-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="21112-127">Quando viene visualizzata la finestra di dialogo del **Pannello di controllo di Skype for Business Server** , fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="21112-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="21112-128">Rimozione delle impostazioni di configurazione del trunk tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21112-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="21112-129">È possibile eliminare le impostazioni di configurazione del trunk utilizzando Windows PowerShell e il cmdlet **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="21112-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="21112-130">È possibile eseguire questo cmdlet sia da Skype for Business Server Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21112-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="21112-131">**Per rimuovere una raccolta specificata di impostazioni**</span><span class="sxs-lookup"><span data-stu-id="21112-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="21112-132">Il comando seguente rimuove le impostazioni di configurazione dei trunk applicate al sito di Redmond:</span><span class="sxs-lookup"><span data-stu-id="21112-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="21112-133">**Per rimuovere tutte le raccolte applicate all'ambito del sito**</span><span class="sxs-lookup"><span data-stu-id="21112-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="21112-134">Questo comando rimuove tutte le impostazioni di configurazione dei trunk applicate all'ambito servizio:</span><span class="sxs-lookup"><span data-stu-id="21112-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="21112-135">**Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale**</span><span class="sxs-lookup"><span data-stu-id="21112-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="21112-136">Il comando seguente rimuove tutte le impostazioni di configurazione dei trunk in cui è stato abilitato il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="21112-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="21112-137">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="21112-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
