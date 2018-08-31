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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) è un servizio di Skype for Business eseguito in background che aggiorna automaticamente le riunioni di Skype for Business e Microsoft Teams per gli utenti. MMS è progettato per eliminare la necessità di avviare lo Strumento di migrazione riunioni per aggiornare le riunioni di Skype for Business e Microsoft Teams.
ms.openlocfilehash: 013e68ada16f15b3a410823680ec062b9fb7fa3a
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780502"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="3d0b6-104">Configurazione del servizio MMS (Meeting Migration Service)</span><span class="sxs-lookup"><span data-stu-id="3d0b6-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="3d0b6-105">Meeting Migration Service (MMS) è un servizio di Skype for Business eseguito in background che aggiorna automaticamente le riunioni di Skype for Business e Microsoft Teams per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-105">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype meetings for users.</span></span> <span data-ttu-id="3d0b6-106">MMS è progettato per eliminare la necessità di avviare lo Strumento di migrazione riunioni per aggiornare le riunioni di Skype for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-106">MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype meetings.</span></span>  <span data-ttu-id="3d0b6-107">Questo strumento non esegue la migrazione delle riunioni di Skype for Business in quelle di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-107">This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.</span></span>  
  
 <span data-ttu-id="3d0b6-108">**Requisiti**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-108">**Requirements**</span></span>
  
<span data-ttu-id="3d0b6-109">MMS richiede che le caselle postali degli organizzatori delle riunioni siano su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-109">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="3d0b6-110">**Scenari primari**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-110">**Primary scenarios**</span></span>
  
<span data-ttu-id="3d0b6-111">MMS aggiorna le riunioni Skype per un utente nei due seguenti scenari primari:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-111">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="3d0b6-112">Quando l'utente viene migrato da Skype for Business Server locale a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-112">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online</span></span>
    
- <span data-ttu-id="3d0b6-113">Quando un amministratore apporta una modifica alle impostazioni di audioconferenza dell'utente che richiederebbe l'aggiornamento delle informazioni di audioconferenza nelle riunioni di questo utente.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-113">When an admin makes a change to the user's dial-in conferencing settings that would require updating the dial-in conferencing information in that user's meetings</span></span>
    
 <span data-ttu-id="3d0b6-114">**Scenari comuni in cui non è possibile utilizzare il servizio MMS**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-114">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="3d0b6-p103">Ecco alcuni scenari comuni che potrebbero essere applicabili all'utente. Questi sono tutti scenari supportati per la migrazione. Tuttavia, il servizio MMS non verrà eseguito in questi scenari e sarà invece necessario utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="3d0b6-118">Le cassette postali degli utenti sono in Exchange Server locale</span><span class="sxs-lookup"><span data-stu-id="3d0b6-118">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="3d0b6-119">Utilizzo di un provider di servizi di audioconferenza di terze parti</span><span class="sxs-lookup"><span data-stu-id="3d0b6-119">Using a third-party dial-in conferencing provider</span></span>
    
- <span data-ttu-id="3d0b6-120">Migrazione di utenti da Skype for Business online a Skype for Business Server locale</span><span class="sxs-lookup"><span data-stu-id="3d0b6-120">Migrating users from Skype for Business online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="3d0b6-121">Aggiornamento delle riunioni quando un utente locale viene migrato a Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3d0b6-121">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="3d0b6-122">Questo è lo scenario più comune in cui il servizio MMS può contribuire a creare una transizione agevole per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-122">This is the most common scenario where MMS can help create a smoother transition for your users.</span></span> <span data-ttu-id="3d0b6-123">Quando l'utente viene migrato da Skype for Business Server locale a Skype for Business online, il servizio MMS rileva il nuovo utente e analizza il calendario di quell'utente alla ricerca di riunioni di Skype for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-123">When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype meetings.</span></span> <span data-ttu-id="3d0b6-124">Tutte le future riunioni saranno aggiornate con le nuove informazioni per l'utente.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-124">Any future Skype meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="3d0b6-125">Se si sta attualmente utilizzando Skype Server 2015 per le audioconferenze</span><span class="sxs-lookup"><span data-stu-id="3d0b6-125">If you're currently using Skype Server 2015 for dial-in conferencing</span></span>

<span data-ttu-id="3d0b6-126">Si consiglia di seguire le migliori pratiche riportate di seguito per la migliore esperienza con MMS in questo scenario:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-126">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="3d0b6-127">Dato che MMS richiede che la posta dell'utente sia su Exchange Online, se si esegue la migrazione anche da Exchange Server locale, spostare prima la posta dell'utente su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-127">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="3d0b6-128">Assegnare la licenza di **Audioconferenza** all'utente prima di eseguire il `Move-CSUser` cmdlet per migrare l'utente.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-128">Assign the PSTN Conferencing license to the user before you run the   cmdlet to migrate the user.</span></span> <span data-ttu-id="3d0b6-129">Questo perché MMS aggiorna anche le riunioni quando vengono modificate le impostazioni di audioconferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-129">This is because MMS also updates meetings when dial-in conferencing settings are changed for a user.</span></span> <span data-ttu-id="3d0b6-130">Se non si assegna prima la licenza, il servizio MMS aggiornerà di nuovo tutte le riunioni quando si assegna la licenza.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-130">If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="3d0b6-131">Se si sta utilizzando un provider di servizi di audioconferenza (ACP) di terze parti</span><span class="sxs-lookup"><span data-stu-id="3d0b6-131">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="3d0b6-132">Con un ACP di terze parti, il fatto che venga eseguito o meno il servizio MMS dipende dalle impostazioni di audioconferenza dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-132">With a third-party ACP, whether or not MMS runs depends on your organization's dial-in conferencing settings.</span></span> <span data-ttu-id="3d0b6-133">È possibile scegliere di sostituire automaticamente i numeri di accesso esterno dal proprio ACP quando si assegna a un utente una licenza di **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-133">You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a PSTN Conferencing license.</span></span> <span data-ttu-id="3d0b6-134">D'altra parte, potrebbe essere necessario evitare che ciò accada e mantenere i numeri di accesso esterno dal proprio ACP.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-134">On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP.</span></span> <span data-ttu-id="3d0b6-135">Per consultare l'impostazione della propria organizzazione, eseguire il seguente comando di Windows PowerShell e controllare il valore del parametro `AutomaticallyReplaceAcpProvider`.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-135">To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter  `AutomaticallyReplaceAcpProvider`.</span></span> <span data-ttu-id="3d0b6-136">Se serve aiuto con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-136">If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="3d0b6-137">Se il valore di questo parametro è $true, il servizio MMS verrà eseguito quando un utente riceve una licenza di **Audioconferenza** e aggiorna le proprie riunioni.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-137">If the value of this parameter is $true, then MMS will run when a user is assigned a PSTN Conferencing license and update their meetings.</span></span> <span data-ttu-id="3d0b6-138">I numeri di accesso esterno dal proprio ACP vengono mantenuti finché non viene assegnata la licenza di **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-138">The dial-in numbers from your ACP are retained until the PSTN Conferencing license is assigned.</span></span>
    
- <span data-ttu-id="3d0b6-139">Se il valore di questo parametro è $false, il servizio MMS non aggiornerà le riunioni anche se un utente riceve una licenza di **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-139">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a PSTN Conferencing licence.</span></span> <span data-ttu-id="3d0b6-140">I numeri di accesso esterno dal proprio ACP vengono mantenuti finché l'utente non viene configurato manualmente per l'audioconferenza nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-140">The dial-in numbers from your ACP are retained until the user is manually provisioned for dial-in conferencing in Skype admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="3d0b6-141">Aggiornamento delle riunioni quando si modificano le impostazioni di audioconferenza di un utente</span><span class="sxs-lookup"><span data-stu-id="3d0b6-141">Updating meetings when a user's dial-in conferencing settings change</span></span>

<span data-ttu-id="3d0b6-142">MMS aggiornerà le riunioni esistenti di Skype for Business e Microsoft Teams nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-142">MMS will update an existing Skype for Business online user's meetings in the following cases:</span></span>
  
- <span data-ttu-id="3d0b6-143">Quando si assegna o si rimuove la licenza di **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-143">When you assign or remove PSTN Conferencing license</span></span>
    
- <span data-ttu-id="3d0b6-144">Quando si attiva o si disattiva l'audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-144">When you enable or disable dial-in conferencing</span></span>
    
- <span data-ttu-id="3d0b6-145">Quando si modifica o si reimposta l'ID conferenza per un utente configurato per l'uso di riunioni pubbliche.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-145">When you change or reset the Conference ID for a user configured to use public meetings</span></span>
    
- <span data-ttu-id="3d0b6-146">Quando si trasferisce l'utente a un nuovo bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-146">When you move the user to a new dial-in conferencing bridge</span></span>
    
- <span data-ttu-id="3d0b6-147">Quando un numero di telefono non è impostato in un bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-147">When a phone number is unassigned from a dial-in conferencing bridge.</span></span> <span data-ttu-id="3d0b6-148">Questo è uno scenario complesso che richiede passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-148">This is a complex scenario which requires additional steps.</span></span> <span data-ttu-id="3d0b6-149">Per maggiori informazioni, vedere [Modifica i numeri a tariffa o i numeri verdi del bridge di audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-149">For more information, see [Change the toll or toll-free numbers on your dial-in conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3d0b6-150">Il servizio MMS aggiorna le riunioni solo quando si utilizza il bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-150">MMS only updates meetings when you're using the Microsoft bridge.</span></span> <span data-ttu-id="3d0b6-151">Se si utilizza un provider di servizi di audioconferenza di terze parti, gli utenti dovranno aggiornare le riunioni manualmente.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-151">If you are using a third-party dial-in conferencing provider, the users will need to update their meetings manually.</span></span> <span data-ttu-id="3d0b6-152">In questo caso, è possibile utilizzare lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-152">In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="3d0b6-153">Non tutte le modifiche alle impostazioni di audioconferenza di un utente attivano il servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-153">Not all changes to a user's dial-in conferencing settings trigger MMS.</span></span> <span data-ttu-id="3d0b6-154">In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-154">Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="3d0b6-155">Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)</span><span class="sxs-lookup"><span data-stu-id="3d0b6-155">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="3d0b6-156">Quando si cambia l'URL della riunione dell'organizzazione utilizzando il comando [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-156">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="3d0b6-157">Cosa succede quando il servizio MMS aggiorna le riunioni?</span><span class="sxs-lookup"><span data-stu-id="3d0b6-157">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="3d0b6-158">Quando rileva che le riunioni di un utente devono essere aggiornate, il servizio MMS procede come segue:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-158">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="3d0b6-159">Identifica tutte le riunioni di Skype for Business e Microsoft Teams che l'utente ha in programma in futuro</span><span class="sxs-lookup"><span data-stu-id="3d0b6-159">Identify all Skype meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="3d0b6-160">Eventuali riunioni di Skype for Business o Microsoft Teams che sono avvenute prima dell'esecuzione del servizio MMS vengono tralasciate</span><span class="sxs-lookup"><span data-stu-id="3d0b6-160">Any Skype meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="3d0b6-161">Vengono aggiornate solo le riunioni in cui l'utente è l'organizzatore</span><span class="sxs-lookup"><span data-stu-id="3d0b6-161">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="3d0b6-162">Sostituisce il blocco di informazioni sulla riunione online nei dettagli della riunione</span><span class="sxs-lookup"><span data-stu-id="3d0b6-162">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="3d0b6-163">Invia aggiornamenti a tutti i destinatari della riunione a nome dell'organizzatore della riunione</span><span class="sxs-lookup"><span data-stu-id="3d0b6-163">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="3d0b6-164">**Quanto tempo occorre per l'esecuzione del servizio MMS?**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-164">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="3d0b6-165">La quantità di tempo necessaria al servizio MMS per la migrazione delle riunioni varia a seconda di quanti utenti sono interessati e del numero totale di riunioni di Skype for Business o Microsoft Teams che ogni utente ha sul proprio calendario.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-165">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype meetings each user has on their calendar.</span></span> <span data-ttu-id="3d0b6-166">Come minimo, occorreranno 10 minuti per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-166">At a minimum, it will take 10 minutes to run.</span></span> <span data-ttu-id="3d0b6-167">Alcune grandi migrazioni possono richiedere fino a 12 ore, ma la maggior parte delle migrazioni dovrebbe essere completata entro 1 ora.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-167">While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="3d0b6-168">**Limitazioni e potenziali problemi**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-168">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="3d0b6-169">Facendo clic sul pulsante **Aggiungi riunione Skype** in Outlook sul web o utilizzando il componente aggiuntivo Riunione Skype per Outlook vengono migrate solo le riunioni di Skype for Business o Microsoft Teams pianificate.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-169">Only the Skype meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="3d0b6-170">In altre parole, se un utente copia e incolla le informazioni sulla riunione online Skype da una riunione a una nuova riunione, quella nuova riunione non sarà aggiornata.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-170">In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="3d0b6-p114">Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="3d0b6-p115">I contenuti della riunione creati o allegati alla riunione (lavagne, sondaggi e così via) non saranno mantenuti dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="3d0b6-p116">Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note di riunione effettive memorizzate in OneNote saranno ancora presenti, solo il collegamento alle note condivise viene sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="3d0b6-179">Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-179">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="3d0b6-180">Alcuni caratteri UNICODE nel corpo dell';invito possono essere aggiornati in modo non corretto e modificati in uno dei seguenti caratteri speciali: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-180">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="3d0b6-181">Cosa vedranno gli utenti quando il servizio MMS aggiorna le loro riunioni?</span><span class="sxs-lookup"><span data-stu-id="3d0b6-181">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="3d0b6-182">Proprio come lo Strumento di migrazione riunioni, MMS invia aggiornamenti sulle riunioni per conto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-182">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users.</span></span> <span data-ttu-id="3d0b6-183">Pertanto, l'unica cosa che gli utenti vedranno sarà un altro giro di notifiche di accettazione delle loro riunioni.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-183">Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings.</span></span> <span data-ttu-id="3d0b6-184">Questo potrebbe essere fonte di confusione per gli utenti, perciò si consiglia di informare gli utenti in anticipo non solo per la migrazione da Skype for Business locale a Skype for Business online, ma anche quando si effettua una modifica all'audioconferenza che attiverà il servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-184">This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make dial-in conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="3d0b6-185">Gestione del servizio MMS</span><span class="sxs-lookup"><span data-stu-id="3d0b6-185">Managing MMS</span></span>

<span data-ttu-id="3d0b6-186">È necessario utilizzare Windows PowerShell per gestire il servizio MMS e controllare lo stato delle migrazioni in corso.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-186">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations.</span></span> <span data-ttu-id="3d0b6-187">Le informazioni in questa sezione presuppongono che l'utente abbia familiarità con l'uso di PowerShell per gestire l'organizzazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-187">The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization.</span></span> <span data-ttu-id="3d0b6-188">Se non si ha dimestichezza con PowerShell, vedere la sezione [Uso di PowerShell per gestire l'organizzazione di Skype for Business](setting-up-the-meeting-migration-service-mms.md#WPSInfo) al termine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-188">If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="3d0b6-189">Procedure relative al controllo dello stato della migrazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="3d0b6-189">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="3d0b6-p119">Per controllare lo stato della migrazione delle riunioni è necessario usare il cmdlet  `Get-CsMeetingMigrationStatus`. Di seguito sono riportati alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="3d0b6-192">Per ottenere un riepilogo di tutte le migrazioni MMS, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-192">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="3d0b6-193">Questo mostrerà una rappresentazione tabulare di tutti gli stati di migrazione come questa:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-193">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="3d0b6-194">Stato UserCount---------------</span><span class="sxs-lookup"><span data-stu-id="3d0b6-194">State UserCount---------------</span></span><br/> <span data-ttu-id="3d0b6-195">21 in sospeso</span><span class="sxs-lookup"><span data-stu-id="3d0b6-195">Pending 21</span></span><br/><span data-ttu-id="3d0b6-196">6 in corso</span><span class="sxs-lookup"><span data-stu-id="3d0b6-196">InProgress 6</span></span><br/> <span data-ttu-id="3d0b6-197">2 non riuscito</span><span class="sxs-lookup"><span data-stu-id="3d0b6-197">Failed 2</span></span> <br/> <span data-ttu-id="3d0b6-198">131 completato</span><span class="sxs-lookup"><span data-stu-id="3d0b6-198">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3d0b6-p120">Se si notano migrazioni non riuscite (stato Failed), intervenire per risolvere questi problemi il più presto possibile. Le persone non saranno in grado di utilizzare l'accesso esterno per le riunioni organizzate da quegli utenti fino a quando i problemi non saranno risolti. Vedere la sezione [Cosa devo fare se si verifica un errore?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) per maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="3d0b6-p121">Per avere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, è possibile utilizzare i parametri  `StartTime` e `EndTime`. Ad esempio, il seguente comando restituirà tutti i dettagli su tutte le migrazioni che si sono verificate dal 1° ottobre 2016 all'8 ottobre 2016.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="3d0b6-p122">Si consiglia inoltre di controllare lo stato della migrazione per un utente specifico, ed è possibile utilizzare il parametro  `UserId` per questo. Ad esempio, il seguente comando restituirà lo stato dell'utente ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="3d0b6-206">Cosa devo fare se si verifica un errore?</span><span class="sxs-lookup"><span data-stu-id="3d0b6-206">What do I do if there is an error?</span></span>
<span data-ttu-id="3d0b6-207"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0b6-207"></span></span>

<span data-ttu-id="3d0b6-208">Quando si esegue il cmdlet  `Get-CsMeetingMigrationStatus` per ottenere una visualizzazione Riepilogo e si nota che ci sono migrazioni in stato "non riuscito" le operazioni da eseguire sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-208">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="3d0b6-p123">Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l'elenco degli utenti interessati e l'errore specifico che è stato segnalato:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="3d0b6-211">Per ciascuno di questi utenti, eseguire lo [Strumento di migrazione riunioni](https://go.microsoft.com/fwlink/p/?linkid=626047) per migrare manualmente le relative riunioni.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-211">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="3d0b6-212">Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="3d0b6-213">Far creare agli utenti nuove riunioni Skype.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-213">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="3d0b6-214">[Contattare l'assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="3d0b6-215">Attivazione e disattivazione del servizio MMS</span><span class="sxs-lookup"><span data-stu-id="3d0b6-215">Enabling and disabling MMS</span></span>
<span data-ttu-id="3d0b6-216"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0b6-216"></span></span>

<span data-ttu-id="3d0b6-217">MMS è attivato per impostazione predefinita per tutte le organizzazioni, ma può essere disattivato, se necessario.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-217">MMS is enabled by default for all organizations, but it can be disabled as needed.</span></span> <span data-ttu-id="3d0b6-218">Ad esempio, se si desidera migrare manualmente tutte le riunioni o se si utilizza un provider di servizi di audioconferenza di terze parti, potrebbe non essere necessario eseguire il servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-218">For example, if you want to manually migrate all meetings or if you use a third-party dial-in conferencing provider, you may not need MMS running.</span></span> <span data-ttu-id="3d0b6-219">È inoltre possibile scegliere di disattivare temporaneamente il servizio MMS.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-219">You may also choose to temporarily disable MMS.</span></span> <span data-ttu-id="3d0b6-220">Ad esempio, possono essere in corso modifiche sostanziali alle impostazioni di audioconferenza per l'organizzazione e non si desidera che MMS venga eseguito fino a quando sono state completate tutte.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-220">For example, you may be doing substantial changes to the dial-in conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="3d0b6-p125">Per verificare se il servizio MMS è attivato nella propria organizzazione, eseguire il seguente comando e controllare il valore del parametro  `MeetingMigrationEnabled`. Se questo parametro è impostato su $true, il servizio MMS è abilitato.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="3d0b6-223">Per disabilitare il servizio MMS, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-223">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="3d0b6-224">Per abilitare il servizio MMS, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-224">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="3d0b6-225">Abilitazione e disabilitazione del servizio MMS solo per le modifiche relative all'audioconferenza</span><span class="sxs-lookup"><span data-stu-id="3d0b6-225">Enabling and disabling MMS only for dial-in conferencing changes</span></span>
<span data-ttu-id="3d0b6-226"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0b6-226"></span></span>

<span data-ttu-id="3d0b6-227">È anche possibile disattivare il servizio MMS solo le modifiche relative all'audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-227">You can also disable MMS only for dial-in conferencing changes.</span></span> <span data-ttu-id="3d0b6-228">Il servizio verrà comunque eseguito quando l'utente viene migrato da Skype for Business Server locale a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-228">It will still run when a user is migrated from Skype on-premises to Skype for Business Online.</span></span> <span data-ttu-id="3d0b6-229">Per verificare lo stato attuale del servizio MMS per gli aggiornamenti relativi all'audioconferenza, eseguire il seguente comando e controllare il valore del parametro `AutomaticallyMigrateUserMeetings`.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-229">To check the current MMS status for dial-in conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter.</span></span> <span data-ttu-id="3d0b6-230">Se questo parametro è impostato su $true, il servizio MMS è impostato per aggiornare le riunioni degli utenti quando vengono modificate le impostazioni di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-230">If this parameter is set to$true, MMS is set to update user meetings when dial-in conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="3d0b6-231">Per disabilitare il servizio MMS per l'audioconferenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-231">To disable MMS for dial-in conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="3d0b6-232">Per abilitare il servizio MMS per l'audioconferenza, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-232">To enable MMS for dial-in conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="3d0b6-233">Procedure relative all'esecuzione manuale della migrazione delle riunioni per un utente</span><span class="sxs-lookup"><span data-stu-id="3d0b6-233">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="3d0b6-234"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0b6-234"></span></span>

<span data-ttu-id="3d0b6-235">Oltre alle migrazioni automatiche delle riunioni, è anche possibile effettuare manualmente la migrazione delle riunioni per un utente eseguendo il cmdlet **Start-CsExMeetingMigration**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-235">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**.</span></span> <span data-ttu-id="3d0b6-236">Questo cmdlet consente di aggiungere l'utente nella coda di migrazione delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-236">This cmdlet addsthe user in meeting migration queue.</span></span> <span data-ttu-id="3d0b6-237">Meeting Migration Service leggerà la richiesta dell'utente e migrerà le sue riunioni.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-237">Meeting Migration Service will read the user request and migrate their meetings.</span></span> <span data-ttu-id="3d0b6-238">È possibile controllare lo stato della migrazione riunioni con il cmdlet **Get-CsMeetingMigrationStatus**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-238">You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="3d0b6-239">Ecco un esempio che avvia la migrazione riunioni per l'utente ashaw@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-239">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="3d0b6-240">Uso di PowerShell per gestire l'organizzazione di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d0b6-240">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="3d0b6-241"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="3d0b6-241"></span></span>

 <span data-ttu-id="3d0b6-242">**Verificare che sia in esecuzione Windows PowerShell 3.0 o versioni successive**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-242">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="3d0b6-243">A questo scopo, fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-243">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3d0b6-244">Controllare la versione digitando  _Get-Host_ nella finestra di **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-244">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="3d0b6-p128">Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="3d0b6-p129">Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="3d0b6-251">Per altre informazioni, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-251">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="3d0b6-252">**Avviare una sessione di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3d0b6-252">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="3d0b6-253">Fare clic sul pulsante **Start** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-253">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3d0b6-254">Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-254">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3d0b6-255">Il comando **Import-Module** va eseguito solo la prima volta che si usa il modulo Windows PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3d0b6-255">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="3d0b6-256">Per altre informazioni sull'avvio di Windows PowerShell, vedere [Connettersi a tutti i servizi di Office 365 in un'unica finestra di Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o[Connessione a Skype for Business online con Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="3d0b6-256">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="3d0b6-p130">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. È possibile gestire Office 365 e Skype for Business online da un'unica risorsa di amministrazione, semplificando il lavoro quotidiano se si hanno molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3d0b6-260">Introduzione a Windows PowerShell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3d0b6-260">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="3d0b6-261">Perché è importante utilizzare PowerShell di Office 365</span><span class="sxs-lookup"><span data-stu-id="3d0b6-261">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="3d0b6-p131">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Office 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d0b6-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="3d0b6-264">Gestire Office 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="3d0b6-264">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="3d0b6-265">Usare Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3d0b6-265">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="3d0b6-266">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="3d0b6-266">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="3d0b6-267">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3d0b6-267">Related topics</span></span>

[<span data-ttu-id="3d0b6-268">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="3d0b6-268">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
