---
title: 'Lync Server 2013: creare o modificare manualmente una regola di traduzione'
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
ms.openlocfilehash: 372b394619a83ec01ca7a36bac4037c815f09fc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="bec25-102">Creare o modificare manualmente una regola di traduzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec25-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bec25-103">_**Argomento Ultima modifica:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="bec25-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="bec25-104">Seguire questa procedura se si vuole definire una regola di traduzione scrivendo un'espressione regolare per il modello e la regola di traduzione corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="bec25-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="bec25-105">In alternativa, è possibile immettere un set di valori nello strumento **Compila una regola di traduzione** e abilitare il pannello di controllo di Lync Server per generare la regola di corrispondenza corrispondente e il criterio di traduzione.</span><span class="sxs-lookup"><span data-stu-id="bec25-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="bec25-106">Per informazioni dettagliate, vedere [creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="bec25-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="bec25-107">Per definire manualmente una regola di traduzione</span><span class="sxs-lookup"><span data-stu-id="bec25-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="bec25-108">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bec25-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bec25-109">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bec25-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bec25-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bec25-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bec25-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bec25-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bec25-112">Per iniziare a definire una regola di traduzione, seguire la procedura descritta in [configurare un trunk con il bypass multimediale in Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) tramite il passaggio 10 o [configurare un trunk senza bypass multimediale in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) tramite il passaggio 9.</span><span class="sxs-lookup"><span data-stu-id="bec25-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="bec25-113">Nel campo **nome** della pagina **nuova** regola di traduzione o **Modifica regola di traduzione** digitare un nome che descriva il modello di numero da tradurre.</span><span class="sxs-lookup"><span data-stu-id="bec25-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="bec25-114">Opzionale In **Descrizione**Digitare una descrizione della regola di traduzione, ad esempio le **chiamate interurbane internazionali degli Stati Uniti**.</span><span class="sxs-lookup"><span data-stu-id="bec25-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="bec25-115">Fare clic su **modifica** nella parte inferiore della sezione **Compila una regola di traduzione** .</span><span class="sxs-lookup"><span data-stu-id="bec25-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="bec25-116">Immettere le opzioni seguenti nell' **espressione regolare di tipo**:</span><span class="sxs-lookup"><span data-stu-id="bec25-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="bec25-117">In **Confronta questo modello**, specifica il motivo che verrà usato per corrispondere ai numeri da tradurre.</span><span class="sxs-lookup"><span data-stu-id="bec25-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="bec25-118">Nella **regola di traduzione**specificare un motivo per il formato dei numeri tradotti.</span><span class="sxs-lookup"><span data-stu-id="bec25-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="bec25-119">Ad esempio, se si immette \*\* ^ \\+ (\\d{9}\\d +) $\*\* in **corrisponde a questo modello** e **011 $1** nella **regola di traduzione**, la regola tradurrà + 441235551010 in 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="bec25-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="bec25-120">Fare clic su **OK** per salvare la regola di traduzione.</span><span class="sxs-lookup"><span data-stu-id="bec25-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="bec25-121">Fare clic su **OK** per salvare la configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="bec25-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="bec25-122">Nella pagina **trunk Configuration** fare clic su **commit**e quindi su **Commit all**.</span><span class="sxs-lookup"><span data-stu-id="bec25-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bec25-123">Ogni volta che si crea o si modifica una regola di traduzione, è necessario eseguire il comando <STRONG>commit tutti</STRONG> per pubblicare la modifica della configurazione.</span><span class="sxs-lookup"><span data-stu-id="bec25-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="bec25-124">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">pubblicare le modifiche in sospeso nella configurazione del routing vocale in Lync Server 2013</A> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="bec25-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bec25-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bec25-125">See Also</span></span>


[<span data-ttu-id="bec25-126">Creare o modificare una regola di traduzione usando lo strumento crea una regola di traduzione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec25-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="bec25-127">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec25-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="bec25-128">Configurare un trunk senza bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec25-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="bec25-129">Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec25-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="bec25-130">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bec25-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

