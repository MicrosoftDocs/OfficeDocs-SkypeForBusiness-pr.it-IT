---
title: Abilitare Skype Meeting Broadcast
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Prima che gli utenti dell'organizzazione possano usare Skype meeting broadcast, è necessario abilitarlo. A questo scopo, devi sapere come usare Windows PowerShell. Se non si conosce Windows PowerShell, è consigliabile assumere un partner Microsoft per eseguire questo passaggio.
ms.openlocfilehash: 601cef096b032dd387de6d84bb7e676dc08054ec
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739054"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="d07cd-105">Abilitare Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="d07cd-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d07cd-106">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="d07cd-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="d07cd-107">Tutte le impostazioni per la gestione di Skype for business si trovano ora nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="d07cd-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="d07cd-108">Per altre informazioni, vedere [gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="d07cd-108">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="d07cd-109">Prima che gli utenti dell'organizzazione possano usare Skype meeting broadcast, è necessario abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="d07cd-109">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="d07cd-110">A questo scopo, devi sapere come usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d07cd-110">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="d07cd-111">Se non si conosce Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d07cd-111">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="d07cd-112">Abilitare Skype meeting broadcast con l'interfaccia di amministrazione di Skype for business</span><span class="sxs-lookup"><span data-stu-id="d07cd-112">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="d07cd-113">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d07cd-113">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d07cd-114">Accedere con l'account di amministratore globale o con l'account di amministratore di Skype for business [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="d07cd-114">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="d07cd-115">Nell'interfaccia di amministrazione accedere a **Admin centers**  >  **Teams**di interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d07cd-115">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="d07cd-116">Nell'interfaccia di **amministrazione di teams**, passa a riunioni broadcast **legacy Portal**  >  **online**  >  **Broadcast meetings**e quindi seleziona **Abilita Skype meeting broadcast**.</span><span class="sxs-lookup"><span data-stu-id="d07cd-116">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="d07cd-117">Abilitare Skype meeting broadcast tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="d07cd-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="d07cd-118">Verificare che sia in esecuzione la versione 3,0 o successiva di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d07cd-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="d07cd-119">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d07cd-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="d07cd-120">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d07cd-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="d07cd-121">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d07cd-121">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="d07cd-122">Vedere [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) per scaricare e aggiornare Windows PowerShell alla versione 4,0.</span><span class="sxs-lookup"><span data-stu-id="d07cd-122">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="d07cd-123">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d07cd-123">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="d07cd-p105">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="d07cd-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="d07cd-127">Scegliere **Windows PowerShell**dal **menu Start**.</span><span class="sxs-lookup"><span data-stu-id="d07cd-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="d07cd-128">Nella finestra di **Windows PowerShell** connettersi a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="d07cd-128">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="d07cd-129">Conferma la configurazione corrente di Skype meeting broadcast eseguendo:</span><span class="sxs-lookup"><span data-stu-id="d07cd-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="d07cd-130">Verificare che il parametro  _EnableBroadcastMeeting_ sia impostato su `False` .</span><span class="sxs-lookup"><span data-stu-id="d07cd-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet per l'organizzazione di Skype meeting broadcast.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="d07cd-132">Abilitare Skype meeting broadcast per l'organizzazione eseguendo:</span><span class="sxs-lookup"><span data-stu-id="d07cd-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="d07cd-133">È possibile verificare che l'impostazione sia abilitata eseguendo di  `Get-CsBroadcastMeetingConfiguration` nuovo.</span><span class="sxs-lookup"><span data-stu-id="d07cd-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet per l'organizzazione di Skype meeting broadcast.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="d07cd-135">Dopo aver apportato la modifica, il portale di Skype meeting broadcast può richiedere fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="d07cd-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="d07cd-136">Gli utenti possono ora tenere riunioni broadcast con altri utenti nella tua azienda.</span><span class="sxs-lookup"><span data-stu-id="d07cd-136">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="d07cd-137">Per iniziare, posizionare il puntatore su [Skype meeting broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="d07cd-137">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="d07cd-138">Configurare la rete per la trasmissione di riunioni con partecipanti esterni</span><span class="sxs-lookup"><span data-stu-id="d07cd-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="d07cd-139">Se si dispone di un firewall e si vogliono tenere le trasmissioni broadcast con persone esterne all'azienda (che non sono una società federata), è necessario configurare la rete usando queste istruzioni: configurare [la rete per Skype meeting broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="d07cd-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="d07cd-140">Se non si ha esperienza con la configurazione del firewall, prendere in considerazione l'assunzione di un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="d07cd-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="d07cd-141">Per ignorare questo passaggio e aggiungere un altro business alla Federazione, vedere [consentire agli utenti di contattare utenti Skype for business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="d07cd-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="d07cd-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d07cd-142">Related topics</span></span>

[<span data-ttu-id="d07cd-143">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d07cd-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="d07cd-144">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d07cd-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
