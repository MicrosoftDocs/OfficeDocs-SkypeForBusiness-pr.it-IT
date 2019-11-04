---
title: Abilitazione di QoS per i dispositivi non basati su Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Informazioni su come abilitare QoS per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows.
ms.openlocfilehash: 956fff0e7fc69b1950e35261c02f9f44977510ce
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37341942"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Abilitazione di QoS in Skype for Business Server per dispositivi non basati su Windows


Quando si installa Skype for Business Server, la qualità del servizio (QoS) non verrà abilitata per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows. Puoi verificare questa operazione eseguendo il comando seguente dall'interno di Skype for business ServerManagement Shell:

    Get-CsMediaConfiguration

Supponendo che non siano state apportate modifiche alle impostazioni di configurazione multimediali, è consigliabile recuperare le informazioni in modo simile al seguente:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se la proprietà EnableQoS è impostata su false (come nell'output precedente), ciò significa che la qualità del servizio non è abilitata per i computer e i dispositivi che usano un sistema operativo diverso da Windows.

Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando seguente dall'interno di Skype for Business Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

Il comando precedente consente di abilitare il QoS nell'ambito globale; Tuttavia, è importante notare che le impostazioni di configurazione multimediali possono essere applicate anche all'ambito del sito. Se è necessario abilitare la qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration. Ad esempio, questo comando Abilita QoS per il sito Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> È necessario abilitare QoS nell'ambito del sito? Dipende. Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale. Supponiamo di avere abilitato QoS nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond). In questo caso, la qualità del servizio verrebbe disabilitata per il sito Redmond; il motivo è che le impostazioni del sito hanno la precedenza. Per abilitare QoS per il sito Redmond, è necessario usare le impostazioni di configurazione multimediale applicate a tale sito.


Se si vuole abilitare il QoS simultaneamente per tutte le impostazioni di configurazione multimediali (indipendentemente dall'ambito), eseguire questo comando dall'interno di LSkype for Business Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puoi disabilitare QoS per i dispositivi che usano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su false. Ad esempio:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

In questo modo puoi implementare QoS in alcune parti della rete, ad esempio nel sito Redmond, lasciando la qualità del servizio disabilitata in altre parti della rete.

Il QoS può essere abilitato e disabilitato solo con Windows PowerShell. Queste opzioni non sono disponibili nel pannello di controllo di Skype for Business Server.

> [!NOTE]
> I client Skype for business per iOS versione 6,17 e versioni successive ora supportano QoS.  Questa funzionalità QoS è applicabile solo ai client Skype for business e ai dispositivi di telefonia IP registrati direttamente in un server interno Skype for business o Lync pool su reti gestite. QoS non è applicabile per il traffico instradato tramite Internet.



