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

# <a name="populate-the-location-database-in-lync-server-2013"></a>Compilare il database della posizione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-17_

Per individuare automaticamente i client all'interno di una rete, è prima di tutto necessario popolare il database della posizione con una rete *wiremap*, che mappa gli elementi di rete agli indirizzi civici (ovvero via). Puoi usare subnet, punti di accesso wireless, switch e porte per definire il wiremap.

È possibile aggiungere gli indirizzi al database della posizione singolarmente o in blocco usando un file CSV contenente i formati di colonna descritti nella tabella seguente.

Se si usa un gateway ELIN (Emergency Location Identification Number), includere il numero ELIN nel campo **CompanyName** per ogni posizione. È possibile includere più ELIN per ogni posizione, separate da un punto e virgola.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento Network</th>
<th>Colonne obbligatorie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Punto di accesso wireless</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;Cap&gt;,&lt;paese&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Subnet</strong></p></td>
<td><p>&lt;Subnet&gt;,&lt;Descrizione&gt;,&lt;posizione&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;&gt;,... predirezionali</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;Cap&gt;,&lt;paese&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porta</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</p>
<p>... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;City&gt;,&lt;state&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Interruttore</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;Description&gt;,&lt;location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;Predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;Postdirectional&gt;,&lt;città&gt;,&lt;stato&gt;,&lt;Cap&gt;,&lt;paese&gt;</p></td>
</tr>
</tbody>
</table>


Se non si popola il database della posizione e la **posizione richiesta** nei criteri di posizione è impostata su **Sì** o su **dichiarazione**di non responsabilità, il client chiederà all'utente di immettere manualmente una posizione.

Per informazioni dettagliate sulla compilazione del database della posizione, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

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

## <a name="to-add-network-elements-to-the-location-database"></a>Per aggiungere elementi di rete al database della posizione

1.  Eseguire il cmdlet seguente per aggiungere una posizione subnet al database della posizione.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Per i gateway ELIN, inserire il nome ELIN nel campo CompanyName. Puoi includere più di un ELIN. Ad esempio:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Subnets. csv" per l'aggiornamento in blocco dei percorsi della subnet.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Eseguire il cmdlet seguente per aggiungere posizioni wireless al database della posizione.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "WAP. csv" per aggiornare i percorsi wireless in blocco.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Eseguire il cmdlet seguente per aggiungere posizioni di cambio al database della posizione.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "switchs. csv" per le posizioni degli switch di aggiornamento in blocco.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Eseguire il cmdlet seguente per aggiungere posizioni della porta al database della posizione
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Il valore predefinito per PortIDSubType è LocallyAssigned. È anche possibile impostarla su InterfaceAlias o su interfaccia utente
    
    In alternativa, è possibile eseguire i cmdlet seguenti e usare un file denominato "Ports. csv" per l'aggiornamento in blocco delle posizioni della porta.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

