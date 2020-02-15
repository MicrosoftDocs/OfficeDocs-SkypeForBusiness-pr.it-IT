---
title: "Lync Server 2013: prerequisiti per l'abilitazione dell'autenticazione Kerberos"
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
ms.openlocfilehash: ecbba3403024663e529cef7653b310148faa2e2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="8b757-102">Prerequisiti per l'abilitazione dell'autenticazione Kerberos in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b757-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b757-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8b757-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8b757-104">Prima di abilitare l'autenticazione Kerberos, accertarsi di aver completato tutte le operazioni preliminari di configurazione e di preparazione dell'infrastruttura:</span><span class="sxs-lookup"><span data-stu-id="8b757-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="8b757-105">Lo schema di Active Directory è esteso per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b757-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="8b757-106">La preparazione della foresta di Active Directory è stata completata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b757-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="8b757-107">La preparazione del dominio Active Directory è stata completata per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b757-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="8b757-108">L'archivio di gestione centrale è stato installato e disponibile correttamente.</span><span class="sxs-lookup"><span data-stu-id="8b757-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="8b757-109">La topologia è stata creata e pubblicata tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="8b757-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="8b757-110">I server e i ruoli che richiedono i servizi Web sono stati definiti e distribuiti, inclusi front end server, server Standard Edition e Director.</span><span class="sxs-lookup"><span data-stu-id="8b757-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="8b757-111">Internet Information Services (IIS) è configurato e distribuito con i servizi ruolo consigliati per il supporto dei servizi Web in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b757-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="8b757-112">Dopo aver soddisfatto i prerequisiti, è necessario essere pronti a creare uno o più account per i servizi Web da utilizzare per l'autenticazione Kerberos per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8b757-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="8b757-113">È necessario creare come minimo un account di autenticazione Kerberos per ogni distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8b757-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="8b757-114">È tuttavia possibile creare un account per ogni sito per fornire l'autenticazione Kerberos locale nel sito.</span><span class="sxs-lookup"><span data-stu-id="8b757-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="8b757-115">È possibile specificare un solo account di autenticazione Kerberos per sito.</span><span class="sxs-lookup"><span data-stu-id="8b757-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

