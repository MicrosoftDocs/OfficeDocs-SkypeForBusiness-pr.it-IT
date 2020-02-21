---
title: 'Lync Server 2013: creare o modificare manualmente una regola di normalizzazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91b69eedcdb58d5a7cdb5cf96c1b98e7a6eedbd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="ca995-102">Creare o modificare manualmente una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca995-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca995-103">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="ca995-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="ca995-104">Se si desidera creare o modificare manualmente una regola di normalizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="ca995-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="ca995-105">Se si desidera creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione nel pannello di controllo di Lync Server, vedere [creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span><span class="sxs-lookup"><span data-stu-id="ca995-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="ca995-106">Per definire manualmente una regola di normalizzazione</span><span class="sxs-lookup"><span data-stu-id="ca995-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="ca995-107">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ca995-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ca995-108">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ca995-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ca995-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ca995-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ca995-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca995-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ca995-111">Optional Seguire la procedura illustrata in [creare un dial plan in Lync server 2013](lync-server-2013-create-a-dial-plan.md) o [modificare un dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="ca995-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="ca995-112">In **nuova regola di normalizzazione** o **Modifica regola di normalizzazione**digitare un nome che descriva il tipo di numero normalizzato in **nome** (ad esempio, denominare la regola di normalizzazione **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="ca995-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="ca995-113">Optional In campo **Descrizione** Digitare una descrizione della regola di normalizzazione (ad esempio, "converte le estensioni a 5 cifre").</span><span class="sxs-lookup"><span data-stu-id="ca995-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="ca995-114">In **genera una regola di normalizzazione**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="ca995-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="ca995-115">Immettere quanto segue in **Digita espressione regolare**:</span><span class="sxs-lookup"><span data-stu-id="ca995-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="ca995-116">In **corrispondenza di questo modello**specificare il modello che si desidera utilizzare per la corrispondenza con il numero di telefono composto.</span><span class="sxs-lookup"><span data-stu-id="ca995-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="ca995-117">In **regola di conversione**specificare un modello per il formato dei numeri di telefono E. 164 tradotti.</span><span class="sxs-lookup"><span data-stu-id="ca995-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="ca995-118">Ad esempio, se si immette **^ (\\d{7}) $** in **corrispondenza di questo modello** e **+ 1425 $1** in **regola di conversione**, la regola Normalizza 5550100 in + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="ca995-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="ca995-119">(Facoltativo) Se la regola di normalizzazione restituisce un numero di telefono interno all'organizzazione, selezionare **Estensione interna**.</span><span class="sxs-lookup"><span data-stu-id="ca995-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="ca995-120">Optional Immettere un numero per testare la regola di normalizzazione e quindi fare clic su **Vai**.</span><span class="sxs-lookup"><span data-stu-id="ca995-120">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="ca995-121">I risultati del test vengono visualizzati in **Immetti numero di telefono da testare**.</span><span class="sxs-lookup"><span data-stu-id="ca995-121">The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca995-122">È possibile salvare una regola di normalizzazione che non passa ancora il test e quindi riconfigurarla successivamente.</span><span class="sxs-lookup"><span data-stu-id="ca995-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="ca995-123">Per ulteriori informazioni, vedere <A href="lync-server-2013-test-voice-routing.md">test Voice routing in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ca995-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="ca995-124">Fare clic su **OK** per salvare la regola di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca995-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="ca995-125">Fare clic su **OK** per salvare il dial plan.</span><span class="sxs-lookup"><span data-stu-id="ca995-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="ca995-126">Nella pagina **Dial plan** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="ca995-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ca995-127">Ogni volta che si crea o si modifica una regola di normalizzazione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="ca995-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ca995-128">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="ca995-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca995-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca995-129">See Also</span></span>


[<span data-ttu-id="ca995-130">Creare o modificare una regola di normalizzazione utilizzando crea una regola di normalizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca995-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="ca995-131">Creare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca995-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="ca995-132">Modificare un dial plan in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca995-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="ca995-133">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca995-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="ca995-134">Testare il routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca995-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

