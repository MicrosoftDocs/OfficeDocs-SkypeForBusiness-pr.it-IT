---
title: Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138fe6b55f82b451fee12d4159e147f73160c741
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="f7794-102">Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7794-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7794-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f7794-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f7794-104">Se si desidera creare o modificare una regola di normalizzazione nel pannello di controllo di Lync Server, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="f7794-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="f7794-105">In alternativa, se si desidera creare o modificare manualmente una regola di normalizzazione, vedere [creare o modificare manualmente una regola di normalizzazione in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="f7794-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="f7794-106">Per definire una regola mediante Crea regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="f7794-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="f7794-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f7794-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f7794-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f7794-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f7794-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f7794-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f7794-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f7794-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f7794-111">Optional Seguire la procedura illustrata in [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) tramite il passaggio 11 o [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) tramite il passaggio 10.</span><span class="sxs-lookup"><span data-stu-id="f7794-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="f7794-112">In **Nuova regola di normalizzazione** o **Modifica regola di normalizzazione** digitare un nome descrittivo del formato del numero da normalizzare in **Nome**, ad esempio **Prefisso5Cifre**.</span><span class="sxs-lookup"><span data-stu-id="f7794-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="f7794-113">(Facoltativo) In **Descrizione** digitare una descrizione della regola di normalizzazione, ad esempio "Converte prefissi a 5 cifre".</span><span class="sxs-lookup"><span data-stu-id="f7794-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="f7794-114">In **Crea regola di normalizzazione** immettere valori nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f7794-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="f7794-115">**Cifre iniziali (**   facoltativo) specificare le cifre iniziali dei numeri composti che si desidera che il modello corrisponda.</span><span class="sxs-lookup"><span data-stu-id="f7794-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="f7794-116">Digitare ad esempio **425** se si desidera che il formato corrisponda ai numeri composti che iniziano con 425.</span><span class="sxs-lookup"><span data-stu-id="f7794-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="f7794-117">**Lunghezza**   specificare il numero di cifre nel criterio di corrispondenza e selezionare se si desidera che il motivo corrisponda esattamente a questa lunghezza, corrispondere ai numeri composti almeno per questa lunghezza o corrispondere a numeri composti di qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="f7794-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="f7794-118">**Cifre da rimuovere**   (facoltativa) specificare il numero di cifre iniziali che devono essere rimosse dai numeri composti che si desidera che il modello corrisponda.</span><span class="sxs-lookup"><span data-stu-id="f7794-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="f7794-119">**Cifre da aggiungere**   (facoltativa) specificare le cifre che devono essere aggiunte ai numeri composti che si desidera corrispondano al modello.</span><span class="sxs-lookup"><span data-stu-id="f7794-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="f7794-p105">I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se ad esempio il campo **Cifre iniziali** viene lasciato vuoto, si digita **7** nel campo **Lunghezza** e si seleziona **Esattamente**, quindi si specifica **0** in **Cifre da rimuovere**, l'espressione regolare risultante nel campo **Formato per corrispondenza** sarà:</span><span class="sxs-lookup"><span data-stu-id="f7794-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="f7794-122">**^ (\\d{7}) $**</span><span class="sxs-lookup"><span data-stu-id="f7794-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="f7794-123">In **Regola di conversione** specificare un modello per il formato dei numeri di telefono E.164 convertiti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f7794-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="f7794-124">Un valore che rappresenta il numero di cifri specificato nel formato della corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="f7794-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="f7794-125">Ad esempio, se il motivo corrispondente è **^ (\\d{7}) $** quindi **$1** nella regola di conversione rappresenta numeri composti a 7 cifre.</span><span class="sxs-lookup"><span data-stu-id="f7794-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="f7794-126">(Facoltativo) Digitare un valore nel campo **Prefisso** per specificare le cifre da anteporre al numero convertito (ad esempio **+1425**).</span><span class="sxs-lookup"><span data-stu-id="f7794-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="f7794-127">Ad esempio, se **pattern to match** contiene **^ (\\d{7}) $** come modello per i numeri composti e la **regola di conversione** contiene **+ 1425 $1** come modello per i numeri di telefono e. 164, la regola Normalizza 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="f7794-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="f7794-128">(Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.</span><span class="sxs-lookup"><span data-stu-id="f7794-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="f7794-p107">(Facoltativo) Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**. I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.</span><span class="sxs-lookup"><span data-stu-id="f7794-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f7794-131">È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente.</span><span class="sxs-lookup"><span data-stu-id="f7794-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="f7794-132">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f7794-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="f7794-133">Fare clic su **OK** per salvare la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="f7794-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="f7794-134">Fare clic su **OK** per salvare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="f7794-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="f7794-135">Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="f7794-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="f7794-136">Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="f7794-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f7794-137">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="f7794-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7794-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7794-138">See Also</span></span>


[<span data-ttu-id="f7794-139">Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7794-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="f7794-140">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7794-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="f7794-141">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7794-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="f7794-142">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7794-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="f7794-143">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7794-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

