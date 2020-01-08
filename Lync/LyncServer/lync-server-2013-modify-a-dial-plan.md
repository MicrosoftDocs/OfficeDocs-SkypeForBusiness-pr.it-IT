---
title: 'Lync Server 2013: Modificare un dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd6cc46d6e3317ca678b20e86c546db7dcc94fcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="3c77c-102">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c77c-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c77c-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3c77c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3c77c-104">Per modificare un piano di chiamata esistente, eseguire i passaggi descritti nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="3c77c-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="3c77c-105">Se si vuole creare un nuovo piano di chiamata, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="3c77c-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="3c77c-106">Per modificare un dial plan</span><span class="sxs-lookup"><span data-stu-id="3c77c-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="3c77c-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3c77c-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3c77c-108">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3c77c-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3c77c-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3c77c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3c77c-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3c77c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3c77c-111">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **dial plan**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="3c77c-112">Nella pagina **dial plan** fare doppio clic su un nome di dial plan.</span><span class="sxs-lookup"><span data-stu-id="3c77c-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c77c-113">L'ambito e il nome del dial plan sono stati impostati quando è stato creato il dial plan.</span><span class="sxs-lookup"><span data-stu-id="3c77c-113">The dial plan scope and name were set when the dial plan was created.</span></span> <span data-ttu-id="3c77c-114">Non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="3c77c-114">They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="3c77c-115">Opzionale In **Modifica dial plan**modificare il campo **nome semplice** , che viene prepopolato con lo stesso nome visualizzato nel campo **nome** per specificare un nome più descrittivo che rispecchi il sito, il servizio o l'utente a cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="3c77c-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3c77c-116">Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c77c-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="3c77c-117">Non può superare i caratteri Unicode di 256, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.), un segno di addizione (+) o una sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="3c77c-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="3c77c-118">Gli spazi non sono consentiti nel campo <STRONG>nome semplice</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3c77c-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="3c77c-119">Opzionale Nel campo **Descrizione** digitare informazioni descrittive sul dial plan.</span><span class="sxs-lookup"><span data-stu-id="3c77c-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="3c77c-120">Opzionale Se si vuole usare questo dial plan come area geografica per i numeri di accesso esterno, specificare un' **area di conferenza telefonica con chiamata in**ingresso.</span><span class="sxs-lookup"><span data-stu-id="3c77c-120">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="3c77c-121">Se non si vuole usare questo dial plan per i numeri di accesso esterno, lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="3c77c-121">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c77c-122">Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c77c-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="3c77c-123">Opzionale Nel campo **prefisso di accesso esterno** specificare un valore solo se gli utenti devono chiamare una o più cifre iniziali aggiuntive per ottenere una linea esterna, ad esempio 9.</span><span class="sxs-lookup"><span data-stu-id="3c77c-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="3c77c-124">È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri, \# \*ovvero, e 0-9.</span><span class="sxs-lookup"><span data-stu-id="3c77c-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c77c-125">Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includere il prefisso.</span><span class="sxs-lookup"><span data-stu-id="3c77c-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="3c77c-126">Associare e configurare le regole di normalizzazione per il dial plan:</span><span class="sxs-lookup"><span data-stu-id="3c77c-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="3c77c-127">Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3c77c-128">Nella finestra di dialogo **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="3c77c-129">Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="3c77c-130">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="3c77c-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="3c77c-131">Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="3c77c-132">Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="3c77c-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="3c77c-133">Per copiare una regola di normalizzazione esistente da usare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **copia**e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="3c77c-134">Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="3c77c-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="3c77c-135">Per rimuovere una regola di normalizzazione dal dial plan, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c77c-136">Ogni dial plan deve avere almeno una regola di normalizzazione associata.</span><span class="sxs-lookup"><span data-stu-id="3c77c-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="3c77c-137">Per informazioni dettagliate su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3c77c-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="3c77c-138">Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="3c77c-138">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="3c77c-139">Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="3c77c-139">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3c77c-140">Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="3c77c-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="3c77c-141">Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="3c77c-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="3c77c-142">L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ ({11}\d) $</STRONG> corrisponde a qualsiasi numero di 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="3c77c-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="3c77c-143">Se, ad esempio, si aggiunge una regola di normalizzazione che corrisponde a numeri di 11 cifre che iniziano con 1425, assicurarsi che <STRONG>Keep all</STRONG> sia ordinato sotto la regola più restrittiva <STRONG>^ (1425{7}\ d) $</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3c77c-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="3c77c-144">Opzionale Immettere un numero per testare il dial plan e quindi fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-144">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="3c77c-145">I risultati del test vengono visualizzati in **immettere un numero da testare**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-145">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c77c-146">È possibile salvare un dial plan che non supera ancora il test e quindi riconfigurarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="3c77c-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="3c77c-147">Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3c77c-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="3c77c-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-148">Click **OK**.</span></span>

13. <span data-ttu-id="3c77c-149">Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="3c77c-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3c77c-150">Ogni volta che si crea o si modifica un dial plan, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="3c77c-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3c77c-151">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="3c77c-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c77c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c77c-152">See Also</span></span>


[<span data-ttu-id="3c77c-153">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c77c-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="3c77c-154">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c77c-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="3c77c-155">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c77c-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

