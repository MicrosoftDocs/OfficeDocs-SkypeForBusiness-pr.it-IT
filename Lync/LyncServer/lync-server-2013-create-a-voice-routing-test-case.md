---
title: 'Lync Server 2013: Creare un test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice routing test case
ms:assetid: 43a07a5b-2f20-462a-81e5-d628c18391e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425935(v=OCS.15)
ms:contentKeyID: 48183979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a98e8b9400b0a268474429ad464b1aef7bbbe56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-routing-test-case-in-lync-server-2013"></a><span data-ttu-id="0866d-102">Creare un test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0866d-102">Create a voice routing test case in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0866d-103">_**Argomento Ultima modifica:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="0866d-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<div>

## <a name="to-create-a-test-case"></a><span data-ttu-id="0866d-104">Per creare un test case</span><span class="sxs-lookup"><span data-stu-id="0866d-104">To create a test case</span></span>

1.  <span data-ttu-id="0866d-105">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0866d-105">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0866d-106">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0866d-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0866d-107">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0866d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0866d-108">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0866d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0866d-109">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="0866d-109">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="0866d-110">Nella pagina **test Voice routing** fare clic su **nuovo** per creare un nuovo test case.</span><span class="sxs-lookup"><span data-stu-id="0866d-110">On the **Test Voice Routing** page, click **New** to create a new test case.</span></span>

5.  <span data-ttu-id="0866d-111">In **nome**Digitare un nome univoco per il test case.</span><span class="sxs-lookup"><span data-stu-id="0866d-111">In **Name**, type in a unique name for the test case.</span></span>
    
    <span data-ttu-id="0866d-112">Il nome deve essere univoco tra tutti i casi di test di routing vocale nella distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="0866d-112">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="0866d-113">Può essere di lunghezza fino a 32 caratteri e può contenere caratteri alfanumerici, oltre alla barra rovesciata (\\), punto (.) o carattere di sottolineatura\_().</span><span class="sxs-lookup"><span data-stu-id="0866d-113">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>

6.  <span data-ttu-id="0866d-114">In **numero composto da testare**Digitare il numero composto che si vuole usare per verificare la configurazione di routing specificata per il test case.</span><span class="sxs-lookup"><span data-stu-id="0866d-114">In **Dialed number to test**, type in the dialed number that you want to use to test the routing configuration that you specify for this test case.</span></span> <span data-ttu-id="0866d-115">In base ai criteri di dial plan, route e Voice, questo numero verrà normalizzato e visualizzato come output.</span><span class="sxs-lookup"><span data-stu-id="0866d-115">Based on the dial plan, route, and voice policy, this number will be normalized and displayed as output.</span></span>

7.  <span data-ttu-id="0866d-116">Nell'elenco **dial plan** selezionare il dial plan da usare durante l'esecuzione del test.</span><span class="sxs-lookup"><span data-stu-id="0866d-116">In the **Dial Plan** list, select the dial plan to use when running the test.</span></span> <span data-ttu-id="0866d-117">L'impostazione predefinita è il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="0866d-117">Default is the Global dial plan.</span></span>

8.  <span data-ttu-id="0866d-118">Nell'elenco dei **criteri vocali** selezionare il criterio vocale da usare quando si eseguirà il test.</span><span class="sxs-lookup"><span data-stu-id="0866d-118">In the **Voice Policy** list, select the voice policy to use when running the test.</span></span> <span data-ttu-id="0866d-119">L'impostazione predefinita è il criterio vocale globale.</span><span class="sxs-lookup"><span data-stu-id="0866d-119">Default is the Global voice policy.</span></span>

9.  <span data-ttu-id="0866d-120">Nella **traduzione prevista**Digitare il numero di telefono nel formato che si prevede venga visualizzato dopo la traduzione.</span><span class="sxs-lookup"><span data-stu-id="0866d-120">In **Expected translation**, type in the phone number in the format you expect to see it after translation.</span></span> <span data-ttu-id="0866d-121">Questo è il valore del numero di telefono che stai testando dopo che è stato tradotto dalla prima regola di normalizzazione che corrisponde al dial plan selezionato.</span><span class="sxs-lookup"><span data-stu-id="0866d-121">This is the value of the phone number that you are testing after it has been translated by the first normalization rule that matches in the selected dial plan.</span></span> <span data-ttu-id="0866d-122">Quando si esegue il test case, se il numero che si sta testando non restituisce il valore nella **traduzione prevista**, il test ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="0866d-122">When you run the test case, if the number you are testing does not result in the value in **Expected translation**, the test fails.</span></span>

10. <span data-ttu-id="0866d-123">Opzionale Nell'elenco di **utilizzo PSTN previsto** , è possibile selezionare il record di utilizzo PSTN (Public Switched Telephone Network) che si prevede venga usato quando si esegue il test case, in base al piano di chiamata e al criterio vocale specificati.</span><span class="sxs-lookup"><span data-stu-id="0866d-123">(Optional) In the **Expected PSTN usage** list, you can select the public switched telephone network (PSTN) usage record that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="0866d-124">Se viene usato un record di utilizzo PSTN diverso, il test non riesce.</span><span class="sxs-lookup"><span data-stu-id="0866d-124">If a different PSTN usage record is used, the test fails.</span></span>

11. <span data-ttu-id="0866d-125">Opzionale Nell'elenco di **Route previsto** è possibile selezionare la route vocale che si prevede venga usata quando si esegue il test case, in base al piano di chiamata e al criterio vocale specificati.</span><span class="sxs-lookup"><span data-stu-id="0866d-125">(Optional) In the **Expected route** list, you can select the voice route that you expect to be used when you run the test case, based on the specified dial plan and voice policy.</span></span> <span data-ttu-id="0866d-126">Se viene usata una route vocale diversa, il test non riesce.</span><span class="sxs-lookup"><span data-stu-id="0866d-126">If a different voice route is used, the test fails.</span></span>

12. <span data-ttu-id="0866d-127">Opzionale Fare clic su **Esegui** per eseguire il test case.</span><span class="sxs-lookup"><span data-stu-id="0866d-127">(Optional) Click **Run** to run the test case.</span></span> <span data-ttu-id="0866d-128">I risultati vengono visualizzati nel riquadro destro della pagina.</span><span class="sxs-lookup"><span data-stu-id="0866d-128">The results are shown in the right panel of the page.</span></span>

13. <span data-ttu-id="0866d-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0866d-129">Click **OK**.</span></span>

14. <span data-ttu-id="0866d-130">Fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="0866d-130">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0866d-131">Ogni volta che si crea un test case di routing vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="0866d-131">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0866d-132">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="0866d-132">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="0866d-133">Se il dial plan usato nel test normalizza i numeri di telefono che iniziano con un segno più (ad esempio + 12065551219), tale piano può causare un errore del test di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="0866d-133">If the dial plan being employed in the test normalizes phone numbers that begin with a plus sign (for example, +12065551219), that plan might cause the voice routing test to fail.</span></span> <span data-ttu-id="0866d-134">(Il dial plan e la route vocale funzioneranno; in realtà, Test-CsDialPlan avrà successo.</span><span class="sxs-lookup"><span data-stu-id="0866d-134">(The dial plan and the voice route will work; in fact, Test-CsDialPlan will succeed.</span></span> <span data-ttu-id="0866d-135">Tuttavia, il test di routing vocale potrebbe non riuscire.) Questo è un aspetto da ricordare durante il test delle route vocali.</span><span class="sxs-lookup"><span data-stu-id="0866d-135">However, the voice routing test might fail.) This is something to keep in mind when testing voice routes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0866d-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0866d-136">See Also</span></span>


[<span data-ttu-id="0866d-137">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0866d-137">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="0866d-138">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0866d-138">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="0866d-139">Configurazione dei dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0866d-139">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="0866d-140">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0866d-140">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

