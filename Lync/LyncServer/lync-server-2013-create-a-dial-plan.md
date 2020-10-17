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
ms.openlocfilehash: f530faa83cb2e924d93abce6f7496c3ef1b82311
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516923"
---
# <a name="create-a-dial-plan-in-lync-server-2013"></a><span data-ttu-id="68fb3-102">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fb3-102">Create a dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68fb3-103">_**Ultimo argomento modificato:** 2013-10-24_</span><span class="sxs-lookup"><span data-stu-id="68fb3-103">_**Topic Last Modified:** 2013-10-24_</span></span>

<span data-ttu-id="68fb3-104">Per creare un nuovo dial plan, eseguire i passaggi illustrati nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="68fb3-104">To create a new dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="68fb3-105">Se si desidera modificare un dial plan, vedere [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-105">If you want to edit a dial plan, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-create-a-dial-plan"></a><span data-ttu-id="68fb3-106">Per creare un dial plan</span><span class="sxs-lookup"><span data-stu-id="68fb3-106">To create a dial plan</span></span>

1.  <span data-ttu-id="68fb3-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="68fb3-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="68fb3-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="68fb3-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68fb3-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="68fb3-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="68fb3-111">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Dial plan**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="68fb3-112">Nella pagina **Dial plan** fare clic su **Nuovo** e selezionare un ambito per il dial plan:</span><span class="sxs-lookup"><span data-stu-id="68fb3-112">On the **Dial Plan** page, click **New** and select a scope for the dial plan:</span></span>
    
      - <span data-ttu-id="68fb3-p104">**Dial plan sito** è applicabile a un intero sito, ad eccezione degli eventuali utenti o gruppi assegnati a un dial plan utente. Se si seleziona **Sito** come ambito di un dial plan, è necessario scegliere il sito nella finestra di dialogo **Seleziona un sito**. Se per un sito è stato già creato un dial plan, il sito non viene visualizzato nella finestra di dialogo **Seleziona un sito**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p104">**Site dial plan** applies to an entire site, except any users or groups that are assigned to a user dial plan. If you select **Site** for a dial plan’s scope, you must choose the site from the **Select a Site** dialog box. If a dial plan has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="68fb3-p105">**Dial plan pool** può essere applicabile a un gateway PSTN (Public Switched Telephone Network) o a una funzione di registrazione. Se si seleziona **Pool** come ambito di un dial plan, scegliere il gateway PSTN o la funzione di registrazione nella finestra di dialogo **Seleziona un servizio**. Se è stato già creato un dial plan per un servizio (gateway PSTN o funzione di registrazione), il servizio non viene visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p105">**Pool dial plan** can apply to a public switched telephone network (PSTN) gateway or a Registrar. If you select **Pool** for a dial plan’s scope, choose the PSTN gateway or Registrar from the **Select a Service** dialog box. If a dial plan has already been created for a service (PSTN gateway or Registrar), the service does not appear in the list.</span></span>
    
      - <span data-ttu-id="68fb3-119">**Dial plan utente** può essere applicato a utenti o gruppi specificati.</span><span class="sxs-lookup"><span data-stu-id="68fb3-119">**User dial plan** can be applied to specified users or groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-120">Dopo aver selezionato l'ambito del dial plan, non è più possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="68fb3-120">After you select the dial plan scope, it cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="68fb3-p106">Se si crea un dial plan utente, immettere un nome descrittivo nel campo **Nome** della finestra di dialogo **Nuovo dial plan**. Dopo aver salvato tale nome, non è più possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p106">If you are creating a user dial plan, enter a descriptive name in the **Name** field on the **New Dial Plan** dialog box. After this name is saved, it cannot be changed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-123">Per i dial plan sito, il campo <STRONG>Nome</STRONG> viene prepopolato con il nome del sito e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="68fb3-123">For site dial plans, the <STRONG>Name</STRONG> field is prepopulated with the site name and cannot be changed.</span></span><BR><span data-ttu-id="68fb3-124">Per i dial plan pool, il campo <STRONG>Nome</STRONG> viene prepopolato con il nome del gateway PSTN o della funzione di registrazione e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="68fb3-124">For pool dial plans, the <STRONG>Name</STRONG> field is prepopulated with the PSTN gateway or Registrar name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="68fb3-p107">Il campo **Nome semplice** viene prepopolato con lo stesso nome visualizzato nel campo **Nome**. Se si desidera, è possibile modificare il campo per specificare un nome più descrittivo che rifletta il sito, il servizio o l'utente al quale viene applicato il dial plan.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p107">The **Simple name** field is prepopulated with the same name that appears in the **Name** field. You can optionally edit this field to specify a more descriptive name that reflects the site, service, or user to which the dial plan applies.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="68fb3-127">Il <STRONG>nome semplice</STRONG> deve essere univoco tra tutti i dial plan all'interno della distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68fb3-127">The <STRONG>Simple name</STRONG> must be unique among all dial plans within the Lync Server deployment.</span></span> <span data-ttu-id="68fb3-128">Non può superare 256 caratteri Unicode, ognuno dei quali può essere di tipo alfabetico o numerico, un segno meno (-), un punto (.) o un carattere di sottolineatura (_).</span><span class="sxs-lookup"><span data-stu-id="68fb3-128">It cannot exceed 256 Unicode characters, each of which can be an alphabetic or numeric character, a hyphen (-), a period (.), or an underscore (_).</span></span><BR><span data-ttu-id="68fb3-129">I caratteri <STRONG>non supportati</STRONG> includono spazi e caratteri riservati, come definito in RFC 3966 ( http://www.ietf.org/rfc/rfc3966.txt) .</span><span class="sxs-lookup"><span data-stu-id="68fb3-129">Characters <STRONG>not supported</STRONG> include spaces and Reserved characters as defined in RFC 3966 (http://www.ietf.org/rfc/rfc3966.txt).</span></span> <span data-ttu-id="68fb3-130">I caratteri riservati che <STRONG>non sono supportati</STRONG> nel <STRONG>nome semplice</STRONG> sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="68fb3-130">Reserved characters that are <STRONG>not supported</STRONG> in the <STRONG>Simple Name</STRONG> include the following:</span></span><BR><span data-ttu-id="68fb3-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span><span class="sxs-lookup"><span data-stu-id="68fb3-131">";" "/" "?" ":" "@" "&amp;" "=" "+" "$" ","</span></span>

    
    </div>

7.  <span data-ttu-id="68fb3-132">(Facoltativo) Nel campo **Descrizione** è possibile digitare ulteriori informazioni descrittive sul dial plan.</span><span class="sxs-lookup"><span data-stu-id="68fb3-132">(Optional) In the **Description** field, you can type additional descriptive information about the dial plan.</span></span>

8.  <span data-ttu-id="68fb3-p110">(Facoltativo) Se si desidera utilizzare questo dial plan come area per i numeri di accesso esterno, specificare un'**Area conferenza telefonica con accesso esterno**. Se non si desidera utilizzare questo dial plan per i numeri di accesso esterno, lasciare vuoto il campo.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p110">(Optional) If you want to use this dial plan as a region for dial-in access numbers, specify a **Dial-in conferencing region**. If you do not want to use this dial plan for dial-in access numbers, leave this field empty.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-135">Le aree di conferenza telefonica con accesso esterno sono necessarie per associare i numeri di accesso alla conferenza telefonica con accesso esterno a uno o più dial plan.</span><span class="sxs-lookup"><span data-stu-id="68fb3-135">Dial-in conferencing regions are required to associate dial-in conferencing access numbers with one or more dial plans.</span></span>

    
    </div>

9.  <span data-ttu-id="68fb3-136">(Facoltativo) Nel campo **Prefisso accesso esterno** specificare un valore solo se gli utenti devono comporre una o più cifre iniziali aggiuntive, ad esempio 9, per accedere a una linea esterna.</span><span class="sxs-lookup"><span data-stu-id="68fb3-136">(Optional) In the **External access prefix** field, specify a value only if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="68fb3-137">È possibile digitare un valore di prefisso composto da un massimo di quattro caratteri ( \# \* e 0-9).</span><span class="sxs-lookup"><span data-stu-id="68fb3-137">You can type in a prefix value of up to four characters (\#, \*, and 0-9).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-138">Se si specifica un prefisso di accesso esterno, non è necessario creare una nuova regola di normalizzazione per includerlo.</span><span class="sxs-lookup"><span data-stu-id="68fb3-138">If you specify an external access prefix, you do not need to create a new normalization rule to accommodate the prefix.</span></span>

    
    </div>

10. <span data-ttu-id="68fb3-139">Associare e configurare le regole di normalizzazione per il dial plan nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="68fb3-139">Associate and configure normalization rules for the dial plan as follows:</span></span>
    
      - <span data-ttu-id="68fb3-140">Per scegliere una o più regole da un elenco di tutte le regole di normalizzazione disponibili nella distribuzione VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-140">To choose one or more rules from a list of all normalization rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="68fb3-141">In **Seleziona regole di normalizzazione** evidenziare le regole da associare al dial plan e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-141">In **Select Normalization Rules**, highlight the rules you want to associate with the dial plan and then click **OK**.</span></span>
    
      - <span data-ttu-id="68fb3-142">Per definire una nuova regola di normalizzazione e associarla al dial plan, fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-142">To define a new normalization rule and associate it with the dial plan, click **New**.</span></span> <span data-ttu-id="68fb3-143">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-143">For details about defining a new rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="68fb3-144">Per modificare una regola di normalizzazione già associata al dial plan, evidenziare il nome della regola e fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-144">To edit a normalization rule that is already associated with the dial plan, highlight the rule name and click **Show details**.</span></span> <span data-ttu-id="68fb3-145">Per informazioni dettagliate sulla modifica della regola, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-145">For details about editing the rule, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="68fb3-146">Per copiare una regola di normalizzazione esistente da utilizzare come punto di partenza per la definizione di una nuova regola, evidenziare il nome della regola e fare clic su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-146">To copy an existing normalization rule to use as a starting point for defining a new rule, highlight the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="68fb3-147">Per informazioni dettagliate sulla modifica della copia, vedere [definizione di regole di normalizzazione in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-147">For details about editing the copy, see [Defining normalization rules in Lync Server 2013](lync-server-2013-defining-normalization-rules.md).</span></span>
    
      - <span data-ttu-id="68fb3-148">Per rimuovere una regola di normalizzazione dal dial plan, evidenziarne il nome e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-148">To remove a normalization rule from the dial plan, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-149">A ogni dial plan deve essere associata almeno una regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="68fb3-149">Each dial plan must have at least one associated normalization rule.</span></span> <span data-ttu-id="68fb3-150">Per informazioni su come determinare tutte le regole di normalizzazione richieste da un dial plan, vedere <A href="lync-server-2013-dial-plans-and-normalization-rules.md">dial plans and normalizzation Rules in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="68fb3-150">For information about how to determine all of the normalization rules a dial plan requires, see <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Dial plans and normalization rules in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

11. <span data-ttu-id="68fb3-p117">Verificare che le regole di normalizzazione del dial plan siano disposte nell'ordine corretto. Per modificare la posizione di una regola nell'elenco, evidenziare il nome della regola e fare clic sulla freccia su o giù.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p117">Verify that the dial plan’s normalization rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="68fb3-153">Lync Server attraversa l'elenco delle regole di normalizzazione dall'alto verso il basso e utilizza la prima regola che corrisponde al numero composto.</span><span class="sxs-lookup"><span data-stu-id="68fb3-153">Lync Server traverses the normalization rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="68fb3-154">Se si configura un dial plan in modo che un numero composto possa corrispondere a più regole di normalizzazione, assicurarsi che le regole più restrittive siano elencate prima di quelle meno restrittive.</span><span class="sxs-lookup"><span data-stu-id="68fb3-154">If you configure a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span><BR><span data-ttu-id="68fb3-155">L'impostazione predefinita <STRONG>Mantieni tutte</STRONG> le regole di normalizzazione <STRONG>^ (\d {11} ) $</STRONG> corrisponde a qualsiasi numero di 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="68fb3-155">The default <STRONG>Keep All</STRONG> normalization rule <STRONG>^(\d{11})$</STRONG> matches any 11-digit number.</span></span> <span data-ttu-id="68fb3-156">Ad esempio, se si aggiunge una regola di normalizzazione che corrisponde a numeri a 11 cifre che iniziano con 1425, assicurarsi che la <STRONG>conservazione tutto</STRONG> sia ordinata al di sotto della regola più restrittiva <STRONG>^ (1425 \ d {7} ) $</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="68fb3-156">For example, if you add a normalization rule that matches 11-digit numbers that start with 1425, make sure that <STRONG>Keep All</STRONG> is sorted below the more restrictive <STRONG>^(1425\d{7})$</STRONG> rule.</span></span>

    
    </div>

12. <span data-ttu-id="68fb3-p120">(Facoltativo) Immettere un numero per testare il dial plan e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Numero composto da testare**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-p120">(Optional) Enter a number to test the dial plan and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-159">È possibile salvare un dial plan che non ha superato ancora il test e quindi riconfigurarlo successivamente.</span><span class="sxs-lookup"><span data-stu-id="68fb3-159">You can save a dial plan that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="68fb3-160">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="68fb3-160">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="68fb3-161">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-161">Click **OK**.</span></span>

14. <span data-ttu-id="68fb3-162">Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-162">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68fb3-163">Ogni volta che si crea un dial plan, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="68fb3-163">Any time you create a dial plan, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="68fb3-164">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="68fb3-164">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68fb3-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68fb3-165">See Also</span></span>


[<span data-ttu-id="68fb3-166">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fb3-166">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="68fb3-167">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fb3-167">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="68fb3-168">Definizione di regole di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68fb3-168">Defining normalization rules in Lync Server 2013</span></span>](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

