---
title: 'Lync Server 2013: configurare il bypass multimediale per ignorare sempre il Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76cf44ee24c94b4a243fe84db1f3bbf7a28ba2e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="28f0a-102">Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="28f0a-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28f0a-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="28f0a-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28f0a-104">In questo argomento si presuppone che la funzionalità di bypass multimediale sia già stata configurata per qualsiasi connessione trunk a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet ITSP) per un sito o un servizio specifico per il quale si vuole ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="28f0a-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="28f0a-105">Non è possibile configurare il contenuto multimediale in modo da ignorare sempre il Mediation Server e abilitare contemporaneamente il servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="28f0a-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="28f0a-106">Queste impostazioni sono incompatibili e sono quindi impostazioni mutuamente esclusive nell'interfaccia utente del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28f0a-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="28f0a-107">Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer del Mediation Server, è inoltre necessario configurare le impostazioni globali per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="28f0a-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="28f0a-108">Se si utilizzano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che si disponga di una buona connettività tra gli endpoint di Lync e qualsiasi peer per il quale è stato configurato il bypass multimediale sulla connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="28f0a-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="28f0a-109">Se non si dispone di una buona connettività tra gli endpoint di Lync Server e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni globali di bypass multimediale per l'utilizzo delle informazioni relative a siti e aree geografiche quando utilizzo del bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="28f0a-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="28f0a-110">Ciò consente di specificare in modo più preciso quando il contenuto multimediale deve ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="28f0a-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="28f0a-111">A tale scopo, eseguire la procedura descritta in [Configure Media Bypass Global Settings in Lync server 2013 per utilizzare le informazioni sui siti e le aree](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) geografiche e [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .</span><span class="sxs-lookup"><span data-stu-id="28f0a-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="28f0a-112">Per abilitare il bypass multimediale globalmente in modo che il Mediation Server venga ignorato sempre</span><span class="sxs-lookup"><span data-stu-id="28f0a-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="28f0a-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="28f0a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="28f0a-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28f0a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="28f0a-115">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="28f0a-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="28f0a-116">Fare doppio clic sulla configurazione **Globale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="28f0a-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="28f0a-117">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.</span><span class="sxs-lookup"><span data-stu-id="28f0a-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="28f0a-118">Fare clic su **Ignora sempre**.</span><span class="sxs-lookup"><span data-stu-id="28f0a-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="28f0a-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="28f0a-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="28f0a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28f0a-120">See Also</span></span>


[<span data-ttu-id="28f0a-121">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28f0a-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="28f0a-122">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28f0a-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="28f0a-123">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28f0a-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="28f0a-124">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28f0a-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

