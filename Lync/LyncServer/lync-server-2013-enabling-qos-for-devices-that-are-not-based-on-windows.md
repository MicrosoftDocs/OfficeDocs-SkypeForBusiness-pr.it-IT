---
title: 'Lync Server 2013: abilitare QoS per i dispositivi che non sono basati su Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Abilitazione del QoS in Lync Server 2013 per i dispositivi che non sono basati su Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Quando si installa Microsoft Lync Server 2013, la qualità del servizio (QoS) non verrà abilitata per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows. Puoi verificare questa operazione eseguendo il comando seguente dall'interno di Lync Server 2013 Management Shell:

    Get-CsMediaConfiguration

Supponendo che non siano state apportate modifiche alle impostazioni di configurazione multimediali, è consigliabile ripristinare le informazioni in modo simile al seguente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che usano un sistema operativo diverso da Windows. La funzionalità QoS è abilitata per impostazione predefinita per i dispositivi Lync Phone Edition; Tuttavia, è possibile disabilitare la qualità del servizio per Lync Phone Edition.

Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando seguente all'interno di Lync Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

Il comando precedente consente di abilitare il QoS nell'ambito globale; Tuttavia, è importante notare che le impostazioni di configurazione multimediali possono essere applicate anche all'ambito del sito. Se è necessario abilitare la qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration. Ad esempio, questo comando Abilita QoS per il sito Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> È necessario abilitare QoS nell'ambito del sito? Dipende. Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale. Supponiamo di avere abilitato QoS nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond). In questo caso, la qualità del servizio verrà disabilitata per il sito Redmond; il motivo è che le impostazioni del sito hanno la precedenza. Per abilitare QoS per il sito Redmond, sarà necessario usare le impostazioni di configurazione multimediale applicate a tale sito.



</div>

Se si vuole abilitare contemporaneamente QoS per tutte le impostazioni di configurazione multimediali (indipendentemente dall'ambito), eseguire questo comando dall'interno di Lync Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puoi disabilitare QoS per i dispositivi che usano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false. Ad esempio:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

In questo modo puoi implementare QoS in alcune parti della rete, ad esempio nel sito Redmond, lasciando la qualità del servizio disabilitata in altre parti della rete.

Il QoS può essere abilitato e disabilitato solo con Windows PowerShell queste opzioni non sono disponibili nel pannello di controllo di Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

