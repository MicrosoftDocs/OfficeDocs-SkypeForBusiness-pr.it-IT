---
title: Abilitare la trasmissione riunione Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: SMB
description: "Le persone all'interno dell'organizzazione possono utilizzare Skype riunione trasmissione, è necessario abilitarla. A tale scopo, è necessario conoscere le modalità di utilizzo di Windows PowerShell. Se non si conosce Windows PowerShell, potrebbe essere necessario rivolgersi a un partner Microsoft per eseguire questo passaggio è."
ms.openlocfilehash: 975f0304f2053e23375c5eabc62ec224bedc02e7
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="7cc43-105">Abilitare la trasmissione riunione Skype</span><span class="sxs-lookup"><span data-stu-id="7cc43-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="7cc43-106">Le persone all'interno dell'organizzazione possono utilizzare Skype riunione trasmissione, è necessario abilitarla.</span><span class="sxs-lookup"><span data-stu-id="7cc43-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="7cc43-107">A tale scopo, è necessario conoscere le modalità di utilizzo di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cc43-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="7cc43-108">Se non si conosce Windows PowerShell, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.</span><span class="sxs-lookup"><span data-stu-id="7cc43-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7cc43-109">Skype riunione trasmissione è disattivata per impostazione predefinita in quanto la distribuzione dei contenuti multimediali di una riunione di trasmissione utilizza contenuto di rete (CDN del Microsoft Azure) per garantire la scalabilità molto alta per supportare migliaia di persone che seguono una trasmissione.</span><span class="sxs-lookup"><span data-stu-id="7cc43-109">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast.</span></span> <span data-ttu-id="7cc43-110">Il contenuto multimediale in blocchi passare attraverso la rete CDN è crittografato e la cache CDN con una durata limitata.</span><span class="sxs-lookup"><span data-stu-id="7cc43-110">The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime.</span></span> <span data-ttu-id="7cc43-111">Inoltre, il componente di Azure CDN potrebbe non ancora soddisfare tutti gli elementi delle clausole modello UE derivanti dalla direttiva sulla protezione dei dati dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="7cc43-111">Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive.</span></span> <span data-ttu-id="7cc43-112">Se si attiva questa caratteristica, l'utente riconosce questo avviso.</span><span class="sxs-lookup"><span data-stu-id="7cc43-112">By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="7cc43-113">Abilitare Skype riunione trasmessi utilizzando il Skype per interfaccia di amministrazione di Business</span><span class="sxs-lookup"><span data-stu-id="7cc43-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="7cc43-114">Accedere con l'account amministratore globale di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="7cc43-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="7cc43-115">Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="7cc43-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="7cc43-116">In **Skype per interfaccia di amministrazione di Business**, accedere alle **riunioni in linea** > **trasmettere le riunioni**e quindi selezionare **Abilita trasmissione riunione Skype**.</span><span class="sxs-lookup"><span data-stu-id="7cc43-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="7cc43-117">Abilitare Skype riunione trasmissione tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cc43-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="7cc43-118">Verificare che sia in esecuzione versione 3.0 o versione successiva di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cc43-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="7cc43-119">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7cc43-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="7cc43-120">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7cc43-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="7cc43-p104">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="7cc43-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="7cc43-p105">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="7cc43-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="7cc43-127">Dal **Menu Start**, scegliere **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7cc43-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="7cc43-128">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="7cc43-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="7cc43-129">Verificare la configurazione corrente Skype trasmissione riunione eseguendo:</span><span class="sxs-lookup"><span data-stu-id="7cc43-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="7cc43-130">Verificare che il parametro _EnableBroadcastMeeting_ è impostato su `False`.</span><span class="sxs-lookup"><span data-stu-id="7cc43-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Skype riunione trasmissione abilitare organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="7cc43-132">Abilitare trasmissione riunione Skype per l'organizzazione mediante l'esecuzione:</span><span class="sxs-lookup"><span data-stu-id="7cc43-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="7cc43-133">È possibile verificare che l'impostazione viene abilitata eseguendo `Get-CsBroadcastMeetingConfiguration` nuovamente.</span><span class="sxs-lookup"><span data-stu-id="7cc43-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype riunione trasmissione abilitare Cmdlet dell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="7cc43-135">Dopo aver apportato le modifiche, potrebbero richiedere un'ora per rendere effettive nel portale di trasmissione riunione Skype.</span><span class="sxs-lookup"><span data-stu-id="7cc43-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="7cc43-136">Gli utenti possono ora riunisce trasmissione con altri utenti nell'azienda.</span><span class="sxs-lookup"><span data-stu-id="7cc43-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="7cc43-137">Per ottenere tali introduttiva, puntino al [che cos'è una riunione Skype trasmissione?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="7cc43-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="7cc43-138">Configurazione della rete per le riunioni con partecipanti esterni di trasmissione</span><span class="sxs-lookup"><span data-stu-id="7cc43-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="7cc43-139">Se è presente un firewall e si desidera mantenere le trasmissioni con utenti esterni all'azienda (che non sono un'azienda federata), è necessario configurare la rete queste istruzioni: [configurazione di rete per la trasmissione riunione Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="7cc43-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="7cc43-140">Se non si è pratici di configurazione del firewall, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio è.</span><span class="sxs-lookup"><span data-stu-id="7cc43-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="7cc43-141">Per ignorare questo passaggio e invece aggiungere un'altra business per la federazione, vedere [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="7cc43-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7cc43-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7cc43-142">Related topics</span></span>

[<span data-ttu-id="7cc43-143">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7cc43-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="7cc43-144">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="7cc43-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

