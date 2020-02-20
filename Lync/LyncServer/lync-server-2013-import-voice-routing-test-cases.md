---
title: 'Lync Server 2013: importare test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43ab26d61009683623d3c536a26c8be04a3846e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="cb30a-102">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb30a-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb30a-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="cb30a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="cb30a-104">I test case consentono di testare le route vocali nell'organizzazione: è possibile definire elementi quali il numero da comporre e il dial plan e i criteri vocali da utilizzare e Lync Server 2013 può quindi verificare che, date queste condizioni, il numero fornito possa essere succes sfully essere instradato alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="cb30a-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="cb30a-105">I test case, che possono essere creati utilizzando il pannello di controllo di Lync Server, vengono in genere salvati solo sul server in cui è stato creato ed eseguito originariamente il caso.</span><span class="sxs-lookup"><span data-stu-id="cb30a-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="cb30a-106">È comunque possibile esportarli come file XML (con estensione vtest) per poi importarli in altri server.</span><span class="sxs-lookup"><span data-stu-id="cb30a-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="cb30a-107">Ciò consente di eseguire gli stessi test in computer diversi in punti diversi della topologia.</span><span class="sxs-lookup"><span data-stu-id="cb30a-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="cb30a-108">Per importare un test case di routing vocale</span><span class="sxs-lookup"><span data-stu-id="cb30a-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="cb30a-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cb30a-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="cb30a-110">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cb30a-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="cb30a-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb30a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb30a-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cb30a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cb30a-113">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="cb30a-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="cb30a-114">Scegliere **Importa test case** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="cb30a-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="cb30a-115">Trovare il file del test case che si desidera importare (con estensione vtest) e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="cb30a-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="cb30a-116">Fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="cb30a-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cb30a-117">Tutte le volte che si importa un file vtest, è necessario utilizzare il comando <STRONG>Salva tutto</STRONG> per pubblicare il test case.</span><span class="sxs-lookup"><span data-stu-id="cb30a-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="cb30a-118">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="cb30a-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb30a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb30a-119">See Also</span></span>


[<span data-ttu-id="cb30a-120">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb30a-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

