---
title: 'Lync Server 2013: Acquisizione di una posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="7aecf-102">Acquisizione di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aecf-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aecf-103">_**Argomento Ultima modifica:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7aecf-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7aecf-104">In una distribuzione di E9-1-1 di Lync Server 2013, ogni client Lync o Lync Phone Edition, connesso internamente, acquisisce la propria posizione.</span><span class="sxs-lookup"><span data-stu-id="7aecf-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="7aecf-105">Dopo la registrazione SIP, il client fornisce tutte le informazioni di connettività di rete che conosce da sola in una richiesta di posizione al servizio informazioni sulla posizione, un servizio Web supportato da un database di SQL Server replicato.</span><span class="sxs-lookup"><span data-stu-id="7aecf-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="7aecf-106">Ogni pool di sito centrale include un servizio di informazioni sulla posizione, che usa le informazioni di rete per eseguire query sui record per una posizione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7aecf-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="7aecf-107">Se c'è una corrispondenza, il servizio informazioni sulla posizione restituisce un percorso al client.</span><span class="sxs-lookup"><span data-stu-id="7aecf-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="7aecf-108">Se non è presente una corrispondenza, all'utente potrebbe essere richiesto di immettere manualmente una posizione (a seconda delle impostazioni dei criteri di posizione).</span><span class="sxs-lookup"><span data-stu-id="7aecf-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="7aecf-109">I dati della posizione vengono trasmessi al client in un formato XML standardizzato di Internet Engineering Task Force (IETF), denominato oggetto location Data Format Information (PIDF-LO).</span><span class="sxs-lookup"><span data-stu-id="7aecf-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="7aecf-110">Il client Lync Server include i dati di PIDF-LO come parte di una chiamata di emergenza e questi dati vengono usati dal provider di servizi E9-1-1 per determinare la PSAP appropriata e instradare la chiamata a tale PSAP insieme al ESQK corretto, che consente al dispatcher di PSAP di ottenere l' posizione del chiamante.</span><span class="sxs-lookup"><span data-stu-id="7aecf-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="7aecf-111">Il diagramma seguente mostra il modo in cui un client Lync Server acquisisce una posizione (ad eccezione del metodo di posizione basato su indirizzo MAC del client di terze parti):</span><span class="sxs-lookup"><span data-stu-id="7aecf-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="7aecf-112">![Come il client acquisisce un diagramma di posizione]in(images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "che modo il cliente acquisisce un diagramma di posizione")</span><span class="sxs-lookup"><span data-stu-id="7aecf-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="7aecf-113">Affinché un client acquisisca una posizione, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7aecf-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="7aecf-114">L'amministratore compila il database del servizio informazioni sulla posizione con il wiremap di rete (tabelle che mappano vari tipi di indirizzi di rete ai corrispondenti percorsi di risposta di emergenza (posizioni ERL)).</span><span class="sxs-lookup"><span data-stu-id="7aecf-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="7aecf-115">Se si usa un provider di servizi E9-1-1 trunk SIP, l'amministratore convalida le parti degli indirizzi civici di posizioni ERL in base a un database di stradario (Master Street Address Guide) gestito dal provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7aecf-115">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="7aecf-116">Se si usa un gateway ELIN, l'amministratore garantisce che il gestore PSTN carichi i numeri ELIN nel database ALI (Automatic Location Identification).</span><span class="sxs-lookup"><span data-stu-id="7aecf-116">If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="7aecf-117">Durante la registrazione o ogni volta che si verifica un cambiamento di rete, un client connesso internamente invia una richiesta di posizione che contiene gli indirizzi di rete individuati del client al servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="7aecf-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="7aecf-118">Il servizio informazioni sulla posizione esegue una query sui record pubblicati per una posizione e, se viene trovata una corrispondenza, restituisce gli elfi al client in formato PIDF-LO.</span><span class="sxs-lookup"><span data-stu-id="7aecf-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

