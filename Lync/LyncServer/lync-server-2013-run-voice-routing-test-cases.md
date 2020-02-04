---
title: 'Lync Server 2013: esecuzione di test case di routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="43dac-102">Eseguire test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43dac-102">Run voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43dac-103">_**Argomento Ultima modifica:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="43dac-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="43dac-104">È possibile eseguire tutti i test case nella famiglia di test case con routing vocale oppure eseguire uno o più test case selezionati.</span><span class="sxs-lookup"><span data-stu-id="43dac-104">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="43dac-105">Per eseguire tutti i test case di routing vocale</span><span class="sxs-lookup"><span data-stu-id="43dac-105">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="43dac-106">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="43dac-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="43dac-107">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="43dac-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="43dac-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43dac-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43dac-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="43dac-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43dac-110">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="43dac-110">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="43dac-111">Nella pagina **test Voice routing** fare clic su **azione** e quindi su **Esegui tutto**.</span><span class="sxs-lookup"><span data-stu-id="43dac-111">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="43dac-112">Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="43dac-112">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="43dac-113">Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/d.</span><span class="sxs-lookup"><span data-stu-id="43dac-113">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="43dac-114">Opzionale Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case.</span><span class="sxs-lookup"><span data-stu-id="43dac-114">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="43dac-115">I risultati vengono visualizzati nell'area ombreggiata sul lato destro della pagina **modifica test case** :</span><span class="sxs-lookup"><span data-stu-id="43dac-115">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="43dac-116">**Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.</span><span class="sxs-lookup"><span data-stu-id="43dac-116">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="43dac-117">**Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto (il valore nel campo **numero da testare** ).</span><span class="sxs-lookup"><span data-stu-id="43dac-117">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="43dac-118">**Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha tradotto.</span><span class="sxs-lookup"><span data-stu-id="43dac-118">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="43dac-119">**Primo utilizzo PSTN:** Il primo record di utilizzo PSTN (Public Switched Telephone Network) nel criterio vocale selezionato per questo test case che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="43dac-119">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="43dac-120">**Prima route:** La prima route vocale nel primo record di utilizzo PSTN che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="43dac-120">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43dac-121">Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione dei test dei casi di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="43dac-121">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="43dac-122">Se il test case non specifica questi valori, il campo corrispondente nei risultati del test sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="43dac-122">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="43dac-123">Per eseguire uno o più casi di test di routing vocale selezionati</span><span class="sxs-lookup"><span data-stu-id="43dac-123">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="43dac-124">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="43dac-124">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="43dac-125">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="43dac-125">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="43dac-126">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="43dac-126">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="43dac-127">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="43dac-127">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="43dac-128">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi fare clic su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="43dac-128">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="43dac-129">Nella pagina **test Voice routing** fare clic sui nomi dei test case che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="43dac-129">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="43dac-130">Nel menu **azione** fare clic su **Esegui selezionato**.</span><span class="sxs-lookup"><span data-stu-id="43dac-130">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="43dac-131">Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="43dac-131">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="43dac-132">Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/d.</span><span class="sxs-lookup"><span data-stu-id="43dac-132">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="43dac-133">Opzionale Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case.</span><span class="sxs-lookup"><span data-stu-id="43dac-133">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="43dac-134">I risultati vengono visualizzati nell'area ombreggiata sul lato destro della pagina **modifica test case** :</span><span class="sxs-lookup"><span data-stu-id="43dac-134">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="43dac-135">**Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.</span><span class="sxs-lookup"><span data-stu-id="43dac-135">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="43dac-136">**Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto (il valore nel campo **numero da testare** ).</span><span class="sxs-lookup"><span data-stu-id="43dac-136">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="43dac-137">**Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha tradotto.</span><span class="sxs-lookup"><span data-stu-id="43dac-137">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="43dac-138">**Primo utilizzo PSTN:** Il primo record di utilizzo PSTN nel criterio vocale selezionato per questo test case che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="43dac-138">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="43dac-139">**Prima route:** La prima route vocale nel primo record di utilizzo PSTN che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="43dac-139">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="43dac-140">Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione dei test dei casi di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="43dac-140">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="43dac-141">Se il test case non specifica questi valori, il campo corrispondente nei risultati del test sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="43dac-141">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43dac-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43dac-142">See Also</span></span>


[<span data-ttu-id="43dac-143">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43dac-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="43dac-144">Esecuzione di test del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43dac-144">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

