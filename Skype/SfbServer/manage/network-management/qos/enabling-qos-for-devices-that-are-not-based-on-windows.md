---
title: Abilitazione di QoS per dispositivi non basati su Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come abilitare QoS per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814176"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Abilitazione del QoS in Skype for Business Server per dispositivi che non sono basati su Windows


Quando si installa Skype for Business Server, la qualità del servizio (QoS) non verrà abilitata per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows. È possibile verificarlo eseguendo il comando riportato di seguito dall'interno della shell di ServerManagement di Skype for business:

    Get-CsMediaConfiguration

Presupponendo che non siano state apportate modifiche alle impostazioni di configurazione del supporto, è consigliabile recuperare informazioni simili alle seguenti:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che utilizzano un sistema operativo diverso da Windows.

Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando riportato di seguito dall'interno di Skype for Business Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

Il comando precedente abilita QoS nell'ambito globale, tuttavia è importante osservare che le impostazioni di configurazione dei supporti possono essere applicate anche nell'ambito del sito. Se è necessario abilitare la qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione durante la chiamata a Set-CsMediaConfiguration. Questo comando, ad esempio, abilita QoS per il sito di Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> È necessario abilitare QoS nell'ambito del sito? Dipende. Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale. Si supponga di disporre di QoS abilitato nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond). In tal caso, la qualità del servizio verrebbe disabilitata per il sito Redmond. Questo perché le impostazioni del sito hanno la precedenza. Per abilitare QoS per il sito Redmond, è necessario utilizzare le impostazioni di configurazione multimediale applicate a tale sito.


Se si desidera abilitare contemporaneamente QoS per tutte le impostazioni di configurazione dei contenuti multimediali (indipendentemente dall'ambito), eseguire questo comando da LSkype for Business Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

È possibile disabilitare QoS per i dispositivi che utilizzano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false. Ad esempio:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Questo consente di implementare QoS su alcune parti della rete, ad esempio nel sito di Redmond, e lasciarlo disabilitato su altre parti.

La funzionalità QoS può essere abilitata e disabilitata solo tramite Windows PowerShell. Queste opzioni non sono disponibili nel pannello di controllo di Skype for Business Server.

> [!NOTE]
> I client Skype for business per iOS versione 6,17 e versioni successive supportano QoS.  Questa funzionalità QoS è applicabile solo ai client Skype for business e ai dispositivi di telefonia IP che sono registrati direttamente su un server interno Skype for business o Lync pool su reti gestite. Il QoS non è applicabile per il traffico su Internet.



