---
title: 'Lync Server 2013: Verificare la connettività per gli utenti esterni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1f8a9bbda54c596a9ccae8451b15ce7300bffd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="72015-102">Verificare la connettività per gli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72015-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72015-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="72015-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="72015-104">La convalida della connettività per gli utenti esterni richiede la garanzia della connettività degli utenti al server e alla porta per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="72015-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="72015-105">Una risorsa preziosa per confermare la configurazione e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari necessari per l'accesso degli utenti esterni è il sito dell'analizzatore connettività remota (<http://www.testocsconnectivity.com>).</span><span class="sxs-lookup"><span data-stu-id="72015-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="72015-106">Il sito viene gestito e mantenuto dal supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72015-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="72015-107">Per accedere all'analizzatore connettività remota, aprire il sito Web in un browser e seguire le istruzioni per selezionare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="72015-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="72015-108">Testare la connettività degli utenti esterni e dell'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="72015-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="72015-109">I test per l'accesso degli utenti esterni devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi uno o tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="72015-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="72015-110">Utenti di almeno un dominio federato e test di messaggistica istantanea, presenza, A/V e condivisione desktop.</span><span class="sxs-lookup"><span data-stu-id="72015-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="72015-111">Utenti di ogni provider di servizi di messaggistica istantanea pubblico supportato dall'organizzazione (e per il quale è stato completato il provisioning).</span><span class="sxs-lookup"><span data-stu-id="72015-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="72015-112">Utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="72015-112">Anonymous users.</span></span>

  - <span data-ttu-id="72015-113">Utenti all'interno dell'organizzazione che hanno effettuato l'accesso in Lync in remoto, ma non con VPN.</span><span class="sxs-lookup"><span data-stu-id="72015-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="72015-114">Questi test determinano se il server perimetrale è:</span><span class="sxs-lookup"><span data-stu-id="72015-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="72015-115">Ascolto sulle porte necessarie usando un client Telnet all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="72015-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="72015-116">Esempio: Telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="72015-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="72015-117">Eseguire il test precedente sulle porte in uso nel pool di Edge Server o Edge Server a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="72015-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="72015-118">Esecuzione di una risoluzione DNS esterna accurata.</span><span class="sxs-lookup"><span data-stu-id="72015-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="72015-119">Dall'esterno della rete eseguire il ping di ogni FQDN esterno del pool di Edge o Edge.</span><span class="sxs-lookup"><span data-stu-id="72015-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="72015-120">Anche se il ping non riesce, verranno visualizzati gli indirizzi IP, che è possibile confrontare con quelli assegnati.</span><span class="sxs-lookup"><span data-stu-id="72015-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

