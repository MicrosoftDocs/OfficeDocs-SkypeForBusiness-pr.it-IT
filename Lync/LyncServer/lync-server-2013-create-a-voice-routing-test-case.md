---
title: 'Lync Server 2013: creare un test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9fac6f65d1bb1c04b8d8597454df775f8545d2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="09663-102">Creare un test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09663-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09663-103">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="09663-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="09663-104">Per creare un test case</span><span class="sxs-lookup"><span data-stu-id="09663-104">To create a test case</span></span>

1.  <span data-ttu-id="09663-105">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="09663-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="09663-106">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="09663-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="09663-107">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09663-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="09663-108">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="09663-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="09663-109">Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="09663-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="09663-110">Nella pagina **Test routing vocale** fare clic su **Nuovo** per creare un nuovo test case.</span><span class="sxs-lookup"><span data-stu-id="09663-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="09663-111">Nel campo **Nome** digitare un nome univoco per il test case.</span><span class="sxs-lookup"><span data-stu-id="09663-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="09663-112">Il nome deve essere univoco tra tutti i test case di routing vocale nella distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="09663-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="09663-113">Può avere una lunghezza massima di 32 caratteri e può contenere caratteri alfanumerici, oltre alla barra rovesciata (\\), al punto (.) o al carattere di sottolineatura (\_).</span><span class="sxs-lookup"><span data-stu-id="09663-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="09663-p104">Nel campo **Numero composto da testare** digitare il numero composto che si desidera utilizzare per testare la configurazione di routing specificata per il test case. A seconda del dial plan, della route e del criterio vocale, questo numero verrà normalizzato e visualizzato come output.</span><span class="sxs-lookup"><span data-stu-id="09663-p104">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case. Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="09663-p105">Nell'elenco **Dial plan** selezionare il dial plan da utilizzare per eseguire il test. Il dial pan predefinito è quello globale.</span><span class="sxs-lookup"><span data-stu-id="09663-p105">In the **Dial Plan** list, select the dial plan to use when running the test. Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="09663-p106">Nell'elenco **Criteri vocali** selezionare il criterio vocale da utilizzare per eseguire il test. Il criterio vocale predefinito è quello globale.</span><span class="sxs-lookup"><span data-stu-id="09663-p106">In the **Voice Policy** list, select the voice policy to use when running the test. Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="09663-p107">Nel campo **Conversione prevista** digitare il numero di telefono nel formato previsto dopo la conversione. Questo è il valore del numero di telefono che si desidera testare, dopo la conversione da parte della prima regola di normalizzazione corrispondente nel dial plan selezionato. Se, quando si esegue il test case, il numero che si desidera testare non viene convertito nel valore riportato nel campo **Conversione prevista**, il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="09663-p107">In **Expected translation**, type in the phone number in the format you expect to see it after translation. This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan. When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="09663-p108">(Facoltativo) Nell'elenco **Utilizzo PSTN previsto** è possibile selezionare il record di utilizzo PSTN (Public Switched Telephone Network) che si prevede venga utilizzato quando si esegue il test case, a seconda del dial plan e del criterio vocale selezionati. Se viene utilizzato un record di utilizzo PSTN diverso, il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="09663-p108">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="09663-p109">(Facoltativo) Nell'elenco **Route prevista** è possibile selezionare la route vocale che si prevede venga utilizzata quando si esegue il test case, a seconda del dial plan e del criterio vocale selezionati. Se viene utilizzata una route vocale diversa, il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="09663-p109">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy. If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="09663-p110">(Facoltativo) Fare clic su **Esegui** per eseguire il test case. I risultati verranno visualizzati nel riquadro destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="09663-p110">(Optional) Click **Run** to run the test case. The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="09663-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="09663-129">Click **OK**.</span></span>

14. <span data-ttu-id="09663-130">Fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="09663-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="09663-131">Ogni volta che si crea un test case di routing vocale, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="09663-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="09663-132">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="09663-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="09663-133">Se il dial plan utilizzato nel test normalizza i numeri di telefono che iniziano con un segno di addizione, ad esempio + 12065551219, tale piano potrebbe causare l'esito negativo del test di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="09663-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="09663-134">(Il dial plan e la route vocale funzioneranno, in effetti, Test-CsDialPlan avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="09663-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="09663-135">Tuttavia, il test di routing vocale potrebbe avere esito negativo. Questo è un aspetto da tenere presente quando si testano le route vocali.</span><span class="sxs-lookup"><span data-stu-id="09663-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="09663-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09663-136">See Also</span></span>


[<span data-ttu-id="09663-137">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09663-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="09663-138">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09663-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="09663-139">Configurazione di dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09663-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="09663-140">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09663-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

