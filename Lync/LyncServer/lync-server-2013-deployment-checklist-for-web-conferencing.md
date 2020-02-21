---
title: Elenco di controllo di distribuzione di Lync Server 2013 per Web Conferencing
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d3825891fe6934699e310073825e50a4aee731
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a><span data-ttu-id="c31d0-102">Elenco di controllo di distribuzione per le conferenze Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c31d0-102">Deployment checklist for web conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c31d0-103">_**Ultimo argomento modificato:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="c31d0-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="c31d0-104">Come per la distribuzione degli altri componenti di Lync Server 2013, la distribuzione di Web Conferencing richiede l'utilizzo di generatore di topologie per creare e pubblicare una topologia che incorpora servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c31d0-104">As with deployment of your other Lync Server 2013 components, deployment of web conferencing requires that you use Topology Builder to create and publish a topology that incorporates conferencing.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="c31d0-105">Sequenza di distribuzione</span><span class="sxs-lookup"><span data-stu-id="c31d0-105">Deployment Sequence</span></span>

<span data-ttu-id="c31d0-106">È possibile distribuire le conferenze nello stesso momento in cui si distribuisce la topologia iniziale o dopo aver distribuito almeno un pool Front end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c31d0-106">You can deploy conferencing at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span>

</div>

<div>

## <a name="conferencing-deployment-process"></a><span data-ttu-id="c31d0-107">Processo di distribuzione delle funzioni di conferenza</span><span class="sxs-lookup"><span data-stu-id="c31d0-107">Conferencing Deployment Process</span></span>

<span data-ttu-id="c31d0-108">Nella tabella seguente viene fornita una panoramica dei passaggi da eseguire per distribuire il supporto per la conferenza in una topologia esistente.</span><span class="sxs-lookup"><span data-stu-id="c31d0-108">The following table provides an overview of the steps required to deploy conferencing into an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c31d0-109">Fase</span><span class="sxs-lookup"><span data-stu-id="c31d0-109">Phase</span></span></th>
<th><span data-ttu-id="c31d0-110">Passaggi</span><span class="sxs-lookup"><span data-stu-id="c31d0-110">Steps</span></span></th>
<th><span data-ttu-id="c31d0-111">Ruoli e gruppi a cui è necessario appartenere</span><span class="sxs-lookup"><span data-stu-id="c31d0-111">Roles and group memberships</span></span></th>
<th><span data-ttu-id="c31d0-112">Documentazione</span><span class="sxs-lookup"><span data-stu-id="c31d0-112">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c31d0-113"><strong>Installare l'hardware e il software prerequisiti</strong></span><span class="sxs-lookup"><span data-stu-id="c31d0-113"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="c31d0-114">I servizi di conferenza vengono eseguiti nei front end server in un pool Front end e server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c31d0-114">Conferencing runs on Front End Servers in a Front End pool and Standard Edition servers.</span></span> <span data-ttu-id="c31d0-115">Non esistono ulteriori requisiti di hardware o software oltre a quelli necessari per l'installazione di questi server.</span><span class="sxs-lookup"><span data-stu-id="c31d0-115">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c31d0-116">Lync Server 2013 utilizza Office Web Apps e il server Office Web Apps per gestire la condivisione e il rendering delle presentazioni di PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="c31d0-116">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="c31d0-117">Per informazioni sull'installazione e sulla configurazione del server Office Web Apps, vedere <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">configurazione dell'integrazione con Office Web Apps Server e Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c31d0-117">For information about installing and configuring the Office Web Apps Server, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>


</div></td>
<td><p><span data-ttu-id="c31d0-118">Utente del dominio membro del gruppo Administrators locale</span><span class="sxs-lookup"><span data-stu-id="c31d0-118">Domain user who is a member of the local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="c31d0-119"><a href="lync-server-2013-supported-hardware.md">Hardware supportato per Lync Server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="c31d0-119"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c31d0-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Supporto dell'infrastruttura e del software server in Lync server 2013</a> nella documentazione relativa alla supportabilità</span><span class="sxs-lookup"><span data-stu-id="c31d0-120"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="c31d0-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determinazione dei requisiti di sistema per Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c31d0-121"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="c31d0-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisiti tecnici per l'archiviazione in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c31d0-122"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c31d0-123"><strong>Creare la topologia interna appropriata per supportare le funzioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="c31d0-123"><strong>Create the appropriate internal topology to support conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="c31d0-124">Eseguire Generatore di topologie per aggiungere servizi di conferenza alla topologia e quindi pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="c31d0-124">Run Topology Builder to add conferencing to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="c31d0-125">Per definire una topologia, un account membro del gruppo Users locale</span><span class="sxs-lookup"><span data-stu-id="c31d0-125">To define a topology, an account that is a member of the local Users group</span></span></p>
<p><span data-ttu-id="c31d0-126">Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che disponga di autorizzazioni di controllo completo (lettura/scrittura/modifica) sulla condivisione file da utilizzare per l'archivio file di Lync Server 2013 (in modo che il generatore di topologie possa configurare gli elenchi DACL necessari)</span><span class="sxs-lookup"><span data-stu-id="c31d0-126">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs)</span></span></p></td>
<td><p><span data-ttu-id="c31d0-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c31d0-127"><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Define and configure a topology in Topology Builder for Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c31d0-128"><strong>Configurare i criteri e il supporto per le funzioni di conferenza</strong></span><span class="sxs-lookup"><span data-stu-id="c31d0-128"><strong>Configure conferencing policies and support</strong></span></span></p></td>
<td><p><span data-ttu-id="c31d0-129">Utilizzare il pannello di controllo di Lync Server 2013 o Lync Server Management Shell per configurare le impostazioni di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c31d0-129">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to configure conferencing settings.</span></span></p></td>
<td><p><span data-ttu-id="c31d0-130">Gruppo RTCUniversalServerAdmins (solo Windows PowerShell) oppure assegnare gli utenti al ruolo [] o CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="c31d0-130">RTCUniversalServerAdmins group ( Windows PowerShell only) or assign users to the [] or CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="c31d0-131"><a href="lync-server-2013-conferencing-policies.md">Criteri di conferenza in Lync Server 2013</a> nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="c31d0-131"><a href="lync-server-2013-conferencing-policies.md">Conferencing policies in Lync Server 2013</a> in the Operations documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c31d0-132">Lync Server 2013 ora include l'impostazione **MaxUploadFileSizeMb** , che consente di limitare le dimensioni dei file che possono essere caricati durante una riunione.</span><span class="sxs-lookup"><span data-stu-id="c31d0-132">Lync Server 2013 now includes the **MaxUploadFileSizeMb** setting, which limits the size of files that can be uploaded during a meeting.</span></span> <span data-ttu-id="c31d0-133">Il valore predefinito per questa impostazione è di 500 MB.</span><span class="sxs-lookup"><span data-stu-id="c31d0-133">The default value for this setting is 500 MB.</span></span> <span data-ttu-id="c31d0-134">È possibile modificare **MaxUploadFileSizeMb** mediante il cmdlet **Set-CsConferencingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c31d0-134">You can adjust **MaxUploadFileSizeMb** using the **Set-CsConferencingConfiguration** cmdlet.</span></span>

<span data-ttu-id="c31d0-135">**MaxUploadFileSizeMb** non limita l'impostazione di caricamento dei file per Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="c31d0-135">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="c31d0-136">Il limite di caricamento delle dimensioni dei file per Lync Web App è impostato su approssimativamente 30MB ed è controllato dal file Web. config di\[IIS\]:/DataCollabWeb/int ext/handler/Web.config. Per configurare il limite di caricamento delle dimensioni dei file per Lync Web `maxRequestLength` app `maxAllowedContentLength` , aggiornarlo e nel file Web. config come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c31d0-136">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="c31d0-137">È necessario aggiornare il file Web. config per ogni Front End Server.</span><span class="sxs-lookup"><span data-stu-id="c31d0-137">You must update the web.config file for each Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

