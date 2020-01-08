---
title: 'Lync Server 2013: eseguire test di routing vocale informale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b47394f595926fe37df9a0809380ed96fa1dec66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a><span data-ttu-id="20b99-102">Eseguire test di routing vocale informale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-102">Run informal voice routing tests in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20b99-103">_**Argomento Ultima modifica:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="20b99-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="20b99-104">È possibile usare la finestra di dialogo **Crea informazioni per il routing vocale** per eseguire test informali prima di creare un vero e proprio test case.</span><span class="sxs-lookup"><span data-stu-id="20b99-104">You can use the **Create voice routing test case information** dialog box to run informal tests before creating an actual test case.</span></span> <span data-ttu-id="20b99-105">Quando si è soddisfatti del risultato di un test, è possibile salvarlo come test case formale.</span><span class="sxs-lookup"><span data-stu-id="20b99-105">When you are satisfied with the outcome of a test, you have the option of saving it as a formal test case.</span></span>

<div>

## <a name="to-run-an-informal-voice-routing-test"></a><span data-ttu-id="20b99-106">Per eseguire un test di routing vocale informale</span><span class="sxs-lookup"><span data-stu-id="20b99-106">To run an informal voice routing test</span></span>

1.  <span data-ttu-id="20b99-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="20b99-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="20b99-108">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="20b99-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="20b99-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="20b99-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="20b99-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="20b99-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="20b99-111">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi fare clic su **Test routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="20b99-111">In the left navigation bar, click **Voice Routing**, and then click **Test Voice Routing**.</span></span>

4.  <span data-ttu-id="20b99-112">Nella pagina **test Voice routing** fare clic su **Crea informazioni sui casi di test per il routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="20b99-112">On the **Test Voice Routing** page, click **Create voice routing test case information**.</span></span>

5.  <span data-ttu-id="20b99-113">Nel campo **numero composto** Digitare il numero di telefono che si vuole usare per questo test.</span><span class="sxs-lookup"><span data-stu-id="20b99-113">In the **Dialed number** field, type in the phone number you want to use for this test.</span></span> <span data-ttu-id="20b99-114">Questo numero verrà normalizzato e visualizzato nel campo **numero normalizzato** del riquadro **risultati** .</span><span class="sxs-lookup"><span data-stu-id="20b99-114">This number will be normalized and displayed in the **Normalized number** field of the **Results** pane.</span></span>

6.  <span data-ttu-id="20b99-115">Nell'elenco **dial plan** selezionare il dial plan da usare per testare il numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="20b99-115">In the **Dial plan** list, select the dial plan to use for testing the dialed number.</span></span> <span data-ttu-id="20b99-116">L'impostazione predefinita è il dial plan globale.</span><span class="sxs-lookup"><span data-stu-id="20b99-116">Default is the Global dial plan.</span></span>
    
    <span data-ttu-id="20b99-117">Quando si esegue il test, la prima regola di normalizzazione in questo dial plan che corrisponde al numero composto verrà visualizzata nel campo **regola di normalizzazione** del riquadro **risultati** .</span><span class="sxs-lookup"><span data-stu-id="20b99-117">When you run the test, the first normalization rule in this dial plan that matches the dialed number will be displayed in the **Normalization rule** field of the **Results** pane.</span></span>

7.  <span data-ttu-id="20b99-118">Nell'elenco dei **criteri vocali** selezionare il criterio vocale da usare per testare il numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="20b99-118">In the **Voice Policy** list, select the voice policy to use for testing the dialed number.</span></span> <span data-ttu-id="20b99-119">L'impostazione predefinita è il criterio vocale globale.</span><span class="sxs-lookup"><span data-stu-id="20b99-119">Default is the Global voice policy.</span></span>
    
    <span data-ttu-id="20b99-120">Quando si esegue il test, il primo record di utilizzo PSTN corrispondente in questo criterio vocale verrà visualizzato nel **primo campo utilizzo PSTN** del riquadro **risultati** .</span><span class="sxs-lookup"><span data-stu-id="20b99-120">When you run the test, the first matching PSTN usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="20b99-121">Inoltre, la prima route vocale corrispondente associata a questo record di utilizzo PSTN verrà visualizzata nel campo **First Route** .</span><span class="sxs-lookup"><span data-stu-id="20b99-121">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

8.  <span data-ttu-id="20b99-122">Opzionale Selezionare la casella **di controllo popola da utente** se si vuole testare il numero di telefono con il criterio vocale assegnato a un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="20b99-122">(Optional) Select the **Populate from user** check box if you want to test the dialed number against the voice policy assigned to a particular user.</span></span>
    
    1.  <span data-ttu-id="20b99-123">Fare clic su **Sfoglia** per visualizzare la finestra di dialogo **Seleziona utenti VoIP aziendale** .</span><span class="sxs-lookup"><span data-stu-id="20b99-123">Click **Browse** to display the **Select Enterprise Voice Users** dialog box.</span></span>
    
    2.  <span data-ttu-id="20b99-124">Fare clic su **trova** per visualizzare l'elenco di utenti abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="20b99-124">Click **Find** to display the list of users who are enabled for Enterprise Voice.</span></span>
    
    3.  <span data-ttu-id="20b99-125">Fare doppio clic sul nome utente di cui si vuole usare il criterio vocale assegnato per questo test.</span><span class="sxs-lookup"><span data-stu-id="20b99-125">Double-click the user name whose assigned voice policy you want to use for this test.</span></span> <span data-ttu-id="20b99-126">Il campo **policy** viene ora popolato con il criterio vocale assegnato all'utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="20b99-126">The **Policy** field is now populated with the voice policy assigned to the selected user.</span></span>
    
    <span data-ttu-id="20b99-127">Quando si esegue il test, il primo record di utilizzo PSTN (Public Switched Telephone Network) corrispondente in questo criterio vocale verrà visualizzato nel **primo campo utilizzo PSTN** del riquadro **risultati** .</span><span class="sxs-lookup"><span data-stu-id="20b99-127">When you run the test, the first matching public switched telephone network (PSTN) usage record in this voice policy will be displayed in the **First PSTN usage** field of the **Results** pane.</span></span> <span data-ttu-id="20b99-128">Inoltre, la prima route vocale corrispondente associata a questo record di utilizzo PSTN verrà visualizzata nel campo **First Route** .</span><span class="sxs-lookup"><span data-stu-id="20b99-128">Also, the first matching voice route that is associated with this PSTN usage record will be displayed in the **First route** field.</span></span>

9.  <span data-ttu-id="20b99-129">Fare clic su **Esegui** per eseguire il test case.</span><span class="sxs-lookup"><span data-stu-id="20b99-129">Click **Run** to run the test case.</span></span> <span data-ttu-id="20b99-130">I risultati vengono visualizzati nel riquadro destro della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="20b99-130">The results are shown in the right panel of the dialog box.</span></span>

10. <span data-ttu-id="20b99-131">Opzionale Fare clic su **Salva come** se si vuole salvare la configurazione di test come test case formale.</span><span class="sxs-lookup"><span data-stu-id="20b99-131">(Optional) Click **Save as** if you want to save this test configuration as a formal test case.</span></span>
    
    1.  <span data-ttu-id="20b99-132">Nel campo **nome** della finestra di dialogo **Salva informazioni sul test case di routing vocale** digitare un nome univoco per il test case.</span><span class="sxs-lookup"><span data-stu-id="20b99-132">In the **Name** field of the **Save Voice Routing Test Case Information** dialog box, type a unique name for the test case.</span></span>
        
        <span data-ttu-id="20b99-133">Il nome deve essere univoco tra tutti i casi di test di routing vocale nella distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="20b99-133">The name must be unique among all voice routing test cases in your Enterprise Voice deployment.</span></span> <span data-ttu-id="20b99-134">Può essere di lunghezza fino a 32 caratteri e può contenere caratteri alfanumerici, oltre alla barra rovesciata (\\), punto (.) o carattere di sottolineatura\_().</span><span class="sxs-lookup"><span data-stu-id="20b99-134">It can be up to 32 characters in length and may contain any alphanumeric characters, in addition to the backslash (\\), period (.), or underscore (\_).</span></span>
    
    2.  <span data-ttu-id="20b99-135">Tieni presente che i campi rimanenti nella finestra di dialogo **Salva informazioni sul test case di routing vocale** sono di sola lettura e vengono prepopolati dalla configurazione *e* dai risultati del test informale.</span><span class="sxs-lookup"><span data-stu-id="20b99-135">Note that the remaining fields on the **Save Voice Routing Test Case Information** dialog box are read-only, and are prepopulated from the informal test configuration *and* results.</span></span> <span data-ttu-id="20b99-136">Verificare che questa sia la configurazione che si vuole salvare per il test case.</span><span class="sxs-lookup"><span data-stu-id="20b99-136">Verify that this is the configuration that you want to save for the test case.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="20b99-137">I valori dei risultati del test vengono usati per precompilare i campi nella finestra di dialogo <STRONG>Salva informazioni sul caso di test del routing vocale</STRONG> come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="20b99-137">Values from the test results are used to prepopulate fields on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box as follows:</span></span> 
        > <UL>
        > <LI>
        > <P><span data-ttu-id="20b99-138">La <STRONG>traduzione prevista</STRONG> viene prepopolata con il valore nel campo <STRONG>numero normalizzato</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="20b99-138"><STRONG>Expected translation</STRONG> is prepopulated with the value in the <STRONG>Normalized number</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="20b99-139">La <STRONG>Route prevista</STRONG> viene prepopolata con il valore nel campo <STRONG>First Route</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="20b99-139"><STRONG>Expected route</STRONG> is prepopulated with the value in the <STRONG>First route</STRONG> field.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="20b99-140">Il <STRONG>record di utilizzo PSTN previsto</STRONG> viene precompilato con il valore nel <STRONG>primo campo utilizzo PSTN</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="20b99-140"><STRONG>Expected PSTN usage record</STRONG> is prepopulated with the value in the <STRONG>First PSTN usage</STRONG> field.</span></span></P></LI></UL><span data-ttu-id="20b99-141">Se non sono state trovate corrispondenze per uno di questi valori durante l'esecuzione di test, il campo corrispondente è vuoto nella finestra di dialogo <STRONG>Salva informazioni sul test case di routing vocale</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="20b99-141">If matches for any of these values were not found during the test run, the corresponding field is empty on the <STRONG>Save Voice Routing Test Case Information</STRONG> dialog box.</span></span>

        
        </div>
    
    3.  <span data-ttu-id="20b99-142">Fare clic su **OK** per salvare il test case oppure fare clic su **Annulla** per tornare alla finestra di dialogo **Visualizza informazioni sul test dei casi di routing vocale** per sviluppare ulteriormente il test prima di salvarlo.</span><span class="sxs-lookup"><span data-stu-id="20b99-142">Click **Ok** to save the test case, or click **Cancel** to return to return to the **View voice routing test case information** dialog box to further develop the test before saving it.</span></span>

11. <span data-ttu-id="20b99-143">Fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="20b99-143">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="20b99-144">Ogni volta che si crea un test case di routing vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare il test case.</span><span class="sxs-lookup"><span data-stu-id="20b99-144">Whenever you create a voice routing test case, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="20b99-145">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="20b99-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20b99-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20b99-146">See Also</span></span>


[<span data-ttu-id="20b99-147">Creare un test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-147">Create a voice routing test case in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-routing-test-case.md)  
[<span data-ttu-id="20b99-148">Eseguire test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-148">Run voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-run-voice-routing-test-cases.md)  
[<span data-ttu-id="20b99-149">Esportare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-149">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
[<span data-ttu-id="20b99-150">Importare test case di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-150">Import voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-import-voice-routing-test-cases.md)  


[<span data-ttu-id="20b99-151">Configurazione dei dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-151">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="20b99-152">Configurazione dei criteri vocali, dei record di utilizzo PSTN e delle route vocali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20b99-152">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

