---
title: 'Lync Server 2013: Configurare i certificati per il server Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a><span data-ttu-id="7922b-102">Configurare i certificati per il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7922b-102">Configure certificates for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7922b-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7922b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7922b-104">Quando si esegue la creazione guidata certificato, verificare di avere effettuato l'accesso con un account membro di un gruppo a cui sono state assegnate le autorizzazioni appropriate per il tipo di modello di certificato che verrà usato.</span><span class="sxs-lookup"><span data-stu-id="7922b-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="7922b-105">Per impostazione predefinita, una richiesta di certificato di Lync Server 2013 utilizzerà il modello di certificato del server Web.</span><span class="sxs-lookup"><span data-stu-id="7922b-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="7922b-106">Se si usa un account che è un membro del gruppo RTCUniversalServerAdmins per richiedere un certificato con questo modello, verificare che al gruppo siano state assegnate le autorizzazioni di registrazione necessarie per l'uso di tale modello.</span><span class="sxs-lookup"><span data-stu-id="7922b-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="7922b-107">Ogni amministratore richiede un certificato predefinito, un certificato interno Web e un certificato esterno Web.</span><span class="sxs-lookup"><span data-stu-id="7922b-107">Each Director requires a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="7922b-108">Per informazioni dettagliate sui requisiti dei certificati per gli amministratori, vedere [requisiti di certificato per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="7922b-108">For details about the certificate requirements for Directors, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="7922b-109">Usare la procedura seguente per configurare i certificati di Director.</span><span class="sxs-lookup"><span data-stu-id="7922b-109">Use the following procedure to configure Director certificates.</span></span> <span data-ttu-id="7922b-110">Ripetere la procedura per ogni amministratore.</span><span class="sxs-lookup"><span data-stu-id="7922b-110">Repeat the procedure for each Director.</span></span> <span data-ttu-id="7922b-111">I passaggi di questa procedura descrivono come configurare un certificato da un'autorità di certificazione radice aziendale (CA) interna distribuita dall'organizzazione e con l'elaborazione delle richieste offline.</span><span class="sxs-lookup"><span data-stu-id="7922b-111">The steps of this procedure describe how to configure a certificate from an Internal Enterprise Root certification authority (CA) deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="7922b-112">Per informazioni dettagliate su come ottenere certificati da una CA esterna, contattare il team di supporto.</span><span class="sxs-lookup"><span data-stu-id="7922b-112">For details about obtaining certificates from an external CA, contact your support team.</span></span>

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a><span data-ttu-id="7922b-113">Per configurare i certificati per il pool di Director o Director</span><span class="sxs-lookup"><span data-stu-id="7922b-113">To configure certificates for the Director or Director pool</span></span>

1.  <span data-ttu-id="7922b-114">Nella distribuzione guidata di Lync Server, accanto al **passaggio 3: Richiedi, installa o assegna certificati**, fai clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7922b-114">In the Lync Server Deployment Wizard, next to **Step 3: Request, Install or Assign Certificates**, click **Run**.</span></span>

2.  <span data-ttu-id="7922b-115">Nella pagina **creazione guidata certificato** fare clic su **Richiedi**.</span><span class="sxs-lookup"><span data-stu-id="7922b-115">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="7922b-116">Nella pagina **richiesta certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-116">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="7922b-117">Nella pagina **richieste immediate o posticipate** accettare il **messaggio di richiesta predefinito invia immediatamente l'opzione a un'autorità di certificazione online** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-117">On the **Delayed or Immediate Requests** page, accept the default **Send the request immediately to an online certification authority** option, and then click **Next**.</span></span>

5.  <span data-ttu-id="7922b-118">Nella pagina **Scegli autorità di certificazione (CA)** fare clic sull'autorità di certificazione Windows interna che si vuole usare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-118">On the **Choose a Certification Authority (CA)** page, click the internal Windows certification authority that you want to use, and then click **Next**.</span></span>

6.  <span data-ttu-id="7922b-119">Nella pagina dell' **account dell'autorità di certificazione** specificare le credenziali alternative da usare se l'account con cui si è connessi non dispone dell'autorità sufficiente per richiedere il certificato e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-119">On the **Certification Authority Account** page, specify alternate credentials to be used if the account you are logged on with does not have sufficient authority to request the certificate, and then click **Next**.</span></span>

7.  <span data-ttu-id="7922b-120">Nella pagina **Specifica modello di certificato alternativo** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-120">On the **Specify Alternate Certificate Template** page, click **Next**.</span></span>

8.  <span data-ttu-id="7922b-121">Nella pagina **Impostazioni nome e sicurezza** è possibile specificare un **nome descrittivo**, accettare la lunghezza della chiave di 2048 bit e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-121">On the **Name and Security Settings** page, you can specify a **Friendly Name**, accept the 2048-bit key length, and then click **Next**.</span></span>

9.  <span data-ttu-id="7922b-122">Nella pagina **informazioni organizzazione** , facoltativamente, specificare le informazioni sull'organizzazione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-122">On the **Organization Information** page, optionally specify organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="7922b-123">Nella pagina **informazioni geografiche** specificare facoltativamente informazioni geografiche e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-123">On the **Geographical Information** page, optionally specify geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="7922b-124">Nella pagina **nome oggetto/nomi alternativi oggetto** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-124">On the **Subject Name / Subject Alternative Names** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7922b-125">L'elenco nome alternativo oggetto deve contenere il nome del computer in cui si sta installando il Director (se un singolo amministratore) o il nome del pool di Director e i nomi di URL semplici configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7922b-125">The subject alternative name list should contain the name of the computer on which you are installing the Director (if a single Director) or the Director pool name, and the simple URL names configured for the organization.</span></span>

    
    </div>

12. <span data-ttu-id="7922b-126">Nell' **impostazione del dominio SIP nella pagina nome alternativo soggetto (sans)** selezionare i **domini SIP configurati** per tutti i domini che si desidera vengano gestiti dal Director e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-126">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the **Configured SIP Domains** for all domains that you want the Director to handle, and then click **Next**.</span></span>

13. <span data-ttu-id="7922b-127">Nella pagina **Configura altri nomi alternativi** per l'oggetto aggiungere eventuali nomi alternativi di altri soggetti obbligatori e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-127">On the **Configure Additional Subject Alternative Names** page, add any additional required subject alternative names, and then click **Next**.</span></span>

14. <span data-ttu-id="7922b-128">Nella pagina **Riepilogo richiesta di certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-128">On the **Certificate Request Summary** page, click **Next**.</span></span>

15. <span data-ttu-id="7922b-129">Nella pagina **esecuzione dei comandi** fare clic su **Avanti** dopo che i comandi hanno terminato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7922b-129">On the **Executing Commands** page, click **Next** after the commands have finished running.</span></span>

16. <span data-ttu-id="7922b-130">Nella pagina **stato richiesta di certificato online** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="7922b-130">On the **Online Certificate Request Status** page, click **Finish**.</span></span>

17. <span data-ttu-id="7922b-131">Nella pagina **assegnazione certificato** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-131">On the **Certificate Assignment** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7922b-132">Se si vuole visualizzare il certificato, fare doppio clic sul certificato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7922b-132">if you want to view the certificate, double-click the certificate in the list.</span></span>

    
    </div>

18. <span data-ttu-id="7922b-133">Nella pagina **Riepilogo assegnazione certificati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7922b-133">On the **Certificate Assignment Summary** page, click **Next**.</span></span>

19. <span data-ttu-id="7922b-134">Nella pagina **esecuzione dei comandi** fare clic su **fine** dopo che i comandi hanno terminato l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7922b-134">On the **Executing Commands** page, click **Finish** after the commands have finished running.</span></span>

20. <span data-ttu-id="7922b-135">Nella pagina **creazione guidata certificato** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7922b-135">On the **Certificate Wizard** page, click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

