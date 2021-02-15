---
title: Eliminare una raccolta esistente di impostazioni di configurazione dei trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Riepilogo: informazioni su come eliminare una raccolta di impostazioni di configurazione trunk utilizzando il Pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836976"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0ca49-103">Eliminare una raccolta esistente di impostazioni di configurazione dei trunk SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0ca49-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0ca49-104">**Riepilogo:** Informazioni su come eliminare una raccolta di impostazioni di configurazione trunk utilizzando il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ca49-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="0ca49-105">Le impostazioni di configurazione dei trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un IP-Public Branch eXchange (PBX) o un session border controller (SBC) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="0ca49-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="0ca49-106">Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0ca49-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="0ca49-107">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="0ca49-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="0ca49-108">Condizioni in cui vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="0ca49-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="0ca49-109">Indica se è necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="0ca49-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="0ca49-110">Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione dei trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="0ca49-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="0ca49-111">Questa raccolta globale di impostazioni non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="0ca49-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="0ca49-112">Tuttavia, è possibile utilizzare il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) per ripristinare i valori predefiniti delle proprietà della raccolta globale.</span><span class="sxs-lookup"><span data-stu-id="0ca49-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="0ca49-113">Se ad esempio la proprietà Enable3pccRefer è stata impostata su True, quando si reimposta l'insieme globale, la proprietà Enable3pccRefer viene ripristinata sul valore predefinito False.</span><span class="sxs-lookup"><span data-stu-id="0ca49-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="0ca49-p103">Gli amministratori possono inoltre creare impostazioni di configurazione personalizzate per i trunk con ambito sito o servizio (per un gateway PSTN singolo) che possono essere rimosse. Quando si rimuovono le impostazioni personalizzate, tenere presente che:</span><span class="sxs-lookup"><span data-stu-id="0ca49-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="0ca49-p104">Se si rimuovono le impostazioni con ambito servizio, il trunk SIP gestito da tali impostazioni verrà gestito dalle impostazioni applicate al rispettivo sito, se esistenti. In caso contrario, i trunk verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.</span><span class="sxs-lookup"><span data-stu-id="0ca49-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="0ca49-118">Se si rimuovono le impostazioni con ambito sito, i trunk SIP gestiti da tali impostazioni verranno gestiti dalla raccolta globale di impostazioni di configurazione dei trunk.</span><span class="sxs-lookup"><span data-stu-id="0ca49-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="0ca49-119">Per rimuovere le impostazioni di configurazione dei trunk con il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0ca49-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0ca49-120">Nel Pannello di controllo di Skype for Business Server fare clic su **Routing vocale** e quindi su **Configurazione trunk.**</span><span class="sxs-lookup"><span data-stu-id="0ca49-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="0ca49-p105">Nella scheda **Configurazione trunk** selezionare la raccolta di impostazioni di configurazione dei trunk SIP da eliminare, fare clic su **Modifica**, quindi su **Elimina**. Per eliminare più raccolte con una sola operazione, fare clic sulla prima raccolta da eliminare, quindi sulle altre raccolte tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="0ca49-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="0ca49-p106">La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="0ca49-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="0ca49-125">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ca49-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="0ca49-126">Nella finestra di dialogo Del Pannello di controllo di **Skype for Business Server** fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="0ca49-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="0ca49-127">Se si decide di non eliminare più la raccolta, fare clic su **Commit**, quindi su **Annulla tutte le modifiche di cui non è stato eseguito il commit**.</span><span class="sxs-lookup"><span data-stu-id="0ca49-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="0ca49-128">Quando viene visualizzata la finestra di dialogo Del Pannello di controllo di **Skype for Business Server,** fare clic su **OK.**</span><span class="sxs-lookup"><span data-stu-id="0ca49-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="0ca49-129">Rimozione delle impostazioni di configurazione dei trunk tramite i cmdlet di Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="0ca49-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="0ca49-130">È possibile eliminare le impostazioni di configurazione dei trunk utilizzando Skype for Business Server Management Shell e il cmdlet **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="0ca49-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="0ca49-131">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0ca49-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="0ca49-132">Per rimuovere una raccolta specificata di impostazioni</span><span class="sxs-lookup"><span data-stu-id="0ca49-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="0ca49-133">Il comando seguente rimuove le impostazioni di configurazione dei trunk applicate al sito di Redmond:</span><span class="sxs-lookup"><span data-stu-id="0ca49-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="0ca49-134">Per rimuovere tutte le raccolte applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="0ca49-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="0ca49-135">Questo comando rimuove tutte le impostazioni di configurazione dei trunk applicate all'ambito servizio:</span><span class="sxs-lookup"><span data-stu-id="0ca49-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="0ca49-136">Per rimuovere tutte le raccolte in cui è abilitato il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="0ca49-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="0ca49-137">Il comando seguente rimuove tutte le impostazioni di configurazione dei trunk in cui è stato abilitato il bypass multimediale:</span><span class="sxs-lookup"><span data-stu-id="0ca49-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="0ca49-138">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0ca49-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

