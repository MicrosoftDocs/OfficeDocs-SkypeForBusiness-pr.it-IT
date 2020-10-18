---
title: 'Lync Server 2013: creare o modificare un criterio conferenza'
description: 'Lync Server 2013: creare o modificare un criterio di conferenza.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8715dcde033c4181069f3e30f65b3c29231f51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577982"
---
# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="83e42-103">Creare o modificare criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83e42-103">Create or modify a conferencing policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83e42-104">_**Ultimo argomento modificato:** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="83e42-104">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="83e42-105">Eseguire la procedura seguente per creare criteri di conferenza a livello di utente o di sito.</span><span class="sxs-lookup"><span data-stu-id="83e42-105">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="83e42-106">Per informazioni dettagliate sull'assegnazione di un criterio a livello di utente a un utente, vedere [assegnazione di un criterio di conferenza per utente in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="83e42-106">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="83e42-107">Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="83e42-107">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="83e42-108">Per creare nuovi criteri a livello di utente o sito</span><span class="sxs-lookup"><span data-stu-id="83e42-108">To create a new user or site policy</span></span>

1.  <span data-ttu-id="83e42-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="83e42-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="83e42-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83e42-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="83e42-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83e42-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="83e42-112">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.</span><span class="sxs-lookup"><span data-stu-id="83e42-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="83e42-113">Fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-113">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="83e42-p103">Per creare criteri a livello di utente, fare clic su **Criteri utente**. In **Nuovi criteri conferenza**, in **Nome** digitare un nome descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="83e42-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="83e42-p104">Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare tutto o parte del nome dei sito per cui si desidera creare il criterio. Nell'elenco dei siti fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="83e42-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83e42-119">Il nome del sito diventa il nome del criterio di conferenza e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="83e42-119">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="83e42-120">In **Descrizione** digitare una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="83e42-120">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="83e42-p105">In **Criteri organizzatore**, in **Dimensione massima riunione** digitare il numero massimo di utenti consentiti in una riunione. Per impostazione predefinita, la dimensione massima della riunione è 250 utenti.</span><span class="sxs-lookup"><span data-stu-id="83e42-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="83e42-123">Per impedire ai partecipanti di invitare utenti anonimi alle riunioni, deselezionare la casella di controllo **Consenti ai partecipanti di invitare utenti anonimi**.</span><span class="sxs-lookup"><span data-stu-id="83e42-123">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="83e42-124">Gli utenti anonimi sono utenti che non dispongono di credenziali nei servizi di dominio Active Directory dell'organizzazione e che, pertanto, non vengono autenticati.</span><span class="sxs-lookup"><span data-stu-id="83e42-124">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="83e42-125">Per impostazione predefinita, l'invito di utenti anonimi alle riunioni è consentito.</span><span class="sxs-lookup"><span data-stu-id="83e42-125">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="83e42-126">In **Registrazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-126">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="83e42-p107">Per impedire ai partecipanti di registrare le riunioni, fare clic su **Nessuno**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="83e42-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="83e42-129">Per consentire ai partecipanti di registrare le riunioni, fare clic su \*\* Abilita registrazione\*\*.</span><span class="sxs-lookup"><span data-stu-id="83e42-129">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="83e42-p108">Per consentire ai partecipanti esterni di registrare le riunioni, selezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di registrare**. L'impostazione predefinita non consente ai partecipanti esterni di registrare le riunioni.</span><span class="sxs-lookup"><span data-stu-id="83e42-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="83e42-132">In **Audio/Video** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-132">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="83e42-133">Per impedire l'utilizzo di audio e video, fare clic su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="83e42-133">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="83e42-134">Per consentire l'utilizzo dell'audio, ma non del video, fare clic su **Abilita audio IP**.</span><span class="sxs-lookup"><span data-stu-id="83e42-134">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="83e42-p109">Per consentire l'utilizzo dell'audio e del video, fare clic su **Abilita audio/video IP**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="83e42-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="83e42-137">Se si sceglie di consentire l'utilizzo dell'audio in **Audio/Video**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-137">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="83e42-p110">Per impedire agli utenti di accedere alle riunioni tramite telefono, deselezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono accedere alle riunioni utilizzando la rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="83e42-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="83e42-p111">Se si consente agli utenti di accedere alle riunioni tramite telefono e si desidera consentire agli utenti non autenticati (anonimi) di accedere utilizzando chiamate in uscita, selezionare la casella di controllo **Consenti chiamate in uscita ai partecipanti anonimi**. Con le chiamate in uscita il server per conferenze telefona all'utente, il quale accederà alla riunione rispondendo al telefono. Per impostazione predefinita, gli utenti anonimi non possono accedere alle riunioni utilizzando chiamate in uscita.</span><span class="sxs-lookup"><span data-stu-id="83e42-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="83e42-143">Se si sceglie di consentire l'utilizzo del video in **Audio/Video** selezionare **Consenti più flussi video** .</span><span class="sxs-lookup"><span data-stu-id="83e42-143">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="83e42-144">In **Collaborazione dati** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-144">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="83e42-145">Per impedire la collaborazione sui dati, fare clic su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="83e42-145">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="83e42-p112">Per consentire la collaborazione sui dati, fare clic su **Abilita collaborazione dati**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="83e42-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="83e42-148">Se si è scelto di consentire la collaborazione sui dati in **Collaborazione dati**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-148">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="83e42-p113">Per impedire i download esterni, deselezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di scaricare contenuto**. Per impostazione predefinita, gli utenti esterni possono scaricare contenuto.</span><span class="sxs-lookup"><span data-stu-id="83e42-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="83e42-p114">Per impedire i trasferimenti di file, deselezionare la casella di controllo **Consenti ai partecipanti di trasferire file**. Per impostazione predefinita, gli utenti possono trasferire file.</span><span class="sxs-lookup"><span data-stu-id="83e42-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="83e42-p115">Per impedire l'utilizzo delle annotazioni, deselezionare la casella di controllo **Consenti annotazioni**. Per utilizzare le annotazioni in presentazioni di PowerPoint condivise, deselezionare **Abilita annotazioni di PowerPoint**. Per impostazione predefinita, le annotazioni sono consentite.</span><span class="sxs-lookup"><span data-stu-id="83e42-p115">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="83e42-p116">Per impedire l'utilizzo dei sondaggi, deselezionare la casella di controllo **Consenti sondaggi**. Per impostazione predefinita, i sondaggi sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="83e42-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="83e42-158">In **Condivisione applicazioni** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-158">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="83e42-159">Per impedire l'utilizzo della condivisione applicazioni, fare clic su **Disabilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="83e42-159">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="83e42-p117">Per consentire l'utilizzo della condivisione applicazioni, fare clic su **Abilita condivisione applicazioni**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="83e42-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="83e42-162">Se si è scelto di consentire la condivisione applicazioni in **Condivisione applicazioni**, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-162">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="83e42-p118">Per impedire ai partecipanti della riunione di assumere il controllo della condivisione applicazioni, deselezionare la casella di controllo **Consenti ai partecipanti di assumere il controllo**. Per impostazione predefinita, i partecipanti possono assumere il controllo.</span><span class="sxs-lookup"><span data-stu-id="83e42-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="83e42-p119">Se si è scelto di consentire ai partecipanti di assumere il controllo della condivisione applicazioni, selezionare la casella di controllo **Consenti ai partecipanti anonimi e federati di assumere il controllo** per consentire agli utenti esterni di assumere il controllo della condivisione applicazioni. Per impostazione predefinita, gli utenti esterni non possono assumere il controllo.</span><span class="sxs-lookup"><span data-stu-id="83e42-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="83e42-167">In **Criteri partecipante** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83e42-167">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="83e42-168">Per impedire sia la condivisione applicazioni che la condivisione desktop, fare clic su **Disabilita condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="83e42-168">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="83e42-169">Per consentire la condivisione applicazioni, ma non la condivisione desktop, fare clic su **Abilita condivisione applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="83e42-169">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="83e42-p120">Per consentire sia la condivisione applicazioni che la condivisione desktop, fare clic su **Abilita condivisione applicazioni e desktop**.</span><span class="sxs-lookup"><span data-stu-id="83e42-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="83e42-p121">Per impedire i trasferimenti di file peer-to-peer, deselezionare la casella di controllo **Consenti trasferimento di file tramite peer-to-peer**. Per impostazione predefinita, i trasferimenti di file peer-to-peer sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="83e42-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="83e42-p122">Per consentire la registrazione peer-to-peer, selezionare la casella di controllo **Consenti registrazione peer-to-peer**. Per impostazione predefinita, la registrazione peer-to-peer non è consentita.</span><span class="sxs-lookup"><span data-stu-id="83e42-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="83e42-p123">Per consentire ai partecipanti di partecipare con più flussi video, selezionare la casella di controllo **Consenti ai partecipanti di unirsi con più flussi video**. Per impostazione predefinita sono consentiti più flussi video.</span><span class="sxs-lookup"><span data-stu-id="83e42-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="83e42-178">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="83e42-178">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="83e42-179">Per modificare criteri utente o sito esistenti</span><span class="sxs-lookup"><span data-stu-id="83e42-179">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="83e42-180">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="83e42-180">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="83e42-181">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83e42-181">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="83e42-182">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="83e42-182">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="83e42-183">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Criteri conferenza**.</span><span class="sxs-lookup"><span data-stu-id="83e42-183">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="83e42-184">Nell'elenco dei criteri per conferenza fare clic sui criteri che si desidera modificare, fare clic su \*\*Modifica \*\* e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="83e42-184">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="83e42-185">In **Modifica criteri conferenza** modificare qualsiasi impostazione dei criteri ad eccezione del nome, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="83e42-185">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="83e42-186">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="83e42-186">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

