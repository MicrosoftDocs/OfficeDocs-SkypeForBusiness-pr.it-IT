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
ms.openlocfilehash: 35c470b704e7467f573cd5e1fec03d63cf1f4b4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="ad9b6-102">Gestione delle posizioni per i gateway ELIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad9b6-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad9b6-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ad9b6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ad9b6-104">Affinché Lync Server fornisca automaticamente le posizioni per i client all'interno di una rete, è necessario eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad9b6-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="ad9b6-105">Popolare il database del servizio informazioni percorso con un wiremap di rete e includere i numeri di identificazione delle posizioni di emergenza (ELIN) nel campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="ad9b6-106">Pubblicare le posizioni in modo che siamo disponibili per i client nella rete.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="ad9b6-107">Caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="ad9b6-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="ad9b6-108">Per informazioni dettagliate su come eseguire queste attività, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad9b6-109">I percorsi aggiunti al database delle posizioni centrali non sono disponibili per il client finché non sono stati pubblicati utilizzando un comando di Lync Server Management Shell e vengono replicati negli archivi locali del pool.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="ad9b6-110">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database delle posizioni da Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="ad9b6-111">In questa sezione vengono descritti gli aspetti da prendere in considerazione quando si pianificano l'aggiornamento e la gestione del database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="ad9b6-112">Pianificazione delle posizioni di emergenza</span><span class="sxs-lookup"><span data-stu-id="ad9b6-112">Planning Emergency Locations</span></span>

<span data-ttu-id="ad9b6-113">Quando si utilizzano i gateway ELIN, è possibile popolare il database del servizio informazioni percorso con l'indirizzo civico, una posizione specifica all'interno di un edificio e almeno un ELIN per ogni percorso.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="ad9b6-114">Durante la fase di pianificazione, è opportuno decidere come denominare le posizioni e come assegnare i numeri ELIN.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="ad9b6-115">Pianificazione dei nomi delle posizioni</span><span class="sxs-lookup"><span data-stu-id="ad9b6-115">Planning Location Names</span></span>

<span data-ttu-id="ad9b6-116">Il campo percorso servizio **informazioni percorso,** che conserva la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi).</span><span class="sxs-lookup"><span data-stu-id="ad9b6-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="ad9b6-117">Tentare di includere gli elementi seguenti rispettando questi limiti di lunghezza:</span><span class="sxs-lookup"><span data-stu-id="ad9b6-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="ad9b6-p104">Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo civico. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, altrimenti si rischia che gli addetti del servizio di emergenza si rechino nel luogo sbagliato.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="ad9b6-121">Un identificatore di posizione che consenta agli utenti di verificare facilmente che il proprio client Lync abbia selezionato la posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="ad9b6-122">Il client Lync concatena e visualizza automaticamente i campi **Location** e **City** rilevati nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="ad9b6-123">Una buona procedura consiste nell'aggiungere l'indirizzo civico dell'edificio a ogni identificatore di posizione (ad esempio, "numero \<\>civico del primo piano").</span><span class="sxs-lookup"><span data-stu-id="ad9b6-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="ad9b6-124">Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="ad9b6-125">Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è consigliabile aggiungere la parola Near Near, ad esempio "Near 1° piano 1234".</span><span class="sxs-lookup"><span data-stu-id="ad9b6-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="ad9b6-126">Pianificazione dei numeri ELIN</span><span class="sxs-lookup"><span data-stu-id="ad9b6-126">Planning ELINs</span></span>

<span data-ttu-id="ad9b6-p106">Dopo aver stabilito come suddividere lo spazio dell'edificio in posizioni, è necessario decidere quanti numeri ELIN assegnare a ogni posizione. In un edificio a più piani o con più occupanti ad esempio è possibile assegnare alle diverse aree dell'edificio diverse zone di emergenza. In genere, ogni piano di un edificio viene designato come posizione. A ogni posizione vengono quindi assegnati uno o più numeri ELIN, utilizzati come numeri chiamanti durante una chiamata di emergenza. Contattare il gestore PSTN per conoscere i numeri di telefono che è possibile utilizzare come numeri ELIN. Nella tabella seguente sono illustrati alcuni esempi di posizioni per un indirizzo specifico.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="ad9b6-133">Posizioni e assegnazioni di numeri ELIN di esempio</span><span class="sxs-lookup"><span data-stu-id="ad9b6-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad9b6-134">Area dell'edificio</span><span class="sxs-lookup"><span data-stu-id="ad9b6-134">Building Area</span></span></th>
<th><span data-ttu-id="ad9b6-135">Posizione</span><span class="sxs-lookup"><span data-stu-id="ad9b6-135">Location</span></span></th>
<th><span data-ttu-id="ad9b6-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="ad9b6-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad9b6-137">Primo piano</span><span class="sxs-lookup"><span data-stu-id="ad9b6-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="ad9b6-138">1 </span><span class="sxs-lookup"><span data-stu-id="ad9b6-138">1</span></span></p></td>
<td><p><span data-ttu-id="ad9b6-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="ad9b6-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad9b6-140">Secondo piano</span><span class="sxs-lookup"><span data-stu-id="ad9b6-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="ad9b6-141">2 </span><span class="sxs-lookup"><span data-stu-id="ad9b6-141">2</span></span></p></td>
<td><p><span data-ttu-id="ad9b6-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="ad9b6-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad9b6-143">Terzo piano</span><span class="sxs-lookup"><span data-stu-id="ad9b6-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="ad9b6-144">3 </span><span class="sxs-lookup"><span data-stu-id="ad9b6-144">3</span></span></p></td>
<td><p><span data-ttu-id="ad9b6-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="ad9b6-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad9b6-146">Le posizioni definite devono soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad9b6-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="ad9b6-147">Essere conformi alle disposizioni locali e nazionali/regionali in termini di area massima per posizione e numero di posizioni per indirizzo.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="ad9b6-148">Essere sufficientemente specifiche da consentire di individuare senza difficoltà la persona che effettua la chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="ad9b6-149">Popolamento del database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="ad9b6-149">Populating the Location Database</span></span>

<span data-ttu-id="ad9b6-150">Le considerazioni seguenti possono essere utili per determinare come verrà popolato il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="ad9b6-151">**Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**</span><span class="sxs-lookup"><span data-stu-id="ad9b6-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="ad9b6-p107">Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="ad9b6-154">**Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**</span><span class="sxs-lookup"><span data-stu-id="ad9b6-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="ad9b6-155">Se si utilizza l'opzione servizio informazioni percorso secondario di Lync Server per la connessione a un database di terze parti, è possibile raggruppare e gestire percorsi tramite una piattaforma offline.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="ad9b6-156">Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="ad9b6-157">Questo significa che il servizio informazioni percorso può restituire più indirizzi, provenienti dal servizio informazioni percorso secondario, a un client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="ad9b6-158">L'utente può quindi scegliere la posizione più appropriata.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="ad9b6-159">Per l'integrazione con il servizio informazioni percorso, è necessario che il database di terze parti segua lo schema di richiesta/risposta percorso di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="ad9b6-160">Per informazioni dettagliate, <http://go.microsoft.com/fwlink/p/?linkid=213819>vedere.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="ad9b6-161">Per informazioni dettagliate sulla distribuzione di un servizio informazioni percorso secondario, vedere [Configure a Secondary Location Information Service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ad9b6-162">Per informazioni dettagliate sul popolamento del database delle posizioni, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="ad9b6-163">Gestione del database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="ad9b6-163">Maintaining the Location Database</span></span>

<span data-ttu-id="ad9b6-p110">Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="ad9b6-166">**Valutare come verrà aggiornato il database delle posizioni.**</span><span class="sxs-lookup"><span data-stu-id="ad9b6-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="ad9b6-p111">Esistono diversi scenari che richiedono un aggiornamento del database delle posizioni, tra cui l'aggiunta di punti di accesso wireless, il ricablaggio degli uffici (con assegnazioni diverse dei commutatori) e l'espansione delle subnet. Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="ad9b6-169">**Considerare se verrà utilizzata un'applicazione SNMP per creare una corrispondenza tra gli indirizzi MAC dei client Lync e gli identificatori di porte e commutatori,**</span><span class="sxs-lookup"><span data-stu-id="ad9b6-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="ad9b6-170">Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="ad9b6-171">Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire un percorso al client.</span><span class="sxs-lookup"><span data-stu-id="ad9b6-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

