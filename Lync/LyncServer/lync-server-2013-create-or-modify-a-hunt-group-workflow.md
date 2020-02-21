---
title: 'Lync Server 2013: creare o modificare un flusso di lavoro di un gruppo di risposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e8fd10947bab25e522f35e9cd121a04abbb4a45
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="38123-102">Creare o modificare un flusso di lavoro di un gruppo di risposta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38123-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38123-103">_**Ultimo argomento modificato:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="38123-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="38123-104">Eseguire una delle procedure seguenti per creare o modificare il flusso di lavoro di un gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="38123-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38123-105">È possibile utilizzare Lync Server Management Shell o lo strumento di configurazione di Response Group per creare e modificare i flussi di lavoro del gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="38123-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="38123-106">È possibile accedere allo strumento di configurazione di Response Group dal pannello di controllo di Lync Server o aprendo la pagina Web direttamente da un browser digitando l'URL seguente: <STRONG>https://</STRONG>&lt;FQDNpoolWeb&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38123-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="38123-107">Per utilizzare lo strumento di configurazione di Response Group per creare o modificare un flusso di lavoro di un gruppo di risposta</span><span class="sxs-lookup"><span data-stu-id="38123-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="38123-108">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="38123-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38123-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="38123-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="38123-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="38123-111">Sulla barra di spostamento sinistra fare clic su **Response Group** e quindi su **Flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="38123-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="38123-112">Nella pagina **Flusso di lavoro** fare clic su **Crea o modifica un flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="38123-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="38123-113">Nel campo di ricerca **Seleziona un servizio** digitare tutto o parte del nome del servizio **ApplicationServer** che ospita il flusso di lavoro che si desidera creare o modificare.</span><span class="sxs-lookup"><span data-stu-id="38123-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="38123-114">Nell'elenco di servizi risultante fare clic sul servizio desiderato e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="38123-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-115">Verrà aperto lo strumento di configurazione di Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="38123-116">È inoltre possibile aprire lo strumento di configurazione di Response Group direttamente da un Web browser digitando il seguente URL: <STRONG>https://</STRONG>&lt;FQDNpoolWeb&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38123-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="38123-117">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="38123-118">In **Crea un nuovo flusso di lavoro** fare clic su **Crea** accanto a Gruppo di risposta.</span><span class="sxs-lookup"><span data-stu-id="38123-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="38123-119">In **Gestisci un flusso di lavoro esistente** individuare il flusso di lavoro che si desidera modificare e quindi fare clic su **Modifica** in **Azione**.</span><span class="sxs-lookup"><span data-stu-id="38123-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="38123-120">Se gli utenti possono iniziare a chiamare il flusso di lavoro immediatamente, selezionare **Attiva il flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="38123-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-p105">Se si desidera creare un flusso di lavoro gestito, selezionare <STRONG>Attiva il flusso di lavoro</STRONG>. Dopo aver salvato il flusso di lavoro gestito attivo, è possibile modificarlo e disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="38123-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="38123-123">Per consentire agli utenti federati di chiamare il gruppo, selezionare la casella di controllo **Abilita per federazione**.</span><span class="sxs-lookup"><span data-stu-id="38123-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="38123-124">È inoltre necessario disporre di un criterio di accesso esterno che si applica all'applicazione Response Group configurata per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="38123-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-125">Il criterio di accesso esterno globale è valido per l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="38123-126">È possibile configurare i criteri globali per la Federazione dei Response Group utilizzando il pannello di controllo di Lync Server oppure utilizzando il cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> per impostare il parametro EnableOutsideAccess su true.</span><span class="sxs-lookup"><span data-stu-id="38123-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="38123-127">Considerare che le impostazioni di criteri globali vengono applicate a tutti gli utenti, a meno che non dispongano di un criterio sito o utente assegnato.</span><span class="sxs-lookup"><span data-stu-id="38123-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="38123-128">Prima di modificare questa impostazione per i Response Group, verificare quindi che le impostazioni della federazione soddisfino i requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38123-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="38123-129">Per informazioni dettagliate sulla modalità di applicazione dei criteri agli utenti, vedere <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external Access Policy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="38123-130">Per informazioni dettagliate sull'impostazione di federazione, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-131">Gli utenti ospitati in Lync Online non possono effettuare chiamate ai Response Group ospitate in una distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="38123-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="38123-132">Questo è vero sia nelle distribuzioni ibride sia nei casi in cui una distribuzione locale è federata con una distribuzione di Lync Online.</span><span class="sxs-lookup"><span data-stu-id="38123-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="38123-133">Per nascondere l'identità degli agenti durante le chiamate, selezionare la casella di controllo **Abilita anonimato agente**.</span><span class="sxs-lookup"><span data-stu-id="38123-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-134">Le chiamate anonime non possono iniziare con un messaggio istantaneo o un video, sebbene l'agente o il chiamante possa aggiungere messaggi istantanei e video dopo l'attivazione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="38123-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="38123-135">Un agente anonimo può inoltre mettere le chiamate in attesa, eseguire trasferimenti di chiamata, nascosti o con consultazione del destinatario, nonché parcheggiare e recuperare le chiamate.</span><span class="sxs-lookup"><span data-stu-id="38123-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="38123-136">Per le chiamate anonime non sono supportate conferenze, condivisione di applicazioni, condivisione del desktop, trasferimenti di file, collaborazione con lavagna e sui dati e registrazione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="38123-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="38123-137">Gli agenti che utilizzano il plug-in di Lync VDI sono in grado di ricevere le chiamate in arrivo anonime, ma non possono effettuare chiamate in uscita in modo anonimo.</span><span class="sxs-lookup"><span data-stu-id="38123-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="38123-138">In **Immettere l'indirizzo del gruppo che riceverà le chiamate** digitare l'indirizzo URI (Uniform Resource Identifier) SIP primario del gruppo che dovrà rispondere alle chiamate al flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38123-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-139">L'URI primario di un flusso di lavoro viene utilizzato come identificazione e riferimento per un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38123-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="38123-140">L'URI SIP immesso viene creato come oggetto contatto in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38123-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="38123-141">Per creare l'URI, è necessario che l'oggetto sia univoco in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38123-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="38123-142">In **nome visualizzato**Digitare il nome che si desidera visualizzare per il flusso di lavoro, ad esempio Sales Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-143">Non includere i caratteri "&lt;" o "&gt;" nel nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="38123-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="38123-144">Non utilizzare i nomi visualizzati seguenti, perché sono riservati: <STRONG>RGS Presence Watcher</STRONG> o <STRONG>Servizio Annuncio</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38123-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="38123-145">In **Numero di telefono** digitare l'URI di linea per il Response Group, ad esempio +14255550165.</span><span class="sxs-lookup"><span data-stu-id="38123-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="38123-146">In **Numero visualizzato** digitare il numero nel modo in cui si desidera venga visualizzato per il Response Group, ad esempio +1 (425) 555-0165.</span><span class="sxs-lookup"><span data-stu-id="38123-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="38123-147">Optional In **Descrizione**Digitare una descrizione per il flusso di lavoro che si desidera venga visualizzata nella scheda contatto del client Lync.</span><span class="sxs-lookup"><span data-stu-id="38123-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="38123-148">In **Tipo di flusso di lavoro** selezionare **Gestito** se il flusso di lavoro verrà gestito da un responsabile di Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="38123-149">Per assegnare i responsabili dei Response Group al flusso di lavoro, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="38123-150">Digitare l'URI SIP di un responsabile per questo flusso di lavoro e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="38123-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="38123-151">Digitare l'URI SIP di ulteriori responsabili da aggiungere al flusso di lavoro e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="38123-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38123-p113">A ogni utente designato come responsabile di un Response Group deve essere assegnato il ruolo CsResponseGroupManager. Se non viene assegnato loro questo ruolo, non potranno gestire i Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="38123-154">In **Passaggio 2 Selezionare una lingua** fare clic sulla lingua che si desidera utilizzare per il riconoscimento vocale e la sintesi vocale.</span><span class="sxs-lookup"><span data-stu-id="38123-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="38123-155">Se si desidera configurare un messaggio di benvenuto, in **Passaggio 3 Configurare un messaggio di benvenuto** selezionare la casella di controllo **Riprodurre un messaggio di benvenuto**, quindi effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="38123-156">Per immettere il messaggio di benvenuto come testo della sintesi vocale per i chiamanti, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="38123-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-p114">Non includere tag HTML nel testo immesso. Se si includono tag HTML verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="38123-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="38123-p115">Per utilizzare la registrazione di un file WAVE (WAV) o Windows Media Audio (WMA) per il messaggio di benvenuto, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser fare clic su **Sfoglia**, selezionare il file audio che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="38123-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-163">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="38123-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="38123-164">Per informazioni dettagliate sui formati di file supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="38123-165">In **Passaggio 4 Specificare l'orario di ufficio** fare clic sul fuso orario del flusso di lavoro in **Fuso orario**.</span><span class="sxs-lookup"><span data-stu-id="38123-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-p117">È necessario specificare il fuso orario in cui risiedono i chiamanti e gli agenti del flusso di lavoro. Il fuso orario viene utilizzato per calcolare le ore di apertura e di chiusura. Se, ad esempio, il flusso di lavoro è configurato per l'utilizzo del fuso orario orientale ed è pianificato per l'apertura alle 7.00 e la chiusura alle 23.00, si presuppone che le ore di apertura e di chiusura siano rispettivamente le 7.00 e le 23.00 del fuso orario orientale. È necessario immettere le ore nel formato a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="38123-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="38123-171">Selezionare il tipo di pianificazione dell'orario di ufficio che si desidera utilizzare eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="38123-172">Per utilizzare una pianificazione dell'orario di ufficio predefinita, fare clic su **Usa pianificazione preimpostata**, quindi selezionare la pianificazione che si desidera utilizzare nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="38123-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-173">Per potere selezionare questa opzione, è necessario che in precedenza sia stata definita almeno una pianificazione preimpostata.</span><span class="sxs-lookup"><span data-stu-id="38123-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="38123-174">Per definire le pianificazioni preimpostate, utilizzare il cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38123-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="38123-175">Per ulteriori informazioni, vedere <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facoltativo) definire gli orari di ufficio di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-176">Quando si seleziona una pianificazione preimpostata, nei campi <STRONG>Giorno</STRONG>, <STRONG>Apri</STRONG> e <STRONG>Chiudi</STRONG> vengono inseriti automaticamente i giorni e le ore in cui il Response Group è disponibile.</span><span class="sxs-lookup"><span data-stu-id="38123-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="38123-177">Per utilizzare una pianificazione personalizzata da applicare solo a questo flusso di lavoro, fare clic su **Usa pianificazione personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="38123-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="38123-178">Se si crea una pianificazione personalizzata per questo flusso di lavoro, fare clic sulle caselle di controllo per i giorni della settimana in cui il Response Group è disponibile.</span><span class="sxs-lookup"><span data-stu-id="38123-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="38123-179">Se si crea una pianificazione personalizzata, digitare le ore in **Apri** e **Chiudi** per ogni giorno della settimana in cui il Response Group è disponibile.</span><span class="sxs-lookup"><span data-stu-id="38123-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-p119">Le ore in <STRONG>Apri</STRONG> e <STRONG>Chiudi</STRONG> devono essere nel formato a 24 ore. Se l'ufficio, ad esempio, è operativo dalle 9.00 alle 17.00 con una pausa per il pranzo a mezzogiorno, è possibile specificare l'orario di ufficio impostando <STRONG>Apri</STRONG> su 9.00, <STRONG>Chiudi</STRONG> su 12.00, quindi di nuovo <STRONG>Apri</STRONG> su 13.00 e <STRONG>Chiudi</STRONG> su 17.00.</span><span class="sxs-lookup"><span data-stu-id="38123-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="38123-182">Se si desidera riprodurre un messaggio quando l'ufficio non è aperto, selezionare la casella di controllo **Riproduci un messaggio quando il Response Group non è durante l'orario di ufficio**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="38123-183">Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="38123-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-p120">Non includere tag HTML nel testo immesso o verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="38123-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="38123-p121">Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="38123-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-190">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="38123-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="38123-191">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="38123-192">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="38123-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="38123-193">Per interrompere la chiamata, fare clic su **Interrompi chiamata**.</span><span class="sxs-lookup"><span data-stu-id="38123-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="38123-194">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="38123-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="38123-195">Il formato dell'indirizzo di segreteria telefonica \<è\>@\<nomeutente DomainName\> (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="38123-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="38123-196">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="38123-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="38123-197">Il \<formato dell'indirizzo utente è nomeutente\>@\<domainname.\></span><span class="sxs-lookup"><span data-stu-id="38123-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="38123-198">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="38123-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="38123-199">Il formato del numero di telefono è \<il\>@\<numero di\> dominio (ad esempio, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="38123-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="38123-200">Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="38123-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="38123-201">In **Passaggio 5 Specificare le festività** fare clic sulle caselle di controllo per uno o più insiemi di festività che definiscono i giorni in cui il Response Group è chiuso.</span><span class="sxs-lookup"><span data-stu-id="38123-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-202">È necessario definire le festività e i relativi insiemi prima di configurare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38123-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="38123-203">Utilizzare i cmdlet <STRONG>New-CsRgsHoliday</STRONG> e <STRONG>New-CsRgsHolidaySet</STRONG> per definire le festività e i relativi insiemi.</span><span class="sxs-lookup"><span data-stu-id="38123-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="38123-204">Per ulteriori informazioni, vedere <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(facoltativo) definire i set di festività di Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="38123-205">Se si desidera riprodurre un messaggio delle festività, selezionare la casella di controllo **Riproduci un messaggio durante le festività**, quindi specificare il messaggio da riprodurre effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="38123-206">Per immettere il messaggio come testo della sintesi vocale per il chiamante, fare clic su **Usa sintesi vocale**, quindi digitare il messaggio nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="38123-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-p127">Non includere tag HTML nel testo immesso o verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="38123-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="38123-p128">Per utilizzare la registrazione di un file audio per il messaggio, fare clic su **Selezionare una registrazione**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **una registrazione**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare, quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="38123-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-213">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="38123-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="38123-214">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="38123-215">Specificare come gestire le chiamate dopo la riproduzione del messaggio (se è stato configurato un messaggio):</span><span class="sxs-lookup"><span data-stu-id="38123-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="38123-216">Per interrompere la chiamata, fare clic su **Interrompi chiamata**.</span><span class="sxs-lookup"><span data-stu-id="38123-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="38123-217">Per inoltrare la chiamata alla segreteria telefonica, fare clic su **Inoltra a segreteria telefonica** e quindi digitare l'indirizzo della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="38123-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="38123-218">Il formato dell'indirizzo di segreteria telefonica \<è\>@\<nomeutente DomainName\> (ad esempio, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="38123-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="38123-219">Per inoltrare la chiamata a un altro utente, fare clic su **Inoltra a URI SIP** e quindi digitare l'indirizzo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="38123-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="38123-220">Il \<formato dell'indirizzo utente è nomeutente\>@\<domainname.\></span><span class="sxs-lookup"><span data-stu-id="38123-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="38123-221">Per inoltrare la chiamata a un altro numero di telefono, fare clic su **Inoltra a numero di telefono** e quindi digitare il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="38123-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="38123-222">Il formato del numero di telefono è \<il\>@\<numero di\> dominio (ad esempio, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="38123-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="38123-223">Il nome di dominio viene utilizzato per instradare il chiamante alla destinazione corretta.</span><span class="sxs-lookup"><span data-stu-id="38123-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="38123-224">In **Passaggio 6 Configurare una coda** selezionare la coda in cui si desidera mettere in attesa i chiamanti fino a quando non diventa disponibile un agente in **Selezionare la coda che riceverà le chiamate**.</span><span class="sxs-lookup"><span data-stu-id="38123-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="38123-225">In **Passaggio 7 Configurare la musica di attesa** scegliere la musica che si desidera riprodurre per i chiamanti in attesa della risposta di un agente effettuando una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38123-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="38123-226">Per utilizzare la registrazione della musica di attesa predefinita, fare clic su **Usa predefinita**.</span><span class="sxs-lookup"><span data-stu-id="38123-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="38123-p133">Per utilizzare la registrazione di un file audio per la musica di attesa, fare clic su **Selezionare un file musicale**. Se si desidera caricare un nuovo file audio, fare clic sul collegamento **un file musicale**. Nella nuova finestra del browser, fare clic su **Sfoglia**, selezionare il file che si desidera utilizzare e quindi fare clic su **Apri**. Fare clic su **Carica** per caricare il file audio.</span><span class="sxs-lookup"><span data-stu-id="38123-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="38123-231">Tutti i file audio forniti dall'utente devono soddisfare requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="38123-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="38123-232">Per informazioni dettagliate sui formati di file audio supportati, vedere <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="38123-233">Fare clic su **Distribuisci**.</span><span class="sxs-lookup"><span data-stu-id="38123-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="38123-234">Per utilizzare Windows PowerShell per creare o modificare un flusso di lavoro di un gruppo di risposta</span><span class="sxs-lookup"><span data-stu-id="38123-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="38123-235">Accedere come membro del gruppo RTCUniversalServerAdmins oppure come membro di uno dei ruoli amministrativi predefiniti che supportano Response Group.</span><span class="sxs-lookup"><span data-stu-id="38123-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="38123-236">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="38123-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="38123-p135">Creare il messaggio di benvenuto e salvarlo in una variabile. Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="38123-p135">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="38123-239">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38123-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-240">Per utilizzare un file audio per il messaggio, eseguire il cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38123-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="38123-241">Per informazioni dettagliate, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="38123-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="38123-242">Ottenere l'identità della coda o informazioni sull'indirizzamento delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="38123-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="38123-243">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="38123-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="38123-244">Per informazioni dettagliate sulla creazione della coda, vedere [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span><span class="sxs-lookup"><span data-stu-id="38123-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="38123-p138">Definire l'azione predefinita da eseguire quando viene aperto un flusso di lavoro durante l'orario di ufficio e salvarla in una variabile. Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="38123-p138">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-p139">Per i flussi di lavoro di gruppi di risposta, l'azione predefinita consiste nell'indirizzare la chiamata a una coda. Questo parametro è obbligatorio per i flussi di lavoro attivi. Non è obbligatorio invece per i flussi di lavoro inattivi.</span><span class="sxs-lookup"><span data-stu-id="38123-p139">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="38123-250">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38123-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="38123-251">Se si desidera definire l'orario di ufficio e le festività, è necessario crearli prima della creazione o della modifica del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38123-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="38123-252">Per ulteriori informazioni, vedere [(facoltativo) definire gli orari di ufficio di Response Group in Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) e [(facoltativo) definire i set di festività di Response Group in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span><span class="sxs-lookup"><span data-stu-id="38123-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="38123-253">Se si desidera definire messaggi per le chiamate ricevute al di fuori dell'orario di ufficio o durante le festività, utilizzare il cmdlet **New-CsRgsPrompt** per definire il messaggio e il cmdlet **New-CsRgsCallAction** per definire l'azione da eseguire dopo il messaggio.</span><span class="sxs-lookup"><span data-stu-id="38123-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="38123-254">Per informazioni dettagliate, vedere [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) e [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span><span class="sxs-lookup"><span data-stu-id="38123-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="38123-255">Recuperare il nome del servizio per il servizio Response Group di Lync Server e assegnarlo a una variabile.</span><span class="sxs-lookup"><span data-stu-id="38123-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="38123-256">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="38123-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="38123-257">Creare o modificare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="38123-257">Create or modify the workflow.</span></span> <span data-ttu-id="38123-258">Per creare un flusso di lavoro, utilizzare **New-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="38123-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="38123-259">Per modificare un flusso di lavoro, utilizzare **Set-CsRgsWorkflow**.</span><span class="sxs-lookup"><span data-stu-id="38123-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="38123-260">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="38123-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="38123-261">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="38123-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38123-262">A tutti gli utenti designati come responsabili dei flussi di lavoro deve essere assegnato il ruolo CsResponseGroupManager.</span><span class="sxs-lookup"><span data-stu-id="38123-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38123-263">Per informazioni dettagliate sui parametri facoltativi aggiuntivi, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> o <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span><span class="sxs-lookup"><span data-stu-id="38123-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38123-264">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38123-264">See Also</span></span>


[<span data-ttu-id="38123-265">Optional Definire i set di festività di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38123-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="38123-266">Optional Definire l'orario di ufficio di Response Group in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38123-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="38123-267">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="38123-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="38123-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="38123-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="38123-269">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="38123-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="38123-270">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="38123-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

