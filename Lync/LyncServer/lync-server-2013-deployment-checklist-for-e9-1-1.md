---
title: 'Lync Server 2013: elenco di controllo di distribuzione per il servizio E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52920c81e2055b5151280bbd65e9b2b6a90c0b73
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522803"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="7444e-102">Elenco di controllo di distribuzione per il servizio E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7444e-102">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7444e-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="7444e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="7444e-104">Per pianificare in modo efficace la funzionalità Enhanced 9-1-1 (E9-1-1), assicurarsi di includere i requisiti di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7444e-104">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="7444e-105">Prerequisiti per la distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7444e-105">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="7444e-106">Passaggi necessari per la distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7444e-106">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="7444e-107">Prerequisiti per la distribuzione di E9-1-1</span><span class="sxs-lookup"><span data-stu-id="7444e-107">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="7444e-108">Prima di distribuire il servizio E9-1-1, è necessario che siano già stati distribuiti i server interni di Lync Server, tra cui un archivio di gestione centrale, un pool Front end o un server Standard Edition, uno o più Mediation Server o pool di Mediation, nonché i client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7444e-108">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="7444e-109">Inoltre, una distribuzione di E9-1-1 richiede un trunk SIP a un provider di servizi E9-1-1 qualificato o a un gateway ELIN (Emergency Location Identification Number) per la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="7444e-109">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="7444e-110">Lync Server supporta l'utilizzo di provider di servizi E9-1-1 solo all'interno degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="7444e-110">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="7444e-111">Processo di distribuzione</span><span class="sxs-lookup"><span data-stu-id="7444e-111">Deployment Process</span></span>

<span data-ttu-id="7444e-112">Nella tabella seguente viene fornita una panoramica del processo di distribuzione di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7444e-112">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="7444e-113">Per informazioni dettagliate sui passaggi di distribuzione, vedere [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="7444e-113">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7444e-114">Fase</span><span class="sxs-lookup"><span data-stu-id="7444e-114">Phase</span></span></th>
<th><span data-ttu-id="7444e-115">Passaggi</span><span class="sxs-lookup"><span data-stu-id="7444e-115">Steps</span></span></th>
<th><span data-ttu-id="7444e-116">Ruoli</span><span class="sxs-lookup"><span data-stu-id="7444e-116">Roles</span></span></th>
<th><span data-ttu-id="7444e-117">Documentazione relativa alla distribuzione</span><span class="sxs-lookup"><span data-stu-id="7444e-117">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7444e-118">Configurare gli utilizzi vocali, le route e le configurazioni trunk</span><span class="sxs-lookup"><span data-stu-id="7444e-118">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7444e-119">Creare un nuovo record di utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="7444e-119">Create a new PSTN usage record.</span></span> <span data-ttu-id="7444e-120">Si tratta dello stesso nome utilizzato per l'impostazione di <strong>utilizzo PSTN</strong> nei criteri percorso.</span><span class="sxs-lookup"><span data-stu-id="7444e-120">This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="7444e-121">Creare o assegnare una route vocale al record di utilizzo PSTN creato nel passaggio precedente e quindi fare in modo che l'attributo del gateway punti al trunk SIP E9-1-1 o al gateway ELIN.</span><span class="sxs-lookup"><span data-stu-id="7444e-121">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="7444e-122">Per un provider di servizi E9-1-1 trunk SIP, impostare il trunk che gestirà le chiamate E9-1-1 sul SIP per passare i dati di PIDF-LO tramite il cmdlet <strong>Set-CsTrunkConfiguration – EnablePIDFLOSupport</strong> .</span><span class="sxs-lookup"><span data-stu-id="7444e-122">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="7444e-123">Facoltativamente, per un provider di servizi E9-1-1 trunk SIP creare o assegnare una route PSTN locale per le chiamate non gestite dal trunk SIP del provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7444e-123">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="7444e-124">Questa route verrà utilizzata se la connessione al provider di servizi E9-1-1 non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="7444e-124">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> <span data-ttu-id="7444e-125">Se supportato dal provider di servizi E9-1-1, assegnare una regola di configurazione trunk al gateway che converte la stringa di composizione 911 nel numero DID (Direct Inward Dialing) del National/Regional Emergency Call Response Center (ECRC).</span><span class="sxs-lookup"><span data-stu-id="7444e-125">If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7444e-126">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="7444e-126">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="7444e-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurare una route vocale E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-127"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7444e-128">Creare criteri percorso e assegnarli a utenti e subnet</span><span class="sxs-lookup"><span data-stu-id="7444e-128">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7444e-129">Esaminare il criterio percorso globale.</span><span class="sxs-lookup"><span data-stu-id="7444e-129">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="7444e-130">Creare un criterio percorso con un ambito a livello di utente. in alternativa, se l'organizzazione dispone di più siti con usi di emergenza diversi, creare un criterio percorso con un ambito a livello di rete.</span><span class="sxs-lookup"><span data-stu-id="7444e-130">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="7444e-131">Assegnare il criterio percorso ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="7444e-131">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="7444e-132">Aggiungere le subnet appropriate al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="7444e-132">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="7444e-133">Optional Assegnare i criteri percorso ai criteri utente.</span><span class="sxs-lookup"><span data-stu-id="7444e-133">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7444e-134">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="7444e-134">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="7444e-135">CSLocationAdmin (eccetto per la creazione di criteri percorso)</span><span class="sxs-lookup"><span data-stu-id="7444e-135">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="7444e-136"><a href="lync-server-2013-create-location-policies.md">Creare criteri percorso in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-136"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7444e-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Aggiungere un criterio percorso a un sito di rete in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-137"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7444e-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associare subnet a siti di rete per il servizio E9-1-1 in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-138"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7444e-139">Configurare il database di percorso</span><span class="sxs-lookup"><span data-stu-id="7444e-139">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7444e-140">Popolare il database con il mapping degli elementi di rete ai percorsi.</span><span class="sxs-lookup"><span data-stu-id="7444e-140">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="7444e-141">Per i gateway ELIN, aggiungere i numeri ELIN alla &lt; colonna CompanyName &gt; .</span><span class="sxs-lookup"><span data-stu-id="7444e-141">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="7444e-142">Configurare la connessione al provider di servizi E9-1-1 per la convalida degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="7444e-142">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="7444e-143">Convalidare gli indirizzi con il provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7444e-143">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="7444e-144">Pubblicare il database aggiornato.</span><span class="sxs-lookup"><span data-stu-id="7444e-144">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="7444e-145">Per i gateway ELIN, caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore PSTN.</span><span class="sxs-lookup"><span data-stu-id="7444e-145">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7444e-146">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="7444e-146">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="7444e-147">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="7444e-147">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="7444e-148"><a href="lync-server-2013-configure-the-location-database.md">Configurare il database delle posizioni in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-148"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7444e-149">Configurare le funzionalità avanzate (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7444e-149">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7444e-150">Configurare l'URL per l'applicazione SNMP.</span><span class="sxs-lookup"><span data-stu-id="7444e-150">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="7444e-151">Configurare l'URL per la posizione del servizio informazioni percorso secondario.</span><span class="sxs-lookup"><span data-stu-id="7444e-151">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="7444e-152">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="7444e-152">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="7444e-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configurare un'applicazione SNMP in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-153"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7444e-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurare un servizio informazioni percorso secondario in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="7444e-154"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

