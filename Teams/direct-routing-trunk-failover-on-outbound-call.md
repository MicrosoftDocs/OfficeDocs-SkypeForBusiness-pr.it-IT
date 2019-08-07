---
title: Failover trunk sulle chiamate in uscita
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Leggere questo argomento per informazioni su come gestire i failover trunk sulle chiamate in uscita da Teams a session border controller (SBC).
ms.openlocfilehash: 5c456aab52159859112b44c19c1b15fe81bc6293
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36183739"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="dcf5f-103">Failover trunk sulle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="dcf5f-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="dcf5f-104">Questo argomento descrive come evitare i failover trunk sulle chiamate in uscita, da Teams a session border controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="dcf5f-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="dcf5f-105">Failover sugli errori di rete</span><span class="sxs-lookup"><span data-stu-id="dcf5f-105">Failover on network errors</span></span>

<span data-ttu-id="dcf5f-106">Se non è possibile connettere un trunk per qualsiasi motivo, la connessione allo stesso trunk verrà provata da un Data Center Microsoft diverso.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="dcf5f-107">Un trunk potrebbe non essere connesso, ad esempio se è stata rifiutata una connessione, se è presente un timeout TLS o se sono presenti altri problemi relativi al livello di rete.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="dcf5f-108">Ad esempio, una connessione potrebbe non riuscire se un amministratore limita l'accesso a SBC solo da indirizzi IP noti, ma dimentica di inserire gli indirizzi IP di tutti i datacenter di routing Microsoft Direct nell'elenco di controllo di accesso (ACL) di SBC.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="dcf5f-109">Failover di codici SIP specifici ricevuti da Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="dcf5f-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="dcf5f-110">Se il routing diretto riceve qualsiasi codice di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="dcf5f-111">In uscita si intende una chiamata da un client teams alla rete PSTN (Public Switched Telephone Network) con il flusso di traffico seguente: teams client-> Direct routing-> SBC-> rete di telefonia.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="dcf5f-112">L'elenco dei codici SIP può essere trovato nella [RFC SIP (Session Initiation Protocol)](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="dcf5f-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="dcf5f-113">Si presuppone una situazione in cui un SBC ha risposto in un invito in arrivo con il codice "408 Request Timeout: il server non ha potuto produrre una risposta entro un periodo di tempo appropriato, ad esempio se non è in grado di determinare la posizione dell'utente nel tempo.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="dcf5f-114">Il client può ripetere la richiesta senza apportare modifiche in un secondo momento. "</span><span class="sxs-lookup"><span data-stu-id="dcf5f-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="dcf5f-115">Questo particolare SBC potrebbe avere difficoltà a connettersi al chiamato, magari a causa di una disconfigurazione della rete o di un altro errore.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="dcf5f-116">Tuttavia, c'è un altro SBC nella route che potrebbe essere in grado di raggiungere il chiamato.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="dcf5f-117">Nel diagramma seguente, quando un utente effettua una chiamata a un numero di telefono, esistono due SBCs nella route che possono potenzialmente recapitare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="dcf5f-118">Inizialmente, SBC1.contoso.com è selezionato per la chiamata, ma SBC1.contoso.com non è in grado di raggiungere una rete PTSN a causa di un problema di rete.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="dcf5f-119">Per impostazione predefinita, la chiamata verrà completata in questo momento.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagramma che mostra SBC che non riesce a raggiungere la rete PSTN a causa di un problema](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="dcf5f-121">Ma c'è un altro SBC nella route che può potenzialmente consegnare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="dcf5f-122">Se si configura il parametro `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, verrà provato il secondo SBC--SBC2.contoso.com nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="dcf5f-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagramma che mostra il routing per il secondo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="dcf5f-124">Impostando il parametro-FailoverResponseCodes e specificando i codici è possibile ottimizzare il routing ed evitare potenziali problemi quando un SBC non può effettuare una chiamata a causa di problemi di rete o altri.</span><span class="sxs-lookup"><span data-stu-id="dcf5f-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="dcf5f-125">Valori predefiniti: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="dcf5f-125">Default values:  408, 503, 504</span></span>

