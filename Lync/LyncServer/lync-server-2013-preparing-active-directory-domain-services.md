---
title: 'Lync Server 2013: Preparazione di Servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e1d7285d743da2270121389bbb5a510fe3b12d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="3acec-102">Preparazione di Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3acec-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3acec-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3acec-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3acec-104">Prima di distribuire e gestire Lync Server 2013, è necessario preparare i servizi di dominio Active Directory estendendo lo schema e quindi creando e configurando gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3acec-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="3acec-105">Le estensioni dello schema aggiungono le classi e gli attributi di Active Directory richiesti da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3acec-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="3acec-106">Gli argomenti in questa sezione descrivono come preparare Servizi di dominio Active Directory per la distribuzione di Lync Server e come assegnare le autorizzazioni di configurazione e unità organizzativa (OU).</span><span class="sxs-lookup"><span data-stu-id="3acec-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="3acec-107">Per informazioni dettagliate sulle modifiche allo schema necessarie per Lync Server, vedere [estensioni dello schema di Active Directory, classi e attributi usati da Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="3acec-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3acec-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3acec-108">In This Section</span></span>

  - [<span data-ttu-id="3acec-109">Requisiti dell'infrastruttura di Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3acec-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="3acec-110">Panoramica della preparazione di Servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3acec-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="3acec-111">Preparazione di Servizi di dominio Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3acec-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="3acec-112">Preparazione di un ambiente Servizi di dominio Active Directory bloccato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3acec-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="3acec-113">Concessione di autorizzazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3acec-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

