---
title: Unione tramite la creazione guidata generatore di topologia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61981ae875fef9976377644a9b67f0a329581a90
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="fcb91-102">Unione tramite la creazione guidata generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="fcb91-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb91-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fcb91-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="fcb91-104">Scaricare la distribuzione esistente tramite Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="fcb91-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="fcb91-105">Nel menu **azione** selezionare **Unisci Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="fcb91-106">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-106">Click **Next**.</span></span>

4.  <span data-ttu-id="fcb91-107">In **specifica configurazione del bordo**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="fcb91-108">![Procedura guidata per l'unione delle topologie - Pagina Specificare installazione server perimetrale](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Procedura guidata per l'unione delle topologie - Pagina Specificare installazione server perimetrale")</span><span class="sxs-lookup"><span data-stu-id="fcb91-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="fcb91-109">In **Specifica tipo di bordo**immettere il tipo di configurazione del server perimetrale e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-109">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**.</span></span> <span data-ttu-id="fcb91-110">Questo esempio usa l'opzione **Single Edge Server** .</span><span class="sxs-lookup"><span data-stu-id="fcb91-110">This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fcb91-111">La <STRONG>distribuzione di Edge espansa</STRONG> non è una configurazione supportata.</span><span class="sxs-lookup"><span data-stu-id="fcb91-111"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration.</span></span> <span data-ttu-id="fcb91-112">Un <STRONG>server perimetrale espanso</STRONG> deve prima essere convertito in un <STRONG>singolo Edge Server</STRONG> o in un server <STRONG>perimetrale consolidato con bilanciamento del carico</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="fcb91-112">An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="fcb91-113">In **specificare le impostazioni dei bordi interni** immettere le informazioni rilevanti per il nome di dominio completo e le porte interne del pool Edge in base alle esigenze e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="fcb91-114">![Finestra di dialogo Specificare le impostazioni del perimetro interno](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Finestra di dialogo Specificare le impostazioni del perimetro interno")</span><span class="sxs-lookup"><span data-stu-id="fcb91-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="fcb91-115">In **specifica bordo esterno**immettere le informazioni di dominio completo per le conferenze Web per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="fcb91-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fcb91-116">Prima di fare clic su <STRONG>Avanti</STRONG>, eseguire il passaggio successivo di questa procedura.</span><span class="sxs-lookup"><span data-stu-id="fcb91-116">Before you click <STRONG>Next</STRONG>, do the next step in this procedure.</span></span> <span data-ttu-id="fcb91-117">È molto importante non perdere questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="fcb91-117">It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="fcb91-118">Selezionare la casella di controllo **questo pool di bordi viene usato per la Federazione e la connettività di messaggistica istantanea pubblica** se si prevede di usare il server perimetrale legacy di Office Communications Server 2007 R2 per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="fcb91-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="fcb91-119">Se sono distribuiti più server perimetrali, solo uno di essi verrà abilitato per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="fcb91-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="fcb91-120">Se non si seleziona questa casella e si decide in seguito che si vuole abilitare la Federazione, è necessario eseguire la procedura guidata unione generatore di topologia e pubblicare di nuovo la topologia.</span><span class="sxs-lookup"><span data-stu-id="fcb91-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="fcb91-121">![Finestra di dialogo Server perimetrale - Pagina Specificare il perimetro esterno](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Finestra di dialogo Server perimetrale - Pagina Specificare il perimetro esterno")</span><span class="sxs-lookup"><span data-stu-id="fcb91-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="fcb91-122">In **specifica hop successivo**immettere il nome di dominio completo (FQDN) della posizione dell'hop successivo nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="fcb91-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="fcb91-123">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="fcb91-124">![Finestra di dialogo Server perimetrale - Pagina Specificare hop successivo](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Finestra di dialogo Server perimetrale - Pagina Specificare hop successivo")</span><span class="sxs-lookup"><span data-stu-id="fcb91-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="fcb91-125">In **specifica configurazione di Edge**, se sono stati aggiunti tutti i server Edge di Office Communications Server 2007 R2, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="fcb91-126">Se sono presenti più server Edge di Office Communications Server 2007 R2 da aggiungere, ripetere questa procedura a partire dal passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="fcb91-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="fcb91-127">In **specifica porta SIP interna** selezionare l'impostazione predefinita, ovvero se non è stata modificata la porta SIP predefinita.</span><span class="sxs-lookup"><span data-stu-id="fcb91-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="fcb91-128">Modificare il valore appropriato se non si usa una porta predefinita di 5061 e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="fcb91-129">In **Riepilogo**, fare clic su **Avanti** per iniziare a unire le topologie.</span><span class="sxs-lookup"><span data-stu-id="fcb91-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="fcb91-130">La pagina della procedura guidata verifica che l'Unione delle topologie abbia avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fcb91-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="fcb91-131">Nella colonna **stato** verificare che il valore sia **successo**e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="fcb91-132">Nel riquadro sinistro di generatore di topologia è ora necessario vedere il **BackCompatSite**, che indica che l'ambiente Office Communications Server 2007 R2 è stato unito a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcb91-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="fcb91-133">![Unione di topologie visualizzata nel Generatore di topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Unione di topologie visualizzata nel Generatore di topologie")</span><span class="sxs-lookup"><span data-stu-id="fcb91-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="fcb91-134">Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="fcb91-135">Al termine della **pubblicazione guidata** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="fcb91-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcb91-136">È importante completare l'argomento successivo, <A href="import-policies-and-settings.md">importare criteri e impostazioni</A>per verificare che le impostazioni dei criteri legacy vengano importate in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fcb91-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

