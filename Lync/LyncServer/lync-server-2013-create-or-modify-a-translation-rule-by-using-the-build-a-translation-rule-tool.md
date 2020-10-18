---
title: Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione
description: Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116048fff834e797bca76a895f45cd0ebc83ab94
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574522"
---
# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="6fed9-103">Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fed9-103">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fed9-104">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6fed9-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6fed9-105">Se si desidera definire una regola di conversione, eseguire la procedura seguente per specificare un insieme di valori nello strumento **Crea regola di conversione** e per abilitare il pannello di controllo di Lync Server per generare la regola di conversione e il motivo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6fed9-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="6fed9-106">In alternativa, è possibile scrivere manualmente un'espressione regolare per definire il formato e la regola di conversione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6fed9-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="6fed9-107">Per ulteriori informazioni, vedere [creare o modificare manualmente una regola di conversione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="6fed9-107">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="6fed9-108">Per definire una regola tramite lo strumento Crea regola di conversione</span><span class="sxs-lookup"><span data-stu-id="6fed9-108">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="6fed9-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6fed9-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6fed9-110">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6fed9-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6fed9-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fed9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fed9-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6fed9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fed9-113">Per iniziare a definire una regola di conversione, eseguire la procedura descritta in [Configure a Trunk with media bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through Step 10 oppure [Configure a Trunk Without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through Step 9.</span><span class="sxs-lookup"><span data-stu-id="6fed9-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="6fed9-114">In **Nome** nella pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome descrittivo del formato del numero da convertire.</span><span class="sxs-lookup"><span data-stu-id="6fed9-114">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="6fed9-115">(Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio **Chiamate interurbane internazionali**.</span><span class="sxs-lookup"><span data-stu-id="6fed9-115">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="6fed9-116">Nella sezione **Crea regola di conversione** della finestra di dialogo immettere i valore nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fed9-116">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="6fed9-117">**Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si desidera corrisponda il formato.</span><span class="sxs-lookup"><span data-stu-id="6fed9-117">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="6fed9-118">Ad esempio, immettere **+** in questo campo per associare i numeri nel formato E. 164 (che iniziano con +).</span><span class="sxs-lookup"><span data-stu-id="6fed9-118">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="6fed9-p105">**Lunghezza**: specificare il numero di cifre nel formato e specificare se si desidera applicare il formato ai numeri esattamente di questa lunghezza, almeno di questa lunghezza o di qualsiasi lunghezza. Ad esempio, immettere **11** e selezionare **Almeno** nell'elenco a discesa per specificare una corrispondenza con i numeri con una lunghezza di almeno 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="6fed9-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="6fed9-121">**Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="6fed9-121">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="6fed9-122">Ad esempio, immettere **1** per eliminare il **+** valore dall'inizio del numero.</span><span class="sxs-lookup"><span data-stu-id="6fed9-122">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="6fed9-p107">**Prefisso**: (facoltativo) specificare le cifre da aggiungere all'inizio dei numeri convertiti. Ad esempio, immettere **011** se si desidera aggiungere 011 all'inizio dei numeri convertiti quando si applica questa regola.</span><span class="sxs-lookup"><span data-stu-id="6fed9-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="6fed9-p108">I valori immessi in questi campi vengono riportati nei campi **Formato per corrispondenza** e **Regola di conversione**. Se si specificano i valori di esempio precedenti, ad esempio, l'espressione regolare risultante nel campo **Formato per corrispondenza** sarà:</span><span class="sxs-lookup"><span data-stu-id="6fed9-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="6fed9-127">**^\\+ ( \\ d {9} \\ d +) $**</span><span class="sxs-lookup"><span data-stu-id="6fed9-127">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="6fed9-p109">Nel campo **Regola di conversione** specificare un modello per il formato dei numeri convertiti. Il modello è composto da due parti:</span><span class="sxs-lookup"><span data-stu-id="6fed9-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="6fed9-130">Un valore (ad esempio **$1**) che rappresenta il numero di cifre nel formato corrispondente</span><span class="sxs-lookup"><span data-stu-id="6fed9-130">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="6fed9-131">(Facoltativo) Un valore che è possibile aggiungere all'inizio del numero immettendolo nel campo **Prefisso**</span><span class="sxs-lookup"><span data-stu-id="6fed9-131">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="6fed9-132">In base ai valori di esempio precedenti, nel campo **Regola di conversione** viene visualizzato **011$1**.</span><span class="sxs-lookup"><span data-stu-id="6fed9-132">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="6fed9-133">Con l'applicazione di questa regola di conversione il numero +441235551010 diventa 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="6fed9-133">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="6fed9-134">Fare clic su **OK** per salvare la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="6fed9-134">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="6fed9-135">Fare clic su **OK** per salvare la configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="6fed9-135">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="6fed9-136">Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="6fed9-136">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6fed9-137">Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="6fed9-137">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="6fed9-138">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="6fed9-138">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fed9-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fed9-139">See Also</span></span>


[<span data-ttu-id="6fed9-140">Creare o modificare manualmente una regola di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fed9-140">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="6fed9-141">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fed9-141">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="6fed9-142">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fed9-142">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="6fed9-143">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fed9-143">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="6fed9-144">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fed9-144">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

