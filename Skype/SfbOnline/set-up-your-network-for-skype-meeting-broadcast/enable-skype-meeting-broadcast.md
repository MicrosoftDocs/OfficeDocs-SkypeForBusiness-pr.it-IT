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
description: Prima che le persone dell'organizzazione possano usare Riunione Skype Broadcast, è necessario abilitarlo. A questo scopo, è necessario sapere come usare Windows PowerShell. Se non si conosce il Windows PowerShell, è consigliabile assumere un partner Microsoft per eseguire questo passaggio.
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237012"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="1c7e5-105">Abilitare Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="1c7e5-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="1c7e5-106">Skype for Business Online è in ritiro il 31 luglio 2021, quando l'accesso al servizio terminerà.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="1c7e5-107">Incoraggiamo i clienti a iniziare l'aggiornamento a Microsoft Teams, il client principale per le comunicazioni e il lavoro in team in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="1c7e5-108">Prima che le persone dell'organizzazione possano usare Riunione Skype Broadcast, è necessario abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="1c7e5-109">A questo scopo, è necessario sapere come usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="1c7e5-110">Se non si conosce il Windows PowerShell, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="1c7e5-111">L Microsoft Teams di amministrazione ha sostituito l'Skype for Business di amministrazione (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="1c7e5-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="1c7e5-112">Tutte le impostazioni per la Skype for Business sono ora disponibili nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="1c7e5-113">È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire Skype for Business funzionalità di Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="1c7e5-114">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="1c7e5-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="1c7e5-115">Abilitare Riunione Skype Broadcast tramite l'interfaccia Skype for Business di amministrazione</span><span class="sxs-lookup"><span data-stu-id="1c7e5-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="1c7e5-116">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="1c7e5-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="1c7e5-117">Accedere con l'account di amministratore globale o Skype for Business di amministrazione su [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="1c7e5-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="1c7e5-118">Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="1c7e5-119">**Nell'Teams di amministrazione** passare **a** Riunioni online legacy del portale e quindi selezionare Abilita Riunione Skype  >    >   **Broadcast.**</span><span class="sxs-lookup"><span data-stu-id="1c7e5-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="1c7e5-120">Abilitare Riunione Skype broadcast tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="1c7e5-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="1c7e5-121">Installare il [modulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="1c7e5-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="1c7e5-122">Aprire un Windows PowerShell prompt dei comandi ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c7e5-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="1c7e5-123">Confermare la configurazione Riunione Skype broadcast eseguendo:</span><span class="sxs-lookup"><span data-stu-id="1c7e5-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="1c7e5-124">Verificare che il parametro  _EnableBroadcastMeeting_ sia impostato su `False` .</span><span class="sxs-lookup"><span data-stu-id="1c7e5-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Riunione Skype Cmdlet Per abilitare la trasmissione dell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="1c7e5-126">Abilitare Riunione Skype broadcast per l'organizzazione eseguendo:</span><span class="sxs-lookup"><span data-stu-id="1c7e5-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="1c7e5-127">È possibile verificare che l'impostazione sia abilitata eseguendo di  `Get-CsBroadcastMeetingConfiguration` nuovo.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Riunione Skype Cmdlet per abilitare la trasmissione dell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="1c7e5-129">Dopo aver apportato la modifica, l'applicazione della modifica nel portale di Riunione Skype Broadcast potrebbe richiedere fino a un'ora.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="1c7e5-130">Gli utenti possono ora tenere riunioni in broadcast con altri utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="1c7e5-131">Per iniziare, scegliere Che [cos'è](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) un Riunione Skype Broadcast?</span><span class="sxs-lookup"><span data-stu-id="1c7e5-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="1c7e5-132">Configurare la rete per la trasmissione di riunioni con partecipanti esterni</span><span class="sxs-lookup"><span data-stu-id="1c7e5-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="1c7e5-133">Se si ha un firewall e si vogliono tenere trasmissioni con persone esterne all'azienda (che non sono un'azienda federata), è necessario configurare la rete usando queste istruzioni: Configurare la rete [per Riunione Skype Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="1c7e5-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="1c7e5-134">Se non si ha esperienza nella configurazione del firewall, è consigliabile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="1c7e5-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="1c7e5-135">Per ignorare questo passaggio e aggiungere un'altra azienda alla federazione, vedere Consentire agli utenti di contattare utenti Skype for Business [esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="1c7e5-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="1c7e5-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1c7e5-136">Related topics</span></span>

[<span data-ttu-id="1c7e5-137">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1c7e5-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="1c7e5-138">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1c7e5-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
