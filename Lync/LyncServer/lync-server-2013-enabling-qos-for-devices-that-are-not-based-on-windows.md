---
title: 'Lync Server 2013: abilitazione di QoS per i dispositivi che non sono basati su Windows'
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
ms.openlocfilehash: ad830b2cf15e3f34c443feaa5ea21e19279804cb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Abilitazione del QoS in Lync Server 2013 per dispositivi che non sono basati su Windows

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Quando si installa Microsoft Lync Server 2013, la qualità del servizio (QoS) non verrà abilitata per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows. È possibile verificarlo eseguendo il comando riportato di seguito dall'interno di Lync Server 2013 Management Shell:

    Get-CsMediaConfiguration

Supponendo che non siano state apportate modifiche alle impostazioni di configurazione dei supporti, dovrebbero essere visualizzate informazioni simili alle seguenti:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che utilizzano un sistema operativo diverso da Windows. La funzionalità QoS è abilitata per impostazione predefinita per i dispositivi Lync Phone Edition. Tuttavia, è possibile disabilitare la qualità del servizio per Lync Phone Edition.

Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

Il comando precedente abilita QoS nell'ambito globale, tuttavia è importante osservare che le impostazioni di configurazione dei supporti possono essere applicate anche nell'ambito del sito. Se si desidera abilitare Qualità del servizio per un sito, è necessario includere l'Identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration. Questo comando, ad esempio, abilita QoS per il sito di Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Non è sempre necessario abilitare QoS nell'ambito del sito. Le impostazioni assegnate all'ambito del sito hanno la precedenza su quelle assegnate all'ambito globale. Si supponga che QoS sia abilitato nell'ambito globale ma che sia disabilitato nell'ambito del sito (per il sito di Redmond.) In questo caso, Qualità del servizio verrà disabilitato per il sito di Redmond, in quanto le impostazioni del sito sono prioritarie. Per abilitare QoS per il sito di Redmond, sarà necessario usare le impostazioni di configurazione dei supporti applicate a tale sito.



</div>

Se si desidera abilitare contemporaneamente QoS per tutte le impostazioni di configurazione dei contenuti multimediali (indipendentemente dall'ambito), eseguire questo comando dall'interno di Lync Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

È possibile disabilitare QoS per i dispositivi che utilizzano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false. Ad esempio:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Questo consente di implementare QoS su alcune parti della rete, ad esempio nel sito di Redmond, e lasciarlo disabilitato su altre parti.

La funzionalità QoS può essere abilitata e disabilitata solo utilizzando Windows PowerShell queste opzioni non sono disponibili nel pannello di controllo di Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

