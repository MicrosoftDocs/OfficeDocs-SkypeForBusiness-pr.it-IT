---
title: 'Lync Server 2013: Creare o modificare un flusso di lavoro interattivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec10d1d9c3281485078b2d7823978c429ea1be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="3858e-102">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3858e-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3858e-103">_**Argomento Ultima modifica:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="3858e-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="3858e-104">Usare una delle procedure seguenti per creare o modificare un flusso di lavoro interattivo.</span><span class="sxs-lookup"><span data-stu-id="3858e-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3858e-105">È possibile usare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare flussi di lavoro interattivi.</span><span class="sxs-lookup"><span data-stu-id="3858e-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="3858e-106">È possibile accedere allo strumento di configurazione del gruppo di risposte dal pannello di controllo di Lync Server oppure aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3858e-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="3858e-107">Per usare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro interattivo</span><span class="sxs-lookup"><span data-stu-id="3858e-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="3858e-108">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="3858e-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="3858e-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3858e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3858e-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3858e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3858e-111">Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3858e-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="3858e-112">Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="3858e-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="3858e-113">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si vuole creare o modificare.</span><span class="sxs-lookup"><span data-stu-id="3858e-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="3858e-114">Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3858e-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-115">Viene aperto lo strumento di configurazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="3858e-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="3858e-116">È anche possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3858e-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="3858e-117">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="3858e-118">In **creare un nuovo flusso di lavoro**, accanto a **interattivo**, fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="3858e-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="3858e-119">In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole modificare e quindi in **azione**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="3858e-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="3858e-120">Se non si è pronti per consentire agli utenti di iniziare a chiamare il flusso di lavoro, deselezionare la casella di controllo **Attiva flusso di lavoro** .</span><span class="sxs-lookup"><span data-stu-id="3858e-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-121">Per creare un flusso di lavoro gestito, è necessario selezionare <STRONG>attiva il flusso di lavoro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3858e-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="3858e-122">Dopo aver salvato il flusso di lavoro attivo e gestito, è possibile modificarlo e disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="3858e-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="3858e-123">Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per Federazione** .</span><span class="sxs-lookup"><span data-stu-id="3858e-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="3858e-124">Devi anche avere un criterio di accesso esterno che si applica all'applicazione di Response Group configurata per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="3858e-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-125">I criteri di accesso esterno globale si applicano all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="3858e-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="3858e-126">Puoi configurare il criterio globale per la Federazione dei gruppi di risposta usando il pannello di controllo di Lync Server o usando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true.</span><span class="sxs-lookup"><span data-stu-id="3858e-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="3858e-127">Tieni presente che le impostazioni dei criteri globali si applicano a tutti gli utenti, a meno che non vengano assegnati criteri per un sito o un utente.</span><span class="sxs-lookup"><span data-stu-id="3858e-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="3858e-128">Pertanto, prima di modificare questa impostazione per i gruppi di risposta, verificare che l'impostazione della Federazione soddisfi i requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3858e-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="3858e-129">Per informazioni dettagliate su come applicare i criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="3858e-130">Per informazioni dettagliate sull'impostazione della Federazione, vedere <STRONG>Set-CsExternalAccessPolicy</STRONG> nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3858e-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-131">Gli utenti ospitati in Lync Online non possono inserire le chiamate ai gruppi di risposte ospitati in una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="3858e-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="3858e-132">Questo vale sia per le distribuzioni ibride sia per i casi in cui una distribuzione locale è federata con una distribuzione Lync Online.</span><span class="sxs-lookup"><span data-stu-id="3858e-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="3858e-133">Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita agente anonimato** .</span><span class="sxs-lookup"><span data-stu-id="3858e-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-134">Le chiamate anonime non possono iniziare con la messaggistica istantanea (IM) o il video, anche se l'agente o il chiamante può aggiungere messaggi istantanei e video dopo che la chiamata è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="3858e-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="3858e-135">Un agente anonimo può anche inserire chiamate in attesa, trasferire chiamate (sia i trasferimenti non vedenti che consultivi) e parcheggiare e recuperare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="3858e-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="3858e-136">Le chiamate anonime non supportano le conferenze, la condivisione di applicazioni e la condivisione desktop, il trasferimento di file, la lavagna e la collaborazione ai dati e la registrazione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="3858e-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="3858e-137">Gli agenti che usano il plug-in di Lync VDI possono ricevere chiamate in arrivo in forma anonima, ma non possono effettuare chiamate in uscita in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="3858e-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="3858e-138">In **immettere l'indirizzo del gruppo che riceverà le chiamate**Digitare l'indirizzo URI (Uniform Resource Identifier) SIP principale del gruppo che risponderà alle chiamate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3858e-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="3858e-139">In **nome visualizzato**Digitare il nome che si vuole visualizzare per il flusso di lavoro, ad esempio Sales IVR Response Group.</span><span class="sxs-lookup"><span data-stu-id="3858e-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-140">Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3858e-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="3858e-141">Non usare i nomi visualizzati seguenti perché sono riservati: Watcher presenza di RGS o servizio di annuncio.</span><span class="sxs-lookup"><span data-stu-id="3858e-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="3858e-142">In **numero di telefono**Digitare l'URI di linea per il gruppo di risposte, ad esempio + 14255550165.</span><span class="sxs-lookup"><span data-stu-id="3858e-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="3858e-143">In **numero di visualizzazione**Digitare il numero che si vuole visualizzare per il gruppo di risposte, ad esempio + 1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="3858e-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="3858e-144">Opzionale In **Descrizione**Digitare una descrizione per il flusso di lavoro che si vuole visualizzare nella scheda contatto nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="3858e-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="3858e-145">In **tipo flusso di lavoro**selezionare **gestito** se il flusso di lavoro verrà gestito da un responsabile del gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="3858e-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="3858e-146">Eseguire le operazioni seguenti per assegnare i responsabili del gruppo di risposte al flusso di lavoro:</span><span class="sxs-lookup"><span data-stu-id="3858e-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="3858e-147">Digitare l'URI SIP di un Manager per il flusso di lavoro e fare clic su **Aggiungi**..</span><span class="sxs-lookup"><span data-stu-id="3858e-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="3858e-148">Digitare l'URI SIP di altri responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**..</span><span class="sxs-lookup"><span data-stu-id="3858e-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3858e-149">A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="3858e-149">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="3858e-150">Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="3858e-150">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="3858e-151">In **passaggio 2 Selezionare una lingua**, fare clic sulla lingua da usare per il riconoscimento vocale e la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="3858e-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="3858e-152">Se si vuole configurare un messaggio di benvenuto, in **passaggio 3 configurare un messaggio di benvenuto**, selezionare la casella di controllo **Riproduci un messaggio** di benvenuto e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="3858e-153">Per immettere il messaggio di benvenuto come testo convertito in vocale per i chiamanti, fare clic su **USA sintesi vocale**e quindi digitare il messaggio di benvenuto nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="3858e-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-154">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="3858e-154">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="3858e-155">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="3858e-155">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="3858e-156">Per usare una registrazione di file audio Wave o Windows Media per il messaggio di benvenuto, fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="3858e-156">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="3858e-157">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** .</span><span class="sxs-lookup"><span data-stu-id="3858e-157">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="3858e-158">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3858e-158">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="3858e-159">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="3858e-159">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-160">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="3858e-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="3858e-161">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="3858e-162">In **passaggio 4 specificare gli orari di ufficio**, nella casella **fuso orario** fare clic sul fuso orario del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3858e-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-163">Il fuso orario è il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3858e-163">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="3858e-164">Viene usato per calcolare le ore di apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="3858e-164">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="3858e-165">Ad esempio, se il flusso di lavoro è configurato per l'uso del fuso orario orientale nordamericano e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="3858e-165">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="3858e-166">e chiudere alle 11:00 P.M. gli orari di apertura e chiusura si presume siano 7:00 Eastern Time e 11:00 Eastern Time rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="3858e-166">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively.</span></span> <span data-ttu-id="3858e-167">È necessario immettere gli orari nella notazione a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="3858e-167">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="3858e-168">Selezionare il tipo di pianificazione delle ore lavorative che si vuole usare eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="3858e-169">Per usare una programmazione predefinita per le ore lavorative, fare clic su **Usa una programmazione preimpostata**e quindi selezionare la programmazione da usare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3858e-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-170">Per selezionare questa opzione, è necessario aver definito almeno una programmazione preimpostata.</span><span class="sxs-lookup"><span data-stu-id="3858e-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="3858e-171">Puoi definire le pianificazioni predefinite usando il cmdlet <STRONG>New-CsRgsHoursOfBusiness</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3858e-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="3858e-172">Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire le ore lavorative per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="3858e-173">Quando si seleziona una programmazione preimpostata, il <STRONG>giorno</STRONG>, l' <STRONG>apertura</STRONG>e la <STRONG>chiusura</STRONG> vengono automaticamente riempiti con i giorni e le ore che il gruppo di risposte è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3858e-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="3858e-174">Per usare una pianificazione personalizzata che si applica solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="3858e-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="3858e-175">Se si sta creando una pianificazione personalizzata per il flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il gruppo di risposte è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3858e-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="3858e-176">Se si sta creando una pianificazione personalizzata, digitare le ore di **apertura** e **chiusura** quando il gruppo di risposte è disponibile.</span><span class="sxs-lookup"><span data-stu-id="3858e-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-177">Le ore di <STRONG>apertura</STRONG> e <STRONG>chiusura</STRONG> devono essere in notazione oraria 24 ore.</span><span class="sxs-lookup"><span data-stu-id="3858e-177">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation.</span></span> <span data-ttu-id="3858e-178">Ad esempio, se il tuo ufficio lavora a un giorno lavorativo da 9 a 5 e chiude a mezzogiorno per pranzo, gli orari di apertura sono specificati come <STRONG>apri</STRONG> 9:00, <STRONG>Chiudi</STRONG> 12:00, <STRONG>Apri</STRONG> 13:00 e <STRONG>Chiudi</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="3858e-178">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="3858e-179">Se si vuole riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il gruppo di risposte si trova al di fuori degli orari lavorativi** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="3858e-180">Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="3858e-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-181">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="3858e-181">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="3858e-182">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="3858e-182">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="3858e-183">Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="3858e-183">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="3858e-184">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** .</span><span class="sxs-lookup"><span data-stu-id="3858e-184">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="3858e-185">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3858e-185">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="3858e-186">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="3858e-186">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-187">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="3858e-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="3858e-188">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="3858e-189">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="3858e-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="3858e-190">Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.</span><span class="sxs-lookup"><span data-stu-id="3858e-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="3858e-191">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="3858e-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="3858e-192">Il formato per l'indirizzo della segreteria \<telefonica\>@\<è nomeutente\> NomeDominio (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3858e-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="3858e-193">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente.</span><span class="sxs-lookup"><span data-stu-id="3858e-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="3858e-194">Il formato per l'indirizzo utente è \<nomeutente\>@\<NomeDominio\>.</span><span class="sxs-lookup"><span data-stu-id="3858e-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="3858e-195">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="3858e-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="3858e-196">Il formato per il numero di telefono \<è\>@\<Number NomeDominio\> , ad esempio + 14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3858e-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="3858e-197">Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="3858e-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="3858e-198">In **passaggio 5 specificare le festività**, fare clic sulle caselle di controllo relative a uno o più set di festività che definiscono i giorni in cui il gruppo di risposte viene chiuso per le aziende.</span><span class="sxs-lookup"><span data-stu-id="3858e-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-199">Prima di configurare il flusso di lavoro, è necessario definire le festività e i set di festività.</span><span class="sxs-lookup"><span data-stu-id="3858e-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="3858e-200">Usare i cmdlet <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> per definire festività e set di festività.</span><span class="sxs-lookup"><span data-stu-id="3858e-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="3858e-201">Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(facoltativo) definire set di festività di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="3858e-202">Se si vuole riprodurre un messaggio in festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="3858e-203">Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="3858e-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-204">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="3858e-204">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="3858e-205">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="3858e-205">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="3858e-206">Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="3858e-206">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="3858e-207">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** .</span><span class="sxs-lookup"><span data-stu-id="3858e-207">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="3858e-208">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3858e-208">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="3858e-209">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="3858e-209">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-210">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="3858e-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="3858e-211">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="3858e-212">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="3858e-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="3858e-213">Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.</span><span class="sxs-lookup"><span data-stu-id="3858e-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="3858e-214">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="3858e-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="3858e-215">Il formato per l'indirizzo della segreteria \<telefonica\>@\<è nomeutente\> NomeDominio (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3858e-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="3858e-216">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente.</span><span class="sxs-lookup"><span data-stu-id="3858e-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="3858e-217">Il formato per l'indirizzo utente è \<nomeutente\>@\<NomeDominio\>.</span><span class="sxs-lookup"><span data-stu-id="3858e-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="3858e-218">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="3858e-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="3858e-219">Il formato per il numero di telefono \<è\>@\<Number NomeDominio\> , ad esempio + 14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3858e-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="3858e-220">Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="3858e-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="3858e-221">In **passaggio 6 configurare la musica in attesa**, scegliere ciò che si vuole che i chiamanti ascoltino in attesa di un agente eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="3858e-222">Per usare la registrazione predefinita per la musica in attesa, fare clic su **Usa impostazione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="3858e-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="3858e-223">Per usare una registrazione di file audio per la musica in attesa, fare clic su **Seleziona un file musicale**.</span><span class="sxs-lookup"><span data-stu-id="3858e-223">To use an audio file recording for the on-hold music, click **Select a music file**.</span></span> <span data-ttu-id="3858e-224">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **a un file musicale** .</span><span class="sxs-lookup"><span data-stu-id="3858e-224">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="3858e-225">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3858e-225">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="3858e-226">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="3858e-226">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-227">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="3858e-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="3858e-228">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="3858e-229">In **passaggio 7 configurare la risposta vocale interattiva**, in l' **utente sentirà il testo o l'intestazione del messaggio registrato seguente** , specificare la domanda per chiedere ai chiamanti come segue:</span><span class="sxs-lookup"><span data-stu-id="3858e-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="3858e-230">Per immettere la domanda in formato testo, fare clic su **USA sintesi vocale**e digitare la domanda nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="3858e-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-231">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="3858e-231">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="3858e-232">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="3858e-232">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-233">Il simbolo "#" viene tradotto dal motore di sintesi vocale come parola "Number".</span><span class="sxs-lookup"><span data-stu-id="3858e-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="3858e-234">Se devi fare riferimento al tasto #, devi usare il nome della chiave, invece del simbolo, nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="3858e-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="3858e-235">Ad esempio, "per comunicare con le vendite, premi il tasto cancelletto".</span><span class="sxs-lookup"><span data-stu-id="3858e-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="3858e-236">Per usare un file audio preregistrato che contiene la domanda, fare clic su **Seleziona una registrazione**e quindi fare clic sul collegamento **registrazione** per caricare il file.</span><span class="sxs-lookup"><span data-stu-id="3858e-236">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="3858e-237">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="3858e-237">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="3858e-238">Fare clic su **carica** per caricare il file e quindi, facoltativamente, è possibile digitare la domanda nella casella di testo (questo consente alla domanda e alla risposta del chiamante di essere inoltrati all'agente che risponde).</span><span class="sxs-lookup"><span data-stu-id="3858e-238">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3858e-239">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="3858e-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="3858e-240">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3858e-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="3858e-241">In **risposta 1**specificare la prima risposta possibile alla domanda eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3858e-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3858e-242">Non usare le virgolette (") in qualsiasi risposta vocale.</span><span class="sxs-lookup"><span data-stu-id="3858e-242">Do not use quotation marks (") in any voice responses.</span></span> <span data-ttu-id="3858e-243">Le virgolette causano un errore di IVR.</span><span class="sxs-lookup"><span data-stu-id="3858e-243">Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-244">Puoi scegliere di consentire ai chiamanti di rispondere usando il riconoscimento vocale, l'input della tastiera alfanumerica o entrambi.</span><span class="sxs-lookup"><span data-stu-id="3858e-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="3858e-245">Se si vuole consentire al chiamante di rispondere con il riconoscimento vocale, immettere la risposta in **immettere una risposta vocale**.</span><span class="sxs-lookup"><span data-stu-id="3858e-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="3858e-246">Se si vuole consentire al chiamante di rispondere premendo un tasto sulla tastiera, nella **cifra**fare clic sulla cifra del tastierino numerico.</span><span class="sxs-lookup"><span data-stu-id="3858e-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="3858e-247">Specificare se instradare il chiamante a una coda oppure porre un'altra domanda nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3858e-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="3858e-248">Per instradare il chiamante a una coda, fare clic su **Invia a una coda**e in **selezionare una coda**fare clic sulla coda che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="3858e-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="3858e-249">Per porre un'altra domanda, fare clic su **Richiedi un'altra domanda**e quindi fare clic su **USA sintesi vocale** e digitare la domanda oppure fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="3858e-249">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**.</span></span> <span data-ttu-id="3858e-250">Usare i raggruppamenti di risposta in questa sezione per specificare fino a quattro possibili risposte alla domanda aggiuntiva e alla coda da usare per ogni risposta.</span><span class="sxs-lookup"><span data-stu-id="3858e-250">Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response.</span></span> <span data-ttu-id="3858e-251">Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo **Response 3** o sulla casella di controllo **Response 4** .</span><span class="sxs-lookup"><span data-stu-id="3858e-251">To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="3858e-252">Specificare fino a tre risposte più possibili alla domanda originale ripetendo i passaggi 28 e 29 per specificare le possibili risposte e l'azione da eseguire per ogni risposta.</span><span class="sxs-lookup"><span data-stu-id="3858e-252">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response.</span></span> <span data-ttu-id="3858e-253">Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo Rispondi **3** o sulla casella di controllo **risposta 4** .</span><span class="sxs-lookup"><span data-stu-id="3858e-253">To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="3858e-254">Fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="3858e-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="3858e-255">Per usare Windows PowerShell per creare o modificare un flusso di lavoro interattivo</span><span class="sxs-lookup"><span data-stu-id="3858e-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="3858e-256">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="3858e-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="3858e-257">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3858e-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3858e-258">Recuperare il nome del servizio per il servizio Response Group e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="3858e-258">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="3858e-259">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="3858e-259">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="3858e-260">Un flusso di lavoro interattivo richiede due o più code e due o più gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="3858e-260">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="3858e-261">Prima di tutto, crea i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="3858e-261">First, create the agent groups.</span></span> <span data-ttu-id="3858e-262">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-262">Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="3858e-263">Creare le code.</span><span class="sxs-lookup"><span data-stu-id="3858e-263">Create the queues.</span></span> <span data-ttu-id="3858e-264">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-264">Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="3858e-265">Creare il primo prompt di Response Group.</span><span class="sxs-lookup"><span data-stu-id="3858e-265">Create the first response group prompt.</span></span> <span data-ttu-id="3858e-266">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-266">Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="3858e-267">Crea quindi l'azione da eseguire dopo il prompt.</span><span class="sxs-lookup"><span data-stu-id="3858e-267">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="3858e-268">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-268">Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="3858e-269">Creare la risposta al primo Response Group.</span><span class="sxs-lookup"><span data-stu-id="3858e-269">Create the first response group answer.</span></span> <span data-ttu-id="3858e-270">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-270">Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="3858e-271">Ora crea il secondo messaggio, l'azione chiama e rispondi.</span><span class="sxs-lookup"><span data-stu-id="3858e-271">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="3858e-272">Crea prima di tutto il prompt.</span><span class="sxs-lookup"><span data-stu-id="3858e-272">First create the prompt.</span></span> <span data-ttu-id="3858e-273">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-273">Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="3858e-274">Creare la seconda azione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3858e-274">Create the second call action.</span></span> <span data-ttu-id="3858e-275">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-275">Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="3858e-276">Creare la seconda risposta di Response Group.</span><span class="sxs-lookup"><span data-stu-id="3858e-276">Create the second response group answer.</span></span> <span data-ttu-id="3858e-277">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-277">Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="3858e-278">Creare la richiesta di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3858e-278">Create the top-level prompt.</span></span> <span data-ttu-id="3858e-279">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-279">Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="3858e-280">Creare la domanda di primo livello.</span><span class="sxs-lookup"><span data-stu-id="3858e-280">Create the top-level question.</span></span> <span data-ttu-id="3858e-281">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-281">Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="3858e-282">Creare ora il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3858e-282">Now create the workflow.</span></span> <span data-ttu-id="3858e-283">Eseguire</span><span class="sxs-lookup"><span data-stu-id="3858e-283">Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3858e-284">Tutti gli utenti designati come Manager di un Response Group devono essere assegnati al ruolo CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="3858e-284">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role.</span></span> <span data-ttu-id="3858e-285">Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="3858e-285">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

