---
title: 'Lync Server 2013: acquisizione di una posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e726424e9e24c223bc7e75346bd0c2188f29ee7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="00d82-102">Acquisizione di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00d82-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00d82-103">_**Ultimo argomento modificato:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="00d82-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="00d82-104">In una distribuzione di Lync Server 2013 E9-1-1, ogni client Lync o Lync Phone Edition connesso internamente acquisisce la propria posizione.</span><span class="sxs-lookup"><span data-stu-id="00d82-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="00d82-105">Dopo la registrazione SIP, il client fornisce tutte le informazioni di connettività di rete che conosce se stesso in una richiesta di percorso al servizio informazioni percorso, che è un servizio Web di cui è stato eseguito il backup da un database di SQL Server replicato.</span><span class="sxs-lookup"><span data-stu-id="00d82-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="00d82-106">Ogni pool di sito centrale dispone di un servizio informazioni percorso, che utilizza le informazioni di rete per eseguire una query sui record per un percorso corrispondente.</span><span class="sxs-lookup"><span data-stu-id="00d82-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="00d82-107">Se esiste una corrispondenza, il servizio informazioni percorso restituirà una posizione al client.</span><span class="sxs-lookup"><span data-stu-id="00d82-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="00d82-108">Se non viene trovata una corrispondenza, può venire richiesto all'utente di immettere manualmente una posizione (a seconda delle impostazioni dei criteri percorso).</span><span class="sxs-lookup"><span data-stu-id="00d82-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="00d82-109">I dati sulla posizione vengono trasmessi di nuovo al client in un formato XML basato su standard IETF (Internet Engineering Task Force) denominato PIDF-LO (Presence Information Data Format Location Object).</span><span class="sxs-lookup"><span data-stu-id="00d82-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="00d82-110">Il client di Lync Server include i dati di PIDF-LO nell'ambito di una chiamata di emergenza e questi dati vengono utilizzati dal provider di servizi E9-1-1 per determinare le PSAP appropriate e instradare la chiamata a tale PSAP insieme al ESQK corretto, che consente al dispatcher di PSAP di ottenere il posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="00d82-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="00d82-111">Nel diagramma seguente viene illustrato il modo in cui un client di Lync Server acquisisce una posizione (ad eccezione del metodo percorso basato sull'indirizzo MAC di terze parti):</span><span class="sxs-lookup"><span data-stu-id="00d82-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="00d82-112">![Modalità di acquisizione del diagramma di un percorso da parte del client](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Modalità di acquisizione del diagramma di un percorso da parte del client")</span><span class="sxs-lookup"><span data-stu-id="00d82-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="00d82-113">Per consentire a un client di acquisire una posizione, sono necessari i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="00d82-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="00d82-114">L'amministratore compila il database del servizio informazioni percorso con la rete wiremap (tabelle che mappano diversi tipi di indirizzi di rete ai corrispondenti percorsi di risposta alle emergenze (posizioni ERL)).</span><span class="sxs-lookup"><span data-stu-id="00d82-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="00d82-p102">Se si utilizza un provider di servizi E9-1-1 tramite trunk SIP, l'amministratore convalida le parti dell'indirizzo civico della posizione ERL in base a un database dello stradario generale gestito dal provider di servizi E9-1-1. Se si utilizza una gateway ELIN, l'amministratore verifica che i numeri ELIN vengano caricati dal gestore PSTN nel database ALI (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="00d82-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="00d82-117">Durante la registrazione o ogni volta che si verifica una modifica di rete, un client connesso internamente invia una richiesta di posizione contenente gli indirizzi di rete individuati del client al servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="00d82-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="00d82-118">Il servizio informazioni percorso esegue una query sui record pubblicati per una posizione e, se viene trovata una corrispondenza, restituisce gli oggetti di tipo PIDF-LO per il client in formato.</span><span class="sxs-lookup"><span data-stu-id="00d82-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

