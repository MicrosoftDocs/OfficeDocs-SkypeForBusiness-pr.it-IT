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
ms.openlocfilehash: 161a418728362da4817610dfa8e13be3046e3df6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Popolare il database delle posizioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-17_

Per individuare automaticamente i client all'interno di una rete, è necessario innanzitutto popolare il database delle posizioni con una rete *wiremap*, che mappa gli elementi di rete a indirizzi civici, ovvero via. È possibile utilizzare le subnet, i punti di accesso wireless, gli interruttori e le porte per definire il wiremap.

È possibile aggiungere gli indirizzi al database delle posizioni singolarmente o in blocco utilizzando un file CSV contenente i formati di colonna descritti nella tabella seguente.

Se si utilizza un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni percorso. È possibile includere più numeri ELIN per ogni percorso, ognuno separato da un punto e virgola.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento di rete</th>
<th>Colonne obbligatorie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Punto di accesso wireless</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;PostalCode&gt;,&lt;paese&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet</strong></p></td>
<td><p>&lt;Subnet&gt;,&lt;Descrizione&gt;,&lt;posizione&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;PostalCode&gt;,&lt;paese&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</p>
<p>... &lt;Predirectional&gt;,&lt;vianame&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;City&gt;,&lt;state&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Switch</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;PostalCode&gt;,&lt;paese&gt;</p></td>
</tr>
</tbody>
</table>


Se il database delle posizioni non viene popolato e il **percorso necessario** nei criteri percorso è impostato su **Sì** o su **dichiarazione**di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.

Per informazioni dettagliate sul popolamento del database delle posizioni, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>Per aggiungere elementi di rete al database delle posizioni

1.  Eseguire il cmdlet seguente per aggiungere una posizione subnet al database delle posizioni.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Per i gateway ELIN, inserire il ELIN nel campo CompanyName. È possibile includere più di un ELIN. Ad esempio:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "Subnets. csv" per aggiornare in blocco le posizioni della subnet.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Eseguire il cmdlet seguente per aggiungere percorsi wireless al database delle posizioni.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "WAP. csv" per aggiornare in blocco le posizioni wireless.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Eseguire il cmdlet seguente per aggiungere le posizioni dei commutatori al database delle località.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "switches. csv" per aggiornare in blocco le posizioni degli switch.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Eseguire il cmdlet seguente per aggiungere posizioni delle porte al database della posizione
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Il valore predefinito per PortIDSubType è LocallyAssigned. È anche possibile impostarla su InterfaceAlias o su InterfaceName
    
    In alternativa, è possibile eseguire i cmdlet seguenti e utilizzare un file denominato "Ports. csv" per l'aggiornamento in blocco delle posizioni delle porte.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

