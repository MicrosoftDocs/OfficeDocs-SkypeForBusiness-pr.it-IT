---
title: 'Lync Server 2013: creare o modificare un criterio di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 898ffb4473fadd4470ef7e1559fa3cc0c54185c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="4dae8-102">Creare o modificare criteri per i servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4dae8-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4dae8-103">_**Argomento Ultima modifica:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="4dae8-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="4dae8-104">Seguire questa procedura per creare criteri di conferenza a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="4dae8-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="4dae8-105">Per informazioni dettagliate su come assegnare un criterio a livello di utente a un utente, vedere [assegnare criteri di conferenza per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4dae8-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="4dae8-106">Per un elenco di tutte le impostazioni dei criteri di conferenza disponibili, vedere informazioni di [riferimento sulle impostazioni per i criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="4dae8-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="4dae8-107">Per creare un nuovo criterio per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="4dae8-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="4dae8-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4dae8-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4dae8-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dae8-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4dae8-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4dae8-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4dae8-111">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="4dae8-112">Fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="4dae8-113">Per creare un criterio a livello di utente, fare clic su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="4dae8-114">In **nome**digitare un nome descrittivo per il criterio in **nuovi criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-114">In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="4dae8-115">Per creare un criterio a livello di sito, fare clic su **criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="4dae8-116">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per cui si vuole creare un criterio.</span><span class="sxs-lookup"><span data-stu-id="4dae8-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="4dae8-117">Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-117">In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4dae8-118">Il nome del sito diventa il nome del criterio di conferenza e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="4dae8-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="4dae8-119">In **Descrizione**Digitare una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="4dae8-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="4dae8-120">In **Criteri organizzazione**, in **dimensioni massime riunione**, digitare il numero massimo di utenti che si vuole consentire a una riunione.</span><span class="sxs-lookup"><span data-stu-id="4dae8-120">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting.</span></span> <span data-ttu-id="4dae8-121">Per impostazione predefinita, la dimensione massima della riunione è 250.</span><span class="sxs-lookup"><span data-stu-id="4dae8-121">By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="4dae8-122">Per impedire agli utenti di invitare utenti anonimi alle riunioni, deselezionare la casella **di controllo Consenti ai partecipanti di invitare utenti anonimi** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="4dae8-123">Gli utenti anonimi sono utenti che non hanno credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati.</span><span class="sxs-lookup"><span data-stu-id="4dae8-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="4dae8-124">Per impostazione predefinita, gli utenti possono invitare utenti anonimi alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="4dae8-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="4dae8-125">In **registrazione**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="4dae8-126">Per impedire ai partecipanti di registrare riunioni, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-126">To prevent participants from recording meetings, click **None**.</span></span> <span data-ttu-id="4dae8-127">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-127">This is the default setting.</span></span>
    
      - <span data-ttu-id="4dae8-128">Per consentire ai partecipanti di registrare riunioni, fare clic su **Abilita registrazione**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="4dae8-129">Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di registrare** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-129">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box.</span></span> <span data-ttu-id="4dae8-130">Il valore predefinito è impedire ai partecipanti esterni di registrare riunioni.</span><span class="sxs-lookup"><span data-stu-id="4dae8-130">The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="4dae8-131">In **audio/video**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="4dae8-132">Per evitare l'uso di audio e video, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="4dae8-133">Per consentire l'uso di audio ma non video, fare clic su **Abilita audio IP**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="4dae8-134">Per consentire l'uso di audio e video, fare clic su **Abilita audio/video IP**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-134">To allow the use of audio and video, click **Enable IP audio/video**.</span></span> <span data-ttu-id="4dae8-135">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-135">This is the default setting.</span></span>

11. <span data-ttu-id="4dae8-136">Se si è scelto di consentire l'uso di audio in **audio/video**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="4dae8-137">Per impedire agli utenti di partecipare alla riunione effettuando la chiamata, deselezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-137">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="4dae8-138">Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="4dae8-138">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="4dae8-139">Se si consente agli utenti di accedere alle riunioni e si vuole consentire agli utenti non autenticati (anonimi) di partecipare a una riunione con chiamate in uscita, selezionare la casella **di controllo Consenti ai partecipanti anonimi di** effettuare la chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-139">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box.</span></span> <span data-ttu-id="4dae8-140">Con la chiamata in uscita, il server della conferenza chiama l'utente e l'utente risponde al telefono per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="4dae8-140">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting.</span></span> <span data-ttu-id="4dae8-141">Per impostazione predefinita, gli utenti anonimi non possono partecipare a una riunione tramite chiamata in uscita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-141">By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="4dae8-142">Se si è scelto di consentire l'uso di video in **audio/video**, selezionare **Consenti più flussi video** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="4dae8-143">In **collaborazione con i dati**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="4dae8-144">Per impedire la collaborazione con i dati, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="4dae8-145">Per consentire la collaborazione con i dati, fare clic su **Abilita collaborazione dati**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-145">To allow data collaboration, click **Enable data collaboration**.</span></span> <span data-ttu-id="4dae8-146">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-146">This is the default setting.</span></span>

14. <span data-ttu-id="4dae8-147">Se si è scelto di consentire la collaborazione ai dati in collaborazione con i **dati**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="4dae8-148">Per impedire i download esterni, deselezionare la casella **di controllo Consenti ai partecipanti federati e anonimi di scaricare contenuto** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-148">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box.</span></span> <span data-ttu-id="4dae8-149">Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.</span><span class="sxs-lookup"><span data-stu-id="4dae8-149">By default, external users can download content.</span></span>
    
      - <span data-ttu-id="4dae8-150">Per impedire i trasferimenti di file, deselezionare la casella **di controllo Consenti ai partecipanti di trasferire file** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-150">To prevent file transfers, clear the **Allow participants to transfer files** check box.</span></span> <span data-ttu-id="4dae8-151">Per impostazione predefinita, gli utenti possono trasferire file.</span><span class="sxs-lookup"><span data-stu-id="4dae8-151">By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="4dae8-152">Per evitare l'uso di annotazioni, deselezionare la casella di controllo **Abilita annotazioni** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-152">To prevent the use of annotations, clear the **Enable annotations** check box.</span></span> <span data-ttu-id="4dae8-153">Per l'uso delle annotazioni nelle presentazioni di PowerPoint frammentate, deselezionare l' **Abilitazione delle annotazioni di PowerPoint**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-153">To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**.</span></span> <span data-ttu-id="4dae8-154">Per impostazione predefinita, le annotazioni sono consentite.</span><span class="sxs-lookup"><span data-stu-id="4dae8-154">By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="4dae8-155">Per evitare l'uso dei sondaggi, deselezionare la casella di controllo **Abilita sondaggi** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-155">To prevent the use of polls, clear the **Enable polls** check box.</span></span> <span data-ttu-id="4dae8-156">Per impostazione predefinita, i sondaggi sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="4dae8-156">By default, polls are allowed.</span></span>

15. <span data-ttu-id="4dae8-157">In **condivisione applicazioni**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="4dae8-158">Per impedire l'uso della condivisione delle applicazioni, fare clic su **Disattiva condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="4dae8-159">Per consentire l'uso della condivisione delle applicazioni, fare clic su **Abilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-159">To allow the use of application sharing, click **Enable application sharing**.</span></span> <span data-ttu-id="4dae8-160">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-160">This is the default setting.</span></span>

16. <span data-ttu-id="4dae8-161">Se si è scelto di consentire la condivisione delle applicazioni nella **condivisione delle applicazioni**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="4dae8-162">Per evitare che i partecipanti alla riunione prendano il controllo della condivisione delle applicazioni, deselezionare la casella **di controllo Consenti ai partecipanti di assumere controlli** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-162">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box.</span></span> <span data-ttu-id="4dae8-163">Per impostazione predefinita, i partecipanti possono assumere il controllo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4dae8-163">By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="4dae8-164">Se si è scelto di consentire ai partecipanti alla riunione di assumere il controllo della condivisione delle applicazioni, selezionare la casella di controllo **Consenti ai partecipanti federati e anonimi di assumere controlli** per consentire agli utenti esterni di assumere il controllo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4dae8-164">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing.</span></span> <span data-ttu-id="4dae8-165">Per impostazione predefinita, gli utenti esterni non possono assumere il controllo della condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4dae8-165">By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="4dae8-166">In **criteri partecipante**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4dae8-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="4dae8-167">Per impedire sia la condivisione delle applicazioni che la condivisione desktop, fare clic su **Disattiva condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="4dae8-168">Per consentire la condivisione delle applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="4dae8-169">Per consentire la condivisione delle applicazioni e la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-169">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**.</span></span> <span data-ttu-id="4dae8-170">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-170">This is the default setting.</span></span>

18. <span data-ttu-id="4dae8-171">Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento file peer-to-** peer.</span><span class="sxs-lookup"><span data-stu-id="4dae8-171">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box.</span></span> <span data-ttu-id="4dae8-172">Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="4dae8-172">By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="4dae8-173">Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Abilita registrazione peer-to-peer** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-173">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box.</span></span> <span data-ttu-id="4dae8-174">Per impostazione predefinita, la registrazione peer-to-peer non è consentita.</span><span class="sxs-lookup"><span data-stu-id="4dae8-174">By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="4dae8-175">Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella **di controllo Consenti ai partecipanti di partecipare con più flussi video** .</span><span class="sxs-lookup"><span data-stu-id="4dae8-175">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box.</span></span> <span data-ttu-id="4dae8-176">Per impostazione predefinita, sono consentiti più flussi video.</span><span class="sxs-lookup"><span data-stu-id="4dae8-176">By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="4dae8-177">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="4dae8-178">Per modificare un criterio di un utente o di un sito esistente</span><span class="sxs-lookup"><span data-stu-id="4dae8-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="4dae8-179">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4dae8-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4dae8-180">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4dae8-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4dae8-181">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4dae8-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4dae8-182">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="4dae8-183">Nell'elenco dei criteri di conferenza fare clic sul criterio che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4dae8-184">In **modifica criteri di conferenza**modificare le impostazioni dei criteri, ad eccezione del nome del criterio, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="4dae8-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="4dae8-185">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4dae8-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

