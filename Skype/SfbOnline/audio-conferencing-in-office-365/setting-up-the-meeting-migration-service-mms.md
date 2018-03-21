---
title: Configurazione del servizio MMS (Meeting Migration Service)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
description: "Migrazione servizio MMS delle riunioni è Skype per servizio di Business che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft."
ms.openlocfilehash: 0ad7daac2a9edd8c548d97819435563a0643e74a
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="1000c-104">Configurazione del servizio MMS (Meeting Migration Service)</span><span class="sxs-lookup"><span data-stu-id="1000c-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="1000c-105">Migrazione servizio MMS delle riunioni è Skype per servizio di Business che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1000c-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users.</span></span> <span data-ttu-id="1000c-106">MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1000c-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>
  
 <span data-ttu-id="1000c-107">**Requisiti**</span><span class="sxs-lookup"><span data-stu-id="1000c-107">**Requirements**</span></span>
  
<span data-ttu-id="1000c-108">MMS richiede che le caselle postali degli organizzatori delle riunioni siano su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1000c-108">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="1000c-109">**Scenari primari**</span><span class="sxs-lookup"><span data-stu-id="1000c-109">**Primary scenarios**</span></span>
  
<span data-ttu-id="1000c-110">MMS aggiorna le riunioni Skype per un utente nei due seguenti scenari primari:</span><span class="sxs-lookup"><span data-stu-id="1000c-110">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="1000c-111">Quando l'utente viene eseguita la migrazione da locale Skype per Business Server a Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="1000c-111">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="1000c-112">Quando un amministratore apporta una modifica per le impostazioni dell'utente audioconferenze con accesso esterno che richiedono l'aggiornamento delle informazioni di audioconferenza nelle riunioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1000c-112">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="1000c-113">**Scenari comuni in cui non è possibile utilizzare il servizio MMS**</span><span class="sxs-lookup"><span data-stu-id="1000c-113">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="1000c-p103">Ecco sono alcuni scenari comuni che possono applicarsi alla situazione dell';utente. Questi sono tutti scenari supportati per la migrazione. Tuttavia, il servizio MMS non verrà eseguito in questi scenari e sarà invece necessario utilizzare lo strumento [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="1000c-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="1000c-117">Le cassette postali degli utenti sono in Exchange Server locale</span><span class="sxs-lookup"><span data-stu-id="1000c-117">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="1000c-118">Utilizzo di un provider di servizi di conferenza audio di terze parti</span><span class="sxs-lookup"><span data-stu-id="1000c-118">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="1000c-119">Migrazione degli utenti da Skype Business online per il Server locale Skype</span><span class="sxs-lookup"><span data-stu-id="1000c-119">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="1000c-120">Aggiornare le riunioni quando un utente locale viene migrato a Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1000c-120">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="1000c-121">Questo è lo scenario più comune in cui il servizio MMS può contribuire a creare una transizione agevole per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1000c-121">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="1000c-122">Quando un utente viene eseguita la migrazione da un Skype locale per il Server di Business per Skype Business online, MMS in grado di rilevare il nuovo utente e in grado di rilevare calendario dell'utente Skype per le riunioni aziendali e Teams Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1000c-122">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings.</span></span> <span data-ttu-id="1000c-123">Le riunioni future verranno aggiornati con le nuove informazioni per tale utente.</span><span class="sxs-lookup"><span data-stu-id="1000c-123">Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="1000c-124">Se si utilizza attualmente 2015 Server Skype per le conferenze audio</span><span class="sxs-lookup"><span data-stu-id="1000c-124">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="1000c-125">Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:</span><span class="sxs-lookup"><span data-stu-id="1000c-125">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="1000c-126">Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1000c-126">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="1000c-127">Assegnare la licenza di **Audioconferenza** all'utente prima di eseguire il `Move-CSUser` cmdlet per eseguire la migrazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1000c-127">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user.</span></span> <span data-ttu-id="1000c-128">Ciò avviene perché MMS aggiorna anche le riunioni quando si modificano le impostazioni di conferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="1000c-128">This is because MMS also updates meetings when audio conferencing settings are changed for a user.</span></span> <span data-ttu-id="1000c-129">Se non si assegna prima la licenza, il servizio MMS aggiornerà di nuovo tutte le riunioni quando si assegna la licenza.</span><span class="sxs-lookup"><span data-stu-id="1000c-129">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="1000c-130">Se si sta utilizzando un provider di servizi di audioconferenza telefonica audio (ACP) di terze parti</span><span class="sxs-lookup"><span data-stu-id="1000c-130">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="1000c-131">Con un'AUDIOCONFERENZA di terze parti o meno MMS esegue dipende dalle impostazioni di audioconferenze con accesso esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1000c-131">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings.</span></span> <span data-ttu-id="1000c-132">È possibile scegliere di sostituire automaticamente i numeri di accesso dai servizi di Audioconferenza quando un utente si assegna una licenza di **Conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="1000c-132">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license.</span></span> <span data-ttu-id="1000c-133">D';altra parte, potrebbe essere necessario evitare che ciò accada e mantenere i numeri di accesso esterno dal proprio ACP.</span><span class="sxs-lookup"><span data-stu-id="1000c-133">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="1000c-134">Per visualizzare l'impostazione dell'organizzazione, eseguire il seguente comando di Windows PowerShell e controllare il valore del parametro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="1000c-134">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="1000c-135">Se serve aiuto con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1000c-135">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="1000c-136">Se il valore di questo parametro è $true, MMS verrà eseguito quando un utente viene assegnata una licenza di **Conferenze Audio** e aggiornare le riunioni.</span><span class="sxs-lookup"><span data-stu-id="1000c-136">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings.</span></span> <span data-ttu-id="1000c-137">I numeri di accesso dai servizi di Audioconferenza vengono conservati fino a quando non viene assegnata alla licenza di **Conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="1000c-137">The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="1000c-138">Se il valore di questo parametro è $false, MMS non aggiornare le riunioni anche se un utente viene assegnata una licenza di **Conferenze Audio** .</span><span class="sxs-lookup"><span data-stu-id="1000c-138">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence.</span></span> <span data-ttu-id="1000c-139">I numeri di accesso dai servizi di Audioconferenza vengono conservati fino a quando l'utente manualmente il provisioning per l'audioconferenza in Skype per Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1000c-139">The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="1000c-140">Aggiornamento delle riunioni quando modificano le impostazioni di conferenza audio di un utente</span><span class="sxs-lookup"><span data-stu-id="1000c-140">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="1000c-141">MMS per aggiornare un Skype esistente per le riunioni aziendali e Teams Microsoft nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1000c-141">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="1000c-142">Quando si assegnare o rimuovere licenze **Audioconferenze** .</span><span class="sxs-lookup"><span data-stu-id="1000c-142">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="1000c-143">Quando si attiva o disattiva audioconferenze con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="1000c-143">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="1000c-144">Quando si modifica o Reimposta l'ID conferenza per un utente configurato per utilizzare le riunioni pubbliche.</span><span class="sxs-lookup"><span data-stu-id="1000c-144">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="1000c-145">Quando l'utente si passa a un ponte per conferenze audio nuovo.</span><span class="sxs-lookup"><span data-stu-id="1000c-145">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="1000c-146">Quando un numero di telefono è assegnato a un ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="1000c-146">When a phone number is unassigned from a audio conferencing bridge.</span></span> <span data-ttu-id="1000c-147">Questo è uno scenario complesso che richiede passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="1000c-147">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="1000c-148">Per ulteriori informazioni, vedere [modificare il numero a tariffa o numeri gratuito a pagamento il bridge di conferenze Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="1000c-148">For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1000c-149">Il servizio MMS aggiorna le riunioni solo quando si utilizza il bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1000c-149">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="1000c-150">Se si utilizza un provider di servizi di conferenza audio di terze parti, gli utenti saranno necessario aggiornare le riunioni manualmente.</span><span class="sxs-lookup"><span data-stu-id="1000c-150">If you are using a third-party audio conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="1000c-151">In questo caso, è possibile utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="1000c-151">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="1000c-152">Non tutte le modifiche alle impostazioni di conferenza audio di un utente attivano MMS.</span><span class="sxs-lookup"><span data-stu-id="1000c-152">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="1000c-153">In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:</span><span class="sxs-lookup"><span data-stu-id="1000c-153">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="1000c-154">Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il loro nome utente SIP o il dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="1000c-154">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="1000c-155">Quando si cambia l';URL della riunione dell';organizzazione utilizzando il comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="1000c-155">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="1000c-156">Cosa succede quando il servizio MMS aggiorna le riunioni?</span><span class="sxs-lookup"><span data-stu-id="1000c-156">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="1000c-157">Quando il servizio MMS rileva che le riunioni di un utente devono essere aggiornate, procede come segue:</span><span class="sxs-lookup"><span data-stu-id="1000c-157">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="1000c-158">Identificare tutti Skype per le riunioni aziendali e Teams Microsoft, l'utente è pianificata in futuro</span><span class="sxs-lookup"><span data-stu-id="1000c-158">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="1000c-159">Qualsiasi Skype per le riunioni aziendali o Teams Microsoft che si sono verificati prima del quale viene eseguito MMS vengono ignorati</span><span class="sxs-lookup"><span data-stu-id="1000c-159">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="1000c-160">Vengono aggiornate solo le riunioni in cui l'utente è l'organizzatore</span><span class="sxs-lookup"><span data-stu-id="1000c-160">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="1000c-161">Sostituisce il blocco di informazioni sulla riunione online nei dettagli della riunione</span><span class="sxs-lookup"><span data-stu-id="1000c-161">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="1000c-162">Invia aggiornamenti a tutti i destinatari della riunione a nome dell'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="1000c-162">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="1000c-163">**Quanto tempo occorre per l';esecuzione del servizio MMS?**</span><span class="sxs-lookup"><span data-stu-id="1000c-163">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="1000c-164">Il periodo di tempo necessario a MMS eseguire la migrazione di riunioni varia in base al numero di utenti interessato e il numero totale di Skype per le riunioni aziendali o Microsoft Teams che ogni utente dispone sul proprio calendario.</span><span class="sxs-lookup"><span data-stu-id="1000c-164">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar.</span></span> <span data-ttu-id="1000c-165">Come minimo, occorreranno 10 minuti per l';esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1000c-165">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="1000c-166">Alcune grandi migrazioni possono richiedere fino a 12 ore, ma la maggior parte delle migrazioni dovrebbe essere completata entro 1 ora.</span><span class="sxs-lookup"><span data-stu-id="1000c-166">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="1000c-167">**Limitazioni e potenziali problemi**</span><span class="sxs-lookup"><span data-stu-id="1000c-167">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="1000c-168">Viene eseguita la migrazione solo il Skype per Business o Microsoft Teams riunioni pianificate facendo clic sul pulsante **Aggiungi Skype riunione** in Outlook sul Web oppure utilizzando il componente aggiuntivo riunione Skype per Outlook.</span><span class="sxs-lookup"><span data-stu-id="1000c-168">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="1000c-169">In altre parole, se un utente copia e incolla le informazioni sulla riunione online Skype da una riunione a una nuova riunione, quella nuova riunione non sarà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="1000c-169">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="1000c-p114">Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.</span><span class="sxs-lookup"><span data-stu-id="1000c-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="1000c-p115">I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="1000c-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="1000c-p116">Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="1000c-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="1000c-178">Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.</span><span class="sxs-lookup"><span data-stu-id="1000c-178">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="1000c-179">Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="1000c-179">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="1000c-180">Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?</span><span class="sxs-lookup"><span data-stu-id="1000c-180">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="1000c-181">Proprio come lo Strumento di migrazione riunioni, MMS invia aggiornamenti sulle riunioni per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="1000c-181">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="1000c-182">Pertanto, l'unica cosa che gli utenti vedranno sarà un altro giro notifiche di accettazione per le loro riunioni.</span><span class="sxs-lookup"><span data-stu-id="1000c-182">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="1000c-183">Potrebbe essere fuorviante per gli utenti, si consiglia di informare gli utenti in precedenza non solo quando si eseguirne la migrazione da locale a Skype Business online, ma anche quando si apportano modifiche di audioconferenza che venga attivato MMS.</span><span class="sxs-lookup"><span data-stu-id="1000c-183">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="1000c-184">Gestione del servizio MMS</span><span class="sxs-lookup"><span data-stu-id="1000c-184">Managing MMS</span></span>

<span data-ttu-id="1000c-p118">È necessario utilizzare Windows PowerShell per gestire il servizio MMS e controllare lo stato delle migrazioni in corso. Le informazioni in questa sezione danno per scontato che l';utente abbia familiarità con l';uso di PowerShell per gestire l';organizzazione di Skype for Business. Se non si ha dimestichezza con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1000c-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="1000c-188">Come si controlla lo stato della migrazione delle riunioni?</span><span class="sxs-lookup"><span data-stu-id="1000c-188">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="1000c-p119">Per controllare lo stato della migrazione delle riunioni è necessario usare il cmdlet  `Get-CsMeetingMigrationStatus`. Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="1000c-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="1000c-191">Per ottenere un riepilogo di tutte le migrazioni MMS, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="1000c-191">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="1000c-192">Questo darà una rappresentazione tabulare di tutti gli stati di migrazione come questa:</span><span class="sxs-lookup"><span data-stu-id="1000c-192">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="1000c-193">Informazioni sullo stato UserCount--</span><span class="sxs-lookup"><span data-stu-id="1000c-193">State UserCount---------------</span></span><br/> <span data-ttu-id="1000c-194">21 in sospeso</span><span class="sxs-lookup"><span data-stu-id="1000c-194">Pending 21</span></span><br/><span data-ttu-id="1000c-195">6 in corso</span><span class="sxs-lookup"><span data-stu-id="1000c-195">InProgress 6</span></span><br/> <span data-ttu-id="1000c-196">2 non riuscito</span><span class="sxs-lookup"><span data-stu-id="1000c-196">Failed 2</span></span> <br/> <span data-ttu-id="1000c-197">131 completate</span><span class="sxs-lookup"><span data-stu-id="1000c-197">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1000c-p120">Se si notano migrazioni non riuscite (stato Failed), intervenire per risolvere questi problemi il più presto possibile. Le persone non saranno in grado di utilizzare l';accesso esterno per le riunioni organizzate da quegli utenti fino a quando i problemi non saranno risolti. Vedere la sezione [Cosa devo fare se si verifica un errore?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) per maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="1000c-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="1000c-p121">Per avere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, è possibile utilizzare i parametri  `StartTime` e `EndTime`. Ad esempio, il seguente comando restituirà tutti i dettagli su tutte le migrazioni che si sono verificati dal 1° ottobre 2016 al 8 ottobre 2016.</span><span class="sxs-lookup"><span data-stu-id="1000c-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="1000c-p122">Si consiglia inoltre di controllare lo stato della migrazione per un utente specifico, ed è possibile utilizzare il parametro  `UserId` per questo. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="1000c-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="1000c-205">Cosa devo fare se si verifica un errore?</span><span class="sxs-lookup"><span data-stu-id="1000c-205">What do I do if there is an error?</span></span>
<span data-ttu-id="1000c-206"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="1000c-206"></span></span>

<span data-ttu-id="1000c-207">Quando si esegue il cmdlet  `Get-CsMeetingMigrationStatus` per ottenere una riepilogo e si nota che ci sono migrazioni in stato Operazione non riuscita le operazioni da eseguire sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1000c-207">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="1000c-p123">Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:</span><span class="sxs-lookup"><span data-stu-id="1000c-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="1000c-210">Per ciascuno di questi utenti, eseguire lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047) per migrare manualmente le relative riunioni.</span><span class="sxs-lookup"><span data-stu-id="1000c-210">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="1000c-211">Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:</span><span class="sxs-lookup"><span data-stu-id="1000c-211">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="1000c-212">Fare creare agli utenti nuove riunioni Skype.</span><span class="sxs-lookup"><span data-stu-id="1000c-212">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="1000c-213">[Contattare l';assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="1000c-213">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="1000c-214">Attivazione e disattivazione del servizio MMS</span><span class="sxs-lookup"><span data-stu-id="1000c-214">Enabling and disabling MMS</span></span>
<span data-ttu-id="1000c-215"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="1000c-215"></span></span>

<span data-ttu-id="1000c-216">MMS è attivato per impostazione predefinita per tutte le organizzazioni, ma può essere disattivato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="1000c-216">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="1000c-217">Ad esempio, se si desidera eseguire manualmente la migrazione di tutte le riunioni o se si utilizza un provider di servizi di conferenza audio di terze parti, potrebbe non essere MMS in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1000c-217">For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="1000c-218">È inoltre possibile scegliere di disattivare temporaneamente MMS.</span><span class="sxs-lookup"><span data-stu-id="1000c-218">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="1000c-219">Ad esempio durante notevoli modifiche alle impostazioni di conferenza per l'organizzazione e non si desidera MMS eseguito finché non siano state completate tutte le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1000c-219">For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="1000c-p125">Per verificare se il servizio MMS è attivato nella propria organizzazione, eseguire il seguente comando e controllare il valore del parametro  `MeetingMigrationEnabled`. Se questo parametro è impostato su $true, il servizio MMS è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1000c-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="1000c-222">Per disabilitare il servizio MMS, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1000c-222">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="1000c-223">Per abilitare il servizio MMS, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1000c-223">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="1000c-224">Abilitazione e disabilitazione MMS solo le modifiche di audioconferenze con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="1000c-224">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="1000c-225"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="1000c-225"></span></span>

<span data-ttu-id="1000c-226">È inoltre possibile disattivare MMS solo le modifiche di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="1000c-226">You can also disable MMS only for audio conferencing changes.</span></span> <span data-ttu-id="1000c-227">Ancora verrà eseguita quando un utente viene eseguita la migrazione da Skype aziendali locali per Skype Business online.</span><span class="sxs-lookup"><span data-stu-id="1000c-227">It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online.</span></span> <span data-ttu-id="1000c-228">Per verificare lo stato corrente di MMS per gli aggiornamenti di audioconferenza, eseguire il seguente comando e verificare il valore per il `AutomaticallyMigrateUserMeetings` parametro.</span><span class="sxs-lookup"><span data-stu-id="1000c-228">To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="1000c-229">Se questo parametro è impostato su$ true, MMS è impostato per gli aggiornamenti di riunioni utente quando si modificano le impostazioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="1000c-229">If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="1000c-230">Per disabilitare MMS per le conferenze audio, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1000c-230">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="1000c-231">Per abilitare MMS per le conferenze audio, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1000c-231">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="1000c-232">Come si esegue manualmente la migrazione delle riunioni per un utente?</span><span class="sxs-lookup"><span data-stu-id="1000c-232">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="1000c-233"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="1000c-233"></span></span>

<span data-ttu-id="1000c-234">Oltre alle migrazioni automatiche delle riunioni, è possibile anche eseguire la migrazione riunioni manualmente per un utente eseguendo il cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="1000c-234">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="1000c-235">Questo cmdlet consente di aggiungere l'utente nella coda di migrazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="1000c-235">This cmdlet adds the user in meeting migration queue.</span></span> <span data-ttu-id="1000c-236">Meeting Migration Service leggerà la richiesta dell';utente e migrerà le sue riunioni.</span><span class="sxs-lookup"><span data-stu-id="1000c-236">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="1000c-237">È possibile controllare lo stato della migrazione riunioni con il cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="1000c-237">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="1000c-238">Ecco un esempio che avvia la migrazione riunioni per l'utente ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="1000c-238">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="1000c-239">Uso di PowerShell per gestire l'organizzazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1000c-239">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="1000c-240"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="1000c-240"></span></span>

 <span data-ttu-id="1000c-241">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="1000c-241">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="1000c-242">A questo scopo: Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1000c-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1000c-243">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1000c-243">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="1000c-p128">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="1000c-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="1000c-p129">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="1000c-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="1000c-250">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="1000c-250">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="1000c-251">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1000c-251">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="1000c-252">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1000c-252">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1000c-253">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="1000c-253">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1000c-254">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="1000c-254">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="1000c-255">Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1000c-255">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="1000c-p130">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="1000c-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1000c-259">Introduzione a Windows PowerShell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1000c-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1000c-260">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="1000c-260">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1000c-p131">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1000c-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1000c-263">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="1000c-263">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1000c-264">Usare Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1000c-264">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1000c-265">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1000c-265">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1000c-266">See also</span><span class="sxs-lookup"><span data-stu-id="1000c-266">Related topics</span></span>

[<span data-ttu-id="1000c-267">Servizi di conferenza telefonica con accesso esterno in Office 365</span><span class="sxs-lookup"><span data-stu-id="1000c-267">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
