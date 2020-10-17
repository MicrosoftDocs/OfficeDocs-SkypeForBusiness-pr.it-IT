---
title: 'Lync Server 2013: configurazione del Director'
description: 'Lync Server 2013: configurazione del Director.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b917000dec6d30fdec2963ff1e464fbb9a70805
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554112"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="856e9-103">Configurazione del Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856e9-103">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="856e9-104">_**Ultimo argomento modificato:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="856e9-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="856e9-105">Se si Abilita l'accesso per gli utenti esterni tramite la distribuzione di server perimetrali, è possibile distribuire un Director.</span><span class="sxs-lookup"><span data-stu-id="856e9-105">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="856e9-106">Un Director è un server che esegue Microsoft Lync Server 2013 che autentica le richieste degli utenti, ma non ospita gli account utente.</span><span class="sxs-lookup"><span data-stu-id="856e9-106">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="856e9-107">A questo punto, non si tratta di un requisito, ma è molto utile se si è preoccupati per le prestazioni e si desidera semplificare le richieste di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="856e9-107">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="856e9-108">Se si decide che è una buona idea per la propria organizzazione, la procedura per configurare un server Director o un pool di Director è simile alla configurazione di un pool Enterprise Edition front end o di uno Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="856e9-108">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="856e9-109">Dopo aver definito i Director (s) in Generatore di topologie, è necessario eseguire i passaggi illustrati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="856e9-109">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="856e9-110">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="856e9-110">In This Section</span></span>

  - [<span data-ttu-id="856e9-111">Installare l'archivio di configurazione locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856e9-111">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="856e9-112">Installare Lync Server 2013 nel server Director</span><span class="sxs-lookup"><span data-stu-id="856e9-112">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="856e9-113">Configurare i certificati per il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856e9-113">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="856e9-114">Avviare i servizi nel server Director in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="856e9-114">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="856e9-115">Testare il Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856e9-115">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="856e9-116">Configurare Sign-In automatici dei client per l'utilizzo del server Director in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="856e9-116">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

