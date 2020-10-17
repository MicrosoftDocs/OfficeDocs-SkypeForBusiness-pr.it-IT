---
title: 'Lync Server 2013: popolare il database delle posizioni'
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
ms.openlocfilehash: de9a5c9015dcaf83252260c89837a473a6a2291f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527973"
---
# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="bf2de-102">Popolare il database delle posizioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf2de-102">Populate the location database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf2de-103">_**Ultimo argomento modificato:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="bf2de-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="bf2de-104">Per individuare automaticamente i client all'interno di una rete, è necessario innanzitutto popolare il database delle posizioni con una rete *wiremap*, che mappa gli elementi di rete a indirizzi civici, ovvero via.</span><span class="sxs-lookup"><span data-stu-id="bf2de-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="bf2de-105">È possibile utilizzare le subnet, i punti di accesso wireless, gli interruttori e le porte per definire il wiremap.</span><span class="sxs-lookup"><span data-stu-id="bf2de-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="bf2de-106">È possibile aggiungere gli indirizzi al database delle posizioni singolarmente o in blocco utilizzando un file CSV contenente i formati di colonna descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bf2de-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="bf2de-107">Se si utilizza un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni percorso.</span><span class="sxs-lookup"><span data-stu-id="bf2de-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="bf2de-108">È possibile includere più numeri ELIN per ogni percorso, ognuno separato da un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="bf2de-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf2de-109">Elemento di rete</span><span class="sxs-lookup"><span data-stu-id="bf2de-109">Network Element</span></span></th>
<th><span data-ttu-id="bf2de-110">Colonne obbligatorie</span><span class="sxs-lookup"><span data-stu-id="bf2de-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf2de-111"><strong>Punto di accesso wireless</strong></span><span class="sxs-lookup"><span data-stu-id="bf2de-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="bf2de-112">&lt;BSSID &gt; , &lt; Description &gt; , &lt; location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; Predirectional &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bf2de-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="bf2de-113">... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; Postdirectional &gt; , &lt; città &gt; , &lt; stato &gt; , &lt; PostalCode &gt; , &lt; paese&gt;</span><span class="sxs-lookup"><span data-stu-id="bf2de-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf2de-114"><strong>Subnet</strong></span><span class="sxs-lookup"><span data-stu-id="bf2de-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="bf2de-115">&lt;Subnet &gt; , &lt; Descrizione &gt; , &lt; posizione &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; Predirectional &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bf2de-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="bf2de-116">... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; Postdirectional &gt; , &lt; città &gt; , &lt; stato &gt; , &lt; PostalCode &gt; , &lt; paese&gt;</span><span class="sxs-lookup"><span data-stu-id="bf2de-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf2de-117"><strong>Porta</strong></span><span class="sxs-lookup"><span data-stu-id="bf2de-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="bf2de-118">&lt;ChassisID &gt; , &lt; PortIDSubType &gt; , &lt; PortID &gt; , &lt; Description &gt; , &lt; location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bf2de-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="bf2de-119">... &lt; Predirectional &gt; , &lt; vianame &gt; , &lt; StreetSuffix &gt; , &lt; Postdirectional &gt; , &lt; City &gt; , &lt; state &gt; , &lt; PostalCode &gt; , &lt; Country&gt;</span><span class="sxs-lookup"><span data-stu-id="bf2de-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf2de-120"><strong>Switch</strong></span><span class="sxs-lookup"><span data-stu-id="bf2de-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="bf2de-121">&lt;ChassisID &gt; , &lt; Description &gt; , &lt; location &gt; , &lt; CompanyName &gt; , &lt; HouseNumber &gt; , &lt; HouseNumberSuffix &gt; , &lt; Predirectional &gt; ,...</span><span class="sxs-lookup"><span data-stu-id="bf2de-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="bf2de-122">... &lt; StreetName &gt; , &lt; StreetSuffix &gt; , &lt; Postdirectional &gt; , &lt; città &gt; , &lt; stato &gt; , &lt; PostalCode &gt; , &lt; paese&gt;</span><span class="sxs-lookup"><span data-stu-id="bf2de-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bf2de-123">Se il database delle posizioni non viene popolato e il **percorso necessario** nei criteri percorso è impostato su **Sì** o su **dichiarazione**di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="bf2de-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="bf2de-124">Per informazioni dettagliate sul popolamento del database delle posizioni, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf2de-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="bf2de-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="bf2de-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="bf2de-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="bf2de-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="bf2de-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="bf2de-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="bf2de-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="bf2de-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="bf2de-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="bf2de-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="bf2de-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="bf2de-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="bf2de-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="bf2de-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="bf2de-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="bf2de-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="bf2de-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="bf2de-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="bf2de-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="bf2de-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="bf2de-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="bf2de-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="bf2de-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="bf2de-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="bf2de-137">Per aggiungere elementi di rete al database delle posizioni</span><span class="sxs-lookup"><span data-stu-id="bf2de-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="bf2de-138">Eseguire il cmdlet seguente per aggiungere una posizione subnet al database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="bf2de-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="bf2de-139">Per i gateway ELIN, inserire il ELIN nel campo CompanyName.</span><span class="sxs-lookup"><span data-stu-id="bf2de-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="bf2de-140">È possibile includere più di un ELIN.</span><span class="sxs-lookup"><span data-stu-id="bf2de-140">You can include more than one ELIN.</span></span> <span data-ttu-id="bf2de-141">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bf2de-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="bf2de-142">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "subnets.csv" per aggiornare in blocco le posizioni della subnet.</span><span class="sxs-lookup"><span data-stu-id="bf2de-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="bf2de-143">Eseguire il cmdlet seguente per aggiungere percorsi wireless al database delle posizioni.</span><span class="sxs-lookup"><span data-stu-id="bf2de-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="bf2de-144">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "waps.csv" per l'aggiornamento in blocco delle posizioni wireless.</span><span class="sxs-lookup"><span data-stu-id="bf2de-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="bf2de-145">Eseguire il cmdlet seguente per aggiungere le posizioni dei commutatori al database delle località.</span><span class="sxs-lookup"><span data-stu-id="bf2de-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="bf2de-146">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "switches.csv" per aggiornare in blocco le posizioni degli switch.</span><span class="sxs-lookup"><span data-stu-id="bf2de-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="bf2de-147">Eseguire il cmdlet seguente per aggiungere posizioni delle porte al database della posizione</span><span class="sxs-lookup"><span data-stu-id="bf2de-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="bf2de-148">Il valore predefinito per PortIDSubType è LocallyAssigned.</span><span class="sxs-lookup"><span data-stu-id="bf2de-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="bf2de-149">È anche possibile impostarla su InterfaceAlias o su InterfaceName</span><span class="sxs-lookup"><span data-stu-id="bf2de-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="bf2de-150">In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "ports.csv" per l'aggiornamento in blocco delle posizioni delle porte.</span><span class="sxs-lookup"><span data-stu-id="bf2de-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

