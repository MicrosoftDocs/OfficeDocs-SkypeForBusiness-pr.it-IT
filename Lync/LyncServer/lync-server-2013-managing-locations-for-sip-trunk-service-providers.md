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
ms.openlocfilehash: f27eeac11006eab2209bb5491d991a677e3a2887
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="0b7ca-102">Gestione delle posizioni per i provider di servizi trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b7ca-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b7ca-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0b7ca-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0b7ca-104">Per configurare Lync Server per l'individuazione automatica dei client all'interno di una rete, è necessario popolare il database del servizio informazioni percorso con una rete wiremap e pubblicare i percorsi oppure collegarsi a un database esterno che già contiene la corretta mapping.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="0b7ca-105">Come parte di questo processo, è necessario convalidare gli indirizzi civici dei percorsi con il provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="0b7ca-106">Per ulteriori informazioni, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0b7ca-107">È possibile popolare il database del servizio informazioni percorso con un percorso di risposta di emergenza, che è costituito da un indirizzo civico e dall'indirizzo specifico all'interno di un edificio.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="0b7ca-108">Il **campo percorso del servizio informazioni** percorso, che corrisponde alla posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi).</span><span class="sxs-lookup"><span data-stu-id="0b7ca-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="0b7ca-109">Tentare di includere, in tale lunghezza, gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0b7ca-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="0b7ca-p103">Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, che potrebbero indirizzare gli addetti del servizio di emergenza nel posto sbagliato.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="0b7ca-113">Un identificatore di posizione che consenta agli utenti di verificare facilmente che il proprio client Lync abbia selezionato la posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="0b7ca-114">Il client Lync concatena e visualizza automaticamente i campi **Location** e **City** rilevati nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="0b7ca-115">Una buona procedura consiste nell'aggiungere l'indirizzo civico dell'edificio a ogni identificatore di posizione (ad esempio, "numero \<\>civico del primo piano").</span><span class="sxs-lookup"><span data-stu-id="0b7ca-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="0b7ca-116">Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="0b7ca-117">Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è possibile aggiungere la parola Near, ad esempio "Near 1st floor 1234".</span><span class="sxs-lookup"><span data-stu-id="0b7ca-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b7ca-118">I percorsi aggiunti al database delle posizioni centrali non sono disponibili per il client finché non vengono pubblicati utilizzando un comando di Lync Server Management Shell e vengono replicati negli archivi locali del pool.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="0b7ca-119">Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database delle posizioni da Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0b7ca-120">Nelle sezioni seguenti vengono illustrate le considerazioni che è necessario prendere in considerazione durante la compilazione e la gestione del database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="0b7ca-121">Popolamento del database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="0b7ca-121">Populating the Location Database</span></span>

<span data-ttu-id="0b7ca-122">Le domande seguenti possono essere utili per determinare come popolare il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="0b7ca-123">**Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**</span><span class="sxs-lookup"><span data-stu-id="0b7ca-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="0b7ca-p106">Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="0b7ca-126">**Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**</span><span class="sxs-lookup"><span data-stu-id="0b7ca-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="0b7ca-127">Se si utilizza l'opzione servizio informazioni percorso secondario di Lync Server per la connessione a un database di terze parti, è possibile raggruppare e gestire percorsi tramite una piattaforma offline.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="0b7ca-128">Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="0b7ca-129">Questo significa che il servizio informazioni percorso può restituire più indirizzi, provenienti dal servizio informazioni percorso secondario, a un client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="0b7ca-130">L'utente può quindi scegliere la posizione più appropriata.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="0b7ca-131">Per l'integrazione con il servizio informazioni percorso, è necessario che il database di terze parti segua lo schema di richiesta/risposta percorso di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="0b7ca-132">Per informazioni dettagliate, vedere\["MS-\]E911WS: Web Service per la specifica del protocollo di <https://go.microsoft.com/fwlink/p/?linkid=213819>supporto di E911" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="0b7ca-133">Per informazioni dettagliate sulla distribuzione di un servizio informazioni percorso secondario, vedere [Configure a Secondary Location Information Service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="0b7ca-134">Per informazioni dettagliate sul popolamento del database delle posizioni, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="0b7ca-135">Gestione del database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="0b7ca-135">Maintaining the Location Database</span></span>

<span data-ttu-id="0b7ca-p109">Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="0b7ca-138">**Valutare come verrà aggiornato il database delle posizioni.**</span><span class="sxs-lookup"><span data-stu-id="0b7ca-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="0b7ca-139">Sono disponibili diversi scenari che richiedono un aggiornamento al database delle posizioni, tra cui l'aggiunta di WAP, il ricablaggio di Office (con l'assegnazione di diverse assegnazioni di switch) e l'espansione della subnet.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-139">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion.</span></span> <span data-ttu-id="0b7ca-140">Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-140">Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="0b7ca-141">**Considerare se verrà utilizzata un'applicazione SNMP per creare una corrispondenza tra gli indirizzi MAC dei client Lync e gli identificatori di porte e commutatori,**</span><span class="sxs-lookup"><span data-stu-id="0b7ca-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="0b7ca-142">Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="0b7ca-143">Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire un percorso al client.</span><span class="sxs-lookup"><span data-stu-id="0b7ca-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

