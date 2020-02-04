---
title: "Lync Server 2013: configurazione delle impostazioni dell'intervallo di porte multimediali"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a>Configurazione delle impostazioni dell'intervallo di porte multimediali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Le impostazioni dell'intervallo di porte multimediali possono avere un impatto significativo sulle prestazioni del client e configurate. Queste impostazioni possono essere configurate tramite Lync Server Management Shell.

### <a name="media-port-range-settings"></a>Impostazioni dell'intervallo di porte multimediali

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione</th>
<th>Descrizione</th>
<th>Cmdlet di Lync Server Management Shell</th>
<th>Parametri cmdlet</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Portrange\Enabled</p></td>
<td><p>Specifica se gli intervalli di porte inviati dal server devono essere usati dal client per il supporto e la segnalazione. Usato in combinazione con i sottovalori MinMediaPort e MaxMediaPort.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRangeEnabled</p></td>
</tr>
<tr class="even">
<td><p>Portrange\MinMediaPort</p></td>
<td><p>Specifica il numero di porta iniziale da usare per l'elemento multimediale. Combina con MaxMediaPort per specificare l'intervallo di porte. L'intervallo minimo consigliato è 40 porte.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPort (rappresenta il numero di porta iniziale da usare per il supporto client)</p></td>
</tr>
<tr class="odd">
<td><p>Portrange\MaxMediaPort</p></td>
<td><p>Specifica il numero di porta più alto da usare per l'elemento multimediale. Combina con MinMediaPort per specificare l'intervallo di porte. L'intervallo minimo consigliato è 40 porte.</p></td>
<td><p><strong>CsConferencingConfiguration</strong></p></td>
<td><p>ClientMediaPortRange (indica il numero totale di porte disponibili per il supporto client; l'impostazione predefinita è 40)</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a>Per configurare le impostazioni dell'intervallo di porte multimediali

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet seguente:
    
        Get-CsConferencingConfiguration
    
    Questo cmdlet restituisce le impostazioni di configurazione per i servizi di conferenza.

3.  Eseguire il cmdlet seguente con i parametri e i valori che si desidera modificare (per informazioni dettagliate sui parametri per questo cmdlet, vedere la documentazione di Lync Server Management Shell):
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > È possibile creare ulteriori set di impostazioni di configurazione per i servizi di conferenza per siti specifici. Usa il cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> con un'identità del sito. Quando si creano nuove impostazioni di configurazione per i servizi di conferenza per i siti, le impostazioni del sito hanno la precedenza sulle impostazioni globali. Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

