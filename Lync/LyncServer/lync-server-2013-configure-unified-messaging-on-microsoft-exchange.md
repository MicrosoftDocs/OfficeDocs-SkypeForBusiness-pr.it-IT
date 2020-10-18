---
title: 'Lync Server 2013: configurare la messaggistica unificata in Microsoft Exchange'
description: 'Lync Server 2013: configurare la messaggistica unificata in Microsoft Exchange.'
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
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577522"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="9ca63-103">Configurare la messaggistica unificata in Microsoft Exchange per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca63-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca63-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9ca63-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9ca63-105">In questo argomento viene descritto come configurare la messaggistica unificata di Exchange in un server di Microsoft Exchange per l'utilizzo con VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ca63-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ca63-106">Negli esempi di cmdlet riportati in questo argomento viene fornita la sintassi per la versione di Exchange 2007 di Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ca63-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="9ca63-107">Se si esegue Exchange 2010 o Exchange 2013, vedere la documentazione appropriata come riferimento.</span><span class="sxs-lookup"><span data-stu-id="9ca63-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="9ca63-108">Per configurare un server che esegue la messaggistica unificata di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9ca63-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="9ca63-109">Creare un dial plan URI (Uniform Resource Identifier) SIP (Session Initiation Protocol) di messaggistica unificata per ognuno dei profili delle posizioni di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ca63-109">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="9ca63-110">Se si sceglie di utilizzare Exchange Management Console, creare un nuovo dial plan con l'impostazione di sicurezza **protetta (scelta preferita)**.</span><span class="sxs-lookup"><span data-stu-id="9ca63-110">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="9ca63-111">Se si imposta il valore dell'impostazione di sicurezza su <STRONG>SIP Secured</STRONG> per richiedere la crittografia solo per il traffico SIP, come indicato in precedenza, si noti che questa impostazione di sicurezza su un dial plan non è sufficiente se il pool Front End è configurato per richiedere la crittografia, il che significa che il pool richiede la crittografia per il traffico SIP e RTP.</span><span class="sxs-lookup"><span data-stu-id="9ca63-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="9ca63-112">Quando le impostazioni di protezione del dial plan e del pool non sono compatibili, tutte le chiamate alla messaggistica unificata di Exchange dal pool Front End avranno esito negativo, causando un errore che indica che si dispone di un'impostazione di sicurezza incompatibile.</span><span class="sxs-lookup"><span data-stu-id="9ca63-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="9ca63-113">Se si utilizza Exchange Management Shell, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ca63-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="9ca63-114">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ca63-114">For details, see:</span></span>
    
      - <span data-ttu-id="9ca63-115">Per Office Communications Server 2007, vedere "come creare un dial plan URI SIP di messaggistica unificata" [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) e "New-UMDialplan: Exchange 2007 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="9ca63-116">Per Exchange 2010, vedere "creare un dial plan di messaggistica unificata" [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) e "New-UMDialplan: Exchange 2010 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="9ca63-117">Per Exchange 2013, vedere la sezione "messaggistica unificata" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca63-118">Se si seleziona un livello di sicurezza di <STRONG>SIPSecured</STRONG> o <STRONG>protetto</STRONG> a seconda che il protocollo SRTP (Secure Real-Time Transport Protocol) venga attivato o disattivato per la crittografia multimediale.</span><span class="sxs-lookup"><span data-stu-id="9ca63-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="9ca63-119">Per l'integrazione di Lync Server 2010 con la messaggistica unificata di Exchange, questo dovrebbe corrispondere al livello di crittografia nella configurazione multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="9ca63-120">La configurazione multimediale di Lync Server può essere visualizzata eseguendo il cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="9ca63-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="9ca63-121">Per ulteriori informazioni, vedere Get-CsMediaConfiguration nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9ca63-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="9ca63-122">Per informazioni dettagliate sulla selezione delle impostazioni di protezione VoIP appropriate, vedere <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processo di distribuzione per l'integrazione della messaggistica unificata locale e Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9ca63-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="9ca63-123">Eseguire il cmdlet seguente per ottenere il nome di dominio completo (FQDN) per ogni dial plan di messaggistica unificata:</span><span class="sxs-lookup"><span data-stu-id="9ca63-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="9ca63-124">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ca63-124">For details, see:</span></span>
    
      - <span data-ttu-id="9ca63-125">Per Exchange 2007, vedere "Get-UMDialplan: Exchange 2007 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="9ca63-126">Per Exchange 2010, vedere "Get-UMDialplan: Exchange 2010 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="9ca63-127">Per Exchange 2013, vedere la sezione "messaggistica unificata" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="9ca63-128">Registrare il nome del dial plan di ogni dial plan di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="9ca63-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="9ca63-129">A seconda della versione di Exchange Server, potrebbe essere necessario utilizzare il nome di dominio completo (FQDN) di tutti i nomi dei dial plan in un secondo momento come nome del dial plan di Lync Server corrispondente di ogni dial plan di messaggistica unificata in modo che corrisponda ai nomi del dial plan.</span><span class="sxs-lookup"><span data-stu-id="9ca63-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca63-130">I nomi dei dial plan di Lync Server devono corrispondere ai nomi dei dial plan di messaggistica unificata solo se il dial plan di messaggistica unificata è in esecuzione su una versione di Exchange <EM>precedente</EM> a Exchange 2010 SP1.</span><span class="sxs-lookup"><span data-stu-id="9ca63-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="9ca63-131">Aggiungere il dial plan al server che esegue la messaggistica unificata di Exchange come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ca63-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="9ca63-132">Se si sceglie di utilizzare Exchange Management Console, è possibile aggiungere il dial plan dalla finestra delle proprietà del server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-132">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="9ca63-133">Per istruzioni specifiche, vedere la documentazione del prodotto Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-133">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="9ca63-134">Per Exchange 2007, vedere "come aggiungere il server Messaggistica unificata a un dial plan" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="9ca63-135">Per Exchange 2010, vedere "visualizzazione o configurazione delle proprietà di un server di messaggistica unificata" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="9ca63-136">Per Exchange 2013, vedere la sezione "messaggistica unificata" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="9ca63-137">Se si utilizza Exchange Management Shell, eseguire le operazioni seguenti per ognuno dei server di messaggistica unificata di Exchange:</span><span class="sxs-lookup"><span data-stu-id="9ca63-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca63-138">Prima di eseguire il passaggio seguente, verificare che tutti gli utenti di VoIP aziendale siano stati configurati con una cassetta postale di Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="9ca63-139">Per Exchange 2007, vedere la libreria TechNet di Exchange Server 2007 all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> .</span><span class="sxs-lookup"><span data-stu-id="9ca63-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="9ca63-140">Per Exchange 2010, vedere la libreria TechNet di Exchange Server 2010 all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> .</span><span class="sxs-lookup"><span data-stu-id="9ca63-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="9ca63-141">Quando si specifica un criterio cassetta postale per ogni dial plan creato nel passaggio 1, selezionare il criterio predefinito o quello creato.</span><span class="sxs-lookup"><span data-stu-id="9ca63-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="9ca63-142">Passare a \<Exchange installation directory\> \\ script e quindi, se Exchange è distribuito in una singola foresta, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9ca63-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="9ca63-143">In alternativa, se Exchange è distribuito in più foreste, digitare quanto indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ca63-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="9ca63-144">dove la foresta FQDN Specifica la foresta in cui è distribuito Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="9ca63-145">Se si dispone di uno o più dial plan di messaggistica unificata associati a più gateway IP, continuare con il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="9ca63-145">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="9ca63-146">Se i dial plan sono associati a un solo gateway IP, saltare il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="9ca63-146">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9ca63-147">Riavviare il servizio <STRONG>Lync Server Front End</STRONG> (rtcsrv.exe) <EM>dopo</EM> aver eseguito exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="9ca63-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="9ca63-148">In caso contrario, Lync Server non rileverà la messaggistica unificata nella topologia.</span><span class="sxs-lookup"><span data-stu-id="9ca63-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="9ca63-149">Se si utilizza Exchange Management Shell o Exchange Management Console, disabilitare le chiamate in uscita per tutti i gateway IP associati a ognuno dei dial plan.</span><span class="sxs-lookup"><span data-stu-id="9ca63-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca63-150">Questo passaggio è necessario per garantire che le chiamate in uscita dal server che esegue la messaggistica unificata di Exchange Server a utenti esterni (ad esempio, come nel caso di scenari di riproduzione su telefono) attraversino in modo affidabile il firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ca63-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9ca63-151">Quando si seleziona il gateway IP di messaggistica unificata per consentire le chiamate in uscita, scegliere quello che probabilmente gestirà la maggior parte del traffico.</span><span class="sxs-lookup"><span data-stu-id="9ca63-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="9ca63-152">Non consentire il traffico in uscita attraverso un gateway IP che si connette a un pool di Director di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="9ca63-153">Evitare anche i pool in un altro sito centrale o in un sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="9ca63-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="9ca63-154">È possibile utilizzare uno dei metodi seguenti per bloccare le chiamate in uscita passando da un gateway IP:</span><span class="sxs-lookup"><span data-stu-id="9ca63-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="9ca63-155">Se si utilizza Exchange Management Shell, disabilitare ogni gateway IP eseguendo il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ca63-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="9ca63-156">Per Exchange 2007, vedere "Set-UMIPGateway: Exchange 2007 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="9ca63-157">Per Exchange 2010, vedere "Set-UMIPGateway: Exchange 2010 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="9ca63-158">Se si utilizza Exchange Management Console, deselezionare la casella di controllo **Consenti chiamate in uscita tramite questo gateway IP** .</span><span class="sxs-lookup"><span data-stu-id="9ca63-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9ca63-159">Se il dial plan di messaggistica unificata URI SIP è associato a un solo gateway IP, non impedire le chiamate in uscita tramite il gateway.</span><span class="sxs-lookup"><span data-stu-id="9ca63-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="9ca63-160">Creare un operatore automatico di messaggistica unificata per ogni dial plan di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9ca63-161">Non includere spazi nel nome dell'operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="9ca63-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="9ca63-162">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ca63-162">For details, see:</span></span>
    
      - <span data-ttu-id="9ca63-163">Per Exchange 2007, vedere "New-UMAutoAttendant: Exchange 2007 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="9ca63-164">Per Exchange 2010, vedere "New-UMAutoAttendant: Exchange 2010 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="9ca63-165">Il passaggio seguente deve essere eseguito per ogni utente dopo aver abilitato gli utenti di Lync Server per VoIP aziendale e conoscere gli URI SIP.</span><span class="sxs-lookup"><span data-stu-id="9ca63-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="9ca63-166">Associare gli utenti di messaggistica unificata di Exchange (ognuno dei quali deve essere configurato con una cassetta postale di Exchange) al dial plan di messaggistica unificata e creare un URI SIP per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="9ca63-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9ca63-167">L' <STRONG>parametro SIPResourceIdentifier</STRONG> nell'esempio seguente deve essere l'indirizzo SIP dell'utente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9ca63-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="9ca63-168">Per dettagli, vedere:</span><span class="sxs-lookup"><span data-stu-id="9ca63-168">For details, see:</span></span>
    
      - <span data-ttu-id="9ca63-169">Per Exchange 2007, vedere "Enable-UMMailbox: Exchange 2007 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="9ca63-170">Per Exchange 2010, vedere "Enable-UMMailbox: Exchange 2010 Help" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) .</span><span class="sxs-lookup"><span data-stu-id="9ca63-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

