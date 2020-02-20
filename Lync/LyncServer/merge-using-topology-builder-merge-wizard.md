---
title: Unione mediante l'Unione guidata generatore di topologie
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
ms.openlocfilehash: 8578217d5e3b35351937dbf2838e2994e74fb32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a><span data-ttu-id="afab1-102">Unione mediante l'Unione guidata generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="afab1-102">Merge using Topology Builder Merge wizard</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afab1-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="afab1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

1.  <span data-ttu-id="afab1-104">Eseguire il download della distribuzione esistente utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="afab1-104">Download the existing deployment using Topology Builder.</span></span>

2.  <span data-ttu-id="afab1-105">Scegliere **Unisci Office Communications Server 2007 R2** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="afab1-105">From the **Action** menu, select **Merge Office Communications Server 2007 R2**.</span></span>

3.  <span data-ttu-id="afab1-106">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afab1-106">Click **Next**.</span></span>

4.  <span data-ttu-id="afab1-107">In **Specificare installazione server perimetrale** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="afab1-107">In **Specify Edge Setup**, click **Add**.</span></span>
    
    <span data-ttu-id="afab1-108">![Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Procedura guidata per la topologia di Unione, specificare la pagina installazione Edge")</span><span class="sxs-lookup"><span data-stu-id="afab1-108">![Merge Topology Wizard, Specify Edge Setup page](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="afab1-p101">In **Specificare il tipo di server perimetrale** immettere il tipo di configurazione del server perimetrale e quindi fare clic su **Avanti**. In questo esempio viene utilizzata l'opzione **Server perimetrale singolo**.</span><span class="sxs-lookup"><span data-stu-id="afab1-p101">In **Specify Edge Type**, enter the type of Edge Server configuration, and then click **Next**. This example uses the **Single Edge Server** option.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="afab1-p102"><STRONG>Distribuzione server perimetrale espanso</STRONG> non è una configurazione supportata. Un <STRONG>Server perimetrale espanso</STRONG> deve essere prima convertito in un <STRONG>Server perimetrale singolo</STRONG> o in un <STRONG>Server perimetrale consolidato con carico bilanciato</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="afab1-p102"><STRONG>Expanded Edge deployment</STRONG> is not a supported configuration. An <STRONG>Expanded Edge Server</STRONG> must first be converted to a <STRONG>Single Edge Server</STRONG> or a <STRONG>Load-balanced consolidated Edge</STRONG> Server.</span></span>

    
    </div>

6.  <span data-ttu-id="afab1-113">In **specificare le impostazioni del perimetro interno** immettere le informazioni rilevanti per le porte e l'FQDN interno del pool di server perimetrali in base alle esigenze e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afab1-113">In **Specify Internal Edge Settings** , enter the relevant information for your Edge pool’s internal FQDN and ports as needed, and then click **Next**.</span></span>
    
    <span data-ttu-id="afab1-114">![Specificare la finestra di dialogo Impostazioni perimetro interno](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specificare la finestra di dialogo Impostazioni perimetro interno")</span><span class="sxs-lookup"><span data-stu-id="afab1-114">![Specify Internal Edge Settings dialog](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Specify Internal Edge Settings dialog")</span></span>  

7.  <span data-ttu-id="afab1-115">In **Specificare il perimetro esterno** immettere le informazioni relative all'FQDN di Web Conferencing per il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="afab1-115">In **Specify External Edge**, enter the web conferencing FQDN information for your Edge Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="afab1-p103">Prima di fare clic su <STRONG>Avanti</STRONG>, eseguire il passaggio successivo di questa procedura. È molto importante non ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="afab1-p103">Before you click <STRONG>Next</STRONG>, do the next step in this procedure. It is very important that you do not miss this step.</span></span>

    
    </div>

8.  <span data-ttu-id="afab1-118">Selezionare la casella di controllo **questo pool di server perimetrali viene utilizzato per la Federazione e la connettività per la messaggistica istantanea pubblica** se si prevede di utilizzare il server perimetrale di Office Communications 2007 R2 legacy per la Federazione.</span><span class="sxs-lookup"><span data-stu-id="afab1-118">Check the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use the legacy Office Communications Server 2007 R2 Edge Server for federation.</span></span> <span data-ttu-id="afab1-119">Se sono distribuiti più server perimetrali, solo uno di essi sarà abilitato per la federazione.</span><span class="sxs-lookup"><span data-stu-id="afab1-119">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="afab1-120">Se non si seleziona questa casella di controllo e si decide successivamente di abilitare la federazione, sarà necessario eseguire l'unione guidata di Generatore di topologie e ripubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="afab1-120">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard and publish your topology again.</span></span>
    
    <span data-ttu-id="afab1-121">![Finestra di dialogo server perimetrale, specificare la pagina perimetro esterno](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Finestra di dialogo server perimetrale, specificare la pagina perimetro esterno")</span><span class="sxs-lookup"><span data-stu-id="afab1-121">![Edge Server dialog, Specify External Edge page](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edge Server dialog, Specify External Edge page")</span></span>  

9.  <span data-ttu-id="afab1-122">In **Specificare hop successivo** immettere il nome di dominio completo (FQDN) della posizione dell'hop successivo nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="afab1-122">In **Specify Next Hop**, enter the fully qualified domain name (FQDN) of the next hop location in your environment.</span></span> <span data-ttu-id="afab1-123">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="afab1-123">Click **Finish**.</span></span>
    
    <span data-ttu-id="afab1-124">![Finestra di dialogo server perimetrale, specificare la pagina hop successivo](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Finestra di dialogo server perimetrale, specificare la pagina hop successivo")</span><span class="sxs-lookup"><span data-stu-id="afab1-124">![Edge Server dialog, Specify Next Hop page](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edge Server dialog, Specify Next Hop page")</span></span>  

10. <span data-ttu-id="afab1-125">In **specifica installazione perimetrale**, se sono stati aggiunti tutti i server perimetrali di Office Communications Server 2007 R2, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afab1-125">In **Specify Edge Setup**, if all your Office Communications Server 2007 R2 Edge Servers have been added, click **Next**.</span></span> <span data-ttu-id="afab1-126">Se si dispone di più server perimetrali di Office Communications Server 2007 R2 da aggiungere, ripetere questa procedura a partire dal passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="afab1-126">If you have more Office Communications Server 2007 R2 Edge Servers to add, repeat this procedure starting at step 4.</span></span>

11. <span data-ttu-id="afab1-127">In **specifica porta SIP interna** selezionare l'impostazione predefinita, ovvero se non è stata modificata la porta SIP predefinita.</span><span class="sxs-lookup"><span data-stu-id="afab1-127">In **Specify Internal SIP port** , select the default setting (that is, if you did not modify the default SIP port).</span></span> <span data-ttu-id="afab1-128">Se invece non si sta utilizzando la porta predefinita 5061, modificare l'impostazione in base alle proprie esigenze e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afab1-128">Change as appropriate if you are not using a default port of 5061, and then click **Next**.</span></span>

12. <span data-ttu-id="afab1-129">In **Riepilogo** fare clic su **Avanti** per iniziare a unire le topologie.</span><span class="sxs-lookup"><span data-stu-id="afab1-129">In **Summary**, click **Next** to begin merging the topologies.</span></span>

13. <span data-ttu-id="afab1-130">Nella pagina della procedura guidata viene confermato l'esito positivo dell'unione delle topologie.</span><span class="sxs-lookup"><span data-stu-id="afab1-130">The wizard page verifies that the merging of the topologies was successful.</span></span>

14. <span data-ttu-id="afab1-131">Nella colonna **Stato** verificare che il valore sia **Esito positivo** e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="afab1-131">In the **Status** column, verify that the value is **Success**, and then click **Finish**.</span></span>

15. <span data-ttu-id="afab1-132">Nel riquadro sinistro di generatore di topologie, è ora possibile visualizzare **BackCompatSite**, che indica che l'ambiente Office Communications Server 2007 R2 è stato unito a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afab1-132">In the left pane of Topology Builder, you should now see the **BackCompatSite**, which indicates that your Office Communications Server 2007 R2 environment has been merged with Lync Server 2013.</span></span>
    
    <span data-ttu-id="afab1-133">![Generatore di topologie che mostra una topologia unita](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Generatore di topologie che mostra una topologia unita")</span><span class="sxs-lookup"><span data-stu-id="afab1-133">![Topology Builder showing a merged topology](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topology Builder showing a merged topology")</span></span>  

16. <span data-ttu-id="afab1-134">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="afab1-134">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>

17. <span data-ttu-id="afab1-135">Al termine della Pubblicazione guidata \*\*\*\* fare clic su  \*\*Fine \*\*.</span><span class="sxs-lookup"><span data-stu-id="afab1-135">When the **Publishing wizard** completes, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afab1-136">È importante completare l'argomento successivo, <A href="import-policies-and-settings.md">Import Policies and Settings</A>, per assicurarsi che le impostazioni dei criteri legacy vengano importate in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afab1-136">It’s important that you complete the next topic, <A href="import-policies-and-settings.md">Import policies and settings</A>, to ensure that the legacy policy settings are imported into Lync Server 2013.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

