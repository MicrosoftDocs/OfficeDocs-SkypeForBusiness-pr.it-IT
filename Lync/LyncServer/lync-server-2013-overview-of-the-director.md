---
title: 'Lync Server 2013: Panoramica del Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cf4e40f211cb992e914be20dc9962d55f229bc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="49a64-102">Panoramica del Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49a64-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49a64-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="49a64-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="49a64-104">Un Director è un server che esegue Lync Server 2013 che autentica le richieste degli utenti, ma non ospita account utente.</span><span class="sxs-lookup"><span data-stu-id="49a64-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="49a64-105">È facoltativamente possibile distribuire un Director nei due scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="49a64-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="49a64-106">Se si Abilita l'accesso da parte di utenti esterni tramite la distribuzione di server perimetrali, è necessario distribuire anche un Director.</span><span class="sxs-lookup"><span data-stu-id="49a64-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="49a64-107">In questo scenario, il Director esegue l'autenticazione degli utenti esterni e quindi passa il traffico ai server interni.</span><span class="sxs-lookup"><span data-stu-id="49a64-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="49a64-108">Quando un amministratore viene utilizzato per autenticare gli utenti esterni, allevia i server del pool Front end dall'overhead dell'esecuzione dell'autenticazione di tali utenti.</span><span class="sxs-lookup"><span data-stu-id="49a64-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="49a64-109">Consente inoltre di isolare i pool Front end interni da traffico dannoso, ad esempio attacchi Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="49a64-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="49a64-110">Se la rete è inondata da traffico esterno non valido durante un attacco di questo tipo, il traffico termina nel Director.</span><span class="sxs-lookup"><span data-stu-id="49a64-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="49a64-111">Se si distribuiscono più pool Front end in un sito centrale, aggiungendo un Director al sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="49a64-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="49a64-112">In questo scenario, tutte le richieste passano prima al server Director, che le instrada al pool Front end corretto.</span><span class="sxs-lookup"><span data-stu-id="49a64-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

