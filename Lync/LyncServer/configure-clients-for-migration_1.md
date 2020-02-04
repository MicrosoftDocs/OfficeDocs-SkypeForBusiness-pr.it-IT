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
ms.openlocfilehash: 84205c75da4c52aa6c90f3a501c74dd849933d9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a><span data-ttu-id="9c8f7-102">Configurare i client per la migrazione</span><span class="sxs-lookup"><span data-stu-id="9c8f7-102">Configure clients for migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c8f7-103">_**Argomento Ultima modifica:** 2013-11-21_</span><span class="sxs-lookup"><span data-stu-id="9c8f7-103">_**Topic Last Modified:** 2013-11-21_</span></span>

<span data-ttu-id="9c8f7-104">Questo argomento contiene le procedure consigliate per la distribuzione del client da eseguire prima di eseguire la migrazione a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-104">This topic contains the recommended client deployment steps you should take prior to migrating to Lync Server 2013.</span></span> <span data-ttu-id="9c8f7-105">Queste modifiche alla configurazione devono essere eseguite in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-105">These configuration changes should be made on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="9c8f7-106">È molto importante eseguire questi passaggi prima della migrazione.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-106">It is very important that you perform these steps prior to migrating.</span></span> <span data-ttu-id="9c8f7-107">Per informazioni dettagliate, vedere [pianificazione per client e dispositivi in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span><span class="sxs-lookup"><span data-stu-id="9c8f7-107">For details, see [Planning for clients and devices in Lync Server 2013](lync-server-2013-planning-for-clients-and-devices.md).</span></span>

<div>

## <a name="to-configure-clients-prior-to-migration"></a><span data-ttu-id="9c8f7-108">Per configurare i client prima della migrazione</span><span class="sxs-lookup"><span data-stu-id="9c8f7-108">To configure clients prior to migration</span></span>

1.  <span data-ttu-id="9c8f7-109">Distribuire gli aggiornamenti più recenti per server, client e dispositivi di Office Communications Server 2007 R2 (hotfix):</span><span class="sxs-lookup"><span data-stu-id="9c8f7-109">Deploy the most recent Office Communications Server 2007 R2 server, client, and device updates (hotfixes):</span></span>
    
      - [<span data-ttu-id="9c8f7-110">Applicare gli aggiornamenti di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c8f7-110">Apply Office Communications Server 2007 R2 updates</span></span>](apply-office-communications-server-2007-r2-updates.md)
    
      - [<span data-ttu-id="9c8f7-111">Descrizione del pacchetto di aggiornamento cumulativo per Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c8f7-111">Description of the cumulative update package for Communicator 2007 R2</span></span>](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [<span data-ttu-id="9c8f7-112">Ottenere gli aggiornamenti software per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="9c8f7-112">Obtaining Software Updates for Devices</span></span>](http://go.microsoft.com/fwlink/?linkid=335809)

2.  <span data-ttu-id="9c8f7-113">In Office Communications Server 2007 R2 usare il filtro della versione client per consentire solo i client Office Communications Server 2007 R2 con gli aggiornamenti più recenti installati per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-113">On Office Communications Server 2007 R2, use Client Version Filtering to allow only Office Communications Server 2007 R2 clients with the most current updates installed to sign in.</span></span>

3.  <span data-ttu-id="9c8f7-114">In Office Communications Server 2007 R2 usare il filtro della versione client per bloccare i client di Lync Server 2013 dall'accesso.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-114">On Office Communications Server 2007 R2, use Client Version Filtering to block Lync Server 2013 clients from signing in.</span></span> <span data-ttu-id="9c8f7-115">Seguire i passaggi descritti in **configurazione del filtro delle versioni client** in [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) per aggiungere i filtri della versione elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-115">Follow the steps described in **Configuring Client Version Filtering** at [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488) to add the version filters listed in the following table.</span></span> <span data-ttu-id="9c8f7-116">Per ogni filtro della versione, assegnare il **blocco**di azioni.</span><span class="sxs-lookup"><span data-stu-id="9c8f7-116">For each version filter, assign the action **Block**.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="9c8f7-117">Client</span><span class="sxs-lookup"><span data-stu-id="9c8f7-117">Client</span></span></th>
    <th><span data-ttu-id="9c8f7-118">Intestazione dell'agente utente</span><span class="sxs-lookup"><span data-stu-id="9c8f7-118">User agent header</span></span></th>
    <th><span data-ttu-id="9c8f7-119">Versione</span><span class="sxs-lookup"><span data-stu-id="9c8f7-119">Version</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="9c8f7-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9c8f7-120">Lync 2013</span></span></p></td>
    <td><p><span data-ttu-id="9c8f7-121">OC</span><span class="sxs-lookup"><span data-stu-id="9c8f7-121">OC</span></span></p></td>
    <td><p><span data-ttu-id="9c8f7-122">15.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="9c8f7-122">15.*.*.\*</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="9c8f7-123">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="9c8f7-123">Lync Web App</span></span></p></td>
    <td><p><span data-ttu-id="9c8f7-124">CWA</span><span class="sxs-lookup"><span data-stu-id="9c8f7-124">CWA</span></span></p></td>
    <td><p><span data-ttu-id="9c8f7-125">5.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="9c8f7-125">5.*.*.\*</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="9c8f7-126">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9c8f7-126">Lync Phone Edition</span></span></p></td>
    <td><p><span data-ttu-id="9c8f7-127">OCPhone</span><span class="sxs-lookup"><span data-stu-id="9c8f7-127">OCPhone</span></span></p></td>
    <td><p><span data-ttu-id="9c8f7-128">4.*.*. \*</span><span class="sxs-lookup"><span data-stu-id="9c8f7-128">4.*.*.\*</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

