---
title: 'Lync Server 2013: Importare test case di routing vocale'
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
ms.openlocfilehash: 013860ea52773f4109c56bd71d37a9f4b8938225
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="54f09-102">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f09-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f09-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="54f09-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="54f09-104">I casi di test consentono di testare le route vocali nell'organizzazione: si definiscono elementi come il numero da chiamare e il dial plan e il criterio vocale da utilizzare e Lync Server 2013 può quindi verificare che, in base a tali condizioni, il numero fornito possa essere succes sfully essere indirizzato alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="54f09-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="54f09-105">I casi di test, che possono essere creati tramite il pannello di controllo di Lync Server, vengono in genere salvati solo nel server in cui è stato originariamente creato ed eseguito il caso.</span><span class="sxs-lookup"><span data-stu-id="54f09-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="54f09-106">Tuttavia, questi test case possono essere esportati come file XML (con estensione vtest) e quindi importati in altri server.</span><span class="sxs-lookup"><span data-stu-id="54f09-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="54f09-107">In questo modo è possibile eseguire gli stessi test in computer diversi situati in punti diversi della topologia.</span><span class="sxs-lookup"><span data-stu-id="54f09-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="54f09-108">Per importare un test case di routing vocale</span><span class="sxs-lookup"><span data-stu-id="54f09-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="54f09-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54f09-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="54f09-110">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="54f09-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="54f09-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54f09-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54f09-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54f09-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="54f09-113">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="54f09-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="54f09-114">Nel menu **azioni** fare clic su **Importa test case**.</span><span class="sxs-lookup"><span data-stu-id="54f09-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="54f09-115">Individuare il file del test case (con estensione vtest) che si vuole importare e quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="54f09-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="54f09-116">Fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="54f09-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54f09-117">Ogni volta che si importa un file con estensione vtest, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare il test case.</span><span class="sxs-lookup"><span data-stu-id="54f09-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="54f09-118">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="54f09-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54f09-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54f09-119">See Also</span></span>


[<span data-ttu-id="54f09-120">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f09-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

