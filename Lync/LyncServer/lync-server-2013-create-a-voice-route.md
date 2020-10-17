---
title: 'Lync Server 2013: creare una route vocale'
description: 'Lync Server 2013: creare una route vocale.'
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
ms.openlocfilehash: 9a9becac8b35967d7b7ff05014bd6b6600f62a06
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562432"
---
# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="148fd-103">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-103">Create a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="148fd-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="148fd-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="148fd-105">Nella procedura seguente viene illustrato come creare una nuova route vocale utilizzando il pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="148fd-105">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="148fd-106">Per modificare una route esistente, vedere [Modify a Voice Route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) per la procedura.</span><span class="sxs-lookup"><span data-stu-id="148fd-106">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="148fd-107">Per creare una route vocale tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="148fd-107">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="148fd-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="148fd-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="148fd-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="148fd-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="148fd-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="148fd-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="148fd-111">Sulla barra di spostamento sinistra fare clic su **Routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="148fd-111">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="148fd-112">Fare clic su **Route**.</span><span class="sxs-lookup"><span data-stu-id="148fd-112">Click **Route**.</span></span>

5.  <span data-ttu-id="148fd-113">Fare clic su **nuovo** per visualizzare la finestra di dialogo **nuova route vocale** .</span><span class="sxs-lookup"><span data-stu-id="148fd-113">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="148fd-114">In **nome**Digitare un nome descrittivo per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="148fd-114">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="148fd-115">Optional In **Descrizione**digitare altre informazioni descrittive per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="148fd-115">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="148fd-116">Per specificare i modelli che si desidera vengano configurati per l'instradamento, è possibile utilizzare lo strumento **Crea un modello per la corrispondenza** per generare un'espressione regolare o scrivere manualmente l'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="148fd-116">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="148fd-p103">Per utilizzare lo strumento **Formato per corrispondenza** per generare un'espressione regolare, immettere i valori come indicato di seguito. È possibile specificare due tipi di corrispondenze di formato:</span><span class="sxs-lookup"><span data-stu-id="148fd-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="148fd-119">**Cifre iniziali per i numeri che si desidera consentire:** Immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale se necessario).</span><span class="sxs-lookup"><span data-stu-id="148fd-119">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="148fd-120">Ad esempio, digitare **+ 425**, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="148fd-120">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="148fd-121">Ripetere questa operazione per ogni valore di prefisso da includere nella route.</span><span class="sxs-lookup"><span data-stu-id="148fd-121">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="148fd-122">**Eccezioni:** Se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**.</span><span class="sxs-lookup"><span data-stu-id="148fd-122">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="148fd-123">Digitare uno o più valori per i formati di corrispondenza che la route *non* deve includere.</span><span class="sxs-lookup"><span data-stu-id="148fd-123">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="148fd-124">Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore **+ 425237** nel campo **eccezioni** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="148fd-124">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="148fd-125">Per definire manualmente il formato di corrispondenza, fare clic su **Modifica** nello strumento **Formato per corrispondenza** e quindi digitare un'espressione regolare .NET Framework per specificare il formato di corrispondenza per i numeri di telefono di destinazione ai quali viene applicata la route.</span><span class="sxs-lookup"><span data-stu-id="148fd-125">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="148fd-126">Per informazioni dettagliate su come scrivere espressioni regolari, vedere la sezione relativa alle espressioni regolari di .NET Framework all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="148fd-126">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="148fd-p107">Selezionare **Ometti ID chiamante** se non si desidera che l'ID del telefono che effettua la chiamata in uscita venga visualizzato al destinatario della chiamata. Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato sullo schermo dell'ID chiamante del destinatario.</span><span class="sxs-lookup"><span data-stu-id="148fd-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="148fd-129">Per associare uno o più trunk alla route vocale, fare clic su **Aggiungi** e quindi selezionare un trunk dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="148fd-129">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="148fd-130">Se la distribuzione include tutti i Mediation Server di Microsoft Office Communications Server 2007 R2, saranno disponibili anche nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="148fd-130">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="148fd-131">Per associare uno o più utilizzi PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Seleziona** e scegliere un record nell'elenco dei record di utilizzo PSTN definiti per la distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="148fd-131">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="148fd-132">Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="148fd-132">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="148fd-133">Per creare o modificare i record di utilizzo PSTN, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="148fd-133">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="148fd-p108">Disporre i record di utilizzo PSTN per garantire prestazioni ottimali. Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="148fd-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="148fd-136">A differenza di un criterio vocale, in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine in cui i record di utilizzo PSTN sono elencati nella route vocale è insignificante.</span><span class="sxs-lookup"><span data-stu-id="148fd-136">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="148fd-137">Tuttavia, si consiglia di organizzare l'elenco in base alla frequenza di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="148fd-137">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="148fd-138">Ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="148fd-138">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="148fd-139">(Lync Server attraversa l'elenco dall'alto verso il basso).</span><span class="sxs-lookup"><span data-stu-id="148fd-139">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="148fd-p110">Digitare un valore nel campo **Numero convertito da testare** e fare clic su **Vai**. I risultati del test vengono visualizzati nel campo (facoltativo).</span><span class="sxs-lookup"><span data-stu-id="148fd-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="148fd-142">È possibile salvare una route vocale che non passa ancora il test e quindi riconfigurarla successivamente.</span><span class="sxs-lookup"><span data-stu-id="148fd-142">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="148fd-143">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="148fd-143">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="148fd-144">Fare clic su **OK** per salvare la route vocale.</span><span class="sxs-lookup"><span data-stu-id="148fd-144">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="148fd-145">Ogni volta che si crea una route vocale, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="148fd-145">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="148fd-146">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="148fd-146">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="148fd-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="148fd-147">See Also</span></span>


[<span data-ttu-id="148fd-148">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-148">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="148fd-149">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-149">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="148fd-150">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-150">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="148fd-151">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-151">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="148fd-152">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-152">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="148fd-153">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="148fd-153">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

