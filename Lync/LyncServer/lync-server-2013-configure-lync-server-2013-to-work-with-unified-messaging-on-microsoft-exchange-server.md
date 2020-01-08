---
title: "Lync Server 2013: Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="b0e65-102">Configurare Lync Server 2013 per l'utilizzo della messaggistica unificata in Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b0e65-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="b0e65-103">_**Argomento Ultima modifica:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="b0e65-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="b0e65-104">Questo passaggio richiede l'utilità di integrazione della messaggistica unificata di Exchange (OcsUmUtil. exe).</span><span class="sxs-lookup"><span data-stu-id="b0e65-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="b0e65-105">Questo strumento si trova nel server Lync Server 2013 nel.. \\Programmi file\\comuni cartella\\di supporto di Microsoft\\Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0e65-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="b0e65-106">Eseguire l'utilità di integrazione della messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="b0e65-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="b0e65-107">L'utilità di integrazione della messaggistica unificata di Exchange deve essere eseguita da un account utente con le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0e65-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="b0e65-108">Appartenenza ai gruppi RTCUniversalServerAdmins e RtcUniversalUserAdmins, che includono le autorizzazioni per la lettura delle impostazioni di messaggistica unificata di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b0e65-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="b0e65-109">Diritti utente nel dominio per creare oggetti contatto nel contenitore dell'unità organizzativa specificata.</span><span class="sxs-lookup"><span data-stu-id="b0e65-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="b0e65-110">Quando si esegue l'utilità di integrazione della messaggistica unificata di Exchange, vengono eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0e65-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="b0e65-111">Crea oggetti contatto per ogni numero di accesso automatico e Sottoscrittore che deve essere usato dagli utenti di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="b0e65-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="b0e65-112">Verifica che il nome di ogni piano di chiamata VoIP aziendale corrisponda al contesto telefonico di dial plan di messaggistica unificata corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b0e65-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="b0e65-113">Questa corrispondenza è necessaria solo se il dial plan di messaggistica unificata viene eseguito in una versione di Exchange *precedente* rispetto a Exchange 2010 Service Pack 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="b0e65-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0e65-114">Prima di eseguire l'utilità di integrazione della messaggistica unificata di Exchange, verificare di aver eseguito le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0e65-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="b0e65-115">Creare uno o più dial plan di messaggistica unificata di Exchange, come descritto nella documentazione del prodotto Exchange.</span><span class="sxs-lookup"><span data-stu-id="b0e65-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="b0e65-116">Per Microsoft Exchange Server 2010, vedere &quot;creare un dial plan&quot; di <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="b0e65-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="b0e65-117">Per Microsoft Exchange Server 2007 Service Pack 1 (SP1), vedere &quot;come creare un dial plan&quot; URI SIP di messaggistica unificata. <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a></span><span class="sxs-lookup"><span data-stu-id="b0e65-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="b0e65-118">Creare uno o più piani di chiamata di Lync Server corrispondenti, come descritto in <a href="lync-server-2013-create-a-dial-plan.md">creare un dial plan in Lync server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b0e65-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="b0e65-119">Se si usa una versione di Exchange precedente a Microsoft Exchange Server 2010 SP1, è necessario immettere il nome di dominio completo (FQDN) del relativo dial plan di messaggistica unificata di Exchange nel campo <STRONG>nome semplice</STRONG> di Lync Server 2013 dial plan.</span><span class="sxs-lookup"><span data-stu-id="b0e65-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="b0e65-120">Se si usa Microsoft Exchange Server 2010 SP1 o il Service Pack più recente, non è necessario questo nome per il dial plan.</span><span class="sxs-lookup"><span data-stu-id="b0e65-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="b0e65-121">Creare un operatore automatico e verificare che il numero di accesso del Sottoscrittore e il numero di operatore automatico siano in formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="b0e65-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="b0e65-122">Per eseguire l'utilità di integrazione della messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="b0e65-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="b0e65-123">In un server front-end aprire un prompt dei comandi e digitare **CD% COMMONPROGRAMFILES\\% Microsoft Lync Server\\2013 support**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b0e65-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="b0e65-124">Digitare **OcsUmUtil. exe**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b0e65-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="b0e65-125">Fare clic su **Carica dati** per trovare tutte le foreste di Exchange attendibili.</span><span class="sxs-lookup"><span data-stu-id="b0e65-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="b0e65-126">Nell'elenco **dial plan SIP** selezionare un dial plan di messaggistica unificata per cui si vogliono creare oggetti contatto e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b0e65-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="b0e65-127">Nella casella **contatto** accettare l'unità organizzativa predefinita oppure fare clic su **Sfoglia** per avviare la **selezione unità organizzativa**.</span><span class="sxs-lookup"><span data-stu-id="b0e65-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="b0e65-128">Nella casella **selezione unità** organizzativa è possibile selezionare un'unità organizzativa e fare clic su **OK**oppure fare clic su **Crea nuova UO** per creare una nuova unità organizzativa nella radice o in qualsiasi altra UO del dominio, ad esempio "ou = account speciali RTC, DC = fourthcoffee, DC = com", e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0e65-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0e65-129">Il nome distinto (DN) dell'unità organizzativa selezionata o creata viene ora visualizzato nella casella <STRONG>unità organizzativa</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="b0e65-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="b0e65-130">Nella casella **nome** accettare il nome predefinito del dial plan o digitare un nuovo nome visualizzato per l'oggetto contatto che si sta creando.</span><span class="sxs-lookup"><span data-stu-id="b0e65-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0e65-131">Ad esempio, se stai creando un oggetto contatto di accesso sottoscrittore, potresti semplicemente denominarlo accesso sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="b0e65-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="b0e65-132">Nella casella **indirizzo SIP** accettare l'indirizzo SIP predefinito oppure digitare un nuovo indirizzo SIP.</span><span class="sxs-lookup"><span data-stu-id="b0e65-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0e65-133">Se si digita un nuovo indirizzo SIP, è necessario che inizi con <STRONG>SIP:</STRONG> ovvero "SIP:", inclusi i due punti.</span><span class="sxs-lookup"><span data-stu-id="b0e65-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="b0e65-134">Nell'elenco **Server o pool** selezionare il server Standard Edition o il pool Front end in cui deve essere abilitato l'oggetto contatto.</span><span class="sxs-lookup"><span data-stu-id="b0e65-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0e65-135">Preferibilmente, il pool selezionato è lo stesso pool in cui sono distribuiti gli utenti abilitati per la messaggistica unificata di Exchange e Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b0e65-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="b0e65-136">Nell'elenco **numero di telefono** selezionare **Immetti numero di telefono** o **usare questo numero pilota dalla messaggistica unificata di Exchange** e quindi immettere un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="b0e65-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="b0e65-137">Nell'elenco **tipo di contatto** selezionare il tipo di contatto che si vuole creare e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0e65-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="b0e65-138">Ripetere i passaggi da 1 a 10 per gli oggetti contatto aggiuntivi che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="b0e65-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0e65-139">Devi creare almeno un contatto per ogni operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="b0e65-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="b0e65-140">Se si vuole l'accesso esterno, è necessario anche un contatto di accesso abbonato e specificare i numeri di chiamata diretta.</span><span class="sxs-lookup"><span data-stu-id="b0e65-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="b0e65-141">Per verificare che gli oggetti contatto siano stati creati, aprire utenti e computer di Active Directory e selezionare l'unità organizzativa in cui sono stati creati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="b0e65-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="b0e65-142">Gli oggetti contatto devono essere visualizzati nel riquadro dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="b0e65-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="b0e65-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b0e65-143"></span></span></div>

