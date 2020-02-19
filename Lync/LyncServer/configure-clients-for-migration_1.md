---
title: Configurare i client per la migrazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 542ee4d581d4df26a528a14fda5de792c2a2ad09
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="d2b95-102">Configurare i client per la migrazione</span><span class="sxs-lookup"><span data-stu-id="d2b95-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2b95-103">_**Ultimo argomento modificato:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="d2b95-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="d2b95-104">Questo argomento contiene le procedure consigliate per la distribuzione del client che è necessario eseguire prima di eseguire la migrazione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d2b95-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="d2b95-105">Queste modifiche alla configurazione devono essere eseguite su Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d2b95-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="d2b95-106">È molto importante eseguire questa procedura prima della migrazione.</span><span class="sxs-lookup"><span data-stu-id="d2b95-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="d2b95-107">Per informazioni dettagliate, vedere [Planning for clients and Devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="d2b95-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="d2b95-108">Per configurare i client prima della migrazione</span><span class="sxs-lookup"><span data-stu-id="d2b95-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="d2b95-109">Distribuire gli aggiornamenti più recenti per il server, il client e i dispositivi di Office Communications Server 2007 R2 (hotfix):</span><span class="sxs-lookup"><span data-stu-id="d2b95-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="d2b95-110">Applicare gli aggiornamenti di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d2b95-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="d2b95-111">Descrizione del pacchetto di aggiornamento cumulativo per Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="d2b95-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](https://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="d2b95-112">Acquisizione degli aggiornamenti software per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="d2b95-112">Obtaining Software Updates for Devices</span></span>](https://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="d2b95-113">In Office Communications Server 2007 R2, utilizzare il filtro delle versioni client per consentire l'accesso solo ai client di Office Communications Server 2007 R2 con gli aggiornamenti più recenti installati.</span><span class="sxs-lookup"><span data-stu-id="d2b95-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="d2b95-114">In Office Communications Server 2007 R2, utilizzare il filtro delle versioni client per bloccare i client di Lync Server 2013 dall'accesso.</span><span class="sxs-lookup"><span data-stu-id="d2b95-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="d2b95-115">Attenersi alla procedura descritta in **Configuring Client Version Filtering** [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to per aggiungere i filtri di versione elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d2b95-115">Follow the steps described in **Configuring Client Version Filtering** at [https://go.microsoft.com/fwlink/p/?linkId=202488](https://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="d2b95-116">Per ogni filtro di versione assegnare l'azione **Blocca**.</span><span class="sxs-lookup"><span data-stu-id="d2b95-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d2b95-117">Client</span><span class="sxs-lookup"><span data-stu-id="d2b95-117">Client</span></span></th>
    <th><span data-ttu-id="d2b95-118">Intestazione agente utente</span><span class="sxs-lookup"><span data-stu-id="d2b95-118">User agent header</span></span></th>
    <th><span data-ttu-id="d2b95-119">Version</span><span class="sxs-lookup"><span data-stu-id="d2b95-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d2b95-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d2b95-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="d2b95-121">OC</span><span class="sxs-lookup"><span data-stu-id="d2b95-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="d2b95-122">15.*..* \*</span><span class="sxs-lookup"><span data-stu-id="d2b95-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d2b95-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="d2b95-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="d2b95-124">CWA</span><span class="sxs-lookup"><span data-stu-id="d2b95-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="d2b95-125">5.*..* \*</span><span class="sxs-lookup"><span data-stu-id="d2b95-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d2b95-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="d2b95-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="d2b95-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="d2b95-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="d2b95-128">4.*..* \*</span><span class="sxs-lookup"><span data-stu-id="d2b95-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

