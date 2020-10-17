---
title: Elenco di controllo di distribuzione di Lync Server 2013 per A/V Conferencing
description: Elenco di controllo di distribuzione di Lync Server 2013 per servizi di conferenza A/V.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9a4584172ed4c01eb163ea51aa4f62c2ce75185
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557772"
---
# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="6aa8c-103">Elenco di controllo per la distribuzione di A/V Conferencing in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa8c-103">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aa8c-104">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="6aa8c-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="6aa8c-105">Come per la distribuzione degli altri componenti di Lync Server 2013, la distribuzione di A/V Conferencing richiede l'utilizzo di generatore di topologie per creare e pubblicare una topologia che incorpora servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-105">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="6aa8c-106">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="6aa8c-106">Deployment Sequence</span></span>

<span data-ttu-id="6aa8c-107">È possibile distribuire le conferenze nello stesso momento in cui si distribuisce la topologia iniziale o dopo aver distribuito almeno un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-107">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="6aa8c-108">Processo di distribuzione delle funzioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="6aa8c-108">Conferencing Deployment Process</span></span>

<span data-ttu-id="6aa8c-109">Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire il supporto per la conferenza in una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-109">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6aa8c-110">Fase</span><span class="sxs-lookup"><span data-stu-id="6aa8c-110">Phase</span></span></th>
<th><span data-ttu-id="6aa8c-111">Passaggi</span><span class="sxs-lookup"><span data-stu-id="6aa8c-111">Steps</span></span></th>
<th><span data-ttu-id="6aa8c-112">Ruoli e gruppi a cui è necessario appartenere</span><span class="sxs-lookup"><span data-stu-id="6aa8c-112">Roles and group memberships</span></span></th>
<th><span data-ttu-id="6aa8c-113">Documentazione</span><span class="sxs-lookup"><span data-stu-id="6aa8c-113">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6aa8c-114"><strong>Installare l'hardware e il software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="6aa8c-114"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="6aa8c-115">I servizi di conferenza vengono eseguiti nei front end server di un pool Front end e di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-115">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="6aa8c-116">Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-116">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6aa8c-117">Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-117">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="6aa8c-118">Per informazioni dettagliate sull'installazione e sulla configurazione del server Office Web Apps, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-118">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="6aa8c-119">Utente del dominio membro del gruppo Administrators locale</span><span class="sxs-lookup"><span data-stu-id="6aa8c-119">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="6aa8c-120"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="6aa8c-120"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6aa8c-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="6aa8c-121"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="6aa8c-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-122"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="6aa8c-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-123"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aa8c-124"><strong>Creare la topologia interna appropriata per supportare le funzioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="6aa8c-124"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="6aa8c-125">Eseguire Generatore di topologie per aggiungere servizi di conferenza alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-125">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="6aa8c-126">Per definire una topologia, un account membro del gruppo Users locale</span><span class="sxs-lookup"><span data-stu-id="6aa8c-126">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="6aa8c-127">Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (lettura/scrittura/modifica) sulla condivisione file da utilizzare per l'archivio file di Lync Server 2013 (in modo che il generatore di topologie possa configurare gli elenchi DACL necessari)</span><span class="sxs-lookup"><span data-stu-id="6aa8c-127">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="6aa8c-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-128"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aa8c-129"><strong>Configurare i criteri e il supporto per le funzioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="6aa8c-129"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="6aa8c-130">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-130">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="6aa8c-131">Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo [] o CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="6aa8c-131">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="6aa8c-132"><a href="lync-server-2013-conferencing-policies.md">Criteri di conferenza in Lync Server 2013</a> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="6aa8c-132"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6aa8c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aa8c-133">See Also</span></span>


[<span data-ttu-id="6aa8c-134">Panoramica delle conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa8c-134">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="6aa8c-135">Definizione dei requisiti per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6aa8c-135">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

