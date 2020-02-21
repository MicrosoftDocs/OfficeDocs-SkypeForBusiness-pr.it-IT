---
title: "Lync Server 2013: presentazione dell'ID chiamante"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f8feb08297b5588e790917a346557e5e6434930
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a><span data-ttu-id="93aee-102">Presentazione dell'ID chiamante in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93aee-102">Caller ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93aee-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="93aee-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="93aee-104">Con Lync Server 2010, il numero di telefono della parte chiamata, ovvero il numero di telefono chiamato, può essere convertito dal formato E. 164 al formato di composizione locale richiesto dal peer trunk, ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="93aee-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="93aee-105">A tale scopo, è necessario definire una o più regole per la conversione dell'URI di richiesta prima del routing al peer trunk.</span><span class="sxs-lookup"><span data-stu-id="93aee-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="93aee-106">Lync Server 2013 introduce l'opzione di tradurre anche il numero di telefono della parte chiamante (ovvero il numero di telefono da cui il chiamante chiama) dal formato E. 164 al formato di composizione locale richiesto dal peer trunk.</span><span class="sxs-lookup"><span data-stu-id="93aee-106">Lync Server 2013 introduces the option to also translate the calling party’s phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="93aee-107">È ad esempio possibile scrivere una regola di conversione per rimuovere +44 da una stringa di composizione e sostituirlo con 0144.</span><span class="sxs-lookup"><span data-stu-id="93aee-107">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="93aee-108">**Per configurare l'ID chiamante tramite il pannello di controllo di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="93aee-108">**To configure Caller ID by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="93aee-109">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93aee-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="93aee-110">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="93aee-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="93aee-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93aee-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="93aee-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="93aee-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="93aee-113">Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="93aee-113">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="93aee-114">Nella pagina **Configurazione trunk** fare doppio clic su un trunk esistente, ad esempio il trunk **Globale** per visualizzare la finestra di dialogo **Modifica configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="93aee-114">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

5.  <span data-ttu-id="93aee-115">Per configurare la presentazione dell'ID chiamante:</span><span class="sxs-lookup"><span data-stu-id="93aee-115">To configure caller ID presentation:</span></span>
    
      - <span data-ttu-id="93aee-116">Per selezionare una o più regole in un elenco di tutte le regole di conversione disponibili nella distribuzione di VoIP aziendale, fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="93aee-116">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="93aee-117">In **Regola di conversione per il numero del chiamante** fare clic sulle regole da associare al trunk e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93aee-117">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="93aee-118">Per definire una nuova regola di conversione e associarla al trunk, fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="93aee-118">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="93aee-119">Per informazioni dettagliate sulla definizione di una nuova regola, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93aee-119">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="93aee-120">Per modificare una regola di conversione già associata al trunk, fare clic sul nome della regola e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="93aee-120">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="93aee-121">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="93aee-121">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="93aee-122">Per copiare una regola di conversione esistente in modo da usarla come punto di partenza per definire una nuova regola, fare clic sul nome della regola, su **Copia** e quindi su **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="93aee-122">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="93aee-123">Per informazioni dettagliate, vedere [definizione delle regole di conversione in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="93aee-123">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="93aee-124">Per rimuovere una regola di conversione dal trunk, evidenziare il nome della regola e fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="93aee-124">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="93aee-125">Non associare regole di conversione a un trunk se sono state configurate regole di conversione nel trunk peer associato, perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="93aee-125">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

