---
title: "Lync Server 2013: prerequisiti per l'abilitazione dell'autenticazione Kerberos"
description: "Lync Server 2013: prerequisiti per l'abilitazione dell'autenticazione Kerberos."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579922"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="750dc-103">Prerequisiti per l'abilitazione dell'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="750dc-103">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="750dc-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="750dc-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="750dc-105">Prima di abilitare l'autenticazione Kerberos, accertarsi di aver completato tutte le operazioni preliminari di configurazione e di preparazione dell'infrastruttura:</span><span class="sxs-lookup"><span data-stu-id="750dc-105">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="750dc-106">Lo schema di Active Directory è esteso per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="750dc-106">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="750dc-107">La preparazione della foresta di Active Directory è stata completata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="750dc-107">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="750dc-108">La preparazione del dominio Active Directory è stata completata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="750dc-108">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="750dc-109">L'archivio di gestione centrale è stato installato e disponibile correttamente.</span><span class="sxs-lookup"><span data-stu-id="750dc-109">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="750dc-110">La topologia è stata creata e pubblicata tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="750dc-110">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="750dc-111">I server e i ruoli che richiedono i servizi Web sono stati definiti e distribuiti, inclusi front end server, server Standard Edition e Director.</span><span class="sxs-lookup"><span data-stu-id="750dc-111">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="750dc-112">Internet Information Services (IIS) è configurato e distribuito con i servizi ruolo consigliati per il supporto dei servizi Web in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="750dc-112">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="750dc-113">Dopo aver soddisfatto i prerequisiti, è necessario essere pronti a creare uno o più account per i servizi Web da utilizzare per l'autenticazione Kerberos per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="750dc-113">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="750dc-114">È necessario creare come minimo un account di autenticazione Kerberos per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="750dc-114">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="750dc-115">È tuttavia possibile creare un account per ogni sito per fornire l'autenticazione Kerberos locale nel sito.</span><span class="sxs-lookup"><span data-stu-id="750dc-115">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="750dc-116">È possibile specificare un solo account di autenticazione Kerberos per sito.</span><span class="sxs-lookup"><span data-stu-id="750dc-116">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

