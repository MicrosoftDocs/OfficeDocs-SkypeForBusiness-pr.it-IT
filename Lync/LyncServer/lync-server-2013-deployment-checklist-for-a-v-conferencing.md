---
title: Elenco di controllo della distribuzione di Lync Server 2013 per i servizi di conferenza A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for A/V conferencing
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49733684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d787cbc1e2bbefcc2cb125e64ab7143ddbd6cf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-av-conferencing-in-lync-server-2013"></a><span data-ttu-id="77ee7-102">Elenco di controllo della distribuzione per i servizi di conferenza A/V in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ee7-102">Deployment checklist for A/V conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77ee7-103">_**Argomento Ultima modifica:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="77ee7-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="77ee7-104">Come per la distribuzione degli altri componenti di Lync Server 2013, la distribuzione di servizi di conferenza A/V richiede l'uso di generatore di topologie per creare e pubblicare una topologia che incorpora servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77ee7-104">As with deployment of your other Lync Server 2013 components, deployment of A/V conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="77ee7-105">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="77ee7-105">Deployment Sequence</span></span>

<span data-ttu-id="77ee7-106">È possibile distribuire i servizi di conferenza contemporaneamente alla distribuzione della topologia iniziale o dopo avere distribuito almeno un pool di front-end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="77ee7-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="77ee7-107">Processo di distribuzione delle conferenze</span><span class="sxs-lookup"><span data-stu-id="77ee7-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="77ee7-108">La tabella seguente offre una panoramica dei passaggi necessari per distribuire i servizi di conferenza in una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="77ee7-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77ee7-109">Fase</span><span class="sxs-lookup"><span data-stu-id="77ee7-109">Phase</span></span></th>
<th><span data-ttu-id="77ee7-110">Passaggi</span><span class="sxs-lookup"><span data-stu-id="77ee7-110">Steps</span></span></th>
<th><span data-ttu-id="77ee7-111">Ruoli e appartenenze ai gruppi</span><span class="sxs-lookup"><span data-stu-id="77ee7-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="77ee7-112">Documentazione</span><span class="sxs-lookup"><span data-stu-id="77ee7-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77ee7-113"><strong>Installare hardware e software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="77ee7-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="77ee7-114">I servizi di conferenza vengono eseguiti nei server front-end di un pool Front-end e di server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="77ee7-114">Conferencing runs on Front End Servers of a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="77ee7-115">Non ha requisiti hardware o software aggiuntivi oltre a ciò che è necessario per installare tali server.</span><span class="sxs-lookup"><span data-stu-id="77ee7-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="77ee7-116">Lync Server 2013 usa Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="77ee7-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="77ee7-117">Per informazioni dettagliate sull'installazione e la configurazione del server Office Web Apps, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="77ee7-117">For details about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="77ee7-118">Utente del dominio che è membro del gruppo Administrators locale</span><span class="sxs-lookup"><span data-stu-id="77ee7-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="77ee7-119"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="77ee7-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="77ee7-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto di software e infrastrutture server in Lync server 2013</a> nella documentazione relativa al supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="77ee7-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="77ee7-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determinare i requisiti di sistema per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="77ee7-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="77ee7-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="77ee7-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77ee7-123"><strong>Creare la topologia interna appropriata per supportare i servizi di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="77ee7-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="77ee7-124">Eseguire Generatore di topologie per aggiungere servizi di conferenza alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="77ee7-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="77ee7-125">Per definire una topologia, un account membro del gruppo utenti locali</span><span class="sxs-lookup"><span data-stu-id="77ee7-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="77ee7-126">Per pubblicare la topologia, un account che sia un membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga delle autorizzazioni controllo completo (lettura/scrittura/modifica) nella condivisione file da usare per l'archivio di file di Lync Server 2013 (in modo che il generatore di topologia possa configurare gli elenchi DACL necessari)</span><span class="sxs-lookup"><span data-stu-id="77ee7-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="77ee7-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definire e configurare una topologia in Generatore di topologia per Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="77ee7-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77ee7-128"><strong>Configurare i criteri di conferenza e il supporto</strong></span><span class="sxs-lookup"><span data-stu-id="77ee7-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="77ee7-129">Usare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="77ee7-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="77ee7-130">Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegna gli utenti al ruolo [] o CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="77ee7-130">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="77ee7-131"><a href="lync-server-2013-conferencing-policies.md">Criteri di conferenza in Lync Server 2013</a> nella documentazione Operations.</span><span class="sxs-lookup"><span data-stu-id="77ee7-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77ee7-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77ee7-132">See Also</span></span>


[<span data-ttu-id="77ee7-133">Panoramica delle conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ee7-133">Overview of conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-conferencing.md)  
[<span data-ttu-id="77ee7-134">Definizione dei requisiti per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77ee7-134">Defining your requirements for conferencing in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

