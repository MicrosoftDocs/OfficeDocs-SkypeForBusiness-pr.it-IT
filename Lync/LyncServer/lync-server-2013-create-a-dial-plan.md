---
title: 'Lync Server 2013: creare un dial plan'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="24619-102">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24619-102">Create a dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24619-103">_**Argomento Ultima modifica:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="24619-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="24619-104">Per creare un nuovo piano di chiamata, eseguire i passaggi descritti nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="24619-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="24619-105">Se si vuole modificare un dial plan, vedere [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="24619-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="24619-106">Per creare un dial plan</span><span class="sxs-lookup"><span data-stu-id="24619-106">To create a dial plan</span></span>

1.  <span data-ttu-id="24619-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="24619-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="24619-108">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="24619-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="24619-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24619-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24619-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24619-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24619-111">Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **dial plan**.</span><span class="sxs-lookup"><span data-stu-id="24619-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="24619-112">Nella pagina **dial plan** fare clic su **nuovo** e selezionare un ambito per il dial plan:</span><span class="sxs-lookup"><span data-stu-id="24619-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="24619-113">Il **dial plan di sito** si applica a un intero sito, eccetto gli utenti o i gruppi assegnati a un dial plan utente.</span><span class="sxs-lookup"><span data-stu-id="24619-113">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan.</span></span> <span data-ttu-id="24619-114">Se si seleziona **sito** per l'ambito di un dial plan, è necessario scegliere il sito nella finestra di dialogo **Seleziona sito** .</span><span class="sxs-lookup"><span data-stu-id="24619-114">If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="24619-115">Se è già stato creato un dial plan per un sito, il sito non viene visualizzato nella finestra di dialogo **Seleziona sito** .</span><span class="sxs-lookup"><span data-stu-id="24619-115">If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="24619-116">Il **dial plan per pool** può essere applicato a un gateway PSTN (Public Switched Telephone Network) o a un registrar.</span><span class="sxs-lookup"><span data-stu-id="24619-116">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar.</span></span> <span data-ttu-id="24619-117">Se si seleziona **pool** per l'ambito di un dial plan, scegliere il gateway PSTN o il registrar nella finestra di dialogo **Seleziona servizio** .</span><span class="sxs-lookup"><span data-stu-id="24619-117">If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box.</span></span> <span data-ttu-id="24619-118">Se è già stato creato un dial plan per un servizio (gateway PSTN o registrar), il servizio non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="24619-118">If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="24619-119">Il **dial plan utente** può essere applicato agli utenti o ai gruppi specificati.</span><span class="sxs-lookup"><span data-stu-id="24619-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-120">Dopo aver selezionato l'ambito del dial plan, non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="24619-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="24619-121">Se si sta creando un piano di chiamata utente, immettere un nome descrittivo nel campo **nome** della finestra di dialogo **nuovo piano di chiamata** .</span><span class="sxs-lookup"><span data-stu-id="24619-121">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box.</span></span> <span data-ttu-id="24619-122">Dopo aver salvato questo nome, non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="24619-122">After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-123">Per i piani di chiamata del sito, il campo <STRONG>nome</STRONG> viene precompilato con il nome del sito e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="24619-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="24619-124">Per i piani di chiamata in pool, il campo <STRONG>nome</STRONG> viene prepopolato con il gateway PSTN o il nome del registrar e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="24619-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="24619-125">Il campo **nome semplice** viene prepopolato con lo stesso nome visualizzato nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="24619-125">The **Simple name** field is prepopulated with the same name that appears in the **Name** field.</span></span> <span data-ttu-id="24619-126">Facoltativamente, è possibile modificare questo campo per specificare un nome più descrittivo che rispecchi il sito, il servizio o l'utente a cui si applica il dial plan.</span><span class="sxs-lookup"><span data-stu-id="24619-126">You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24619-127">Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24619-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="24619-128">Non può superare i caratteri Unicode di 256, ognuno dei quali può essere un carattere alfabetico o numerico, un trattino (-), un punto (.) o uno stato di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="24619-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="24619-129">I caratteri <STRONG>non supportati</STRONG> includono spazi e caratteri riservati come definito in RFC 3966http://www.ietf.org/rfc/rfc3966.txt)(.</span><span class="sxs-lookup"><span data-stu-id="24619-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="24619-130">I caratteri riservati <STRONG>non supportati</STRONG> nel <STRONG>nome semplice</STRONG> includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="24619-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="24619-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="24619-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="24619-132">Opzionale Nel campo **Descrizione** è possibile digitare ulteriori informazioni descrittive sul dial plan.</span><span class="sxs-lookup"><span data-stu-id="24619-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="24619-133">Opzionale Se si vuole usare questo dial plan come area geografica per i numeri di accesso esterno, specificare un' **area di conferenza telefonica con chiamata in**ingresso.</span><span class="sxs-lookup"><span data-stu-id="24619-133">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**.</span></span> <span data-ttu-id="24619-134">Se non si vuole usare questo dial plan per i numeri di accesso esterno, lascia vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="24619-134">If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-135">Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri per i servizi di conferenza telefonica con chiamata in ingresso con uno o più piani di chiamata.</span><span class="sxs-lookup"><span data-stu-id="24619-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="24619-136">Opzionale Nel campo **prefisso di accesso esterno** specificare un valore solo se gli utenti devono chiamare una o più cifre iniziali aggiuntive (ad esempio, 9) per ottenere una linea esterna.</span><span class="sxs-lookup"><span data-stu-id="24619-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="24619-137">Puoi digitare un valore di prefisso composto da un massimo di quattro caratteri\#( \*, e 0-9).</span><span class="sxs-lookup"><span data-stu-id="24619-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-138">Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includere il prefisso.</span><span class="sxs-lookup"><span data-stu-id="24619-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="24619-139">Associare e configurare le regole di normalizzazione per il dial plan nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="24619-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="24619-140">Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione vocale aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="24619-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="24619-141">In **Seleziona regole di normalizzazione**evidenziare le regole da associare al dial plan e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="24619-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="24619-142">Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="24619-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="24619-143">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="24619-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="24619-144">Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="24619-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="24619-145">Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="24619-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="24619-146">Per copiare una regola di normalizzazione esistente da usare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **copia**e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="24619-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="24619-147">Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="24619-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="24619-148">Per rimuovere una regola di normalizzazione dal dial plan, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="24619-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-149">Ogni dial plan deve avere almeno una regola di normalizzazione associata.</span><span class="sxs-lookup"><span data-stu-id="24619-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="24619-150">Per informazioni su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plan e regole di normalizzazione in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="24619-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="24619-151">Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="24619-151">Verify that the dial plan’s normalization rules are arranged in the correct order.</span></span> <span data-ttu-id="24619-152">Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e quindi fare clic sulla freccia in su o in giù.</span><span class="sxs-lookup"><span data-stu-id="24619-152">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="24619-153">Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e usa la prima regola che corrisponde al numero selezionato.</span><span class="sxs-lookup"><span data-stu-id="24619-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="24619-154">Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, verificare che le regole più restrittive siano ordinate sopra quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="24619-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="24619-155">L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ ({11}\d) $</STRONG> corrisponde a qualsiasi numero di 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="24619-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="24619-156">Ad esempio, se si aggiunge una regola di normalizzazione che corrisponde a numeri di 11 cifre che iniziano con 1425, assicurarsi che <STRONG>Keep all</STRONG> sia ordinato sotto la regola più restrittiva <STRONG>^ (1425{7}\ d) $</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="24619-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="24619-157">Opzionale Immettere un numero per testare il dial plan e quindi fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="24619-157">(Optional) Enter a number to test the dial plan and then click **Go**.</span></span> <span data-ttu-id="24619-158">I risultati del test vengono visualizzati in **immettere un numero da testare**.</span><span class="sxs-lookup"><span data-stu-id="24619-158">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-159">È possibile salvare un dial plan che non supera ancora il test e quindi riconfigurarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="24619-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="24619-160">Per informazioni dettagliate, vedere <A href="lync-server-2013-test-voice-routing.md">eseguire il test del routing vocale in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="24619-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="24619-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="24619-161">Click **OK**.</span></span>

14. <span data-ttu-id="24619-162">Nella pagina **dial plan** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="24619-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24619-163">Ogni volta che si crea un dial plan, è necessario eseguire il comando <STRONG>Commit all</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="24619-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="24619-164">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="24619-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24619-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24619-165">See Also</span></span>


[<span data-ttu-id="24619-166">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24619-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="24619-167">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24619-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="24619-168">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24619-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

