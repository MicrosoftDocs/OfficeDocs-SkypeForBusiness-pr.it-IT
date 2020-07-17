---
title: 'Fase 4: unire le topologie'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30af9fc21528fbfe183aa3849adeb30e8f41ef10
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="dde7c-102">Fase 4: unire le topologie</span><span class="sxs-lookup"><span data-stu-id="dde7c-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dde7c-103">_**Ultimo argomento modificato:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="dde7c-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="dde7c-104">Negli argomenti seguenti vengono illustrati i passaggi necessari per unire i pool di Microsoft Office Communications Server 2007 R2 ai pool di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dde7c-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="dde7c-105">È innanzitutto necessario utilizzare l'Unione guidata di Generatore di topologie per unire le informazioni della topologia.</span><span class="sxs-lookup"><span data-stu-id="dde7c-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="dde7c-106">Questo strumento consente di raccogliere informazioni sull'ambiente Office Communications Server 2007 R2, incluse le informazioni sui server perimetrali e di pubblicare tali informazioni in un database condiviso con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dde7c-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="dde7c-107">Dopo aver pubblicato la topologia unita, il generatore di topologie viene utilizzato per visualizzare le informazioni sulla topologia di Office Communications Server 2007 R2 e le informazioni sulla topologia di Lync Server 2013 appena distribuita.</span><span class="sxs-lookup"><span data-stu-id="dde7c-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="dde7c-108">È infine necessario utilizzare i cmdlet di nm-csshellper importare i criteri e le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dde7c-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dde7c-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="dde7c-109">In This Section</span></span>

  - [<span data-ttu-id="dde7c-110">Installare il pacchetto di compatibilità con le versioni precedenti di WMI</span><span class="sxs-lookup"><span data-stu-id="dde7c-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="dde7c-111">Unione mediante l'Unione guidata generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="dde7c-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="dde7c-112">Importare criteri e impostazioni</span><span class="sxs-lookup"><span data-stu-id="dde7c-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="dde7c-113">Verificare le informazioni sulla topologia</span><span class="sxs-lookup"><span data-stu-id="dde7c-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

