---
title: 'Lync Server 2013: creare o modificare manualmente una regola di conversione'
description: 'Lync Server 2013: creare o modificare manualmente una regola di conversione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f393ca1983e072090cc27d47b142dace8b566c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574502"
---
# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="8cbcd-103">Creare o modificare manualmente una regola di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-103">Create or modify a translation rule manually in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cbcd-104">_**Ultimo argomento modificato:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="8cbcd-104">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="8cbcd-105">Eseguire questa procedura se si desidera definire una regola di conversione scrivendo un'espressione regolare per il formato e la regola.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-105">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="8cbcd-106">In alternativa, è possibile immettere un insieme di valori nello strumento **Costruisci una regola di conversione** e abilitare il pannello di controllo di Lync Server per generare la corrispondente regola di conversione e il modello corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-106">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="8cbcd-107">Per ulteriori informazioni, vedere [creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="8cbcd-107">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="8cbcd-108">Per definire manualmente una regola di conversione</span><span class="sxs-lookup"><span data-stu-id="8cbcd-108">To define a translation rule manually</span></span>

1.  <span data-ttu-id="8cbcd-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8cbcd-110">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8cbcd-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8cbcd-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8cbcd-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8cbcd-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8cbcd-113">Per iniziare a definire una regola di conversione, eseguire la procedura descritta in [Configure a Trunk with media bypass in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through Step 10 oppure [Configure a Trunk Without Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through Step 9.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="8cbcd-114">Nel campo **Nome** della pagina **Nuova regola di conversione** o **Modifica regola di conversione** digitare un nome che descriva il formato del numero da convertire.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-114">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="8cbcd-115">(Facoltativo) In **Descrizione** digitare una descrizione della regola di conversione, ad esempio **Chiamate internazionali Stati Uniti**.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-115">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="8cbcd-116">Fare clic su **Modifica** nella parte inferiore della sezione **Crea regola di conversione**.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-116">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="8cbcd-117">Immettere quanto segue in **Digita espressione regolare**:</span><span class="sxs-lookup"><span data-stu-id="8cbcd-117">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="8cbcd-118">In **Trova corrispondenza per questo formato** specificare il modello di formato da utilizzare per trovare corrispondenze con i numeri da convertire.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-118">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="8cbcd-119">In **Regola di conversione** specificare un modello per il formato dei numeri convertiti.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-119">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="8cbcd-120">Ad esempio, se si immette \*\* ^ \\ + ( \\ d {9} \\ d +) $\*\* in **corrispondenza di questo modello** e **011 $1** in **regola di conversione**, la regola verrà convertita da + 441235551010 a 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-120">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="8cbcd-121">Fare clic su **OK** per salvare la regola di conversione.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-121">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="8cbcd-122">Fare clic su **OK** per salvare la configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-122">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="8cbcd-123">Nella pagina **Configurazione trunk** fare clic su **Commit** e quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-123">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8cbcd-124">Ogni volta che si crea o modifica una regola di conversione, è necessario eseguire il comando <STRONG>Salva tutto</STRONG> per pubblicare la modifica apportata alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-124">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8cbcd-125">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</A> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="8cbcd-125">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8cbcd-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cbcd-126">See Also</span></span>


[<span data-ttu-id="8cbcd-127">Creare o modificare una regola di conversione utilizzando lo strumento Crea regola di conversione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-127">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="8cbcd-128">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="8cbcd-129">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="8cbcd-130">Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-130">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="8cbcd-131">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cbcd-131">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

