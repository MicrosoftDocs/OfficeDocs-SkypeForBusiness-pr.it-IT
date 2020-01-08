---
title: "Lync Server 2013: Prerequisiti per abilitare l'autenticazione Kerberos"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="6121f-102">Prerequisiti per abilitare l'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6121f-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6121f-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6121f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6121f-104">Prima di abilitare l'autenticazione Kerberos, verificare di aver completato tutti i prerequisiti di configurazione e infrastruttura:</span><span class="sxs-lookup"><span data-stu-id="6121f-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="6121f-105">Lo schema di Active Directory è esteso per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6121f-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="6121f-106">La preparazione della foresta di Active Directory viene completata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6121f-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="6121f-107">La preparazione del dominio Active Directory viene completata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6121f-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="6121f-108">Central Management store è stato installato e disponibile correttamente.</span><span class="sxs-lookup"><span data-stu-id="6121f-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="6121f-109">La topologia è stata creata e pubblicata tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="6121f-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="6121f-110">I server e i ruoli che richiedono servizi Web sono stati definiti e distribuiti, inclusi i server front-end, i server Standard Edition e i direttori.</span><span class="sxs-lookup"><span data-stu-id="6121f-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="6121f-111">Internet Information Services (IIS) è configurato e distribuito con i servizi ruolo consigliati per supportare i servizi Web in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6121f-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="6121f-112">Dopo aver soddisfatto i prerequisiti, è necessario essere pronti per creare uno o più account per i servizi Web da usare per l'autenticazione Kerberos per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6121f-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="6121f-113">Devi almeno creare un account di autenticazione Kerberos per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="6121f-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="6121f-114">Puoi tuttavia creare un account per ogni sito per consentire l'autenticazione Kerberos locale nel sito.</span><span class="sxs-lookup"><span data-stu-id="6121f-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="6121f-115">È possibile specificare un solo account di autenticazione Kerberos per sito.</span><span class="sxs-lookup"><span data-stu-id="6121f-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

