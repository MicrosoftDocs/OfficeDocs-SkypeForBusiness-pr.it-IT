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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leggere questo argomento per informazioni su come gestire il failover trunk sulle chiamate in uscita da Teams al controller dei confini della sessione (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836178"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="721d6-103">Failover trunk sulle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="721d6-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="721d6-104">Questo argomento descrive come evitare il failover trunk sulle chiamate in uscita, da Teams al controller dei confini della sessione (SBC).</span><span class="sxs-lookup"><span data-stu-id="721d6-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="721d6-105">Failover sugli errori di rete</span><span class="sxs-lookup"><span data-stu-id="721d6-105">Failover on network errors</span></span>

<span data-ttu-id="721d6-106">Se non è possibile connettersi a un trunk per qualsiasi motivo, la connessione allo stesso trunk verrà provata da un data center Microsoft diverso.</span><span class="sxs-lookup"><span data-stu-id="721d6-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="721d6-107">Un trunk potrebbe non essere connesso, ad esempio se una connessione viene rifiutata, se c'è un timeout TLS o se ci sono altri problemi a livello di rete.</span><span class="sxs-lookup"><span data-stu-id="721d6-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="721d6-108">Ad esempio, una connessione potrebbe non riuscire se un amministratore limita l'accesso a SBC solo da indirizzi IP noti, dimenticando di inserire gli indirizzi IP di tutti i data center microsoft Direct Routing nell'elenco di controllo di accesso (ACL) del database SBC.</span><span class="sxs-lookup"><span data-stu-id="721d6-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="721d6-109">Failover di codici SIP specifici ricevuti dal controller dei confini della sessione (SBC)</span><span class="sxs-lookup"><span data-stu-id="721d6-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="721d6-110">Se l'instradamento diretto riceve codici di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="721d6-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="721d6-111">In uscita significa una chiamata da un client di Teams alla rete PSTN (Public Switched Telephone Network) con il flusso di traffico seguente: Client Teams -> Direct Routing -> SBC -> Telephony network.</span><span class="sxs-lookup"><span data-stu-id="721d6-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="721d6-112">L'elenco dei codici SIP è disponibile in [RFC (Session Initiation Protocol) (SIP).](https://tools.ietf.org/html/rfc3261)</span><span class="sxs-lookup"><span data-stu-id="721d6-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="721d6-113">Si supponga che un database SBC ha risposto a un invito in arrivo con codice "Timeout richiesta 408: il server non è stato in grado di produrre una risposta entro un periodo di tempo appropriato, ad esempio se non è stato possibile determinare la posizione dell'utente in tempo.</span><span class="sxs-lookup"><span data-stu-id="721d6-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="721d6-114">Il client POTREBBE ripetere la richiesta senza modifiche in qualsiasi momento."</span><span class="sxs-lookup"><span data-stu-id="721d6-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="721d6-115">Questo particolare SBC potrebbe avere difficoltà a connettersi al chiamato, ad esempio a causa di una configurazione errata della rete o di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="721d6-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="721d6-116">Tuttavia, nel percorso è presente un altro SBC che potrebbe essere in grado di raggiungere il chiamato.</span><span class="sxs-lookup"><span data-stu-id="721d6-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="721d6-117">Nel diagramma seguente, quando un utente effettua una chiamata a un numero di telefono, nel percorso sono presenti due SBC che potrebbero recapitare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="721d6-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="721d6-118">Inizialmente, SBC1.contoso.com è selezionata per la chiamata, ma SBC1.contoso.com non è in grado di raggiungere una rete PTSN a causa di un problema di rete.</span><span class="sxs-lookup"><span data-stu-id="721d6-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="721d6-119">Per impostazione predefinita, la chiamata verrà completata in questo momento.</span><span class="sxs-lookup"><span data-stu-id="721d6-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagramma che mostra che SBC non riesce a raggiungere PSTN a causa di un problema di rete](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="721d6-121">Ma c'è un altro SBC nel percorso che potenzialmente può recapitare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="721d6-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="721d6-122">Se si configura il parametro, verrà provato il secondo `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC, SBC2.contoso.com nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="721d6-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagramma che mostra il routing al secondo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="721d6-124">L'impostazione del parametro -FailoverResponseCodes e l'impostazione dei codici consente di ottimizzare il routing ed evitare potenziali problemi quando un servizio SBC non può effettuare una chiamata a causa di problemi di rete o di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="721d6-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="721d6-125">Valori predefiniti: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="721d6-125">Default values:  408, 503, 504</span></span>

