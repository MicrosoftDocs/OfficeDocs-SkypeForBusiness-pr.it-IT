---
title: 'Lync Server 2013: distribuzione del controllo delle chiamate remote'
description: 'Lync Server 2013: distribuzione del controllo delle chiamate remote.'
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
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566082"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="468c7-103">Distribuzione del controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="468c7-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="468c7-104">_**Ultimo argomento modificato:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="468c7-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="468c7-105">In questa sezione viene descritto il processo di distribuzione della funzionalità di controllo delle chiamate remote agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="468c7-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="468c7-106">Benché le caratteristiche di controllo delle chiamate remote siano disponibili per gli utenti remoti che si trovano all'esterno del firewall dell'organizzazione, sono escluse dalla trattazione di questa documentazione informazioni dettagliate sulla distribuzione di scenari di accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="468c7-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="468c7-107">Per informazioni dettagliate sulla distribuzione di accesso utente esterno, vedere <A href="lync-server-2013-deploying-external-user-access.md">Deploying External User Access in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="468c7-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="468c7-108">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="468c7-108">In This Section</span></span>

  - [<span data-ttu-id="468c7-109">Configurazione di Lync Server 2013 per il routing a un gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="468c7-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="468c7-110">Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="468c7-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="468c7-111">Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="468c7-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="468c7-112">[Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (solo se il gateway è configurato per l'utilizzo di TCP)</span><span class="sxs-lookup"><span data-stu-id="468c7-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="468c7-113">Abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="468c7-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="468c7-114">Controllo delle chiamate remote e normalizzazione del numero di telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="468c7-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="468c7-115">[Rimuovere un host autorizzato legacy in Lync Server 2013 (facoltativo)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (solo se si esegue la migrazione degli utenti precedentemente abilitati per il controllo delle chiamate remote)</span><span class="sxs-lookup"><span data-stu-id="468c7-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="468c7-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="468c7-116">Related Sections</span></span>

[<span data-ttu-id="468c7-117">Pianificazione del controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="468c7-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

