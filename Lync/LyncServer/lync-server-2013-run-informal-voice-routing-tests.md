---
title: 'Lync Server 2013: esecuzione di test di routing vocale informali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fd8c20adfa98a10bd0b9a89ad31dda37e4510e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511163"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="4f78c-102">Eseguire test informali di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-102">Run informal voice routing tests in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f78c-103">_**Ultimo argomento modificato:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="4f78c-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="4f78c-p101">È possibile utilizzare la finestra di dialogo **Crea informazioni test case routing vocale** per eseguire test informativi prima di creare un test case vero e proprio. Quando si è soddisfatti del risultato di un test, è possibile salvarlo come test case formale.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p101">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case. When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="4f78c-106">Per eseguire un test informale del routing vocale</span><span class="sxs-lookup"><span data-stu-id="4f78c-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="4f78c-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4f78c-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4f78c-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4f78c-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4f78c-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f78c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f78c-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4f78c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4f78c-111">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="4f78c-112">Nella pagina **Test routing vocale** fare clic su **Crea informazioni test case routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="4f78c-p104">Nel campo **Numero composto** digitare il numero di telefono da utilizzare per il test. Questo numero verrà normalizzato e visualizzato nel campo **Numero normalizzato** del riquadro **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p104">In the **Dialed number** field, type in the phone number you want to use for this test. This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="4f78c-p105">Nell'elenco **Dial plan** selezionare il dial plan da utilizzare per il test del numero composto. Per impostazione predefinita viene utilizzato il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p105">In the **Dial plan** list, select the dial plan to use for testing the dialed number. Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="4f78c-117">Quando si esegue il test, la prima regola di normalizzazione del dial plan che corrisponde al numero composto verrà visualizzata nel campo **Regola di normalizzazione** del riquadro **Risultati**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="4f78c-p106">Nell'elenco **Criteri vocali** selezionare i criteri vocali da utilizzare per il test del numero composto. Per impostazione predefinita vengono utilizzati i criteri vocali globali.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p106">In the **Voice Policy** list, select the voice policy to use for testing the dialed number. Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="4f78c-p107">Quando si esegue il test, il primo record di utilizzo PSTN dei criteri vocali verrà visualizzato nel campo **Primo utilizzo PSTN** del riquadro **Risultati**. Inoltre, la prima route vocale corrispondente associata a questo record di utilizzo PSTN verrà visualizzata nel campo **Prima route**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p107">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="4f78c-122">(Facoltativo) Selezionare la casella di controllo **Popola da utente** se si desidera testare il numero composto rispetto ai criteri vocali assegnati a un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="4f78c-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="4f78c-123">Fare clic su **Sfoglia** per visualizzare la finestra di dialogo **Seleziona utenti VoIP aziendale**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="4f78c-124">Fare clic su **Trova** per visualizzare l'elenco di utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="4f78c-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="4f78c-p108">Fare doppio clic dell'utente a cui sono assegnati i criteri vocali da utilizzare per il test. Il campo **Criteri** viene ora popolato con i criteri vocali assegnati all'utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p108">Double-click the user name whose assigned voice policy you want to use for this test. The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="4f78c-p109">Quando si esegue il test, il primo record di utilizzo PSTN (Public Switched Telephone Network) dei criteri vocali corrispondente verrà visualizzato nel campo **Primo utilizzo PSTN** del riquadro **Risultati**. Inoltre, la prima route vocale corrispondente associata a questo record di utilizzo PSTN verrà visualizzata nel campo **Prima route**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p109">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane. Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="4f78c-p110">Fare clic su **Esegui** per eseguire il test case. I risultati verranno visualizzati nel pannello destro della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p110">Click **Run** to run the test case. The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="4f78c-131">(Facoltativo) Fare clic su **Salva con nome** se si desidera salvare questa configurazione di test come test case formale.</span><span class="sxs-lookup"><span data-stu-id="4f78c-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="4f78c-132">Nel campo **Nome** della finestra di dialogo **Salva informazioni test case routing vocale** digitare un nome univoco per il test case.</span><span class="sxs-lookup"><span data-stu-id="4f78c-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="4f78c-133">Il nome deve essere univoco tra tutti i test case di routing vocale nella distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="4f78c-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="4f78c-134">Può avere una lunghezza massima di 32 caratteri e può contenere caratteri alfanumerici, oltre alla barra rovesciata ( \\ ), al punto (.) o al carattere di sottolineatura ( \_ ).</span><span class="sxs-lookup"><span data-stu-id="4f78c-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="4f78c-p112">Si noti che i campi rimanenti della finestra di dialogo **Salva informazioni test case routing vocale** sono di sola lettura e vengono compilati preventivamente dai risultati *e* dalla configurazione di test informale. Verificare che la configurazione sia quella che si desidera salvare per il test case.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p112">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results. Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4f78c-137">I valori dei risultati vengono utilizzati per prepopolare i campi nella finestra di dialogo <STRONG>Salva informazioni test case routing vocale</STRONG> come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4f78c-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="4f78c-138">Il campo <STRONG>Conversione prevista</STRONG> è prepopolato con il valore del campo <STRONG>Numero normalizzato</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f78c-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="4f78c-139">Il campo <STRONG>Route prevista</STRONG> è prepopolato con il valore del campo <STRONG>Prima route</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f78c-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="4f78c-140">Il campo <STRONG>Utilizzo PSTN previsto</STRONG> è prepopolato con il valore del campo <STRONG>Primo utilizzo PSTN</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f78c-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="4f78c-p113">Se durante l'esecuzione del test non vengono trovate corrispondenze per uno di questi valori, il campo corrispondente sarà vuoto nella finestra di dialogo <STRONG>Salva informazioni test case routing vocale</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4f78c-p113">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.   </span></span></div>
    
    3.  <span data-ttu-id="4f78c-142">Fare clic su **OK** per salvare il test case oppure su **Annulla** per tornare alla finestra di dialogo **Crea informazioni test case routing vocale** per sviluppare ulteriormente il test prima di salvarlo.</span><span class="sxs-lookup"><span data-stu-id="4f78c-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="4f78c-143">Fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="4f78c-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f78c-144">Ogni volta che si crea un test case di routing vocale, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicarlo.</span><span class="sxs-lookup"><span data-stu-id="4f78c-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="4f78c-145">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="4f78c-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f78c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f78c-146">See Also</span></span>


[<span data-ttu-id="4f78c-147">Creare un test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="4f78c-148">Eseguire test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="4f78c-149">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="4f78c-150">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="4f78c-151">Configurazione di dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="4f78c-152">Configurazione di criteri vocali, record di utilizzo PSTN e route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f78c-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

