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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Prima che le persone nella tua organizzazione possano usare Skype Meeting Broadcast, devi abilitarlo. Per eseguire questo passaggio devi sapere come usare Windows PowerShell. Se non conosci Windows PowerShell, può essere utile assumere un partner Microsoft che se ne occupi al posto tuo.
ms.openlocfilehash: 699b82af07b263331ee5508326bf3e7ed015848e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370864"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="96e12-105">Abilitare Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="96e12-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="96e12-p102">[] Prima che le persone nella tua organizzazione possano usare Skype Meeting Broadcast, devi abilitarlo. Per eseguire questo passaggio devi sapere come usare Windows PowerShell. Se non conosci Windows PowerShell, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.</span><span class="sxs-lookup"><span data-stu-id="96e12-p102">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it. To do this, you need to know how to use Windows PowerShell. If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="96e12-109">Abilitare Skype Meeting Broadcast con l'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="96e12-109">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="96e12-110">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="96e12-110">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="96e12-111">Accedere con l'account amministratore globale di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="96e12-111">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="96e12-112">Nell'interfaccia di amministrazione di Office 365, passare a **Interfacce di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="96e12-112">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="96e12-113">In **Skype per interfaccia di amministrazione di Business**, accedere alle **riunioni in linea** > **trasmettere le riunioni**e quindi selezionare **Abilita trasmissione riunione Skype**.</span><span class="sxs-lookup"><span data-stu-id="96e12-113">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="96e12-114">Abilitare Skype Meeting Broadcast con PowerShell</span><span class="sxs-lookup"><span data-stu-id="96e12-114">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="96e12-115">Verifica che sia in esecuzione Windows PowerShell versione 3.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="96e12-115">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="96e12-116">Per verificare che sia in esecuzione la versione 3.0 o successive: **Menu Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96e12-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="96e12-117">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96e12-117">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="96e12-p103">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="96e12-p103">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="96e12-p104">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="96e12-p104">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="96e12-124">Dal **Menu Start**, scegliere **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="96e12-124">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="96e12-125">Nella finestra **Windows PowerShell**, stabilisci la connessione alla tua organizzazione Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="96e12-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   ```
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="96e12-126">Conferma la configurazione corrente di Skype Meeting Broadcast eseguendo:</span><span class="sxs-lookup"><span data-stu-id="96e12-126">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="96e12-127">Verifica che il parametro  _EnableBroadcastMeeting_ sia impostato su `False`.</span><span class="sxs-lookup"><span data-stu-id="96e12-127">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="96e12-129">Abilita Skype Meeting Broadcast per la tua organizzazione eseguendo:</span><span class="sxs-lookup"><span data-stu-id="96e12-129">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="96e12-130">Puoi confermare che l'impostazione sia abilitata eseguendo di nuovo  `Get-CsBroadcastMeetingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="96e12-130">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="96e12-132">Dopo aver apportato la modifica, potrebbe essere necessario attendere fino a un'ora perché questa diventi effettiva nel portale Skype Meeting Broadcast.</span><span class="sxs-lookup"><span data-stu-id="96e12-132">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="96e12-p105">Ora i tuoi utenti possono tenere riunioni in broadcast con altri utenti nell'azienda. Come prime indicazioni, fai riferimento a [Informazioni su Skype Meeting Broadcast](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d).</span><span class="sxs-lookup"><span data-stu-id="96e12-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="96e12-135">Configurare la rete per le riunioni in broadcast con partecipanti esterni</span><span class="sxs-lookup"><span data-stu-id="96e12-135">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="96e12-136">Se hai un firewall e vuoi trasmettere webinar o altre riunioni a partecipanti all'esterno dell'azienda (che non siano aziende federate), devi configurare la rete secondo queste istruzioni: [Configurare la rete per Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="96e12-136">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="96e12-137">Se non hai dimestichezza con la configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.</span><span class="sxs-lookup"><span data-stu-id="96e12-137">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="96e12-138">Per tralasciare questo passaggio e aggiungere un'altra azienda alla federazione, consulta [Consentire agli utenti di contattare utenti Skype for Business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="96e12-138">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="96e12-139">See also</span><span class="sxs-lookup"><span data-stu-id="96e12-139">Related topics</span></span>

[<span data-ttu-id="96e12-140">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="96e12-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="96e12-141">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="96e12-141">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 