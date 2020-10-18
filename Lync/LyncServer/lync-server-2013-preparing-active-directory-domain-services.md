---
title: 'Lync Server 2013: preparazione di servizi di dominio Active Directory'
description: 'Lync Server 2013: preparazione di servizi di dominio Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6ecfcffd55739bc6d1bf1b83a701a0fd515ec56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572537"
---
# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="2c79c-103">Preparazione di Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-103">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c79c-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2c79c-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2c79c-105">Prima di distribuire e utilizzare Lync Server 2013, è necessario preparare i servizi di dominio Active Directory estendendo lo schema e quindi creando e configurando gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="2c79c-105">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="2c79c-106">Le estensioni dello schema aggiungono le classi e gli attributi di Active Directory richiesti da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c79c-106">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="2c79c-107">Negli argomenti di questa sezione viene descritto come preparare Servizi di dominio Active Directory per la distribuzione di Lync Server e come assegnare le autorizzazioni di installazione e unità organizzativa (OU).</span><span class="sxs-lookup"><span data-stu-id="2c79c-107">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="2c79c-108">Per informazioni dettagliate sulle modifiche dello schema necessarie per Lync Server, vedere [estensioni dello schema di Active Directory, classi e attributi utilizzati da Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="2c79c-108">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2c79c-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="2c79c-109">In This Section</span></span>

  - [<span data-ttu-id="2c79c-110">Requisiti dell'infrastruttura di Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-110">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="2c79c-111">Panoramica della preparazione di servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-111">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="2c79c-112">Preparazione di servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-112">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="2c79c-113">Preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-113">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="2c79c-114">Concessione di autorizzazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c79c-114">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

