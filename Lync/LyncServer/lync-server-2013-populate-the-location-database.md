---
title: 'Lync Server 2013: popolare il database della posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a93cee85afec1e3943af692d598d0d02ab678d58
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="2210e-102">Compilare il database della posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2210e-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2210e-103">_**Argomento Ultima modifica:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2210e-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2210e-104">Per individuare automaticamente i client all'interno di una rete, è prima di tutto necessario popolare il database della posizione con una rete *wiremap*, che mappa gli elementi di rete agli indirizzi civici (ovvero via).</span><span class="sxs-lookup"><span data-stu-id="2210e-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="2210e-105">Puoi usare subnet, punti di accesso wireless, switch e porte per definire il wiremap.</span><span class="sxs-lookup"><span data-stu-id="2210e-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="2210e-106">È possibile aggiungere gli indirizzi al database della posizione singolarmente o in blocco usando un file CSV contenente i formati di colonna descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2210e-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="2210e-107">Se si usa un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni posizione.</span><span class="sxs-lookup"><span data-stu-id="2210e-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="2210e-108">È possibile includere più ELIN per ogni posizione, separate da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="2210e-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2210e-109">Elemento Network</span><span class="sxs-lookup"><span data-stu-id="2210e-109">Network Element</span></span></th>
<th><span data-ttu-id="2210e-110">Colonne obbligatorie</span><span class="sxs-lookup"><span data-stu-id="2210e-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2210e-111"><strong>Punto di accesso wireless</strong></span><span class="sxs-lookup"><span data-stu-id="2210e-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="2210e-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="2210e-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="2210e-113">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;Cap&gt;,&lt;paese&gt;</span><span class="sxs-lookup"><span data-stu-id="2210e-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2210e-114"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="2210e-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="2210e-115">&lt;Subnet&gt;,&lt;Descrizione&gt;,&lt;posizione&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;&gt;,... predirezionali</span><span class="sxs-lookup"><span data-stu-id="2210e-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="2210e-116">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;Cap&gt;,&lt;paese&gt;</span><span class="sxs-lookup"><span data-stu-id="2210e-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2210e-117"><strong>Porta</strong></span><span class="sxs-lookup"><span data-stu-id="2210e-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="2210e-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</span><span class="sxs-lookup"><span data-stu-id="2210e-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="2210e-119">... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;City&gt;,&lt;state&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span><span class="sxs-lookup"><span data-stu-id="2210e-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2210e-120"><strong>Interruttore</strong></span><span class="sxs-lookup"><span data-stu-id="2210e-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="2210e-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="2210e-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="2210e-122">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;Cap&gt;,&lt;paese&gt;</span><span class="sxs-lookup"><span data-stu-id="2210e-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2210e-123">Se non si popola il database della posizione e la **posizione richiesta** nei criteri di posizione è impostata su **Sì** o su **dichiarazione**di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="2210e-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="2210e-124">Per informazioni dettagliate sulla compilazione del database della posizione, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="2210e-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="2210e-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="2210e-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="2210e-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="2210e-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="2210e-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="2210e-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="2210e-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="2210e-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="2210e-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="2210e-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="2210e-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="2210e-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="2210e-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="2210e-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="2210e-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="2210e-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="2210e-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="2210e-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="2210e-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="2210e-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="2210e-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="2210e-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="2210e-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="2210e-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="2210e-137">Per aggiungere elementi di rete al database della posizione</span><span class="sxs-lookup"><span data-stu-id="2210e-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="2210e-138">Eseguire il cmdlet seguente per aggiungere una posizione subnet al database della posizione.</span><span class="sxs-lookup"><span data-stu-id="2210e-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="2210e-139">Per i gateway ELIN, inserire il nome ELIN nel campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="2210e-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="2210e-140">Puoi includere più di un ELIN.</span><span class="sxs-lookup"><span data-stu-id="2210e-140">You can include more than one ELIN.</span></span> <span data-ttu-id="2210e-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2210e-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="2210e-142">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Subnets. csv" per l'aggiornamento in blocco dei percorsi della subnet.</span><span class="sxs-lookup"><span data-stu-id="2210e-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="2210e-143">Eseguire il cmdlet seguente per aggiungere posizioni wireless al database della posizione.</span><span class="sxs-lookup"><span data-stu-id="2210e-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="2210e-144">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "WAP. csv" per aggiornare i percorsi wireless in blocco.</span><span class="sxs-lookup"><span data-stu-id="2210e-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="2210e-145">Eseguire il cmdlet seguente per aggiungere posizioni di cambio al database della posizione.</span><span class="sxs-lookup"><span data-stu-id="2210e-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="2210e-146">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "switchs. csv" per le posizioni degli switch di aggiornamento in blocco.</span><span class="sxs-lookup"><span data-stu-id="2210e-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="2210e-147">Eseguire il cmdlet seguente per aggiungere posizioni della porta al database della posizione</span><span class="sxs-lookup"><span data-stu-id="2210e-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="2210e-148">Il valore predefinito per PortIDSubType è LocallyAssigned.</span><span class="sxs-lookup"><span data-stu-id="2210e-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="2210e-149">È anche possibile impostarla su InterfaceAlias o su interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="2210e-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="2210e-150">In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Ports. csv" per l'aggiornamento in blocco delle posizioni della porta.</span><span class="sxs-lookup"><span data-stu-id="2210e-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

