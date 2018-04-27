---
title: Configurazione del servizio MMS (Meeting Migration Service)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Migrazione servizio MMS delle riunioni è Skype per servizio di Business che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.
ms.openlocfilehash: 3dd85d0e4eb588a916c7c4738c982a888133b3bd
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="e5a06-104">Configurazione del servizio MMS (Meeting Migration Service)</span><span class="sxs-lookup"><span data-stu-id="e5a06-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="e5a06-105">Migrazione servizio MMS delle riunioni è Skype per servizio di Business che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e5a06-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="e5a06-106">MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5a06-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>  <span data-ttu-id="e5a06-107">Questo strumento non vengono migrati Skype per le riunioni Business nelle riunioni Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5a06-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="e5a06-108">**Requisiti**</span><span class="sxs-lookup"><span data-stu-id="e5a06-108">**Requirements**</span></span>
  
<span data-ttu-id="e5a06-109">MMS richiede che le caselle postali degli organizzatori delle riunioni siano su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5a06-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="e5a06-110">**Scenari primari**</span><span class="sxs-lookup"><span data-stu-id="e5a06-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="e5a06-111">MMS aggiorna le riunioni Skype per un utente nei due seguenti scenari primari:</span><span class="sxs-lookup"><span data-stu-id="e5a06-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="e5a06-112">Quando l'utente viene eseguita la migrazione da locale Skype per Business Server a Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="e5a06-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="e5a06-113">Quando un amministratore apporta una modifica per le impostazioni dell'utente audioconferenze con accesso esterno che richiedono l'aggiornamento delle informazioni di audioconferenza nelle riunioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5a06-113">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="e5a06-114">**Scenari comuni in cui non è possibile utilizzare il servizio MMS**</span><span class="sxs-lookup"><span data-stu-id="e5a06-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="e5a06-p103">Ecco sono alcuni scenari comuni che possono applicarsi alla situazione dell';utente. Questi sono tutti scenari supportati per la migrazione. Tuttavia, il servizio MMS non verrà eseguito in questi scenari e sarà invece necessario utilizzare lo strumento [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="e5a06-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="e5a06-118">Le cassette postali degli utenti sono in Exchange Server locale</span><span class="sxs-lookup"><span data-stu-id="e5a06-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="e5a06-119">Utilizzo di un provider di servizi di conferenza audio di terze parti</span><span class="sxs-lookup"><span data-stu-id="e5a06-119">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="e5a06-120">Migrazione degli utenti da Skype Business online per il Server locale Skype</span><span class="sxs-lookup"><span data-stu-id="e5a06-120">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="e5a06-121">Aggiornare le riunioni quando un utente locale viene migrato a Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e5a06-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="e5a06-122">Questo è lo scenario più comune in cui il servizio MMS può contribuire a creare una transizione agevole per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e5a06-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="e5a06-123">Quando un utente viene eseguita la migrazione da un Skype locale per il Server di Business per Skype Business online, MMS in grado di rilevare il nuovo utente e in grado di rilevare calendario dell'utente Skype per le riunioni aziendali e Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5a06-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="e5a06-124">Le riunioni future verranno aggiornati con le nuove informazioni per tale utente.</span><span class="sxs-lookup"><span data-stu-id="e5a06-124">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="e5a06-125">Se si utilizza attualmente 2015 Server Skype per le conferenze audio</span><span class="sxs-lookup"><span data-stu-id="e5a06-125">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="e5a06-126">Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:</span><span class="sxs-lookup"><span data-stu-id="e5a06-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="e5a06-127">Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e5a06-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="e5a06-128">Assegnare la licenza di **Audioconferenza** all'utente prima di eseguire il `Move-CSUser` cmdlet per eseguire la migrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e5a06-128">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="e5a06-129">Ciò avviene perché MMS aggiorna anche le riunioni quando si modificano le impostazioni di conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="e5a06-129">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="e5a06-130">Se non si assegna prima la licenza, il servizio MMS aggiornerà di nuovo tutte le riunioni quando si assegna la licenza.</span><span class="sxs-lookup"><span data-stu-id="e5a06-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="e5a06-131">Se si sta utilizzando un provider di servizi di audioconferenza telefonica audio (ACP) di terze parti</span><span class="sxs-lookup"><span data-stu-id="e5a06-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="e5a06-132">Con un'AUDIOCONFERENZA di terze parti o meno MMS esegue dipende dalle impostazioni di audioconferenze con accesso esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e5a06-132">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="e5a06-133">È possibile scegliere di sostituire automaticamente i numeri di accesso dai servizi di Audioconferenza quando un utente si assegna una licenza di **Conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="e5a06-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="e5a06-134">D';altra parte, potrebbe essere necessario evitare che ciò accada e mantenere i numeri di accesso esterno dal proprio ACP.</span><span class="sxs-lookup"><span data-stu-id="e5a06-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="e5a06-135">Per visualizzare l'impostazione dell'organizzazione, eseguire il seguente comando di Windows PowerShell e controllare il valore del parametro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="e5a06-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="e5a06-136">Se serve aiuto con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e5a06-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="e5a06-137">Se il valore di questo parametro è $true, MMS verrà eseguito quando un utente viene assegnata una licenza di **Conferenze Audio** e aggiornare le riunioni.</span><span class="sxs-lookup"><span data-stu-id="e5a06-137">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="e5a06-138">I numeri di accesso dai servizi di Audioconferenza vengono conservati fino a quando non viene assegnata alla licenza di **Conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="e5a06-138">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="e5a06-139">Se il valore di questo parametro è $false, MMS non aggiornare le riunioni anche se un utente viene assegnata una licenza di **Conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="e5a06-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="e5a06-140">I numeri di accesso dai servizi di Audioconferenza vengono conservati fino a quando l'utente manualmente il provisioning per l'audioconferenza in Skype per Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e5a06-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="e5a06-141">Aggiornamento delle riunioni quando modificano le impostazioni di conferenza audio di un utente</span><span class="sxs-lookup"><span data-stu-id="e5a06-141">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="e5a06-142">MMS per aggiornare un Skype esistente per le riunioni aziendali e Teams Microsoft nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5a06-142">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="e5a06-143">Quando si assegnare o rimuovere licenze **Audioconferenze** .</span><span class="sxs-lookup"><span data-stu-id="e5a06-143">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="e5a06-144">Quando si attiva o disattiva audioconferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="e5a06-144">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="e5a06-145">Quando si modifica o Reimposta l'ID conferenza per un utente configurato per utilizzare le riunioni pubbliche.</span><span class="sxs-lookup"><span data-stu-id="e5a06-145">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="e5a06-146">Quando l'utente si passa a un ponte per conferenze audio nuovo.</span><span class="sxs-lookup"><span data-stu-id="e5a06-146">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="e5a06-147">Quando un numero di telefono è assegnato a un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="e5a06-147">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="e5a06-148">Questo è uno scenario complesso che richiede passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e5a06-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="e5a06-149">Per ulteriori informazioni, vedere [modificare il numero a tariffa o numeri gratuito a pagamento il bridge di conferenze Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="e5a06-149">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e5a06-150">Il servizio MMS aggiorna le riunioni solo quando si utilizza il bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5a06-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="e5a06-151">Se si utilizza un provider di servizi di conferenza audio di terze parti, gli utenti saranno necessario aggiornare le riunioni manualmente.</span><span class="sxs-lookup"><span data-stu-id="e5a06-151">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="e5a06-152">In questo caso, è possibile utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="e5a06-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="e5a06-153">Non tutte le modifiche alle impostazioni di conferenza audio di un utente attivano MMS.</span><span class="sxs-lookup"><span data-stu-id="e5a06-153">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="e5a06-154">In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:</span><span class="sxs-lookup"><span data-stu-id="e5a06-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="e5a06-155">Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il loro nome utente SIP o il dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="e5a06-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="e5a06-156">Quando si cambia l';URL della riunione dell';organizzazione utilizzando il comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="e5a06-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="e5a06-157">Cosa succede quando il servizio MMS aggiorna le riunioni?</span><span class="sxs-lookup"><span data-stu-id="e5a06-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="e5a06-158">Quando il servizio MMS rileva che le riunioni di un utente devono essere aggiornate, procede come segue:</span><span class="sxs-lookup"><span data-stu-id="e5a06-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="e5a06-159">Identificare tutti Skype per le riunioni aziendali e Teams Microsoft, l'utente è pianificata in futuro</span><span class="sxs-lookup"><span data-stu-id="e5a06-159">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="e5a06-160">Qualsiasi Skype per le riunioni aziendali o Teams Microsoft che si sono verificati prima del quale viene eseguito MMS vengono ignorati</span><span class="sxs-lookup"><span data-stu-id="e5a06-160">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="e5a06-161">Vengono aggiornate solo le riunioni in cui l'utente è l'organizzatore</span><span class="sxs-lookup"><span data-stu-id="e5a06-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="e5a06-162">Sostituisce il blocco di informazioni sulla riunione online nei dettagli della riunione</span><span class="sxs-lookup"><span data-stu-id="e5a06-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="e5a06-163">Invia aggiornamenti a tutti i destinatari della riunione a nome dell'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="e5a06-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="e5a06-164">**Quanto tempo occorre per l';esecuzione del servizio MMS?**</span><span class="sxs-lookup"><span data-stu-id="e5a06-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="e5a06-165">Il periodo di tempo necessario a MMS eseguire la migrazione di riunioni varia in base al numero di utenti interessato e il numero totale di Skype per le riunioni aziendali o Microsoft Teams che ogni utente dispone sul proprio calendario.</span><span class="sxs-lookup"><span data-stu-id="e5a06-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="e5a06-166">Come minimo, occorreranno 10 minuti per l';esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5a06-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="e5a06-167">Alcune grandi migrazioni possono richiedere fino a 12 ore, ma la maggior parte delle migrazioni dovrebbe essere completata entro 1 ora.</span><span class="sxs-lookup"><span data-stu-id="e5a06-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="e5a06-168">**Limitazioni e potenziali problemi**</span><span class="sxs-lookup"><span data-stu-id="e5a06-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="e5a06-169">Viene eseguita la migrazione solo il Skype per Business o Microsoft Teams riunioni pianificate facendo clic sul pulsante **Aggiungi Skype riunione** in Outlook sul Web oppure utilizzando il componente aggiuntivo riunione Skype per Outlook.</span><span class="sxs-lookup"><span data-stu-id="e5a06-169">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="e5a06-170">In altre parole, se un utente copia e incolla le informazioni sulla riunione online Skype da una riunione a una nuova riunione, quella nuova riunione non sarà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="e5a06-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="e5a06-p114">Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="e5a06-p115">I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="e5a06-p116">Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="e5a06-179">Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.</span><span class="sxs-lookup"><span data-stu-id="e5a06-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="e5a06-180">Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="e5a06-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="e5a06-181">Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?</span><span class="sxs-lookup"><span data-stu-id="e5a06-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="e5a06-182">Proprio come lo Strumento di migrazione riunioni, MMS invia aggiornamenti sulle riunioni per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e5a06-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="e5a06-183">Pertanto, l'unica cosa che gli utenti vedranno sarà un altro giro notifiche di accettazione per le loro riunioni.</span><span class="sxs-lookup"><span data-stu-id="e5a06-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="e5a06-184">Potrebbe essere fuorviante per gli utenti, si consiglia di informare gli utenti in precedenza non solo quando si eseguirne la migrazione da locale a Skype Business online, ma anche quando si apportano modifiche di audioconferenza che venga attivato MMS.</span><span class="sxs-lookup"><span data-stu-id="e5a06-184">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="e5a06-185">Gestione del servizio MMS</span><span class="sxs-lookup"><span data-stu-id="e5a06-185">Managing MMS</span></span>

<span data-ttu-id="e5a06-p118">È necessario utilizzare Windows PowerShell per gestire il servizio MMS e controllare lo stato delle migrazioni in corso. Le informazioni in questa sezione danno per scontato che l';utente abbia familiarità con l';uso di PowerShell per gestire l';organizzazione di Skype for Business. Se non si ha dimestichezza con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="e5a06-189">Come si controlla lo stato della migrazione delle riunioni?</span><span class="sxs-lookup"><span data-stu-id="e5a06-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="e5a06-p119">Per controllare lo stato della migrazione delle riunioni è necessario usare il cmdlet  `Get-CsMeetingMigrationStatus`. Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="e5a06-192">Per ottenere un riepilogo di tutte le migrazioni MMS, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="e5a06-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="e5a06-193">Questo darà una rappresentazione tabulare di tutti gli stati di migrazione come questa:</span><span class="sxs-lookup"><span data-stu-id="e5a06-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="e5a06-194">Informazioni sullo stato UserCount--</span><span class="sxs-lookup"><span data-stu-id="e5a06-194">State UserCount---------------</span></span><br/> <span data-ttu-id="e5a06-195">21 in sospeso</span><span class="sxs-lookup"><span data-stu-id="e5a06-195">Pending 21</span></span><br/><span data-ttu-id="e5a06-196">6 in corso</span><span class="sxs-lookup"><span data-stu-id="e5a06-196">InProgress 6</span></span><br/> <span data-ttu-id="e5a06-197">2 non riuscito</span><span class="sxs-lookup"><span data-stu-id="e5a06-197">Failed 2</span></span> <br/> <span data-ttu-id="e5a06-198">131 completate</span><span class="sxs-lookup"><span data-stu-id="e5a06-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="e5a06-p120">Se si notano migrazioni non riuscite (stato Failed), intervenire per risolvere questi problemi il più presto possibile. Le persone non saranno in grado di utilizzare l';accesso esterno per le riunioni organizzate da quegli utenti fino a quando i problemi non saranno risolti. Vedere la sezione [Cosa devo fare se si verifica un errore?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) per maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="e5a06-p121">Per avere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, è possibile utilizzare i parametri  `StartTime` e `EndTime`. Ad esempio, il seguente comando restituirà tutti i dettagli su tutte le migrazioni che si sono verificati dal 1° ottobre 2016 al 8 ottobre 2016.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="e5a06-p122">Si consiglia inoltre di controllare lo stato della migrazione per un utente specifico, ed è possibile utilizzare il parametro  `UserId` per questo. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="e5a06-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="e5a06-206">Cosa devo fare se si verifica un errore?</span><span class="sxs-lookup"><span data-stu-id="e5a06-206">What do I do if there is an error?</span></span>
<span data-ttu-id="e5a06-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a06-207"></span></span>

<span data-ttu-id="e5a06-208">Quando si esegue il cmdlet  `Get-CsMeetingMigrationStatus` per ottenere una riepilogo e si nota che ci sono migrazioni in stato Operazione non riuscita le operazioni da eseguire sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5a06-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="e5a06-p123">Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:</span><span class="sxs-lookup"><span data-stu-id="e5a06-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="e5a06-211">Per ciascuno di questi utenti, eseguire lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047) per migrare manualmente le relative riunioni.</span><span class="sxs-lookup"><span data-stu-id="e5a06-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="e5a06-212">Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:</span><span class="sxs-lookup"><span data-stu-id="e5a06-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="e5a06-213">Fare creare agli utenti nuove riunioni Skype.</span><span class="sxs-lookup"><span data-stu-id="e5a06-213">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="e5a06-214">[Contattare l';assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="e5a06-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="e5a06-215">Attivazione e disattivazione del servizio MMS</span><span class="sxs-lookup"><span data-stu-id="e5a06-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="e5a06-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a06-216"></span></span>

<span data-ttu-id="e5a06-217">MMS è attivato per impostazione predefinita per tutte le organizzazioni, ma può essere disattivato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="e5a06-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="e5a06-218">Ad esempio, se si desidera eseguire manualmente la migrazione di tutte le riunioni o se si utilizza un provider di servizi di conferenza audio di terze parti, potrebbe non essere MMS in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5a06-218">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="e5a06-219">È inoltre possibile scegliere di disattivare temporaneamente MMS.</span><span class="sxs-lookup"><span data-stu-id="e5a06-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="e5a06-220">Ad esempio durante notevoli modifiche alle impostazioni di conferenza per l'organizzazione e non si desidera MMS eseguito finché non siano state completate tutte le modifiche.</span><span class="sxs-lookup"><span data-stu-id="e5a06-220">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="e5a06-p125">Per verificare se il servizio MMS è attivato nella propria organizzazione, eseguire il seguente comando e controllare il valore del parametro  `MeetingMigrationEnabled`. Se questo parametro è impostato su $true, il servizio MMS è abilitato.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="e5a06-223">Per disabilitare il servizio MMS, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5a06-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="e5a06-224">Per abilitare il servizio MMS, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5a06-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="e5a06-225">Abilitazione e disabilitazione MMS solo le modifiche di audioconferenze con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="e5a06-225">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="e5a06-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a06-226"></span></span>

<span data-ttu-id="e5a06-227">È inoltre possibile disattivare MMS solo le modifiche di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="e5a06-227">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="e5a06-228">Ancora verrà eseguita quando un utente viene eseguita la migrazione da Skype aziendali locali per Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="e5a06-228">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="e5a06-229">Per verificare lo stato corrente di MMS per gli aggiornamenti di audioconferenza, eseguire il seguente comando e verificare il valore per il `AutomaticallyMigrateUserMeetings` parametro.</span><span class="sxs-lookup"><span data-stu-id="e5a06-229">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="e5a06-230">Se questo parametro è impostato su$ true, MMS è impostato per gli aggiornamenti di riunioni utente quando si modificano le impostazioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e5a06-230">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="e5a06-231">Per disabilitare MMS per le conferenze audio, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5a06-231">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="e5a06-232">Per abilitare MMS per le conferenze audio, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e5a06-232">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="e5a06-233">Come si esegue manualmente la migrazione delle riunioni per un utente?</span><span class="sxs-lookup"><span data-stu-id="e5a06-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="e5a06-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a06-234"></span></span>

<span data-ttu-id="e5a06-235">Oltre alle migrazioni automatiche delle riunioni, è possibile anche eseguire la migrazione riunioni manualmente per un utente eseguendo il cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="e5a06-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="e5a06-236">Questo cmdlet consente di aggiungere l'utente nella coda di migrazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="e5a06-236">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="e5a06-237">Meeting Migration Service leggerà la richiesta dell';utente e migrerà le sue riunioni.</span><span class="sxs-lookup"><span data-stu-id="e5a06-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="e5a06-238">È possibile controllare lo stato della migrazione riunioni con il cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="e5a06-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="e5a06-239">Ecco un esempio che avvia la migrazione riunioni per l'utente ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="e5a06-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="e5a06-240">Uso di PowerShell per gestire l'organizzazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e5a06-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="e5a06-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="e5a06-241"></span></span>

 <span data-ttu-id="e5a06-242">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="e5a06-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="e5a06-243">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e5a06-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="e5a06-244">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e5a06-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="e5a06-p128">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="e5a06-p129">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="e5a06-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="e5a06-251">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5a06-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="e5a06-252">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e5a06-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="e5a06-253">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e5a06-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="e5a06-254">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="e5a06-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e5a06-255">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="e5a06-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="e5a06-256">Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5a06-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="e5a06-p130">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="e5a06-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e5a06-260">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5a06-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e5a06-261">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a06-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="e5a06-p131">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5a06-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="e5a06-264">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="e5a06-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="e5a06-265">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5a06-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e5a06-266">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e5a06-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="e5a06-267">See also</span><span class="sxs-lookup"><span data-stu-id="e5a06-267">Related topics</span></span>

[<span data-ttu-id="e5a06-268">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="e5a06-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
