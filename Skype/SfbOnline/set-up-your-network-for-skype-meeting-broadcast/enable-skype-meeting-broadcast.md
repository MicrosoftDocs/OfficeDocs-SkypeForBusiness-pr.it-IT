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
description: Prima che le persone nella tua organizzazione possano utilizzare Skype Meeting Broadcast, devi attivarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, valutare l'assunzione di un partner Microsoft per eseguire questo passaggio per conto dell'utente.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865140"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="7dca3-105">Abilitare Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="7dca3-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dca3-106">Skype for Business online verrà ritirato il 31 luglio 2021, data in cui l'accesso al servizio terminerà.</span><span class="sxs-lookup"><span data-stu-id="7dca3-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="7dca3-107">Consigliamo ai clienti di iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7dca3-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="7dca3-108">Prima che le persone nella tua organizzazione possano utilizzare Skype Meeting Broadcast, devi attivarlo.</span><span class="sxs-lookup"><span data-stu-id="7dca3-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="7dca3-109">A questo scopo, è necessario sapere come usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dca3-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="7dca3-110">Se non si conosce il Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7dca3-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="7dca3-111">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="7dca3-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="7dca3-112">Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="7dca3-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="7dca3-113">Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario disporre del ruolo di amministratore di [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) come amministratore globale o amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7dca3-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="7dca3-114">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="7dca3-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="7dca3-115">Abilitare Skype Meeting Broadcast con l'interfaccia di amministrazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7dca3-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="7dca3-116">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="7dca3-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="7dca3-117">Accedi con il tuo account di amministratore globale o con l'account amministratore di Skype for Business all'indirizzo [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="7dca3-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="7dca3-118">Nell'interfaccia di amministrazione passare a **Team delle interfaccia di**  >  **amministrazione.**</span><span class="sxs-lookup"><span data-stu-id="7dca3-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="7dca3-119">**Nell'interfaccia di amministrazione di Teams,** vai a Riunioni broadcast del portale **legacy** e  >  **riunioni online,** quindi seleziona Abilita Skype Meeting  >   **Broadcast.**</span><span class="sxs-lookup"><span data-stu-id="7dca3-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="7dca3-120">Abilitare Skype Meeting Broadcast con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7dca3-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="7dca3-121">Verificare che sia in esecuzione la versione 3.0 o successiva di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dca3-121">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="7dca3-122">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7dca3-122">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="7dca3-123">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="7dca3-123">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="7dca3-124">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7dca3-124">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="7dca3-125">Vedere [Windows Management Framework 4.0 per](https://go.microsoft.com/fwlink/?LinkId=716845) scaricare e aggiornare Windows PowerShell alla versione 4.0.</span><span class="sxs-lookup"><span data-stu-id="7dca3-125">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="7dca3-126">Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="7dca3-126">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="7dca3-p106">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="7dca3-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="7dca3-130">Nel **menu Start scegliere** **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="7dca3-130">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="7dca3-131">Nella finestra **Windows PowerShell** connessione a Microsoft 365 o Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="7dca3-131">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="7dca3-132">Conferma la configurazione corrente di Skype Meeting Broadcast eseguendo:</span><span class="sxs-lookup"><span data-stu-id="7dca3-132">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="7dca3-133">Verificare che il  _parametro EnableBroadcastMeeting_ sia impostato su `False` .</span><span class="sxs-lookup"><span data-stu-id="7dca3-133">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="7dca3-135">Abilitare Skype Meeting Broadcast per l'organizzazione eseguendo:</span><span class="sxs-lookup"><span data-stu-id="7dca3-135">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="7dca3-136">Per verificare che l'impostazione sia abilitata, eseguire di  `Get-CsBroadcastMeetingConfiguration` nuovo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7dca3-136">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="7dca3-138">Dopo aver apportato la modifica, l'applicazione nel portale di Skype Meeting Broadcast può richiedere fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="7dca3-138">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="7dca3-139">Ora i tuoi utenti possono tenere riunioni in broadcast con altri utenti della tua azienda.</span><span class="sxs-lookup"><span data-stu-id="7dca3-139">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="7dca3-140">Per iniziare, indicargli che [cos'è Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="7dca3-140">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="7dca3-141">Configurare la rete per la trasmissione di riunioni con partecipanti esterni</span><span class="sxs-lookup"><span data-stu-id="7dca3-141">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="7dca3-142">Se hai un firewall e vuoi tenere trasmissioni con persone esterne all'azienda (che non sono aziende federate), devi configurare la rete nel modo seguente: Configurare la rete per [Skype Meeting Broadcast.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="7dca3-142">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="7dca3-143">Se non hai esperienza nella configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per fare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="7dca3-143">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="7dca3-144">Per ignorare questo passaggio e aggiungere un'altra azienda alla federazione, vedere Consentire agli utenti di [contattare utenti Skype for Business esterni.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="7dca3-144">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7dca3-145">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7dca3-145">Related topics</span></span>

[<span data-ttu-id="7dca3-146">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="7dca3-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="7dca3-147">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="7dca3-147">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
