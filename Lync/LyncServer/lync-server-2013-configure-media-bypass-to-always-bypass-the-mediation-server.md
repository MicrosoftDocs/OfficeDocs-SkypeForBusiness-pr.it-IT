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
ms.openlocfilehash: 0023fba32b24243dc4bf2a12659700ace6dea91a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="bb814-102">Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="bb814-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb814-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="bb814-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb814-104">Questo argomento presuppone che sia già stato configurato il bypass multimediale per tutte le connessioni trunk a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un SBC (Session Border Controller) presso un provider di servizi di telefonia Internet (ITSP)) per uno specifico sito o servizio per cui si vuole che l'elemento multimediale ignori il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="bb814-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="bb814-105">Non è possibile configurare l'elemento multimediale per evitare sempre il Mediation Server, ma anche per abilitare il controllo di ammissione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="bb814-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="bb814-106">Queste impostazioni sono incompatibili e quindi sono impostazioni mutuamente esclusive nell'interfaccia utente del pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb814-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="bb814-107">Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer al Mediation Server, è anche necessario configurare le impostazioni globali per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="bb814-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="bb814-108">Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presume che si disponga di una buona connettività tra endpoint Lync e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="bb814-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="bb814-109">Se non si dispone di una buona connettività tra endpoint di Lync Server e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni di bypass multimediale globale per usare le informazioni sul sito e le aree geografiche quando utilizzo del bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="bb814-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="bb814-110">In questo modo è possibile determinare un maggiore controllo quando l'elemento multimediale ignora il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="bb814-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="bb814-111">A questo scopo, eseguire la procedura descritta in [configurare le impostazioni globali di bypass multimediale in Lync server 2013 per usare le informazioni sul sito e le aree](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) geografiche e [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) .</span><span class="sxs-lookup"><span data-stu-id="bb814-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="bb814-112">Per abilitare il bypass multimediale a livello globale per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="bb814-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="bb814-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb814-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bb814-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bb814-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="bb814-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="bb814-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="bb814-116">Fare doppio clic sulla configurazione **globale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bb814-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="bb814-117">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="bb814-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="bb814-118">Fare clic su **Ignora sempre**.</span><span class="sxs-lookup"><span data-stu-id="bb814-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="bb814-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="bb814-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb814-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb814-120">See Also</span></span>


[<span data-ttu-id="bb814-121">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb814-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="bb814-122">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb814-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="bb814-123">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb814-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="bb814-124">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb814-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

