---
title: Creare criteri conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Riepilogo: informazioni su come creare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 8e707e6da1a56fa1818d436714327936369b06fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828236"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="8c1a0-103">Creare criteri conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c1a0-103">Create conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="8c1a0-104">**Riepilogo:** Informazioni su come creare criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-104">**Summary:** Learn how to create conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="8c1a0-105">È possibile creare criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-105">You can create conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8c1a0-106">Creare criteri di conferenza tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c1a0-106">Create conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8c1a0-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8c1a0-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8c1a0-109">Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Criteri conferenza.**</span><span class="sxs-lookup"><span data-stu-id="8c1a0-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="8c1a0-110">Fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-110">Click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="8c1a0-p101">Per creare criteri a livello di utente, fare clic su **Criteri utente**. In **Nuovi criteri conferenza**, in **Nome** digitare un nome descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p101">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
   - <span data-ttu-id="8c1a0-p102">Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare tutto o parte del nome dei sito per cui si desidera creare il criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p102">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="8c1a0-116">Il nome del sito diventa il nome del criterio di conferenza. non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-116">The site name becomes the conferencing policy name; it cannot be changed.</span></span> 
  
5. <span data-ttu-id="8c1a0-117">In **Descrizione** digitare una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-117">In **Description**, type a description for the policy.</span></span>
    
6. <span data-ttu-id="8c1a0-p103">In **Criteri organizzatore**, in **Dimensione massima riunione** digitare il numero massimo di utenti consentiti in una riunione. Per impostazione predefinita, la dimensione massima della riunione è 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p103">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>
    
7. <span data-ttu-id="8c1a0-120">Per impedire ai partecipanti di invitare utenti anonimi alle riunioni, deselezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-120">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="8c1a0-121">Gli utenti anonimi sono utenti che non dispongono di credenziali in Servizi di dominio Active Directory dell'organizzazione e che pertanto non sono autenticati.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-121">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="8c1a0-122">Per impostazione predefinita, l'invito di utenti anonimi alle riunioni è consentito.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-122">By default, users can invite anonymous users to meetings.</span></span>
    
8. <span data-ttu-id="8c1a0-123">In **Registrazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-123">In **Recording**, do one of the following:</span></span>
    
   - <span data-ttu-id="8c1a0-p105">Per impedire ai partecipanti di registrare le riunioni, fare clic su **Nessuno**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p105">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
   - <span data-ttu-id="8c1a0-126">Per consentire ai partecipanti di registrare le riunioni, fare clic su **Abilita registrazione**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-126">To allow participants to record meetings, click **Enable recording**.</span></span>
    
9. <span data-ttu-id="8c1a0-p106">Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di registrare**. L'impostazione predefinita non consente ai partecipanti esterni di registrare le riunioni.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p106">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>
    
10. <span data-ttu-id="8c1a0-129">In **Audio/Video** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-129">In **Audio/video**, do one of the following:</span></span>
    
    - <span data-ttu-id="8c1a0-130">Per impedire l'utilizzo di audio e video, fare clic su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-130">To prevent the use of audio and video, click **None**.</span></span>
    
    - <span data-ttu-id="8c1a0-131">Per consentire l'utilizzo dell'audio, ma non del video, fare clic su **Abilita audio IP**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-131">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
    - <span data-ttu-id="8c1a0-p107">Per consentire l'utilizzo dell'audio e del video, fare clic su **Abilita audio/video IP**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p107">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>
    
11. <span data-ttu-id="8c1a0-134">Se si sceglie di consentire l'utilizzo dell'audio in **Audio/Video**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-134">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
    - <span data-ttu-id="8c1a0-p108">Per impedire agli utenti di accedere alle riunioni tramite telefono, deselezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono accedere alle riunioni utilizzando la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p108">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
    - <span data-ttu-id="8c1a0-p109">Se si consente agli utenti di accedere alle riunioni tramite telefono e si desidera consentire agli utenti non autenticati (anonimi) di accedere utilizzando chiamate in uscita, selezionare la casella di controllo **Consenti chiamate in uscita ai partecipanti anonimi**. Con le chiamate in uscita il server per conferenze telefona all'utente, il quale accederà alla riunione rispondendo al telefono. Per impostazione predefinita, gli utenti anonimi non possono accedere alle riunioni utilizzando chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p109">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>
    
12. <span data-ttu-id="8c1a0-140">Se si è scelto di consentire l'uso di video in **Audio/Video,** selezionare **Consenti più flussi video.**</span><span class="sxs-lookup"><span data-stu-id="8c1a0-140">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams**.</span></span>
    
13. <span data-ttu-id="8c1a0-141">In **Collaborazione dati** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-141">In **Data collaboration**, do one of the following:</span></span>
    
    - <span data-ttu-id="8c1a0-142">Per impedire la collaborazione sui dati, fare clic su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-142">To prevent data collaboration, click **None**.</span></span>
    
    - <span data-ttu-id="8c1a0-p110">Per consentire la collaborazione sui dati, fare clic su **Abilita collaborazione dati**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p110">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>
    
14. <span data-ttu-id="8c1a0-145">Se si è scelto di consentire la collaborazione sui dati in **Collaborazione dati**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-145">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
    - <span data-ttu-id="8c1a0-p111">Per impedire i download esterni, deselezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di scaricare contenuto**. Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p111">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
    - <span data-ttu-id="8c1a0-p112">Per impedire i trasferimenti di file, deselezionare la casella di controllo **Consenti ai partecipanti di trasferire file**. Per impostazione predefinita, gli utenti possono trasferire file.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p112">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
    - <span data-ttu-id="8c1a0-150">Per impedire l'utilizzo delle annotazioni, deselezionare la casella di controllo **Consenti annotazioni**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-150">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="8c1a0-151">Per utilizzare le annotazioni nelle presentazioni di PowerPoint condivise, deselezionare la casella di controllo **Abilita annotazioni di PowerPoint.**</span><span class="sxs-lookup"><span data-stu-id="8c1a0-151">To the use of annotations in shared PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="8c1a0-152">Per impostazione predefinita, le annotazioni sono consentite.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-152">By default, annotations are allowed.</span></span>
    
    - <span data-ttu-id="8c1a0-p114">Per impedire l'utilizzo dei sondaggi, deselezionare la casella di controllo **Consenti sondaggi**. Per impostazione predefinita, i sondaggi sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p114">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>
    
15. <span data-ttu-id="8c1a0-155">In **Condivisione applicazioni** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-155">In **Application sharing**, do one of the following:</span></span>
    
    - <span data-ttu-id="8c1a0-156">Per impedire l'utilizzo della condivisione applicazioni, fare clic su **Disabilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-156">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
    - <span data-ttu-id="8c1a0-p115">Per consentire l'utilizzo della condivisione applicazioni, fare clic su **Abilita condivisione applicazioni**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p115">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>
    
16. <span data-ttu-id="8c1a0-159">Se si è scelto di consentire la condivisione applicazioni in **Condivisione applicazioni**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-159">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
    - <span data-ttu-id="8c1a0-p116">Per impedire ai partecipanti della riunione di assumere il controllo della condivisione applicazioni, deselezionare la casella di controllo **Consenti ai partecipanti di assumere il controllo**. Per impostazione predefinita, i partecipanti possono assumere il controllo.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p116">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
    - <span data-ttu-id="8c1a0-p117">Se si è scelto di consentire ai partecipanti di assumere il controllo della condivisione applicazioni, selezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di assumere il controllo** per consentire agli utenti esterni di assumere il controllo della condivisione applicazioni. Per impostazione predefinita, gli utenti esterni non possono assumere il controllo.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p117">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>
    
17. <span data-ttu-id="8c1a0-164">In **Criteri partecipante** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-164">Under **Participant policy**, do one of the following:</span></span>
    
    - <span data-ttu-id="8c1a0-165">Per impedire sia la condivisione applicazioni che la condivisione desktop, fare clic su **Disabilita condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-165">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
    - <span data-ttu-id="8c1a0-166">Per consentire la condivisione applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-166">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
    - <span data-ttu-id="8c1a0-p118">Per consentire sia la condivisione applicazioni che la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p118">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>
    
18. <span data-ttu-id="8c1a0-p119">Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento di file tramite peer-to-peer**. Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p119">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>
    
19. <span data-ttu-id="8c1a0-p120">Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Consenti registrazione peer-to-peer**. Per impostazione predefinita, la registrazione peer-to-peer non è consentita.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p120">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>
    
20. <span data-ttu-id="8c1a0-p121">Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella di controllo **Consenti ai partecipanti di unirsi con più flussi video**. Per impostazione predefinita sono consentiti più flussi video.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-p121">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>
    
21. <span data-ttu-id="8c1a0-175">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-175">Click **Commit**.</span></span>
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8c1a0-176">Creare criteri conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8c1a0-176">Create conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="8c1a0-177">Per creare criteri di conferenza, utilizzare il cmdlet **New-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="8c1a0-177">To create conferencing policies, use the **New-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="8c1a0-178">Nell'esempio seguente viene creato un nuovo criterio di conferenza con Identità SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-178">The following example creates a new conferencing policy with the Identity SalesConferencingPolicy.</span></span> <span data-ttu-id="8c1a0-179">Questo criterio utilizzerà tutti i valori predefiniti per un criterio di conferenza ad eccezione di uno: MaxMeetingSize.</span><span class="sxs-lookup"><span data-stu-id="8c1a0-179">This policy will use all the default values for a conferencing policy except one: MaxMeetingSize.</span></span> <span data-ttu-id="8c1a0-180">In questo esempio, la dimensione massima di una riunione verrà impostata su 50 anziché sul valore predefinito di 250:</span><span class="sxs-lookup"><span data-stu-id="8c1a0-180">In this example, the maximum size for a meeting will be set to 50 instead of the default value of 250:</span></span>
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

<span data-ttu-id="8c1a0-181">Per ulteriori informazioni, inclusa una descrizione della sintassi completa e un elenco di parametri, vedere [New-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8c1a0-181">For more information, including a complete syntax description and list of parameters, see [New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).</span></span>
  

