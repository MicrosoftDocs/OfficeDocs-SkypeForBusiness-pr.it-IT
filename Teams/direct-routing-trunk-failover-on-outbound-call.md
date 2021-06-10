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
description: Leggere questo argomento per informazioni su come gestire i failover trunk sulle chiamate in uscita Teams al session border controller (SBC).
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836178"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="aef03-103">Failover trunk sulle chiamate in uscita</span><span class="sxs-lookup"><span data-stu-id="aef03-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="aef03-104">Questo argomento descrive come evitare il failover trunk sulle chiamate in uscita, dal Teams al Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="aef03-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="aef03-105">Errori di failover in rete</span><span class="sxs-lookup"><span data-stu-id="aef03-105">Failover on network errors</span></span>

<span data-ttu-id="aef03-106">Se non è possibile connettersi a un trunk per qualsiasi motivo, la connessione allo stesso trunk verrà provata da un altro data center Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aef03-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="aef03-107">Un trunk potrebbe non essere connesso, ad esempio se una connessione viene rifiutata, se c'è un timeout TLS o se ci sono altri problemi a livello di rete.</span><span class="sxs-lookup"><span data-stu-id="aef03-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="aef03-108">Ad esempio, una connessione potrebbe non riuscire se un amministratore limita l'accesso al database SBC solo da indirizzi IP noti, ma dimentica di inserire gli indirizzi IP di tutti i data center di Routing diretto Microsoft nell'elenco di controllo di accesso (ACL) del database SBC.</span><span class="sxs-lookup"><span data-stu-id="aef03-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="aef03-109">Failover di codici SIP specifici ricevuti da Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="aef03-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="aef03-110">Se Routing diretto riceve codici di errore SIP 4xx o 6xx in risposta a un invito in uscita, la chiamata viene considerata completata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="aef03-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="aef03-111">In uscita si intende una chiamata da un client Teams alla rete PSTN (Public Switched Telephone Network) con il flusso di traffico seguente: Teams Client -> Direct Routing -> SBC -> Telephony network.</span><span class="sxs-lookup"><span data-stu-id="aef03-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="aef03-112">L'elenco dei codici SIP è disponibile in [SESSION Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span><span class="sxs-lookup"><span data-stu-id="aef03-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="aef03-113">Si supponga una situazione in cui un SBC ha risposto a un invito in arrivo con il codice "408 Request Timeout: Il server non è stato in grado di produrre una risposta entro un periodo di tempo adeguato, ad esempio se non è stato in grado di determinare la posizione dell'utente in tempo.</span><span class="sxs-lookup"><span data-stu-id="aef03-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="aef03-114">Il client può ripetere la richiesta senza modifiche in un secondo momento".</span><span class="sxs-lookup"><span data-stu-id="aef03-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="aef03-115">Questo particolare SBC potrebbe avere difficoltà a connettersi al chiamato, ad esempio a causa di una configurazione errata della rete o di un altro errore.</span><span class="sxs-lookup"><span data-stu-id="aef03-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="aef03-116">Tuttavia, c'è un altro SBC nel percorso che potrebbe essere in grado di raggiungere il chiamato.</span><span class="sxs-lookup"><span data-stu-id="aef03-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="aef03-117">Nel diagramma seguente, quando un utente effettua una chiamata a un numero di telefono, nel percorso sono presenti due SBC che possono potenzialmente recapitare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aef03-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="aef03-118">Inizialmente, SBC1.contoso.com per la chiamata, ma SBC1.contoso.com non è in grado di raggiungere una rete PTSN a causa di un problema di rete.</span><span class="sxs-lookup"><span data-stu-id="aef03-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="aef03-119">Per impostazione predefinita, la chiamata verrà completata in questo momento.</span><span class="sxs-lookup"><span data-stu-id="aef03-119">By default, the call will be completed at this moment.</span></span> 
 
![Diagramma che mostra che SBC non riesce a raggiungere PSTN a causa di un problema di rete](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="aef03-121">Ma c'è un altro SBC nel percorso che potenzialmente può recapitare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="aef03-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="aef03-122">Se si configura il parametro , verrà provato il secondo `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC, SBC2.contoso.com nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="aef03-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![Diagramma che mostra il routing al secondo SBC](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="aef03-124">L'impostazione del parametro -FailoverResponseCodes e la specifica dei codici consentono di ottimizzare il routing ed evitare potenziali problemi quando un SBC non può effettuare una chiamata a causa di problemi di rete o di altro tipo.</span><span class="sxs-lookup"><span data-stu-id="aef03-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="aef03-125">Valori predefiniti: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="aef03-125">Default values:  408, 503, 504</span></span>

