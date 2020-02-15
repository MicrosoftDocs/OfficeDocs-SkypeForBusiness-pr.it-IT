---
title: 'Lync Server 2013: verificare la connettività per gli utenti esterni'
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
ms.openlocfilehash: 14d3dbc74119ff4f5669776dafce8a7cc2dee21a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="74cb0-102">Verificare la connettività per gli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74cb0-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cb0-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="74cb0-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="74cb0-104">La convalida della connettività per gli utenti esterni garantisce la connettività dagli utenti al server e alla porta per il servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="74cb0-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="74cb0-105">Una risorsa importante per confermare la configurazione e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari necessari per l'accesso degli utenti esterni è il sito analizzatore connettività<http://www.testocsconnectivity.com>remota ().</span><span class="sxs-lookup"><span data-stu-id="74cb0-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="74cb0-106">Il sito è gestito e mantenuto dal supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74cb0-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="74cb0-107">Per accedere a Remote Connectivity Analyzer, aprire il sito Web in un browser e seguire le istruzioni per selezionare lo scenario.</span><span class="sxs-lookup"><span data-stu-id="74cb0-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="74cb0-108">Testare la connettività degli utenti esterni e l'accesso esterno</span><span class="sxs-lookup"><span data-stu-id="74cb0-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="74cb0-109">I test per l'accesso utente esterno devono includere ogni tipo di utente esterno supportato dall'organizzazione, inclusi alcuni o tutti quelli indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="74cb0-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="74cb0-110">Utenti da almeno un dominio federato, con testing di messaggistica istantanea, presenza, audio/video e condivisione del desktop.</span><span class="sxs-lookup"><span data-stu-id="74cb0-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="74cb0-111">Utenti di ogni provider di servizi di messaggistica istantanea pubblica supportati dall'organizzazione e per i quali è stato completato il provisioning.</span><span class="sxs-lookup"><span data-stu-id="74cb0-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="74cb0-112">Utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="74cb0-112">Anonymous users.</span></span>

  - <span data-ttu-id="74cb0-113">Utenti nell'organizzazione connessi a Lync in remoto, ma che non utilizzano una rete VPN.</span><span class="sxs-lookup"><span data-stu-id="74cb0-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="74cb0-114">Questi test determinano se il server perimetrale:</span><span class="sxs-lookup"><span data-stu-id="74cb0-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="74cb0-115">È in attesa sulle porte necessarie tramite un client telnet dall'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="74cb0-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="74cb0-116">Esempio: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="74cb0-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="74cb0-117">Eseguire il test precedente sulle porte utilizzate nel server perimetrale o nel pool di server perimetrali, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="74cb0-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="74cb0-118">Esegue la risoluzione DNS esterna in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="74cb0-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="74cb0-p102">Dall'esterno della rete, eseguire il ping di ognuno degli FQDN esterni del server perimetrale o del pool di server perimetrali. Anche se il ping non riesce verranno visualizzati gli indirizzi IP, confrontabili con quelli assegnati.</span><span class="sxs-lookup"><span data-stu-id="74cb0-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

