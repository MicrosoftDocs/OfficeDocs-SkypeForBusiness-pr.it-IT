---
title: 'Lync Server 2013: Configurazione del server Director'
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
ms.openlocfilehash: 58d0b309e87dddb621d6c3a90b16b6c2e02845df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="7ab41-102">Configurazione del server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ab41-102">Setting up the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ab41-103">_**Argomento Ultima modifica:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="7ab41-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="7ab41-104">Se si Abilita l'accesso per gli utenti esterni distribuendo Edge Server, un'opzione consiste nel distribuire un Director.</span><span class="sxs-lookup"><span data-stu-id="7ab41-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="7ab41-105">Un amministratore è un server che esegue Microsoft Lync Server 2013 che autentica le richieste degli utenti, ma non ospita gli account utente.</span><span class="sxs-lookup"><span data-stu-id="7ab41-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="7ab41-106">Ora, questo non è un requisito, ma è molto utile se si è preoccupati per le prestazioni e si vuole semplificare la semplificazione delle richieste di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="7ab41-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="7ab41-107">Se si decide che questa è una buona idea per l'organizzazione, la procedura per configurare un pool di Director o Director è simile alla configurazione di un pool Enterprise Edition front-end o di un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="7ab41-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="7ab41-108">Dopo aver definito il Director o i direttori in Generatore di topologie, è necessario eseguire i passaggi descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="7ab41-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ab41-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7ab41-109">In This Section</span></span>

  - [<span data-ttu-id="7ab41-110">Installare l'archivio di configurazione locale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ab41-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="7ab41-111">Installare Lync Server 2013 nel server Director</span><span class="sxs-lookup"><span data-stu-id="7ab41-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="7ab41-112">Configurare i certificati per il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ab41-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="7ab41-113">Avviare servizi nel server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ab41-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="7ab41-114">Testare il server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ab41-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="7ab41-115">Configurare l'accesso automatico dei client per l'utilizzo del server Director in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ab41-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

