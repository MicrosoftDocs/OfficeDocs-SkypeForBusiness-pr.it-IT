---
title: 'Lync Server 2013: modificare una route vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0731383eea99e7510ef1748777e7139e2d9f369
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="7a126-102">Modificare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a126-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7a126-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7a126-104">Questo argomento spiega come modificare una route vocale.</span><span class="sxs-lookup"><span data-stu-id="7a126-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="7a126-105">Per creare una nuova route, vedere [creare una route vocale in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="7a126-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="7a126-106">Per modificare una route vocale</span><span class="sxs-lookup"><span data-stu-id="7a126-106">To modify a voice route</span></span>

1.  <span data-ttu-id="7a126-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7a126-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7a126-108">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="7a126-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="7a126-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a126-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7a126-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7a126-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7a126-111">Sulla barra di spostamento sinistra fare clic su **routing vocale**e quindi su **instrada**.</span><span class="sxs-lookup"><span data-stu-id="7a126-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="7a126-112">Nella pagina **Route** usare uno dei metodi seguenti per modificare una route vocale:</span><span class="sxs-lookup"><span data-stu-id="7a126-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="7a126-113">Fare clic sul nome di una route vocale, scegliere **modifica**e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7a126-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="7a126-114">Fare clic sul nome di una route vocale, scegliere **modifica**, fare clic su **copia**e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="7a126-114">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="7a126-115">Fare clic sulla nuova copia della route vocale appena creata, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7a126-115">Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7a126-116">Nel campo **nome** della pagina **modifica route vocale** digitare un nome descrittivo per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="7a126-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="7a126-117">Opzionale Nel campo **Descrizione** digitare altre informazioni descrittive per la route vocale.</span><span class="sxs-lookup"><span data-stu-id="7a126-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="7a126-118">Per specificare i motivi per cui si vuole che questa route sia adatta, è possibile usare lo strumento **Crea un modello per abbinarlo** per generare un'espressione regolare o scrivere manualmente l'espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="7a126-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="7a126-119">Per usare lo strumento **Crea un motivo per** creare un'espressione regolare, immettere i valori come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7a126-119">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="7a126-120">È possibile specificare due tipi di criteri di corrispondenza:</span><span class="sxs-lookup"><span data-stu-id="7a126-120">You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="7a126-121">**Cifre iniziali per i numeri che si desidera consentire:** Immettere i valori di prefisso che questa route deve contenere (incluso il + iniziale, se necessario).</span><span class="sxs-lookup"><span data-stu-id="7a126-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="7a126-122">Ad esempio, digitare **+ 425** e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7a126-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="7a126-123">Ripetere questa operazione per ogni valore di prefisso che si vuole includere nella route.</span><span class="sxs-lookup"><span data-stu-id="7a126-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="7a126-124">**Eccezioni:** Se si desidera specificare una o più eccezioni per un valore di prefisso, evidenziare il prefisso e fare clic su **eccezioni**.</span><span class="sxs-lookup"><span data-stu-id="7a126-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="7a126-125">Digitare uno o più valori per i criteri di corrispondenza che *non* si vuole includere in questa route.</span><span class="sxs-lookup"><span data-stu-id="7a126-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="7a126-126">Ad esempio, per escludere i numeri che iniziano con + 425237 dalla Route, immettere il valore **+ 425237** nel campo **eccezioni** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a126-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="7a126-127">Per definire il modello di corrispondenza manualmente, fare clic su **modifica** nello strumento Crea modello in modo che **corrisponda** e quindi digitare un'espressione regolare di .NET Framework per specificare il modello di corrispondenza per i numeri di telefono di destinazione a cui è applicata la route.</span><span class="sxs-lookup"><span data-stu-id="7a126-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="7a126-128">Per informazioni su come scrivere espressioni regolari, vedere "espressioni regolari di .NET Framework" [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span><span class="sxs-lookup"><span data-stu-id="7a126-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="7a126-129">Selezionare **Elimina ID chiamante** se non si vuole che l'ID del telefono che sta effettuando la chiamata in uscita venga visualizzato nel destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7a126-129">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="7a126-130">Se si seleziona questa opzione, è necessario specificare un **ID chiamante alternativo** che verrà visualizzato nella visualizzazione ID chiamante del destinatario.</span><span class="sxs-lookup"><span data-stu-id="7a126-130">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="7a126-131">Per associare uno o più Trunks PSTN (Public Switched Telephone Network) alla route vocale, fare clic su **Aggiungi**e quindi selezionare un trunk nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a126-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a126-132">Se la distribuzione include qualsiasi server di mediazione di Microsoft Office Communications Server 2007 R2, sarà disponibile anche nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7a126-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="7a126-133">Per associare uno o più usi PSTN alla route vocale, fare clic su **Seleziona** e scegliere un record dall'elenco dei record di utilizzo PSTN definiti per la distribuzione vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="7a126-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a126-134">Per visualizzare le proprietà di ognuno dei record di utilizzo PSTN disponibili, vedere <A href="lync-server-2013-view-pstn-usage-records.md">visualizzare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7a126-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="7a126-135">Per creare o modificare i record di utilizzo PSTN, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7a126-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="7a126-136">Disporre i record di utilizzo PSTN per ottenere prestazioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="7a126-136">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="7a126-137">Per modificare la posizione di un record nell'elenco, evidenziare il nome del record e fare clic sulla freccia verso l'alto o verso il basso.</span><span class="sxs-lookup"><span data-stu-id="7a126-137">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a126-138">A differenza di un criterio vocale in cui l'ordine in cui sono elencati i record di utilizzo PSTN è importante, l'ordine dei record di utilizzo PSTN in una route vocale non è significativo.</span><span class="sxs-lookup"><span data-stu-id="7a126-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="7a126-139">Tuttavia, ti consigliamo di organizzare l'elenco in base alla frequenza di utilizzo, ad esempio: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="7a126-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="7a126-140">(Lync Server attraversa l'elenco dall'alto verso il basso.)</span><span class="sxs-lookup"><span data-stu-id="7a126-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="7a126-141">Opzionale Digitare un valore nel campo **immettere un numero tradotto in test** e fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="7a126-141">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="7a126-142">I risultati del test vengono visualizzati sotto il campo.</span><span class="sxs-lookup"><span data-stu-id="7a126-142">The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a126-143">È possibile salvare una route vocale che non supera ancora il test e quindi riconfigurarla in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7a126-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="7a126-144">Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7a126-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="7a126-145">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7a126-145">Click **OK**.</span></span>

14. <span data-ttu-id="7a126-146">Nella pagina **Route** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="7a126-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a126-147">Ogni volta che si crea o si modifica una route vocale, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="7a126-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="7a126-148">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="7a126-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7a126-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a126-149">See Also</span></span>


[<span data-ttu-id="7a126-150">Creare una route vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="7a126-151">Visualizzare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="7a126-152">Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="7a126-153">Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="7a126-154">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="7a126-155">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a126-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

