---
title: 'Lync Server 2013: creare una route vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30a25f9d070c81d45ffc966be49560dc67c292c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="137b6-102">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="137b6-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="137b6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="137b6-104">La procedura seguente spiega come creare una nuova route vocale usando il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="137b6-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="137b6-105">Per modificare una route esistente, vedere [modificare una route vocale in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) per la procedura.</span><span class="sxs-lookup"><span data-stu-id="137b6-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="137b6-106">Per creare una route vocale tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="137b6-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="137b6-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="137b6-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="137b6-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="137b6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="137b6-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="137b6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="137b6-110">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="137b6-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="137b6-111">Fare clic su **Route**.</span><span class="sxs-lookup"><span data-stu-id="137b6-111">Click **Route**.</span></span>

5.  <span data-ttu-id="137b6-112">Fare clic su **nuovo** per visualizzare la finestra di dialogo **nuova route vocale** .</span><span class="sxs-lookup"><span data-stu-id="137b6-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="137b6-113">In **nome**Digitare un nome descrittivo per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="137b6-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="137b6-114">Opzionale In **Descrizione**digitare altre informazioni descrittive per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="137b6-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="137b6-115">Per specificare i motivi per cui si vuole che questa route venga adattata, è possibile usare lo strumento **Crea un modello per abbinarlo** per generare un'espressione regolare o scrivere manualmente l'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="137b6-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="137b6-116">Per usare lo strumento **Crea un motivo per** creare un'espressione regolare, immettere i valori come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="137b6-116">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="137b6-117">È possibile specificare due tipi di criteri di corrispondenza:</span><span class="sxs-lookup"><span data-stu-id="137b6-117">You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="137b6-118">**Cifre iniziali per i numeri che si desidera consentire:** Immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale, se necessario).</span><span class="sxs-lookup"><span data-stu-id="137b6-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="137b6-119">Ad esempio, digitare **+ 425**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="137b6-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="137b6-120">Ripetere questa operazione per ogni valore di prefisso che si vuole includere nella route.</span><span class="sxs-lookup"><span data-stu-id="137b6-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="137b6-121">**Eccezioni:** Se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**.</span><span class="sxs-lookup"><span data-stu-id="137b6-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="137b6-122">Digitare uno o più valori per i criteri di corrispondenza che *non* si vuole includere in questa route.</span><span class="sxs-lookup"><span data-stu-id="137b6-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="137b6-123">Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore **+ 425237** nel campo **eccezioni** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="137b6-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="137b6-124">Per definire il modello di corrispondenza manualmente, fare clic su **modifica** nello strumento Crea modello in modo che **corrisponda** e quindi digitare un'espressione regolare di .NET Framework per specificare il modello di corrispondenza per i numeri di telefono di destinazione a cui è applicata la route.</span><span class="sxs-lookup"><span data-stu-id="137b6-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="137b6-125">Per informazioni dettagliate su come scrivere espressioni regolari, vedere "espressioni regolari di .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span><span class="sxs-lookup"><span data-stu-id="137b6-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="137b6-126">Selezionare **Elimina ID chiamante** se non si vuole che l'ID del telefono che effettua la chiamata in uscita venga visualizzato nel destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="137b6-126">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="137b6-127">Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato nella visualizzazione ID chiamante del destinatario.</span><span class="sxs-lookup"><span data-stu-id="137b6-127">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="137b6-128">Per associare uno o più Trunks alla route vocale, fare clic su **Aggiungi** e quindi selezionare un trunk nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="137b6-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="137b6-129">Se la distribuzione include qualsiasi server di mediazione di Microsoft Office Communications Server 2007 R2, sarà disponibile anche nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="137b6-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="137b6-130">Per associare uno o più usi PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Seleziona** e scegliere un record dall'elenco dei record di utilizzo PSTN definiti per la distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="137b6-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="137b6-131">Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="137b6-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="137b6-132">Per creare o modificare i record di utilizzo PSTN, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="137b6-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="137b6-133">Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="137b6-133">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="137b6-134">Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="137b6-134">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="137b6-135">A differenza di un criterio vocale, in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine in cui i record di utilizzo PSTN sono elencati nella route vocale è irrilevante.</span><span class="sxs-lookup"><span data-stu-id="137b6-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="137b6-136">Tuttavia, ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="137b6-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="137b6-137">Ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="137b6-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="137b6-138">(Lync Server attraversa l'elenco dall'alto verso il basso.)</span><span class="sxs-lookup"><span data-stu-id="137b6-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="137b6-139">Opzionale Digitare un valore nel campo **immettere un numero tradotto in test** e fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="137b6-139">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="137b6-140">I risultati del test vengono visualizzati sotto il campo.</span><span class="sxs-lookup"><span data-stu-id="137b6-140">The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="137b6-141">È possibile salvare una route vocale che non supera ancora il test e quindi riconfigurarla in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="137b6-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="137b6-142">Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="137b6-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="137b6-143">Fare clic su **OK** per salvare la route vocale.</span><span class="sxs-lookup"><span data-stu-id="137b6-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="137b6-144">Ogni volta che si crea una route vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="137b6-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="137b6-145">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="137b6-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="137b6-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="137b6-146">See Also</span></span>


[<span data-ttu-id="137b6-147">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="137b6-148">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="137b6-149">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="137b6-150">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="137b6-151">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="137b6-152">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="137b6-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

