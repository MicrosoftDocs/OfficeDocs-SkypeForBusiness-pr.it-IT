---
title: Eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fe982dca1c1cfda341bd3226b57e7793a948fb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a><span data-ttu-id="3c1e2-102">Eseguire la transizione di un Mediation Server collocato a un Mediation Server autonomo (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="3c1e2-102">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c1e2-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3c1e2-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3c1e2-104">Eseguire la procedura seguente per la transizione del Mediation Server, collocato nel server Standard Edition o nel pool Front End, in un Mediation Server autonomo per una distribuzione a sito singolo.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-104">Use the procedure that follows to transition your Mediation Server, collocated on your Standard Edition server or Front End pool, to a stand-alone Mediation Server for a single-site deployment.</span></span>

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a><span data-ttu-id="3c1e2-105">Per effettuare la transizione di un Mediation Server collocato in un server Mediation Server autonomo (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="3c1e2-105">To transition a collocated Mediation Server to a stand-alone Mediation Server</span></span>

1.  <span data-ttu-id="3c1e2-106">Apertura di una topologia esistente da Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="3c1e2-106">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="3c1e2-107">Nel riquadro sinistro passare a **Pool Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-107">In the left pane, navigate to **Mediation pools**.</span></span>

3.  <span data-ttu-id="3c1e2-108">Fare clic con il pulsante destro del mouse su **Pool Mediation Server** e quindi scegliere **Nuovo Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-108">Right-click **Mediation pools** and select **New Mediation Server**.</span></span>

4.  <span data-ttu-id="3c1e2-p101">Nella pagina **Definisci nuovo pool Mediation Server** immettere il nome di dominio completo del nuovo pool Mediation Server, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-p101">On the **Define New Mediation Pool** page, provide the FQDN of the new Mediation Server pool. Also, select whether this pool will be a single-server or multiple-server pool, and then click **Next**.</span></span>

5.  <span data-ttu-id="3c1e2-111">Selezionare il pool dell'hop Front End server successivo al quale il nuovo Mediation Server instraderà le chiamate in arrivo e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-111">Select the next hop Front End server pool to which the new Mediation Server will route inbound calls, and then click **Next**.</span></span>

6.  <span data-ttu-id="3c1e2-112">Selezionare il pool di server perimetrali che deve essere utilizzato dal Mediation Server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-112">Select the Edge pool to be used by the Mediation Server and then click **Next**.</span></span>

7.  <span data-ttu-id="3c1e2-p102">Nella pagina **Specificare i gateway PSTN** associare il gateway PSTN precedente al Mediation Server. Selezionare il gateway e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-p102">On the **Specify PSTN gateways** page, associate the previous PSTN gateway with the Mediation Server. Select the gateway and then click **Add**.</span></span>

8.  <span data-ttu-id="3c1e2-115">Fare clic su **Fine** per chiudere la procedura guidata **Definisci nuovo pool Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-115">Click **Finish** to close the **Define New Mediation Pool** wizard.</span></span>

9.  <span data-ttu-id="3c1e2-116">In **Generatore di topologie**selezionare il nodo principale **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-116">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

10. <span data-ttu-id="3c1e2-117">Nel riquadro **Azioni** selezionare **Pubblica topologia** e quindi completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-117">From the **Actions** pane, select **Publish Topology** and complete the wizard.</span></span>

11. <span data-ttu-id="3c1e2-118">Attenersi alla procedura descritta in [Install the files for Mediation Server in Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) nella documentazione relativa alla distribuzione per installare i file nel nuovo Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-118">Follow the steps in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) in the Deployment documentation to install the files on the new Mediation Server.</span></span>

12. <span data-ttu-id="3c1e2-119">Dopo l'installazione dei file nel Mediation Server, tornare al Generatore di topologie e nel riquadro sinistro passare al pool.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-119">After the files are installed on the Mediation Server, return to Topology Builder, and in the left pane navigate to the pool.</span></span>

13. <span data-ttu-id="3c1e2-120">Fare clic con il pulsante destro del mouse sul pool e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-120">Right-click the pool and select **Edit Properties**.</span></span>

14. <span data-ttu-id="3c1e2-121">In **Mediation Server** deselezionare la casella di controllo **Mediation Server nella stessa posizione abilitato** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-121">Under **Mediation Server**, clear the check box **Collocated Mediation Server enabled** and then click **OK**.</span></span>

15. <span data-ttu-id="3c1e2-122">In **Generatore di topologie**selezionare il nodo principale **Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-122">From **Topology Builder**, select the top node **Lync Server 2013**.</span></span>

16. <span data-ttu-id="3c1e2-123">Nel menu **Azioni** selezionare **Pubblica topologia** e quindi completare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3c1e2-123">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

