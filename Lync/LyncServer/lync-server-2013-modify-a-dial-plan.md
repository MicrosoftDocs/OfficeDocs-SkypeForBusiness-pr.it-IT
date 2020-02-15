---
title: 'Lync Server 2013: modificare un dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e20b05a85daa50003ca0062ea427473eae1bf95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="756f9-102">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="756f9-102">Modify a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="756f9-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="756f9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="756f9-104">Per modificare un dial plan esistente, eseguire i passaggi illustrati nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="756f9-104">To modify an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="756f9-105">Se si desidera creare un nuovo dial plan, vedere [creare un dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="756f9-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-modify-a-dial-plan"></a><span data-ttu-id="756f9-106">Per modificare un dial plan</span><span class="sxs-lookup"><span data-stu-id="756f9-106">To modify a dial plan</span></span>

1.  <span data-ttu-id="756f9-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="756f9-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="756f9-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="756f9-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="756f9-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="756f9-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="756f9-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="756f9-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="756f9-111">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.</span><span class="sxs-lookup"><span data-stu-id="756f9-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="756f9-112">Nella pagina **Dial plan** fare doppio clic sul nome di un dial plan.</span><span class="sxs-lookup"><span data-stu-id="756f9-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="756f9-p104">L'ambito e il nome del dial plan sono stati impostati al momento della creazione del dial plan e non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="756f9-p104">The dial plan scope and name were set when the dial plan was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="756f9-115">(Facoltativo) In **Modifica dial plan** modificare il campo **Nome semplice**, in cui viene inserito automaticamente il nome visualizzato nel campo **Nome**, specificando un nome più descrittivo che rifletta il sito, il servizio o l'utente a cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="756f9-115">(Optional) In **Edit Dial Plan**, edit the **Simple name** field, which is prepopulated with the same name that appears in the **Name** field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="756f9-116">Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="756f9-116">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server 2013 deployment.</span></span> <span data-ttu-id="756f9-117">Sono supportati i caratteri alfabetici e numerici, il trattino (-), il punto (.), il segno più (+) o il carattere di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="756f9-117">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), a plus sign (+), or an underscore (_).</span></span><BR><span data-ttu-id="756f9-118">Il campo <STRONG>Nome semplice</STRONG> non supporta gli spazi.</span><span class="sxs-lookup"><span data-stu-id="756f9-118">Spaces are not allowed in the <STRONG>Simple name</STRONG> field.</span></span>

    
    </div>

6.  <span data-ttu-id="756f9-119">(Facoltativo) Nel campo **Descrizione** digitare informazioni descrittive sul dial plan.</span><span class="sxs-lookup"><span data-stu-id="756f9-119">(Optional) In the **Description** field, type descriptive information about the dial plan.</span></span>

7.  <span data-ttu-id="756f9-p106">(Facoltativo) Se si desidera utilizzare questo dial plan come area per i numeri di accesso esterno, specificare un'**Area conferenza telefonica con accesso esterno**. Se non si desidera utilizzare questo dial plan per i numeri di accesso esterno, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="756f9-p106">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="756f9-122">Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri di accesso alla conferenza telefonica con accesso esterno a uno o più dial plan.</span><span class="sxs-lookup"><span data-stu-id="756f9-122">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

8.  <span data-ttu-id="756f9-123">(Facoltativo) Nel campo **Prefisso accesso esterno** specificare un valore solo se gli utenti devono comporre una o più cifre iniziali aggiuntive, ad esempio 9, per accedere a una linea esterna.</span><span class="sxs-lookup"><span data-stu-id="756f9-123">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits to get an external line (for example, 9).</span></span> <span data-ttu-id="756f9-124">È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri (ovvero \# \*, e 0-9).</span><span class="sxs-lookup"><span data-stu-id="756f9-124">You can type in a prefix value of up to four characters (that is, \#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="756f9-125">Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includerlo.</span><span class="sxs-lookup"><span data-stu-id="756f9-125">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

9.  <span data-ttu-id="756f9-126">Associare e configurare le regole di normalizzazione per il dial plan:</span><span class="sxs-lookup"><span data-stu-id="756f9-126">Associate and configure normalization rules for the dial plan:</span></span>
    
      - <span data-ttu-id="756f9-127">Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="756f9-127">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="756f9-128">Nella finestra di dialogo **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="756f9-128">In the **Select Normalization Rules** dialog box, highlight the rules that you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="756f9-129">Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="756f9-129">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="756f9-130">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="756f9-130">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="756f9-131">Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="756f9-131">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="756f9-132">Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="756f9-132">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="756f9-133">Per copiare una regola di normalizzazione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="756f9-133">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="756f9-134">Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="756f9-134">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="756f9-135">Per rimuovere una regola di normalizzazione dal dial plan, evidenziarne il nome e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="756f9-135">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="756f9-136">A ogni dial plan deve essere associata almeno una regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="756f9-136">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="756f9-137">Per informazioni dettagliate su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plans and normalizzation Rules in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="756f9-137">For details about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

10. <span data-ttu-id="756f9-p113">Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e fare clic sulla freccia su o giù.</span><span class="sxs-lookup"><span data-stu-id="756f9-p113">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="756f9-140">Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="756f9-140">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="756f9-141">Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano elencate prima di quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="756f9-141">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="756f9-142">L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ ({11}\d) $</STRONG> corrisponde a qualsiasi numero di 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="756f9-142">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="756f9-143">Se, ad esempio, si aggiunge una regola di normalizzazione che corrisponde a numeri a 11 cifre che iniziano con 1425, assicurarsi che la <STRONG>conservazione tutto</STRONG> sia ordinata al di sotto della regola più restrittiva <STRONG>^ (1425 \{7}d) $</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="756f9-143">If, for example, you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

11. <span data-ttu-id="756f9-p116">(Facoltativo) Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero composto da testare**.</span><span class="sxs-lookup"><span data-stu-id="756f9-p116">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="756f9-146">È possibile salvare un dial plan che non ha superato ancora il test e quindi riconfigurarlo successivamente.</span><span class="sxs-lookup"><span data-stu-id="756f9-146">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="756f9-147">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="756f9-147">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="756f9-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="756f9-148">Click **OK**.</span></span>

13. <span data-ttu-id="756f9-149">Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="756f9-149">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="756f9-150">Ogni volta che si crea o si modifica un dial plan, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="756f9-150">Any time you create or modify a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="756f9-151">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="756f9-151">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="756f9-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="756f9-152">See Also</span></span>


[<span data-ttu-id="756f9-153">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="756f9-153">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="756f9-154">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="756f9-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="756f9-155">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="756f9-155">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

