---
title: 'Lync Server 2013: distribuzione del controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5659bf3e210f1f8294789729a758d4877d3e70bb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="735a9-102">Distribuzione del controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="735a9-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="735a9-103">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="735a9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="735a9-104">In questa sezione viene descritto il processo di distribuzione della funzionalità di controllo delle chiamate remote agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="735a9-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="735a9-105">Benché le caratteristiche di controllo delle chiamate remote siano disponibili per gli utenti remoti che si trovano all'esterno del firewall dell'organizzazione, sono escluse dalla trattazione di questa documentazione informazioni dettagliate sulla distribuzione di scenari di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="735a9-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="735a9-106">Per informazioni dettagliate sulla distribuzione di accesso utente esterno, vedere <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="735a9-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="735a9-107">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="735a9-107">In This Section</span></span>

  - [<span data-ttu-id="735a9-108">Configurazione di Lync Server 2013 per il routing a un gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="735a9-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="735a9-109">Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="735a9-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="735a9-110">Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="735a9-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="735a9-111">[Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (solo se il gateway è configurato per l'utilizzo di TCP)</span><span class="sxs-lookup"><span data-stu-id="735a9-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="735a9-112">Abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="735a9-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="735a9-113">Controllo delle chiamate remote e normalizzazione del numero di telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="735a9-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="735a9-114">[Rimuovere un host autorizzato legacy in Lync Server 2013 (facoltativo)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (solo se si esegue la migrazione degli utenti precedentemente abilitati per il controllo delle chiamate remote)</span><span class="sxs-lookup"><span data-stu-id="735a9-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="735a9-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="735a9-115">Related Sections</span></span>

[<span data-ttu-id="735a9-116">Pianificazione del controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="735a9-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

