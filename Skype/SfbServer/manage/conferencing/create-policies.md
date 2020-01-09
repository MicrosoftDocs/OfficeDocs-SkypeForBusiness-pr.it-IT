---
title: Creare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Riepilogo: informazioni su come creare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 078c80af0304c796bd3935200764a9ce6e13585b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991891"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="20115-103">Creare criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="20115-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="20115-104">**Riepilogo:** Informazioni su come creare criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="20115-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="20115-105">Puoi creare criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="20115-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="20115-106">Creare criteri di conferenza tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="20115-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="20115-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="20115-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="20115-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="20115-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="20115-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="20115-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="20115-110">Fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="20115-111">Per creare un criterio a livello di utente, fare clic su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="20115-111">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="20115-112">In **nome**digitare un nome descrittivo per il criterio in **nuovi criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="20115-112">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="20115-113">Per creare un criterio a livello di sito, fare clic su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="20115-113">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="20115-114">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio.</span><span class="sxs-lookup"><span data-stu-id="20115-114">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="20115-115">Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="20115-115">In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="20115-116">Il nome del sito diventa il nome del criterio di conferenza; non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="20115-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="20115-117">In **Descrizione**Digitare una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="20115-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="20115-118">In **Criteri organizzazione**, in **dimensioni massime riunione**, digitare il numero massimo di utenti che si vuole consentire a una riunione.</span><span class="sxs-lookup"><span data-stu-id="20115-118">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting.</span></span> <span data-ttu-id="20115-119">Per impostazione predefinita, la dimensione massima della riunione è 250.</span><span class="sxs-lookup"><span data-stu-id="20115-119">By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="20115-120">Per impedire agli utenti di invitare utenti anonimi alle riunioni, deselezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** .</span><span class="sxs-lookup"><span data-stu-id="20115-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="20115-121">Gli utenti anonimi sono utenti che non hanno credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati.</span><span class="sxs-lookup"><span data-stu-id="20115-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="20115-122">Per impostazione predefinita, gli utenti possono invitare utenti anonimi alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="20115-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="20115-123">In **registrazione**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="20115-124">Per impedire ai partecipanti di registrare riunioni, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="20115-124">To prevent participants from recording meetings, click **None**.</span></span> <span data-ttu-id="20115-125">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="20115-125">This is the default setting.</span></span>
    
   - <span data-ttu-id="20115-126">Per consentire ai partecipanti di registrare riunioni, fare clic su **Abilita registrazione**.</span><span class="sxs-lookup"><span data-stu-id="20115-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="20115-127">Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di registrare** .</span><span class="sxs-lookup"><span data-stu-id="20115-127">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box.</span></span> <span data-ttu-id="20115-128">Il valore predefinito è impedire ai partecipanti esterni di registrare riunioni.</span><span class="sxs-lookup"><span data-stu-id="20115-128">The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="20115-129">In **audio/video**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="20115-130">Per evitare l'uso di audio e video, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="20115-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="20115-131">Per consentire l'uso di audio ma non video, fare clic su **Abilita audio IP**.</span><span class="sxs-lookup"><span data-stu-id="20115-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="20115-132">Per consentire l'uso di audio e video, fare clic su **Abilita audio/video IP**.</span><span class="sxs-lookup"><span data-stu-id="20115-132">To allow the use of audio and video, click **Enable IP audio/video**.</span></span> <span data-ttu-id="20115-133">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="20115-133">This is the default setting.</span></span>
    
11. <span data-ttu-id="20115-134">Se si è scelto di consentire l'uso di audio in **audio/video**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="20115-135">Per impedire agli utenti di partecipare alla riunione effettuando la chiamata, deselezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** .</span><span class="sxs-lookup"><span data-stu-id="20115-135">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="20115-136">Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="20115-136">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="20115-137">Se si consente agli utenti di accedere alle riunioni e si vuole consentire agli utenti non autenticati (anonimi) di partecipare a una riunione con chiamate in uscita, selezionare la casella **di controllo Consenti ai partecipanti anonimi di** effettuare la chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20115-137">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box.</span></span> <span data-ttu-id="20115-138">Con la chiamata in uscita, il server della conferenza chiama l'utente e l'utente risponde al telefono per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="20115-138">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting.</span></span> <span data-ttu-id="20115-139">Per impostazione predefinita, gli utenti anonimi non possono partecipare a una riunione tramite chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20115-139">By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="20115-140">Se si è scelto di consentire l'uso di video in **audio/video**, selezionare **Consenti più flussi video**.</span><span class="sxs-lookup"><span data-stu-id="20115-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="20115-141">In **collaborazione con i dati**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="20115-142">Per impedire la collaborazione con i dati, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="20115-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="20115-143">Per consentire la collaborazione con i dati, fare clic su **Abilita collaborazione dati**.</span><span class="sxs-lookup"><span data-stu-id="20115-143">To allow data collaboration, click **Enable data collaboration**.</span></span> <span data-ttu-id="20115-144">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="20115-144">This is the default setting.</span></span>
    
14. <span data-ttu-id="20115-145">Se si è scelto di consentire la collaborazione ai dati in collaborazione con i **dati**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="20115-146">Per impedire i download esterni, deselezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di scaricare contenuto** .</span><span class="sxs-lookup"><span data-stu-id="20115-146">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box.</span></span> <span data-ttu-id="20115-147">Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.</span><span class="sxs-lookup"><span data-stu-id="20115-147">By default, external users can download content.</span></span>
    
    - <span data-ttu-id="20115-148">Per impedire i trasferimenti di file, deselezionare la casella **di controllo Consenti ai partecipanti di trasferire file** .</span><span class="sxs-lookup"><span data-stu-id="20115-148">To prevent file transfers, clear the **Allow participants to transfer files** check box.</span></span> <span data-ttu-id="20115-149">Per impostazione predefinita, gli utenti possono trasferire file.</span><span class="sxs-lookup"><span data-stu-id="20115-149">By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="20115-150">Per evitare l'uso di annotazioni, deselezionare la casella di controllo **Abilita annotazioni** .</span><span class="sxs-lookup"><span data-stu-id="20115-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="20115-151">Per l'uso delle annotazioni nelle presentazioni di PowerPoint condivise, deselezionare l' **Abilitazione delle annotazioni di PowerPoint**.</span><span class="sxs-lookup"><span data-stu-id="20115-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="20115-152">Per impostazione predefinita, le annotazioni sono consentite.</span><span class="sxs-lookup"><span data-stu-id="20115-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="20115-153">Per evitare l'uso dei sondaggi, deselezionare la casella di controllo **Abilita sondaggi** .</span><span class="sxs-lookup"><span data-stu-id="20115-153">To prevent the use of polls, clear the **Enable polls** check box.</span></span> <span data-ttu-id="20115-154">Per impostazione predefinita, i sondaggi sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="20115-154">By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="20115-155">In **condivisione applicazioni**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="20115-156">Per impedire l'uso della condivisione delle applicazioni, fare clic su **Disattiva condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="20115-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="20115-157">Per consentire l'uso della condivisione delle applicazioni, fare clic su **Abilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="20115-157">To allow the use of application sharing, click **Enable application sharing**.</span></span> <span data-ttu-id="20115-158">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="20115-158">This is the default setting.</span></span>
    
16. <span data-ttu-id="20115-159">Se si è scelto di consentire la condivisione delle applicazioni nella **condivisione delle applicazioni**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="20115-160">Per evitare che i partecipanti alla riunione prendano il controllo della condivisione delle applicazioni, deselezionare la casella **di controllo Consenti ai partecipanti di assumere controlli** .</span><span class="sxs-lookup"><span data-stu-id="20115-160">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box.</span></span> <span data-ttu-id="20115-161">Per impostazione predefinita, i partecipanti possono assumere il controllo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="20115-161">By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="20115-162">Se si è scelto di consentire ai partecipanti alla riunione di assumere il controllo della condivisione delle applicazioni, selezionare la casella di controllo **Consenti ai partecipanti federati e anonimi di assumere controlli** per consentire agli utenti esterni di assumere il controllo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="20115-162">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing.</span></span> <span data-ttu-id="20115-163">Per impostazione predefinita, gli utenti esterni non possono assumere il controllo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="20115-163">By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="20115-164">In **criteri partecipante**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20115-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="20115-165">Per impedire sia la condivisione delle applicazioni che la condivisione desktop, fare clic su **Disattiva condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="20115-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="20115-166">Per consentire la condivisione delle applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="20115-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="20115-167">Per consentire la condivisione delle applicazioni e la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="20115-167">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**.</span></span> <span data-ttu-id="20115-168">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="20115-168">This is the default setting.</span></span>
    
18. <span data-ttu-id="20115-169">Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento file peer-to-** peer.</span><span class="sxs-lookup"><span data-stu-id="20115-169">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box.</span></span> <span data-ttu-id="20115-170">Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="20115-170">By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="20115-171">Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Abilita registrazione peer-to-peer** .</span><span class="sxs-lookup"><span data-stu-id="20115-171">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box.</span></span> <span data-ttu-id="20115-172">Per impostazione predefinita, la registrazione peer-to-peer non è consentita.</span><span class="sxs-lookup"><span data-stu-id="20115-172">By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="20115-173">Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella **di controllo Consenti ai partecipanti di partecipare con più flussi video** .</span><span class="sxs-lookup"><span data-stu-id="20115-173">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="20115-174">Per impostazione predefinita, sono consentiti più flussi video.</span><span class="sxs-lookup"><span data-stu-id="20115-174">By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="20115-175">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="20115-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="20115-176">Creare criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="20115-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="20115-177">Per creare criteri di conferenza, usare il cmdlet **New-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="20115-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="20115-178">L'esempio seguente crea un nuovo criterio di conferenza con Identity SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="20115-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="20115-179">Questo criterio utilizzerà tutti i valori predefiniti per i criteri di conferenza tranne uno: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="20115-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="20115-180">In questo esempio, la dimensione massima per una riunione verrà impostata su 50 anziché sul valore predefinito di 250:</span><span class="sxs-lookup"><span data-stu-id="20115-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="20115-181">Per altre informazioni, inclusa una descrizione completa della sintassi e un elenco di parametri, vedere [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="20115-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

