---
title: 'Lync Server 2013: configurare i certificati per il Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5fef23ca24d9a09d326b75ec2ad2e30704852f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="c6c09-102">Configurare i certificati per il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6c09-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6c09-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c6c09-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c6c09-104">Quando si esegue la Configurazione guidata certificati, verificare di aver eseguito l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c6c09-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="c6c09-105">Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web.</span><span class="sxs-lookup"><span data-stu-id="c6c09-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="c6c09-106">Se si utilizza un account membro del gruppo RTCUniversalServerAdmins per richiedere un certificato che utilizza questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'utilizzo del modello.</span><span class="sxs-lookup"><span data-stu-id="c6c09-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="c6c09-107">Ogni director richiede un certificato predefinito, un certificato Web interno e un certificato Web esterno.</span><span class="sxs-lookup"><span data-stu-id="c6c09-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="c6c09-108">Per informazioni dettagliate sui requisiti dei certificati per i direttori, vedere [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c6c09-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="c6c09-p103">Utilizzare la procedura seguente per configurare i certificati per i Director. Ripetere la procedura per ogni Director. Nei passaggi di questa procedura viene descritto come configurare un certificato da un'autorità di certificazione (CA) radice globale (enterprise) interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline. Per informazioni dettagliate su come ottenere certificati da una CA esterna, rivolgersi al team di supporto.</span><span class="sxs-lookup"><span data-stu-id="c6c09-p103">Use the following procedure to configure Director certificates. Repeat the procedure for each Director. The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing. For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="c6c09-113">Per configurare certificati per il Director o il pool di server Director</span><span class="sxs-lookup"><span data-stu-id="c6c09-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="c6c09-114">Nella distribuzione guidata di Lync Server, accanto a **passaggio 3: richiesta, installazione o assegnazione dei certificati**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="c6c09-115">Nella pagina **Configurazione guidata certificati** fare clic su **Richiesta**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="c6c09-116">Nella pagina **Richiesta di certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="c6c09-117">Nella pagina **Richiesta posticipata o immediata** accettare l'opzione predefinita **Invia immediatamente la richiesta a un'autorità di certificazione online** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="c6c09-118">Nella pagina **Scegli Autorità di certificazione (CA)** fare clic sull'autorità di certificazione di Windows interna che si desidera utilizzare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="c6c09-119">Nella pagina **Account autorità di certificazione** specificare credenziali alternative da utilizzare se l'account con cui è stato eseguito l'accesso non dispone dell'autorità sufficiente per richiedere il certificato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="c6c09-120">Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="c6c09-121">Nella pagina **Impostazioni nome e sicurezza** è possibile specificare un nome in **Nome descrittivo**, accettare la lunghezza di chiave di 2048 bit e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="c6c09-122">Nella pagina **Informazioni sull'organizzazione** specificare facoltativamente le informazioni sull'organizzazione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="c6c09-123">Nella pagina **Dati geografici** specificare facoltativamente i dati geografici e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="c6c09-124">Nella pagina **Nome soggetto / Nomi soggetto alternativi** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6c09-125">Nell'elenco dei nomi alternativi del soggetto dovrebbero essere contenuti il nome del computer in cui si desidera installare il Director (se singolo) o il nome del pool di server Director e i nomi degli URL semplici configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c6c09-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="c6c09-126">Nella pagina **Impostazione del dominio SIP su nomi soggetto alternativi (SAN)** selezionare **Domini SIP configurati** per tutti i domini che devono essere gestiti dal Director e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="c6c09-127">Nella pagina **Configura nomi soggetto alternativi aggiuntivi** aggiungere altri eventuali nomi alternativi del soggetto necessari e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="c6c09-128">Nella pagina **Riepilogo richiesta certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="c6c09-129">Nella pagina **Esecuzione comandi in corso** fare clic su **Avanti** al termine dell'esecuzione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c6c09-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="c6c09-130">Nella pagina **Stato richiesta di certificato online** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="c6c09-131">Nella pagina **Assegnazione certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6c09-132">Se si desidera visualizzare il certificato, fare doppio clic su di esso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c6c09-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="c6c09-133">Nella pagina **Riepilogo assegnazione certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="c6c09-134">Nella pagina **Esecuzione comandi in corso** fare clic su **Fine** al termine dell'esecuzione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="c6c09-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="c6c09-135">Nella pagina **Configurazione guidata certificati** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c6c09-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

