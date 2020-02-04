---
title: 'Lync Server 2013: gestione delle posizioni per i provider di servizi trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ebc471459c8e406914f5a075d7e4cf8b69fadd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="5cf85-102">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cf85-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cf85-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5cf85-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5cf85-104">Per configurare Lync Server in modo da individuare automaticamente i client all'interno di una rete, è necessario popolare il database del servizio informazioni sulla posizione con una rete wiremap e pubblicare le posizioni oppure creare un collegamento a un database esterno che contiene già il corretto mapping.</span><span class="sxs-lookup"><span data-stu-id="5cf85-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="5cf85-105">Nell'ambito di questo processo devi convalidare gli indirizzi civici dei percorsi con il provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="5cf85-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="5cf85-106">Per informazioni dettagliate, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="5cf85-107">Il database del servizio informazioni sulla posizione viene compilato con un percorso di risposta di emergenza (elfi), che è costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio.</span><span class="sxs-lookup"><span data-stu-id="5cf85-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="5cf85-108">Il campo **percorso** del servizio informazioni posizione, ovvero la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi).</span><span class="sxs-lookup"><span data-stu-id="5cf85-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="5cf85-109">In tale lunghezza limitata, provare a includere le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cf85-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="5cf85-110">Un nome di facile comprensione che identifica la posizione del chiamante di 911 per evitare che i soccorritori di emergenza trovino la posizione specifica subito quando arrivano all'indirizzo civico.</span><span class="sxs-lookup"><span data-stu-id="5cf85-110">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="5cf85-111">Questo nome di posizione può includere un numero di edificio, un numero di piano, un designatore alare, un numero di camera e così via.</span><span class="sxs-lookup"><span data-stu-id="5cf85-111">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="5cf85-112">Evitare i soprannomi noti solo ai dipendenti, in modo che i soccorritori di emergenza possano accedere alla posizione errata.</span><span class="sxs-lookup"><span data-stu-id="5cf85-112">Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="5cf85-113">Un identificatore di posizione che consente agli utenti di vedere facilmente che il client Lync ha rilevato la posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="5cf85-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="5cf85-114">Il client Lync concatena automaticamente e visualizza la **posizione** e i campi della **città** individuati nella relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="5cf85-115">Una buona procedura consiste nell'aggiungere l'indirizzo di strada dell'edificio a ogni identificatore di posizione, ad esempio "numero \<\>civico 1 ° piano".</span><span class="sxs-lookup"><span data-stu-id="5cf85-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="5cf85-116">Senza l'indirizzo stradale, un identificatore di posizione generico come "primo piano" può essere applicato a qualsiasi edificio della città.</span><span class="sxs-lookup"><span data-stu-id="5cf85-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="5cf85-117">Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola Near, ad esempio "near 1 ° piano 1234".</span><span class="sxs-lookup"><span data-stu-id="5cf85-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5cf85-118">I percorsi aggiunti al database della posizione centrale non sono disponibili per il client finché non vengono pubblicati usando un comando Lync Server Management Shell e vengono replicati negli archivi locali del pool.</span><span class="sxs-lookup"><span data-stu-id="5cf85-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="5cf85-119">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database della posizione da Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="5cf85-120">Nelle sezioni seguenti vengono illustrate le considerazioni che è necessario tenere in considerazione durante la compilazione e la gestione del database della posizione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="5cf85-121">Popolamento del database della posizione</span><span class="sxs-lookup"><span data-stu-id="5cf85-121">Populating the Location Database</span></span>

<span data-ttu-id="5cf85-122">Le domande seguenti consentono di determinare come popolare il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="5cf85-123">**Quale processo verrà usato per popolare il database della posizione?**</span><span class="sxs-lookup"><span data-stu-id="5cf85-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="5cf85-124">Dove sono i dati e quali sono i passaggi da eseguire per convertire i dati nel formato richiesto dal database della posizione?</span><span class="sxs-lookup"><span data-stu-id="5cf85-124">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="5cf85-125">Si aggiungono percorsi singolarmente o in blocco usando un file CSV?</span><span class="sxs-lookup"><span data-stu-id="5cf85-125">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="5cf85-126">**Si dispone di un database di terze parti che contiene già una mappatura delle posizioni?**</span><span class="sxs-lookup"><span data-stu-id="5cf85-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="5cf85-127">Se si usa l'opzione del servizio informazioni posizione secondaria di Lync Server per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni usando una piattaforma offline.</span><span class="sxs-lookup"><span data-stu-id="5cf85-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="5cf85-128">Un vantaggio per questo approccio è che, oltre ad associare le posizioni agli identificatori di rete, è possibile associare le posizioni a un utente.</span><span class="sxs-lookup"><span data-stu-id="5cf85-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="5cf85-129">Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni posizione secondaria, a un client Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5cf85-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="5cf85-130">L'utente può quindi scegliere la posizione più appropriata.</span><span class="sxs-lookup"><span data-stu-id="5cf85-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="5cf85-131">Per l'integrazione con il servizio informazioni sulla posizione, il database di terze parti deve seguire lo schema di richiesta/risposta della posizione del server Lync.</span><span class="sxs-lookup"><span data-stu-id="5cf85-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="5cf85-132">Per informazioni dettagliate, vedere\["MS-\]E911WS: Web Service for E911 support Protocol Specification" <http://go.microsoft.com/fwlink/p/?linkid=213819>at.</span><span class="sxs-lookup"><span data-stu-id="5cf85-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="5cf85-133">Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sulla posizione secondaria, vedere [configurare un servizio informazioni sulla posizione secondaria in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="5cf85-134">Per informazioni dettagliate sulla compilazione del database della posizione, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="5cf85-135">Manutenzione del database della posizione</span><span class="sxs-lookup"><span data-stu-id="5cf85-135">Maintaining the Location Database</span></span>

<span data-ttu-id="5cf85-136">Dopo aver popolato il database della posizione, è necessario sviluppare una strategia per l'aggiornamento del database durante la modifica della configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="5cf85-136">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="5cf85-137">Le domande seguenti consentono di determinare come gestire il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="5cf85-137">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="5cf85-138">**Come si aggiorna il database della posizione?**</span><span class="sxs-lookup"><span data-stu-id="5cf85-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="5cf85-139">Sono disponibili diversi scenari che richiedono un aggiornamento per il database della posizione, tra cui l'aggiunta di WAP, il ricablaggio di Office (con le diverse assegnazioni degli switch) e l'espansione della subnet.</span><span class="sxs-lookup"><span data-stu-id="5cf85-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="5cf85-140">Si aggiorna direttamente ogni singola posizione o si esegue un aggiornamento in blocco di tutte le posizioni usando un file CSV?</span><span class="sxs-lookup"><span data-stu-id="5cf85-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="5cf85-141">**Si utilizzerà un'applicazione SNMP per corrispondere agli indirizzi MAC client di Lync alla porta e agli identificatori di switch?**</span><span class="sxs-lookup"><span data-stu-id="5cf85-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="5cf85-142">Se si usa un'applicazione SNMP, è necessario sviluppare un processo manuale che contenga la coerenza tra l'applicazione SNMP e il database della posizione e le informazioni sulla porta.</span><span class="sxs-lookup"><span data-stu-id="5cf85-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="5cf85-143">Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni sulla posizione non sarà in grado di restituire una posizione al client.</span><span class="sxs-lookup"><span data-stu-id="5cf85-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

