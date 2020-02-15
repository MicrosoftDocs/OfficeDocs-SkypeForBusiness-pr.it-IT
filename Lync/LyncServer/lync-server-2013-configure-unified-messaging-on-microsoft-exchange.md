---
title: 'Lync Server 2013: configurare la messaggistica unificata in Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57e48e0ee3e7ef2b9a755ecbd64afaa0f2ce3c2e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="627be-102">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="627be-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="627be-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="627be-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="627be-104">In questo argomento viene descritto come configurare la messaggistica unificata di Exchange in un server di Microsoft Exchange per l'utilizzo con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="627be-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="627be-105">Negli esempi di cmdlet riportati in questo argomento viene fornita la sintassi per la versione di Exchange 2007 di Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="627be-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="627be-106">Se si esegue Exchange 2010 o Exchange 2013, vedere la documentazione appropriata come riferimento.</span><span class="sxs-lookup"><span data-stu-id="627be-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="627be-107">Per configurare un server che esegue la messaggistica unificata di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="627be-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="627be-108">Creare un dial plan URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) di messaggistica unificata per ognuno dei profili delle posizioni di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="627be-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="627be-109">Se si sceglie di utilizzare Exchange Management Console, creare un nuovo dial plan con l'impostazione di sicurezza **protetta (scelta preferita)**.</span><span class="sxs-lookup"><span data-stu-id="627be-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="627be-110">Se si imposta il valore dell'impostazione di sicurezza su <STRONG>SIP Secured</STRONG> per richiedere la crittografia solo per il traffico SIP, come indicato in precedenza, si noti che questa impostazione di sicurezza su un dial plan non è sufficiente se il pool Front End è configurato per richiedere la crittografia, il che significa che il pool richiede la crittografia per il traffico SIP e RTP.</span><span class="sxs-lookup"><span data-stu-id="627be-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="627be-111">Quando le impostazioni di protezione del dial plan e del pool non sono compatibili, tutte le chiamate alla messaggistica unificata di Exchange dal pool Front End avranno esito negativo, causando un errore che indica che si dispone di un'impostazione di sicurezza incompatibile.</span><span class="sxs-lookup"><span data-stu-id="627be-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="627be-112">Se si utilizza Exchange Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="627be-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="627be-113">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="627be-113">For details, see:</span></span>
    
      - <span data-ttu-id="627be-114">Per Office Communications Server 2007, vedere "come creare un dial plan URI SIP di messaggistica unificata" [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) e "New-UMDialplan: Exchange 2007 Help" all'indirizzo [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span><span class="sxs-lookup"><span data-stu-id="627be-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="627be-115">Per Exchange 2010, vedere "creare un dial plan di messaggistica unificata" [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) e "New-UMDialplan: Exchange 2010 Help [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="627be-116">Per Exchange 2013, vedere la sezione "messaggistica unificata [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="627be-117">Se si seleziona un livello di sicurezza di <STRONG>SIPSecured</STRONG> o <STRONG>protetto</STRONG> a seconda che il protocollo SRTP (Secure Real-Time Transport Protocol) venga attivato o disattivato per la crittografia multimediale.</span><span class="sxs-lookup"><span data-stu-id="627be-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="627be-118">Per l'integrazione di Lync Server 2010 con la messaggistica unificata di Exchange, questo dovrebbe corrispondere al livello di crittografia nella configurazione multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627be-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="627be-119">La configurazione multimediale di Lync Server può essere visualizzata eseguendo il cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="627be-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="627be-120">Per informazioni dettagliate, vedere Get-CsMediaConfiguration nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="627be-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="627be-121">Per informazioni dettagliate sulla selezione delle impostazioni di protezione VoIP appropriate, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione della messaggistica unificata locale e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="627be-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="627be-122">Eseguire il cmdlet seguente per ottenere il nome di dominio completo (FQDN) per ogni dial plan di messaggistica unificata:</span><span class="sxs-lookup"><span data-stu-id="627be-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="627be-123">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="627be-123">For details, see:</span></span>
    
      - <span data-ttu-id="627be-124">Per Exchange 2007, vedere "Get-UMDialplan: Exchange 2007 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="627be-125">Per Exchange 2010, vedere "Get-UMDialplan: Exchange 2010 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="627be-126">Per Exchange 2013, vedere la sezione "messaggistica unificata [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="627be-127">Registrare il nome del dial plan di ogni dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="627be-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="627be-128">A seconda della versione di Exchange Server, potrebbe essere necessario utilizzare il nome di dominio completo (FQDN) di tutti i nomi dei dial plan in un secondo momento come nome del dial plan di Lync Server corrispondente di ogni dial plan di messaggistica unificata in modo che corrisponda ai nomi del dial plan.</span><span class="sxs-lookup"><span data-stu-id="627be-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="627be-129">I nomi dei dial plan di Lync Server devono corrispondere ai nomi dei dial plan di messaggistica unificata solo se il dial plan di messaggistica unificata è in esecuzione su una versione di Exchange <EM>precedente</EM> a Exchange 2010 SP1.</span><span class="sxs-lookup"><span data-stu-id="627be-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="627be-130">Aggiungere il dial plan al server che esegue la messaggistica unificata di Exchange come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="627be-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="627be-131">Se si sceglie di utilizzare Exchange Management Console, è possibile aggiungere il dial plan dalla finestra delle proprietà del server.</span><span class="sxs-lookup"><span data-stu-id="627be-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="627be-132">Per istruzioni specifiche, vedere la documentazione del prodotto Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="627be-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="627be-133">Per Exchange 2007, vedere "come aggiungere il server Messaggistica unificata a un dial plan" all' [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="627be-134">Per Exchange 2010, vedere "visualizzazione o configurazione delle proprietà di un server di messaggistica unificata" all'indirizzo [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span><span class="sxs-lookup"><span data-stu-id="627be-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="627be-135">Per Exchange 2013, vedere la sezione "messaggistica unificata [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="627be-136">Se si utilizza Exchange Management Shell, eseguire le operazioni seguenti per ognuno dei server di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="627be-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="627be-137">Prima di eseguire il passaggio seguente, verificare che tutti gli utenti di VoIP aziendale siano stati configurati con una cassetta postale di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="627be-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="627be-138">Per Exchange 2007, vedere la libreria TechNet di Exchange Server 2007 <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="627be-139">Per Exchange 2010, vedere la libreria TechNet di Exchange Server 2010 <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="627be-140">Quando si specifica un criterio cassetta postale per ogni dial plan creato nel passaggio 1, selezionare il criterio predefinito o quello creato.</span><span class="sxs-lookup"><span data-stu-id="627be-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="627be-141">Passare a \<script di directory\>\\di installazione di Exchange, quindi se Exchange è distribuito in una singola foresta, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="627be-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="627be-142">In alternativa, se Exchange è distribuito in più foreste, digitare quanto indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="627be-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="627be-143">dove la foresta FQDN Specifica la foresta in cui è distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627be-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="627be-144">Se si dispone di uno o più dial plan di messaggistica unificata associati a più gateway IP, continuare con il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="627be-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="627be-145">Se i dial plan sono associati a un solo gateway IP, saltare il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="627be-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="627be-146">Riavviare il servizio <STRONG>Lync Server Front End</STRONG> (rtcsrv.exe) <EM>dopo</EM> aver eseguito exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="627be-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="627be-147">In caso contrario, Lync Server non rileverà la messaggistica unificata nella topologia.</span><span class="sxs-lookup"><span data-stu-id="627be-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="627be-148">Se si utilizza Exchange Management Shell o Exchange Management Console, disabilitare le chiamate in uscita per tutti i gateway IP associati a ognuno dei dial plan.</span><span class="sxs-lookup"><span data-stu-id="627be-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="627be-149">Questo passaggio è necessario per garantire che le chiamate in uscita dal server che esegue la messaggistica unificata di Exchange Server a utenti esterni (ad esempio, come nel caso di scenari di riproduzione su telefono) attraversino in modo affidabile il firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="627be-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="627be-150">Quando si seleziona il gateway IP di messaggistica unificata per consentire le chiamate in uscita, scegliere quello che probabilmente gestirà la maggior parte del traffico.</span><span class="sxs-lookup"><span data-stu-id="627be-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="627be-151">Non consentire il traffico in uscita attraverso un gateway IP che si connette a un pool di Director di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627be-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="627be-152">Evitare anche i pool in un altro sito centrale o in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="627be-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="627be-153">È possibile utilizzare uno dei metodi seguenti per bloccare le chiamate in uscita passando da un gateway IP:</span><span class="sxs-lookup"><span data-stu-id="627be-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="627be-154">Se si utilizza Exchange Management Shell, disabilitare ogni gateway IP eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="627be-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="627be-155">Per Exchange 2007, vedere "Set-UMIPGateway: Exchange 2007 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="627be-156">Per Exchange 2010, vedere "Set-UMIPGateway: Exchange 2010 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="627be-157">Se si utilizza Exchange Management Console, deselezionare la casella di controllo **Consenti chiamate in uscita tramite questo gateway IP** .</span><span class="sxs-lookup"><span data-stu-id="627be-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="627be-158">Se il dial plan di messaggistica unificata URI SIP è associato a un solo gateway IP, non impedire le chiamate in uscita tramite il gateway.</span><span class="sxs-lookup"><span data-stu-id="627be-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="627be-159">Creare un operatore automatico di messaggistica unificata per ogni dial plan di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627be-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="627be-160">Non includere spazi nel nome dell'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="627be-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="627be-161">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="627be-161">For details, see:</span></span>
    
      - <span data-ttu-id="627be-162">Per Exchange 2007, vedere "New-UMAutoAttendant: Exchange 2007 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="627be-163">Per Exchange 2010, vedere "New-UMAutoAttendant: Exchange 2010 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="627be-164">Il passaggio seguente deve essere eseguito per ogni utente dopo aver abilitato gli utenti di Lync Server per VoIP aziendale e conoscere gli URI SIP.</span><span class="sxs-lookup"><span data-stu-id="627be-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="627be-165">Associare gli utenti di messaggistica unificata di Exchange (ognuno dei quali deve essere configurato con una cassetta postale di Exchange) al dial plan di messaggistica unificata e creare un URI SIP per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="627be-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="627be-166">L' <STRONG>parametro SIPResourceIdentifier</STRONG> nell'esempio seguente deve essere l'indirizzo SIP dell'utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="627be-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="627be-167">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="627be-167">For details, see:</span></span>
    
      - <span data-ttu-id="627be-168">Per Exchange 2007, vedere "Enable-UMMailbox: Exchange 2007 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="627be-169">Per Exchange 2010, vedere "Enable-UMMailbox: Exchange 2010 Help" all' [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)indirizzo.</span><span class="sxs-lookup"><span data-stu-id="627be-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

