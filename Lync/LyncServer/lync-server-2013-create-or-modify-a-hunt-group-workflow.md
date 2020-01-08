---
title: 'Lync Server 2013: creare o modificare un flusso di lavoro di gruppo di ricerca'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="5b9b9-102">Creare o modificare un flusso di lavoro di gruppo di ricerca in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9b9-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b9b9-103">_**Argomento Ultima modifica:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="5b9b9-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="5b9b9-104">Usare una delle procedure seguenti per creare o modificare un flusso di lavoro di gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b9b9-105">È possibile usare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare i flussi di lavoro di gruppo di ricerca.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="5b9b9-106">È possibile accedere allo strumento di configurazione del gruppo di risposte dal pannello di controllo di Lync Server oppure aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="5b9b9-107">Per usare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro di Hunt Group</span><span class="sxs-lookup"><span data-stu-id="5b9b9-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="5b9b9-108">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="5b9b9-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5b9b9-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5b9b9-111">Nella barra di spostamento sinistra fare clic su **gruppi di risposte**e quindi su flusso di **lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="5b9b9-112">Nella pagina **flusso di lavoro** fare clic su **Crea o modifica flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="5b9b9-113">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si vuole creare o modificare.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="5b9b9-114">Nell'elenco dei servizi risultante fare clic sul servizio desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-115">Viene aperto lo strumento di configurazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="5b9b9-116">È anche possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="5b9b9-117">Esegui una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="5b9b9-118">In **creare un nuovo flusso di lavoro**, accanto a **Cerca gruppo, fare clic su Crea**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="5b9b9-119">In **Gestisci un flusso di lavoro esistente**individuare il flusso di lavoro che si vuole modificare e quindi in **azione**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="5b9b9-120">Se si è pronti per gli utenti a iniziare a chiamare il flusso di lavoro, selezionare **attiva il flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-121">Per creare un flusso di lavoro gestito, è necessario selezionare <STRONG>attiva il flusso di lavoro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="5b9b9-122">Dopo aver salvato il flusso di lavoro attivo e gestito, è possibile modificarlo e disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="5b9b9-123">Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per Federazione** .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="5b9b9-124">Devi anche avere un criterio di accesso esterno che si applica all'applicazione di Response Group configurata per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-125">I criteri di accesso esterno globale si applicano all'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="5b9b9-126">Puoi configurare il criterio globale per la Federazione dei gruppi di risposta usando il pannello di controllo di Lync Server o usando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="5b9b9-127">Tieni presente che le impostazioni dei criteri globali si applicano a tutti gli utenti, a meno che non vengano assegnati criteri per un sito o un utente.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="5b9b9-128">Pertanto, prima di modificare questa impostazione per i gruppi di risposta, verificare che l'impostazione della Federazione soddisfi i requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="5b9b9-129">Per informazioni dettagliate su come applicare i criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestire i criteri di accesso esterno in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="5b9b9-130">Per informazioni dettagliate sull'impostazione della Federazione, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-131">Gli utenti ospitati in Lync Online non possono inserire le chiamate ai gruppi di risposte ospitati in una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="5b9b9-132">Questo vale sia per le distribuzioni ibride sia per i casi in cui una distribuzione locale è federata con una distribuzione Lync Online.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="5b9b9-133">Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita agente anonimato** .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-134">Le chiamate anonime non possono iniziare con la messaggistica istantanea (IM) o il video, anche se l'agente o il chiamante può aggiungere messaggi istantanei e video dopo che la chiamata è stata stabilita.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="5b9b9-135">Un agente anonimo può anche inserire chiamate in attesa, trasferire chiamate (sia i trasferimenti non vedenti che consultivi) e parcheggiare e recuperare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="5b9b9-136">Le chiamate anonime non supportano le conferenze, la condivisione di applicazioni e la condivisione desktop, il trasferimento di file, la lavagna e la collaborazione ai dati e la registrazione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="5b9b9-137">Gli agenti che usano il plug-in di Lync VDI possono ricevere chiamate in arrivo in forma anonima, ma non possono effettuare chiamate in uscita in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="5b9b9-138">In **immettere l'indirizzo del gruppo che riceverà le chiamate**Digitare l'indirizzo URI (Uniform Resource Identifier) SIP principale del gruppo che risponderà alle chiamate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-139">L'URI principale di un flusso di lavoro è la modalità di identificazione e riferimento del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="5b9b9-140">L'URI SIP immesso viene creato come oggetto contatto in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="5b9b9-141">Per creare l'URI, l'oggetto deve essere univoco in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="5b9b9-142">In **nome visualizzato**Digitare il nome che si vuole visualizzare per il flusso di lavoro (ad esempio, Sales Response Group).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-143">Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="5b9b9-144">Non usare i nomi visualizzati seguenti perché sono riservati: <STRONG>Watcher presenza di RGS</STRONG> o <STRONG>servizio di annuncio</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="5b9b9-145">In **numero di telefono**Digitare l'URI di linea per il gruppo di risposte, ad esempio + 14255550165.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="5b9b9-146">In **numero di visualizzazione**Digitare il numero che si vuole visualizzare per il gruppo di risposte, ad esempio + 1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="5b9b9-147">Opzionale In **Descrizione**Digitare una descrizione per il flusso di lavoro che si vuole visualizzare nella scheda contatto del client Lync.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="5b9b9-148">In **tipo flusso di lavoro**selezionare **gestito** se il flusso di lavoro verrà gestito da un responsabile del gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="5b9b9-149">Eseguire le operazioni seguenti per assegnare i responsabili del gruppo di risposte al flusso di lavoro:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="5b9b9-150">Digitare l'URI SIP di un Manager per il flusso di lavoro e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="5b9b9-151">Digitare l'URI SIP di altri responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5b9b9-152">A tutti gli utenti designati come Manager di un Response Group deve essere assegnato il ruolo CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-152">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="5b9b9-153">Se questo ruolo non viene assegnato agli utenti, non è possibile gestire i gruppi di risposta.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-153">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="5b9b9-154">In **passaggio 2 Selezionare una lingua**, fare clic sulla lingua che si vuole usare per il riconoscimento vocale e la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="5b9b9-155">Se si vuole configurare un messaggio di benvenuto, in **passaggio 3 configurare un messaggio di benvenuto**, selezionare la casella di controllo **Riproduci un messaggio** di benvenuto e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5b9b9-156">Per immettere il messaggio di benvenuto come testo convertito in vocale per i chiamanti, fare clic su **USA sintesi vocale**e quindi digitare il messaggio di benvenuto nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-157">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-157">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="5b9b9-158">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-158">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="5b9b9-159">Per usare una registrazione di file Wave (WAV) o Windows Media Audio (con estensione WMA) per il messaggio di benvenuto, fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-159">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="5b9b9-160">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-160">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="5b9b9-161">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file audio che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-161">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="5b9b9-162">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-162">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-163">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="5b9b9-164">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="5b9b9-165">In **passaggio 4 specificare gli orari di ufficio**, nel **fuso orario**, fare clic sul fuso orario per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-166">Il fuso orario è il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-166">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="5b9b9-167">Viene usato per calcolare le ore di apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-167">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="5b9b9-168">Ad esempio, se il flusso di lavoro è configurato per l'uso del fuso orario orientale nordamericano e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-168">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="5b9b9-169">e chiudere alle 11:00 P.M. gli orari di apertura e chiusura si presume siano 7:00 Eastern Time e 23:00 Eastern Time rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-169">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively.</span></span> <span data-ttu-id="5b9b9-170">È necessario immettere gli orari nella notazione a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-170">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="5b9b9-171">Selezionare il tipo di pianificazione delle ore lavorative che si vuole usare eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="5b9b9-172">Per usare una programmazione predefinita per le ore lavorative, fare clic su **Usa una programmazione preimpostata**e quindi selezionare la programmazione da usare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-173">Per selezionare questa opzione, è necessario aver definito almeno una programmazione preimpostata.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="5b9b9-174">Puoi definire le pianificazioni predefinite usando il cmdlet <STRONG>New-CsRgsHoursOfBusiness</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="5b9b9-175">Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire le ore lavorative per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-176">Quando si seleziona una programmazione preimpostata, il <STRONG>giorno</STRONG>, l' <STRONG>apertura</STRONG>e la <STRONG>chiusura</STRONG> vengono automaticamente riempiti con i giorni e le ore che il gruppo di risposte è disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="5b9b9-177">Per usare una pianificazione personalizzata che si applica solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="5b9b9-178">Se si sta creando una pianificazione personalizzata per il flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il gruppo di risposte è disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="5b9b9-179">Se si sta creando una pianificazione personalizzata, digitare le ore di **apertura** e **chiusura** per ogni giorno della settimana in cui il gruppo di risposte è disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-180">Le ore di <STRONG>apertura</STRONG> e <STRONG>chiusura</STRONG> devono essere in notazione oraria 24 ore.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-180">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation.</span></span> <span data-ttu-id="5b9b9-181">Ad esempio, se il tuo ufficio lavora a un giorno lavorativo da 9 a 5 e chiude a mezzogiorno per pranzo, gli orari di apertura sono specificati come <STRONG>apri</STRONG> 9:00, <STRONG>Chiudi</STRONG> 12:00, <STRONG>Apri</STRONG> 13:00 e <STRONG>Chiudi</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-181">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="5b9b9-182">Se si vuole riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il gruppo di risposte si trova al di fuori degli orari lavorativi** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="5b9b9-183">Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-184">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-184">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="5b9b9-185">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-185">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="5b9b9-186">Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-186">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="5b9b9-187">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-187">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="5b9b9-188">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-188">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="5b9b9-189">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-189">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-190">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="5b9b9-191">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="5b9b9-192">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="5b9b9-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="5b9b9-193">Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="5b9b9-194">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="5b9b9-195">Il formato per l'indirizzo della segreteria \<telefonica\>@\<è nomeutente\> NomeDominio (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="5b9b9-196">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="5b9b9-197">Il formato per l'indirizzo utente è \<nomeutente\>@\<NomeDominio\>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="5b9b9-198">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="5b9b9-199">Il formato per il numero di telefono \<è\>@\<Number NomeDominio\> , ad esempio + 14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="5b9b9-200">Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="5b9b9-201">In **passaggio 5 specificare le festività**, fare clic sulle caselle di controllo relative a uno o più set di festività che definiscono i giorni in cui il gruppo di risposte viene chiuso per le aziende.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-202">Prima di configurare il flusso di lavoro, è necessario definire le festività e i set di festività.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="5b9b9-203">Usare i cmdlet <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> per definire festività e set di festività.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="5b9b9-204">Per informazioni dettagliate, vedere <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(facoltativo) definire set di festività di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="5b9b9-205">Se si vuole riprodurre un messaggio in festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività** e quindi specificare il messaggio da riprodurre eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="5b9b9-206">Per immettere il messaggio come testo convertito in vocale per il chiamante, fare clic su **USA sintesi vocale**e quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-207">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-207">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="5b9b9-208">Se si includono tag HTML, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-208">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="5b9b9-209">Per usare una registrazione di file audio per il messaggio, fare clic su **Seleziona una registrazione**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-209">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="5b9b9-210">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **registrazione** .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-210">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="5b9b9-211">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-211">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="5b9b9-212">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-212">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-213">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="5b9b9-214">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="5b9b9-215">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="5b9b9-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="5b9b9-216">Per disconnettere la chiamata, fare clic su **Disconnetti chiamata**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="5b9b9-217">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **inoltra alla**segreteria telefonica e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="5b9b9-218">Il formato per l'indirizzo della segreteria \<telefonica\>@\<è nomeutente\> NomeDominio (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="5b9b9-219">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra all'URI SIP**e quindi digitare un indirizzo utente.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="5b9b9-220">Il formato per l'indirizzo utente è \<nomeutente\>@\<NomeDominio\>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="5b9b9-221">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **inoltra al numero di**telefono e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="5b9b9-222">Il formato per il numero di telefono \<è\>@\<Number NomeDominio\> , ad esempio + 14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="5b9b9-223">Il nome di dominio viene usato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="5b9b9-224">In **passaggio 6 configurare una coda**in **selezionare la coda che riceverà le chiamate**Selezionare la coda che si vuole includere per i chiamanti fino a quando non sarà disponibile un agente.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="5b9b9-225">In **passaggio 7 configurare la musica in attesa**, scegliere la musica che si vuole che i chiamanti ascoltino in attesa di un agente eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="5b9b9-226">Per usare la registrazione predefinita per la musica in attesa, fare clic su **Usa impostazione predefinita**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="5b9b9-227">Per usare una registrazione di file audio per la musica in attesa, fare clic su **Seleziona un file musicale**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-227">To use an audio file recording for the music on hold, click **Select a music file**.</span></span> <span data-ttu-id="5b9b9-228">Se si vuole caricare un nuovo file audio, fare clic sul collegamento **a un file musicale** .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-228">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="5b9b9-229">Nella finestra del nuovo browser fare clic su **Sfoglia**, selezionare il file che si vuole usare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-229">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="5b9b9-230">Fare clic su **carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-230">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5b9b9-231">Tutti i file audio forniti dall'utente devono soddisfare determinati requisiti.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="5b9b9-232">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">requisiti tecnici per il gruppo di risposte in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="5b9b9-233">Fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="5b9b9-234">Per usare Windows PowerShell per creare o modificare un flusso di lavoro di gruppo di ricerca</span><span class="sxs-lookup"><span data-stu-id="5b9b9-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="5b9b9-235">Accedere come membro del gruppo RTCUniversalServerAdmins o come membro di uno dei ruoli amministrativi predefiniti che supportano il gruppo di risposte.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="5b9b9-236">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5b9b9-237">Creare il prompt da riprodurre per il messaggio di benvenuto e salvarlo in una variabile.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-237">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="5b9b9-238">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-238">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="5b9b9-239">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-240">Per usare un file audio per la richiesta, usare il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5b9b9-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="5b9b9-241">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="5b9b9-242">Ottenere l'identità della coda o della domanda in cui verranno indirizzate le chiamate.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="5b9b9-243">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="5b9b9-244">Per informazioni dettagliate sulla creazione della coda, vedere [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="5b9b9-245">Definire l'azione predefinita da intraprendere quando un flusso di lavoro viene aperto durante l'orario di ufficio e salvarlo in una variabile.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-245">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="5b9b9-246">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-246">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-247">Per i flussi di lavoro di gruppo di ricerca, l'azione predefinita deve indirizzare la chiamata a una coda.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-247">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="5b9b9-248">Questo parametro è obbligatorio per i flussi di lavoro attivi.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-248">This is parameter is required for active workflows.</span></span> <span data-ttu-id="5b9b9-249">Non è necessario per i flussi di lavoro inattivi.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-249">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="5b9b9-250">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="5b9b9-251">Se si vogliono definire le ore di lavoro e le festività, è necessario crearle prima di creare o modificare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="5b9b9-252">Per informazioni dettagliate, vedere [(facoltativo) definire le ore lavorative per il gruppo di risposte in Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) e [(facoltativo) definire set di festività di Response Group in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="5b9b9-253">Se si vogliono ricevere richieste per le chiamate ricevute fuori sede o in vacanza, usare il cmdlet **New-CsRgsPrompt** per definire il prompt e usare il **nuovo CsRgsCallAction** per definire l'azione da eseguire dopo il prompt.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="5b9b9-254">Per informazioni dettagliate, vedere [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="5b9b9-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="5b9b9-255">Recuperare il nome del servizio per il servizio Response Group di Lync Server e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="5b9b9-256">Al comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="5b9b9-257">Creare o modificare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-257">Create or modify the workflow.</span></span> <span data-ttu-id="5b9b9-258">Per creare un flusso di lavoro, USA **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="5b9b9-259">Per modificare un flusso di lavoro, usare **Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="5b9b9-260">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="5b9b9-261">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5b9b9-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5b9b9-262">A tutti gli utenti designati come Manager per i flussi di lavoro deve essere assegnato il ruolo CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="5b9b9-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5b9b9-263">Per informazioni dettagliate sui parametri facoltativi aggiuntivi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="5b9b9-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b9b9-264">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b9b9-264">See Also</span></span>


[<span data-ttu-id="5b9b9-265">Opzionale Definire set di festività di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9b9-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="5b9b9-266">Opzionale Definire le ore lavorative per il gruppo di risposte in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9b9-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="5b9b9-267">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="5b9b9-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="5b9b9-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="5b9b9-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="5b9b9-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="5b9b9-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="5b9b9-270">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="5b9b9-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

