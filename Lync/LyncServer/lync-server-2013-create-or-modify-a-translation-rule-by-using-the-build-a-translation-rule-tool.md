---
title: Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f498af25dfd851bd2950ce08d5c66179b95ebc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="6c328-102">Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c328-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c328-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6c328-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6c328-104">Seguire questa procedura se si vuole definire una regola di traduzione immettendo un set di valori nello strumento **Compila una regola di traduzione** e abilitando il pannello di controllo di Lync Server per generare il modello di corrispondenza corrispondente e la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="6c328-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="6c328-105">In alternativa, è possibile eseguire manualmente un'espressione regolare di scrittura per definire il modello e la regola di traduzione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6c328-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="6c328-106">Per informazioni dettagliate, vedere [creare o modificare manualmente una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="6c328-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="6c328-107">Per definire una regola usando lo strumento crea una regola di traduzione</span><span class="sxs-lookup"><span data-stu-id="6c328-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="6c328-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6c328-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6c328-109">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6c328-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="6c328-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6c328-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6c328-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6c328-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6c328-112">Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) tramite il passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="6c328-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="6c328-113">In **nome** nella pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.</span><span class="sxs-lookup"><span data-stu-id="6c328-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="6c328-114">Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le **chiamate interurbane internazionali degli Stati Uniti**.</span><span class="sxs-lookup"><span data-stu-id="6c328-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="6c328-115">Nella sezione **genera una regola di traduzione** della finestra di dialogo immettere i valori nei campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c328-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="6c328-116">**Cifre iniziali**: (facoltativo) specificare le cifre iniziali dei numeri a cui si vuole che corrisponda il motivo.</span><span class="sxs-lookup"><span data-stu-id="6c328-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="6c328-117">Ad esempio, immetti **+** in questo campo i numeri in formato E. 164 (che iniziano con +).</span><span class="sxs-lookup"><span data-stu-id="6c328-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="6c328-118">**Length**: specificare il numero di cifre nel criterio di corrispondenza e selezionare se si vuole che il pattern corrisponda a numeri di lunghezza uguale a quella specificata, almeno questa lunghezza o qualsiasi lunghezza.</span><span class="sxs-lookup"><span data-stu-id="6c328-118">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="6c328-119">Ad esempio, immetti **11** e **Seleziona almeno nell'elenco a discesa** per abbinare i numeri di almeno 11 cifre in lunghezza.</span><span class="sxs-lookup"><span data-stu-id="6c328-119">For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="6c328-120">**Cifre da rimuovere**: (facoltativo) specificare il numero di cifre iniziali da eliminare.</span><span class="sxs-lookup"><span data-stu-id="6c328-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="6c328-121">Ad esempio, immettere **1** per eliminare l' **+** inizio del numero.</span><span class="sxs-lookup"><span data-stu-id="6c328-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="6c328-122">**Cifre da aggiungere**: (facoltativo) specificare le cifre da anteporre ai numeri tradotti.</span><span class="sxs-lookup"><span data-stu-id="6c328-122">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="6c328-123">Ad esempio, immetti **011** se vuoi che 011 venga anteposto ai numeri tradotti quando viene applicata la regola.</span><span class="sxs-lookup"><span data-stu-id="6c328-123">For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="6c328-124">I valori immessi in questi campi si riflettono nei campi della regola **per la corrispondenza** e la **traduzione** .</span><span class="sxs-lookup"><span data-stu-id="6c328-124">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="6c328-125">Ad esempio, se specifichi i valori di esempio precedenti, l'espressione regolare risultante nel campo **pattern to match** è:</span><span class="sxs-lookup"><span data-stu-id="6c328-125">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="6c328-126">**^\\+ (\\d{9}\\d +) $**</span><span class="sxs-lookup"><span data-stu-id="6c328-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="6c328-127">Il campo della **regola di traduzione** specifica un modello per il formato dei numeri tradotti.</span><span class="sxs-lookup"><span data-stu-id="6c328-127">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="6c328-128">Questo modello include due parti:</span><span class="sxs-lookup"><span data-stu-id="6c328-128">This pattern has two parts:</span></span>
    
      - <span data-ttu-id="6c328-129">Un valore, ad esempio **$1**, che rappresenta il numero di cifre nel modello corrispondente</span><span class="sxs-lookup"><span data-stu-id="6c328-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="6c328-130">Opzionale Un valore che puoi anteporre immettendolo nel campo **cifre da aggiungere**</span><span class="sxs-lookup"><span data-stu-id="6c328-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="6c328-131">Usando i valori di esempio precedenti, viene visualizzato **011 $1** nel campo della **regola di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="6c328-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="6c328-132">Quando viene applicata questa regola di traduzione, + 441235551010 diventa 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="6c328-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="6c328-133">Fare clic su **OK** per salvare la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="6c328-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="6c328-134">Fare clic su **OK** per salvare la configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="6c328-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="6c328-135">Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="6c328-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6c328-136">Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="6c328-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="6c328-137">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="6c328-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c328-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c328-138">See Also</span></span>


[<span data-ttu-id="6c328-139">Creare o modificare manualmente una regola di traduzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c328-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="6c328-140">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c328-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="6c328-141">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c328-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="6c328-142">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c328-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="6c328-143">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c328-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

