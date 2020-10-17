---
title: 'Lync Server 2013: esecuzione dei test case di routing vocale'
description: 'Lync Server 2013: eseguire i test case di routing vocale.'
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
ms.openlocfilehash: e521216a12fba6b78913e7f4a79432809bb6e252
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566792"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="8dcd1-103">Eseguire test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dcd1-103">Run voice routing test cases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dcd1-104">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8dcd1-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="8dcd1-105">È possibile eseguire tutti i test case nel gruppo di test case di routing vocale oppure è possibile eseguire uno o più test case selezionati.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-105">You can run all of the test cases in your voice routing test case suite, or you can run one or more selected test cases.</span></span>

<div>

## <a name="to-run-all-voice-routing-test-cases"></a><span data-ttu-id="8dcd1-106">Per eseguire tutti i test case di routing vocale</span><span class="sxs-lookup"><span data-stu-id="8dcd1-106">To run all voice routing test cases</span></span>

1.  <span data-ttu-id="8dcd1-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8dcd1-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8dcd1-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8dcd1-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8dcd1-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8dcd1-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8dcd1-111">Nella barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-111">In the left navigation bar, click **Voice Routing** and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="8dcd1-112">Nella pagina **Test routing vocale** fare clic su **azione** e quindi su **Esegui tutto**.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-112">On the **Test Voice Routing** page, click **Action** and then click **Run all**.</span></span>
    
    <span data-ttu-id="8dcd1-113">Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="8dcd1-113">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="8dcd1-114">Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/a.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-114">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

5.  <span data-ttu-id="8dcd1-115">Optional Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-115">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="8dcd1-116">I risultati vengono visualizzati nell'area ombreggiata a destra della pagina **modifica test case** :</span><span class="sxs-lookup"><span data-stu-id="8dcd1-116">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="8dcd1-117">**Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-117">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="8dcd1-118">**Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto, ovvero il valore nel campo **numero da testare** .</span><span class="sxs-lookup"><span data-stu-id="8dcd1-118">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="8dcd1-119">**Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha convertito.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-119">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="8dcd1-120">**Primo utilizzo PSTN:** Il primo record di utilizzo PSTN (Public Switched Telephone Network) nel criterio vocale selezionato per questo test case che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-120">**First PSTN usage:** The first public switched telephone network (PSTN) usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="8dcd1-121">**Prima route:** La prima route vocale del primo record di utilizzo PSTN che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-121">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8dcd1-122">Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione del test case di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-122">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="8dcd1-123">Se il test case non specifica questi valori, il campo corrispondente nei risultati dei test sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-123">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a><span data-ttu-id="8dcd1-124">Per eseguire uno o più test case di routing vocale selezionati</span><span class="sxs-lookup"><span data-stu-id="8dcd1-124">To run one or more selected voice routing test cases</span></span>

1.  <span data-ttu-id="8dcd1-125">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-125">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8dcd1-126">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8dcd1-126">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8dcd1-127">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-127">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8dcd1-128">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8dcd1-128">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8dcd1-129">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-129">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="8dcd1-130">Nella pagina **Test routing vocale** fare clic sui nomi dei test case che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-130">On the **Test Voice Routing** page, click the names of the test cases that you want to run.</span></span>

5.  <span data-ttu-id="8dcd1-131">Scegliere **Esegui selezionato**dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="8dcd1-131">On the **Action** menu, click **Run selected**.</span></span>
    
    <span data-ttu-id="8dcd1-132">Lo stato superato o non superato di ogni test case viene visualizzato nella colonna **pass/fail** .</span><span class="sxs-lookup"><span data-stu-id="8dcd1-132">The pass or fail status of each test case is shown in the **Pass/fail** column.</span></span> <span data-ttu-id="8dcd1-133">Se un test case non è ancora stato eseguito, nella colonna **pass/fail** viene visualizzato N/a.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-133">If a test case has not yet been run, N/A is shown in the **Pass/fail** column.</span></span>

6.  <span data-ttu-id="8dcd1-134">Optional Per visualizzare i risultati dettagliati per ogni test case, fare doppio clic sul nome del test case.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-134">(Optional) To see detailed results for each test case, double-click the test case name.</span></span> <span data-ttu-id="8dcd1-135">I risultati vengono visualizzati nell'area ombreggiata a destra della pagina **modifica test case** :</span><span class="sxs-lookup"><span data-stu-id="8dcd1-135">Results are shown in the shaded area on the right side of the **Edit Test Case** page:</span></span>
    
    1.  <span data-ttu-id="8dcd1-136">**Risultato del test:** Stato globale superato o non superato dell'esecuzione del test case.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-136">**Test result:** Overall pass or fail status of the test case run.</span></span>
    
    2.  <span data-ttu-id="8dcd1-137">**Regola di normalizzazione:** La prima regola di normalizzazione nel dial plan selezionato per questo test case che corrisponde al numero composto, ovvero il valore nel campo **numero da testare** .</span><span class="sxs-lookup"><span data-stu-id="8dcd1-137">**Normalization rule:** The first normalization rule in the dial plan selected for this test case that matches the dialed number (the value in the **Number to test** field).</span></span>
    
    3.  <span data-ttu-id="8dcd1-138">**Numero normalizzato:** Il valore del numero composto dopo che la regola di normalizzazione lo ha convertito.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-138">**Normalized number:** The value of the dialed number after the normalization rule has translated it.</span></span>
    
    4.  <span data-ttu-id="8dcd1-139">**Primo utilizzo PSTN:** Il primo record di utilizzo PSTN del criterio vocale selezionato per questo test case che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-139">**First PSTN usage:** The first PSTN usage record in the voice policy selected for this test case that matches the dialed number.</span></span>
    
    5.  <span data-ttu-id="8dcd1-140">**Prima route:** La prima route vocale del primo record di utilizzo PSTN che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-140">**First route:** The first voice route in the first PSTN usage record that matches the dialed number.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8dcd1-141">Il <STRONG>record di utilizzo PSTN previsto</STRONG> e i campi <STRONG>Route previsti</STRONG> sono facoltativi nella configurazione del test case di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-141">The <STRONG>Expected PSTN usage record</STRONG> and <STRONG>Expected route</STRONG> fields are optional in voice routing test case configuration.</span></span> <span data-ttu-id="8dcd1-142">Se il test case non specifica questi valori, il campo corrispondente nei risultati dei test sarà vuoto.</span><span class="sxs-lookup"><span data-stu-id="8dcd1-142">If the test case does not specify these values, the corresponding field in the test results will be empty.</span></span>

        
        </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8dcd1-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8dcd1-143">See Also</span></span>


[<span data-ttu-id="8dcd1-144">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dcd1-144">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
[<span data-ttu-id="8dcd1-145">Esecuzione di test del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8dcd1-145">Running voice routing tests in Lync Server 2013</span></span>](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

