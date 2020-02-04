---
title: 'Lync Server 2013: gestione delle posizioni per i gateway ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="b35b6-102">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b35b6-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b35b6-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b35b6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b35b6-104">Per consentire a Lync Server di specificare automaticamente le posizioni per i client all'interno di una rete, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="b35b6-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="b35b6-105">Compilare il database del servizio informazioni sulla posizione con un wiremap di rete e includere i numeri di identificazione della posizione di emergenza (ELINs) nel campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="b35b6-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="b35b6-106">Pubblicare i percorsi in modo che siano disponibili per i client della rete.</span><span class="sxs-lookup"><span data-stu-id="b35b6-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="b35b6-107">Caricare il numero ELINs nel database di identificazione automatica della posizione del vettore (PSTN) del gestore della rete telefonica pubblica.</span><span class="sxs-lookup"><span data-stu-id="b35b6-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="b35b6-108">Per informazioni dettagliate su come eseguire queste attività, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b35b6-109">I percorsi aggiunti al database della posizione centrale non sono disponibili per il client finché non sono stati pubblicati usando un comando Lync Server Management Shell e vengono replicati negli archivi locali del pool.</span><span class="sxs-lookup"><span data-stu-id="b35b6-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="b35b6-110">Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database della posizione da Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="b35b6-111">Questa sezione descrive le informazioni da considerare quando si prevede di aggiornare e gestire il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="b35b6-112">Pianificazione delle posizioni di emergenza</span><span class="sxs-lookup"><span data-stu-id="b35b6-112">Planning Emergency Locations</span></span>

<span data-ttu-id="b35b6-113">Quando si usano i gateway ELIN, si popola il database del servizio informazioni sulla posizione con l'indirizzo civico, una posizione specifica all'interno di un edificio e almeno un ELIN per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="b35b6-114">Durante la fase di pianificazione, è consigliabile decidere come assegnare un nome alle posizioni e come assegnarle.</span><span class="sxs-lookup"><span data-stu-id="b35b6-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="b35b6-115">Pianificazione dei nomi delle posizioni</span><span class="sxs-lookup"><span data-stu-id="b35b6-115">Planning Location Names</span></span>

<span data-ttu-id="b35b6-116">Il campo **percorso** del servizio informazioni posizione, che contiene la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi).</span><span class="sxs-lookup"><span data-stu-id="b35b6-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="b35b6-117">In tale lunghezza limitata, provare a includere le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b35b6-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="b35b6-118">Un nome di facile comprensione che identifica la posizione del chiamante di 911 per evitare che i soccorritori di emergenza trovino la posizione specifica subito quando arrivano all'indirizzo civico.</span><span class="sxs-lookup"><span data-stu-id="b35b6-118">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address.</span></span> <span data-ttu-id="b35b6-119">Questo nome di posizione può includere un numero di edificio, un numero di piano, un designatore alare, un numero di camera e così via.</span><span class="sxs-lookup"><span data-stu-id="b35b6-119">This location name may include a building number, floor number, wing designator, room number, and so on.</span></span> <span data-ttu-id="b35b6-120">Evitare i soprannomi noti solo ai dipendenti, in modo che i soccorritori di emergenza possano accedere alla posizione errata.</span><span class="sxs-lookup"><span data-stu-id="b35b6-120">Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="b35b6-121">Un identificatore di posizione che consente agli utenti di vedere facilmente che il client Lync ha rilevato la posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="b35b6-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="b35b6-122">Il client Lync concatena automaticamente e visualizza la **posizione** e i campi della **città** individuati nella relativa intestazione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="b35b6-123">Una buona procedura consiste nell'aggiungere l'indirizzo di strada dell'edificio a ogni identificatore di posizione, ad esempio "numero \<\>civico 1 ° piano".</span><span class="sxs-lookup"><span data-stu-id="b35b6-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="b35b6-124">Senza l'indirizzo stradale, un identificatore di posizione generico come "primo piano" può essere applicato a qualsiasi edificio della città.</span><span class="sxs-lookup"><span data-stu-id="b35b6-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="b35b6-125">Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è consigliabile aggiungere la parola Near, ad esempio "near 1 ° piano 1234".</span><span class="sxs-lookup"><span data-stu-id="b35b6-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="b35b6-126">Pianificazione di ELINs</span><span class="sxs-lookup"><span data-stu-id="b35b6-126">Planning ELINs</span></span>

<span data-ttu-id="b35b6-127">Dopo aver deciso in che modo si vuole dividere lo spazio per l'edificio in posizioni, è necessario decidere il numero di ELIN da assegnare a ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-127">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location.</span></span> <span data-ttu-id="b35b6-128">Ad esempio, in un edificio multipiano o multitenant, è possibile assegnare aree di emergenza diverse nell'edificio.</span><span class="sxs-lookup"><span data-stu-id="b35b6-128">For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones.</span></span> <span data-ttu-id="b35b6-129">In genere, ogni piano di un edificio viene designato come posizione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-129">Typically, each floor in a building is designated as a location.</span></span> <span data-ttu-id="b35b6-130">A ogni posizione viene quindi assegnato uno o più ELIN, che vengono usati come numeri di chiamata durante una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b35b6-130">Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call.</span></span> <span data-ttu-id="b35b6-131">Contattare il gestore PSTN per i numeri di telefono che è possibile usare per gli ELIN.</span><span class="sxs-lookup"><span data-stu-id="b35b6-131">Contact your PSTN carrier for phone numbers that you can use for ELINs.</span></span> <span data-ttu-id="b35b6-132">La tabella seguente contiene un esempio di posizioni per un indirizzo di strada specifico.</span><span class="sxs-lookup"><span data-stu-id="b35b6-132">The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="b35b6-133">Posizione di esempio e assegnazioni ELIN</span><span class="sxs-lookup"><span data-stu-id="b35b6-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b35b6-134">Area edifici</span><span class="sxs-lookup"><span data-stu-id="b35b6-134">Building Area</span></span></th>
<th><span data-ttu-id="b35b6-135">Posizione</span><span class="sxs-lookup"><span data-stu-id="b35b6-135">Location</span></span></th>
<th><span data-ttu-id="b35b6-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="b35b6-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b35b6-137">Primo piano</span><span class="sxs-lookup"><span data-stu-id="b35b6-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="b35b6-138">1</span><span class="sxs-lookup"><span data-stu-id="b35b6-138">1</span></span></p></td>
<td><p><span data-ttu-id="b35b6-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="b35b6-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b35b6-140">Secondo piano</span><span class="sxs-lookup"><span data-stu-id="b35b6-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="b35b6-141">2</span><span class="sxs-lookup"><span data-stu-id="b35b6-141">2</span></span></p></td>
<td><p><span data-ttu-id="b35b6-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="b35b6-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b35b6-143">Terzo piano</span><span class="sxs-lookup"><span data-stu-id="b35b6-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="b35b6-144">3</span><span class="sxs-lookup"><span data-stu-id="b35b6-144">3</span></span></p></td>
<td><p><span data-ttu-id="b35b6-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="b35b6-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b35b6-146">I percorsi definiti devono soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b35b6-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="b35b6-147">Rispettare le normative locali e nazionali/regionali in termini di area massima per località e numero di posizioni per indirizzo stradale.</span><span class="sxs-lookup"><span data-stu-id="b35b6-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="b35b6-148">Sono sufficientemente specifici per facilitare l'individuazione del chiamante di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b35b6-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="b35b6-149">Popolamento del database della posizione</span><span class="sxs-lookup"><span data-stu-id="b35b6-149">Populating the Location Database</span></span>

<span data-ttu-id="b35b6-150">Le domande seguenti consentiranno di determinare come popolare il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="b35b6-151">**Quale processo verrà usato per popolare il database della posizione?**</span><span class="sxs-lookup"><span data-stu-id="b35b6-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="b35b6-152">Dove sono i dati e quali sono i passaggi da eseguire per convertire i dati nel formato richiesto dal database della posizione?</span><span class="sxs-lookup"><span data-stu-id="b35b6-152">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database?</span></span> <span data-ttu-id="b35b6-153">Si aggiungono percorsi singolarmente o in blocco usando un file CSV?</span><span class="sxs-lookup"><span data-stu-id="b35b6-153">Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="b35b6-154">**Si dispone di un database di terze parti che contiene già una mappatura delle posizioni?**</span><span class="sxs-lookup"><span data-stu-id="b35b6-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="b35b6-155">Se si usa l'opzione del servizio informazioni posizione secondaria di Lync Server per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni usando una piattaforma offline.</span><span class="sxs-lookup"><span data-stu-id="b35b6-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="b35b6-156">Un vantaggio per questo approccio è che, oltre ad associare le posizioni agli identificatori di rete, è possibile associare le posizioni a un utente.</span><span class="sxs-lookup"><span data-stu-id="b35b6-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="b35b6-157">Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni posizione secondaria, a un client Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b35b6-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="b35b6-158">L'utente può quindi scegliere la posizione più appropriata.</span><span class="sxs-lookup"><span data-stu-id="b35b6-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="b35b6-159">Per l'integrazione con il servizio informazioni sulla posizione, il database di terze parti deve seguire lo schema di richiesta/risposta della posizione del server Lync.</span><span class="sxs-lookup"><span data-stu-id="b35b6-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="b35b6-160">Per informazioni dettagliate, <http://go.microsoft.com/fwlink/p/?linkid=213819>vedere.</span><span class="sxs-lookup"><span data-stu-id="b35b6-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="b35b6-161">Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sulla posizione secondaria, vedere [configurare un servizio informazioni sulla posizione secondaria in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b35b6-162">Per informazioni dettagliate sulla compilazione del database della posizione, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="b35b6-163">Manutenzione del database della posizione</span><span class="sxs-lookup"><span data-stu-id="b35b6-163">Maintaining the Location Database</span></span>

<span data-ttu-id="b35b6-164">Dopo aver popolato il database della posizione, è necessario sviluppare una strategia per l'aggiornamento del database durante la modifica della configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="b35b6-164">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes.</span></span> <span data-ttu-id="b35b6-165">Le domande seguenti consentono di determinare come gestire il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="b35b6-165">The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="b35b6-166">**Come si aggiorna il database della posizione?**</span><span class="sxs-lookup"><span data-stu-id="b35b6-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="b35b6-167">Esistono diversi scenari che richiedono un aggiornamento al database della posizione, tra cui l'aggiunta di punti di accesso wireless (WAP), il ricablaggio di Office (con le diverse assegnazioni di switch) e l'espansione della subnet.</span><span class="sxs-lookup"><span data-stu-id="b35b6-167">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="b35b6-168">Si aggiorna direttamente ogni singola posizione o si esegue un aggiornamento in blocco di tutte le posizioni usando un file CSV?</span><span class="sxs-lookup"><span data-stu-id="b35b6-168">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="b35b6-169">**Si utilizzerà un'applicazione SNMP per corrispondere agli indirizzi MAC client di Lync alla porta e agli identificatori di switch?**</span><span class="sxs-lookup"><span data-stu-id="b35b6-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="b35b6-170">Se si usa un'applicazione SNMP, è necessario sviluppare un processo manuale che contenga la coerenza tra l'applicazione SNMP e il database della posizione e le informazioni sulla porta.</span><span class="sxs-lookup"><span data-stu-id="b35b6-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="b35b6-171">Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni sulla posizione non sarà in grado di restituire una posizione al client.</span><span class="sxs-lookup"><span data-stu-id="b35b6-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

