---
title: 'Lync Server 2013: creare o modificare un flusso di lavoro interattivo'
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
ms.openlocfilehash: 93df8640593769b7b90d8b4e157133f8f7df2f19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="661bf-102">Creare o modificare un flusso di lavoro interattivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="661bf-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="661bf-103">_**Ultimo argomento modificato:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="661bf-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="661bf-104">Per creare o modificare un flusso di lavoro interattivo, utilizzare una delle procedure seguenti.</span><span class="sxs-lookup"><span data-stu-id="661bf-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="661bf-105">È possibile utilizzare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare flussi di lavoro interattivi.</span><span class="sxs-lookup"><span data-stu-id="661bf-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="661bf-106">È possibile accedere allo strumento di configurazione di Response Group dal pannello di controllo di Lync Server o aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;FQDNpoolWeb&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="661bf-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="661bf-107">Per utilizzare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro interattivo</span><span class="sxs-lookup"><span data-stu-id="661bf-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="661bf-108">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="661bf-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="661bf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="661bf-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="661bf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="661bf-111">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="661bf-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="661bf-112">Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="661bf-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="661bf-113">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera creare o modificare.</span><span class="sxs-lookup"><span data-stu-id="661bf-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="661bf-114">Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="661bf-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-115">Verrà aperto lo strumento di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="661bf-116">È inoltre possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando il seguente URL: <STRONG>https://</STRONG>&lt;FQDNpoolWeb&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="661bf-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="661bf-117">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="661bf-118">In **Crea un nuovo flusso di lavoro**, accanto a **interattivo**, fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="661bf-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="661bf-119">In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro che si desidera modificare e quindi fare clic su **Modifica** in **Azione**.</span><span class="sxs-lookup"><span data-stu-id="661bf-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="661bf-120">Se non si desidera che gli utenti chiamino il flusso di lavoro immediatamente, deselezionare la casella di controllo **Attiva il flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="661bf-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-p105">Se si desidera creare un flusso di lavoro gestito, selezionare <STRONG>Attiva il flusso di lavoro</STRONG>. Dopo aver salvato il flusso di lavoro gestito attivo, è possibile modificarlo e disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="661bf-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="661bf-123">Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per federazione**.</span><span class="sxs-lookup"><span data-stu-id="661bf-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="661bf-124">È inoltre necessario disporre di un criterio di accesso esterno che si applica all'applicazione Response Group configurata per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="661bf-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-125">Il criterio di accesso esterno globale è valido per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="661bf-126">È possibile configurare i criteri globali per la Federazione dei Response Group utilizzando il pannello di controllo di Lync Server oppure utilizzando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true.</span><span class="sxs-lookup"><span data-stu-id="661bf-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="661bf-127">Considerare che le impostazioni di criteri globali vengono applicate a tutti gli utenti, a meno che non dispongano di un criterio sito o utente assegnato.</span><span class="sxs-lookup"><span data-stu-id="661bf-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="661bf-128">Prima di modificare questa impostazione per i Response Group, verificare quindi che le impostazioni della federazione soddisfino i requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="661bf-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="661bf-129">Per informazioni dettagliate sulla modalità di applicazione dei criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external Access Policy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="661bf-130">Per informazioni dettagliate sull'impostazione di federazione, vedere <STRONG>Set-CsExternalAccessPolicy</STRONG> nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="661bf-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-131">Gli utenti ospitati in Lync Online non possono effettuare chiamate ai Response Group ospitate in una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="661bf-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="661bf-132">Questo è vero sia nelle distribuzioni ibride sia nei casi in cui una distribuzione locale è federata con una distribuzione di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="661bf-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="661bf-133">Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita anonimato agente**.</span><span class="sxs-lookup"><span data-stu-id="661bf-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-134">Le chiamate anonime non possono iniziare con un messaggio istantaneo o un video, sebbene l'agente o il chiamante possa aggiungere messaggi istantanei e video dopo l'attivazione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="661bf-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="661bf-135">Un agente anonimo può inoltre mettere le chiamate in attesa, eseguire trasferimenti di chiamata, nascosti o con consultazione del destinatario, nonché parcheggiare e recuperare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="661bf-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="661bf-136">Per le chiamate anonime non sono supportate conferenze, condivisione di applicazioni, condivisione del desktop, trasferimenti di file, collaborazione con lavagna e sui dati e registrazione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="661bf-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="661bf-137">Gli agenti che utilizzano il plug-in di Lync VDI sono in grado di ricevere le chiamate in arrivo anonime, ma non possono effettuare chiamate in uscita in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="661bf-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="661bf-138">In **Immettere l'indirizzo del gruppo che riceverà le chiamate** digitare l'indirizzo URI (Uniform Resource Identifier) SIP primario del gruppo che dovrà rispondere alle chiamate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="661bf-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="661bf-139">In **nome visualizzato**Digitare il nome che si desidera visualizzare per il flusso di lavoro, ad esempio Sales IVR Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-140">Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="661bf-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="661bf-141">Non utilizzare i nomi visualizzati seguenti poiché sono riservati: RGS Presence Watcher o Servizio Annuncio.</span><span class="sxs-lookup"><span data-stu-id="661bf-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="661bf-142">In **Numero di telefono** digitare l'URI di linea per il Response Group, ad esempio +14255550165.</span><span class="sxs-lookup"><span data-stu-id="661bf-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="661bf-143">In **Numero visualizzato** digitare il numero nel modo in cui si desidera venga visualizzato per il Response Group, ad esempio +1 (425) 555-0165.</span><span class="sxs-lookup"><span data-stu-id="661bf-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="661bf-144">Optional In **Descrizione**Digitare una descrizione per il flusso di lavoro che si desidera venga visualizzata nella scheda contatto nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="661bf-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="661bf-145">In **Tipo di flusso di lavoro** selezionare **Gestito** se il flusso di lavoro verrà gestito da un responsabile di Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="661bf-146">Per assegnare i responsabili dei Response Group al flusso di lavoro, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="661bf-147">Digitare l'URI SIP di un responsabile per il flusso di lavoro e fare clic su **Aggiungi**..</span><span class="sxs-lookup"><span data-stu-id="661bf-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="661bf-148">Digitare l'URI SIP di ulteriori responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**..</span><span class="sxs-lookup"><span data-stu-id="661bf-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="661bf-p112">A ogni utente designato come responsabile di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="661bf-151">In **Passaggio 2 Selezionare una lingua** fare clic sulla lingua da utilizzare per il riconoscimento vocale e la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="661bf-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="661bf-152">Se si desidera configurare un messaggio di benvenuto, in **Passaggio 3 Configurare un messaggio di benvenuto** selezionare la casella di controllo **Riprodurre un messaggio di benvenuto**, quindi effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="661bf-153">Per immettere il messaggio di benvenuto come testo della sintesi vocale per i chiamanti, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="661bf-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-154">Non includere tag HTML nel testo immesso.</span><span class="sxs-lookup"><span data-stu-id="661bf-154">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="661bf-155">Se si includono tag HTML verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="661bf-155">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="661bf-p114">Per utilizzare la registrazione di un file Wave o Windows Media Audio per il messaggio di benvenuto, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="661bf-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-160">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="661bf-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="661bf-161">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="661bf-162">In **Passaggio 4 Specificare l'orario di ufficio** fare clic sul fuso orario del flusso di lavoro nella casella **Fuso orario**.</span><span class="sxs-lookup"><span data-stu-id="661bf-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-163">È necessario specificare il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="661bf-163">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="661bf-164">Il fuso orario viene utilizzato per calcolare le ore di apertura e di chiusura.</span><span class="sxs-lookup"><span data-stu-id="661bf-164">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="661bf-165">Ad esempio, se il flusso di lavoro è configurato per l'utilizzo del fuso orario orientale del Nord America e il flusso di lavoro è programmato per l'apertura alle 7:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="661bf-165">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="661bf-166">e chiudere alle 11:00 P.M., gli orari di apertura e di chiusura sono considerati rispettivamente 7:00 Eastern Time e 11:00 Eastern Time.</span><span class="sxs-lookup"><span data-stu-id="661bf-166">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively.</span></span> <span data-ttu-id="661bf-167">È necessario immettere le ore nel formato a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="661bf-167">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="661bf-168">Selezionare il tipo di pianificazione dell'orario di ufficio che si desidera utilizzare eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="661bf-169">Per utilizzare una pianificazione dell'orario di ufficio predefinita, fare clic su **Usa pianificazione preimpostata**, quindi selezionare la pianificazione che si desidera utilizzare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="661bf-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-170">Per potere selezionare questa opzione, è necessario che in precedenza sia stata definita almeno una pianificazione preimpostata.</span><span class="sxs-lookup"><span data-stu-id="661bf-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="661bf-171">Per definire le pianificazioni preimpostate, utilizzare il cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="661bf-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="661bf-172">Per ulteriori informazioni, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire gli orari di ufficio di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="661bf-173">Quando si seleziona una pianificazione preimpostata, nei campi <STRONG>Giorno</STRONG>, <STRONG>Apri</STRONG> e <STRONG>Chiudi</STRONG> vengono inseriti automaticamente i giorni e le ore in cui il Response Group è disponibile.</span><span class="sxs-lookup"><span data-stu-id="661bf-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="661bf-174">Per utilizzare una pianificazione personalizzata da applicare solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="661bf-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="661bf-175">Se si crea una pianificazione personalizzata per questo flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il Response Group è disponibile.</span><span class="sxs-lookup"><span data-stu-id="661bf-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="661bf-176">Se si crea una pianificazione personalizzata, digitare le ore in **Apri** e **Chiudi** in cui il Response Group è disponibile.</span><span class="sxs-lookup"><span data-stu-id="661bf-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-p118">Le ore in <STRONG>Apri</STRONG> e <STRONG>Chiudi</STRONG> devono essere nel formato a 24 ore. Se l'ufficio, ad esempio, è operativo dalle 9.00 alle 17.00 con una pausa per il pranzo a mezzogiorno, è possibile specificare l'orario di ufficio impostando <STRONG>Apri</STRONG> su 9.00, <STRONG>Chiudi</STRONG> su 12.00, quindi di nuovo <STRONG>Apri</STRONG> su 13.00 e <STRONG>Chiudi</STRONG> su 17.00.</span><span class="sxs-lookup"><span data-stu-id="661bf-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="661bf-179">Se si desidera riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il Response Group non è durante l'orario di ufficio**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="661bf-180">Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="661bf-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-p119">Non includere tag HTML nel testo immesso o verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="661bf-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="661bf-p120">Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="661bf-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-187">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="661bf-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="661bf-188">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="661bf-189">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="661bf-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="661bf-190">Per interrompere la chiamata, fare clic su **Interrompi chiamata**.</span><span class="sxs-lookup"><span data-stu-id="661bf-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="661bf-191">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="661bf-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="661bf-192">Il formato dell'indirizzo di segreteria telefonica \<è\>@\<nomeutente DomainName\> (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="661bf-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="661bf-193">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="661bf-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="661bf-194">Il \<formato dell'indirizzo utente è nomeutente\>@\<domainname.\></span><span class="sxs-lookup"><span data-stu-id="661bf-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="661bf-195">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="661bf-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="661bf-196">Il formato del numero di telefono è \<il\>@\<numero di\> dominio (ad esempio, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="661bf-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="661bf-197">Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="661bf-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="661bf-198">In **Passaggio 5 Specificare le festività** fare clic sulle caselle di controllo per uno o più insiemi di festività che definiscono i giorni in cui il Response Group è chiuso.</span><span class="sxs-lookup"><span data-stu-id="661bf-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-199">È necessario definire le festività e i relativi insiemi prima di configurare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="661bf-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="661bf-200">Utilizzare i cmdlet <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> per definire le festività e i relativi insiemi.</span><span class="sxs-lookup"><span data-stu-id="661bf-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="661bf-201">Per ulteriori informazioni, vedere <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(facoltativo) definire i set di festività di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="661bf-202">Se si desidera riprodurre un messaggio delle festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="661bf-203">Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="661bf-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-p126">Non includere tag HTML nel testo immesso o verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="661bf-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="661bf-p127">Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="661bf-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-210">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="661bf-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="661bf-211">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="661bf-212">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="661bf-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="661bf-213">Per interrompere la chiamata, fare clic su **Interrompi chiamata**.</span><span class="sxs-lookup"><span data-stu-id="661bf-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="661bf-214">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="661bf-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="661bf-215">Il formato dell'indirizzo di segreteria telefonica \<è\>@\<nomeutente DomainName\> (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="661bf-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="661bf-216">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="661bf-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="661bf-217">Il \<formato dell'indirizzo utente è nomeutente\>@\<domainname.\></span><span class="sxs-lookup"><span data-stu-id="661bf-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="661bf-218">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="661bf-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="661bf-219">Il formato del numero di telefono è \<il\>@\<numero di\> dominio (ad esempio, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="661bf-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="661bf-220">Il nome di dominio viene utilizzato per il routing del chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="661bf-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="661bf-221">In **Passaggio 6 Configurare la musica di attesa** scegliere la musica che si desidera riprodurre per i chiamanti in attesa della risposta di un agente effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="661bf-222">Per utilizzare la registrazione musicale predefinita per le chiamate in attesa, fare clic su **Usa predefinito**.</span><span class="sxs-lookup"><span data-stu-id="661bf-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="661bf-p132">Per utilizzare la registrazione di un file audio per la musica di attesa, fare clic su **Selezionare un file musicale**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **un file musicale**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare e quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="661bf-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-227">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="661bf-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="661bf-228">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="661bf-229">In **Passaggio 7 Configurare Interactive Voice Response** specificare la domanda da rivolgere al chiamante nell'intestazione **L'utente ascolterà il seguente testo o messaggio registrato** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="661bf-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="661bf-230">Per immettere la domanda in formato testo, fare clic su **Usa sintesi vocale**, quindi digitare la domanda nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="661bf-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-p134">Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="661bf-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-233">Il simbolo "#" viene convertito nella parola "numero" dal motore di sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="661bf-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="661bf-234">Se è necessario fare riferimento al tasto #, utilizzare il nome del tasto anziché il simbolo nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="661bf-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="661bf-235">Ad esempio, "Per parlare con il reparto vendite, premere cancelletto".</span><span class="sxs-lookup"><span data-stu-id="661bf-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="661bf-p136">Per utilizzare un file con audio preregistrato contenente la domanda, fare clic su **Selezionare una registrazione**, quindi fare clic sul collegamento **una registrazione** per caricare il file. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file, quindi facoltativamente è possibile digitare la domanda nella casella di testo. In questo modo la domanda e la risposta del chiamante verranno inoltrate all'agente che risponde.</span><span class="sxs-lookup"><span data-stu-id="661bf-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="661bf-239">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="661bf-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="661bf-240">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="661bf-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="661bf-241">In **Risposta 1** specificare la prima risposta possibile alla domanda effettuando le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="661bf-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="661bf-p138">Non utilizzare le virgolette doppie (") nelle risposte vocali poiché il sistema IVR potrebbe non funzionare.</span><span class="sxs-lookup"><span data-stu-id="661bf-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-244">È possibile scegliere di consentire ai chiamanti di rispondere a voce o tramite tastierino alfanumerico oppure in entrambi i modi.</span><span class="sxs-lookup"><span data-stu-id="661bf-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="661bf-245">Se si desidera consentire al chiamante di rispondere a voce, immettere la risposta in **Immettere una risposta vocale**.</span><span class="sxs-lookup"><span data-stu-id="661bf-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="661bf-246">Se si desidera consentire al chiamante di rispondere premendo un tasto, in **Cifra** fare clic sulla cifra desiderata.</span><span class="sxs-lookup"><span data-stu-id="661bf-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="661bf-247">Specificare se instradare il chiamante a una coda o se formulare un'altra domanda nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="661bf-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="661bf-248">Per instradare il chiamante a una coda, fare clic su **Invia a una coda** e in **Seleziona una coda** fare clic sulla coda che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="661bf-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="661bf-p139">Per rivolgere un'altra domanda, fare clic su **Formula un'altra domanda**, quindi fare clic su **Usa sintesi vocale** e digitare la domanda oppure fare clic su **Selezionare una registrazione**. Utilizzare i raggruppamenti di risposte di questa sezione per specificare un massimo di quattro possibili risposte alla domanda aggiuntiva e la coda da utilizzare per ogni risposta. Per specificare una terza o una quarta possibile risposta, fare clic sulla casella di controllo **Risposta 3** o **Risposta 4**.</span><span class="sxs-lookup"><span data-stu-id="661bf-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="661bf-252">Specificare un massimo di altre tre possibili risposte alla domanda originale ripetendo i passaggi 28 e 29 per definire le possibili risposte e l'azione da intraprendere per ciascuna risposta.</span><span class="sxs-lookup"><span data-stu-id="661bf-252">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response.</span></span> <span data-ttu-id="661bf-253">Per specificare una terza o quarta risposta possibile, fare clic sulla casella di controllo **Response 3** o la casella di controllo **Response 4** .</span><span class="sxs-lookup"><span data-stu-id="661bf-253">To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="661bf-254">Fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="661bf-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="661bf-255">Per utilizzare Windows PowerShell per creare o modificare un flusso di lavoro interattivo</span><span class="sxs-lookup"><span data-stu-id="661bf-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="661bf-256">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="661bf-257">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="661bf-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="661bf-258">Recuperare il nome del servizio Response Group Service e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="661bf-258">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="661bf-259">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="661bf-259">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="661bf-260">Un flusso di lavoro interattivo richiede due o più code e due o più gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="661bf-260">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="661bf-261">Per prima cosa, creare i gruppi di agenti.</span><span class="sxs-lookup"><span data-stu-id="661bf-261">First, create the agent groups.</span></span> <span data-ttu-id="661bf-262">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-262">Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="661bf-263">Creare le code.</span><span class="sxs-lookup"><span data-stu-id="661bf-263">Create the queues.</span></span> <span data-ttu-id="661bf-264">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-264">Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="661bf-265">Creare il primo prompt di Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-265">Create the first response group prompt.</span></span> <span data-ttu-id="661bf-266">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-266">Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="661bf-267">Creare quindi l'azione da eseguire dopo il prompt.</span><span class="sxs-lookup"><span data-stu-id="661bf-267">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="661bf-268">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-268">Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="661bf-269">Creare la risposta del primo Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-269">Create the first response group answer.</span></span> <span data-ttu-id="661bf-270">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-270">Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="661bf-271">A questo punto, creare la seconda richiesta, l'azione di chiamata e la risposta.</span><span class="sxs-lookup"><span data-stu-id="661bf-271">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="661bf-272">Creare innanzitutto il prompt.</span><span class="sxs-lookup"><span data-stu-id="661bf-272">First create the prompt.</span></span> <span data-ttu-id="661bf-273">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-273">Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="661bf-274">Creare la seconda azione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="661bf-274">Create the second call action.</span></span> <span data-ttu-id="661bf-275">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-275">Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="661bf-276">Creare la seconda risposta Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-276">Create the second response group answer.</span></span> <span data-ttu-id="661bf-277">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-277">Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="661bf-278">Creare il prompt di primo livello.</span><span class="sxs-lookup"><span data-stu-id="661bf-278">Create the top-level prompt.</span></span> <span data-ttu-id="661bf-279">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-279">Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="661bf-280">Creare la domanda di primo livello.</span><span class="sxs-lookup"><span data-stu-id="661bf-280">Create the top-level question.</span></span> <span data-ttu-id="661bf-281">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-281">Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="661bf-282">A questo punto, creare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="661bf-282">Now create the workflow.</span></span> <span data-ttu-id="661bf-283">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="661bf-283">Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="661bf-284">Tutti gli utenti designati come Manager di un Response Group devono essere assegnati al ruolo CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="661bf-284">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role.</span></span> <span data-ttu-id="661bf-285">Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.</span><span class="sxs-lookup"><span data-stu-id="661bf-285">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

