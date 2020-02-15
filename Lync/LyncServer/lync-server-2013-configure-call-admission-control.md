---
title: 'Lync Server 2013: configurare il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ebe3fbdd60409523755c865f4b4f34025acf15d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="01f5a-102">Configurare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f5a-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="01f5a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="01f5a-104">Il servizio Controllo di ammissione di chiamata è una soluzione che determina se è possibile stabilire una sessione in tempo reale in base alla larghezza di banda disponibile per evitare di fornire una qualità audio/video scadente per gli utenti su reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="01f5a-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="01f5a-105">Questo servizio controlla il traffico in tempo reale solo per audio e video e non ha effetto sul traffico di dati.</span><span class="sxs-lookup"><span data-stu-id="01f5a-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="01f5a-106">Controllo di ammissione di chiamata può instradare la chiamata attraverso un percorso Internet qualora la larghezza di banda del percorso WAN predefinito non sia sufficiente.</span><span class="sxs-lookup"><span data-stu-id="01f5a-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="01f5a-107">Per informazioni dettagliate, vedere [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="01f5a-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="01f5a-108">In questa sezione è contenuto un set di procedure di esempio che illustrano in che modo distribuire e gestire Controllo di ammissione di chiamata nella rete.</span><span class="sxs-lookup"><span data-stu-id="01f5a-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="01f5a-109">Prima di distribuire il servizio di controllo di ammissione di chiamata, è necessario raccogliere tutte le informazioni necessarie per la topologia di rete aziendale, come descritto nell' <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">esempio: Gathering your requirements for Call Admission Control in Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="01f5a-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="01f5a-110">Verificare inoltre che i componenti CAC siano stati installati e attivati, come descritto in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definire e configurare un pool Front end o un server Standard Edition in Lync server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="01f5a-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="01f5a-111">Tutti gli esempi di distribuzione e gestione di CAC in questa sezione vengono eseguiti utilizzando Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="01f5a-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="01f5a-112">In alternativa, è possibile utilizzare anche la sezione <STRONG>configurazione di rete</STRONG> del pannello di controllo di Lync Server per gestire il servizio di gestione dei comandi.</span><span class="sxs-lookup"><span data-stu-id="01f5a-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="01f5a-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="01f5a-113">In This Section</span></span>

  - [<span data-ttu-id="01f5a-114">Configurare le aree di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="01f5a-115">Creare profili di criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="01f5a-116">Configurazione dei siti di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="01f5a-117">Associare subnet a siti di rete per il servizio di controllo di ammissione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="01f5a-118">Creare collegamenti area di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="01f5a-119">Creare route tra aree di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="01f5a-120">Creare criteri intersito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="01f5a-121">Abilitare il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="01f5a-122">Elenco di controllo per la distribuzione dei controlli di ammissione di chiamata per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f5a-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

