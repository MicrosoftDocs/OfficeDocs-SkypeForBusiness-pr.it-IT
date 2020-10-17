---
title: 'Lync Server 2013: esportare i test case di routing vocale'
description: 'Lync Server 2013: esportare i test case di routing vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934bd183a17c46cf82fe5bc04faaa55a9bbe4731
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564782"
---
# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="10b1a-103">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b1a-103">Export voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b1a-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="10b1a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="10b1a-105">I test case consentono di testare le route vocali nell'organizzazione: è possibile definire elementi quali il numero da comporre e il dial plan e i criteri vocali da utilizzare e Lync Server può quindi verificare che, date queste condizioni, il numero fornito possa essere instradato correttamente alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="10b1a-105">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="10b1a-106">I test case, che possono essere creati utilizzando il pannello di controllo di Lync Server, vengono in genere salvati solo sul server in cui è stato creato ed eseguito originariamente il caso.</span><span class="sxs-lookup"><span data-stu-id="10b1a-106">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="10b1a-107">È comunque possibile esportarli come file XML (con estensione vtest) per poi importarli in altri server.</span><span class="sxs-lookup"><span data-stu-id="10b1a-107">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="10b1a-108">Ciò consente di eseguire gli stessi test in computer diversi situati in punti diversi della topologia.</span><span class="sxs-lookup"><span data-stu-id="10b1a-108">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-export-a-voice-routing-test-case"></a><span data-ttu-id="10b1a-109">Per esportare un test case di routing vocale</span><span class="sxs-lookup"><span data-stu-id="10b1a-109">To export a voice routing test case</span></span>

1.  <span data-ttu-id="10b1a-110">Nel pannello di controllo di Lync Server, fare clic su **routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="10b1a-110">In Lync Server Control Panel, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

2.  <span data-ttu-id="10b1a-p102">Nella scheda **Test routing vocale** selezionare il test case (o i test case) da esportare. Per selezionare più test case, fare clic sul primo che si desidera esportare e quindi tenere premuto CTRL e selezionare eventuali altri case da esportare.</span><span class="sxs-lookup"><span data-stu-id="10b1a-p102">On the **Test Voice Routing** tab, select the test case (or test cases) to be exported. To select multiple test cases, click the first case to be exported, then hold down the Ctrl key and select the additional cases to be exported.</span></span>

3.  <span data-ttu-id="10b1a-113">Fare clic su **Azione** e quindi su **Esporta test case**.</span><span class="sxs-lookup"><span data-stu-id="10b1a-113">Click **Action**, then click **Export test cases**.</span></span>

4.  <span data-ttu-id="10b1a-p103">Nella finestra di dialogo **Salva con nome** selezionare una cartella in cui memorizzare i test case esportati e digitare un nome per il file XML risultante nella casella **Nome file**. Se si esportano più test case, verranno tutti salvati in un unico file XML.</span><span class="sxs-lookup"><span data-stu-id="10b1a-p103">In the **Save As** dialog box, select a folder to store the exported test cases and type a name for the resulting XML file in the **File name** box. Note that if you are exporting multiple tests cases all of these test cases will be saved to a single XML file.</span></span>

5.  <span data-ttu-id="10b1a-116">Per salvare i test case, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="10b1a-116">To save the test cases, click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="10b1a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10b1a-117">See Also</span></span>


[<span data-ttu-id="10b1a-118">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10b1a-118">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

