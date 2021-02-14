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
description: Scopri come abilitare QoS per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814176"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Abilitazione di QoS in Skype for Business Server per i dispositivi non basati su Windows


Quando si installa Skype for Business Server, la qualità del servizio (QoS) non sarà abilitata per i dispositivi usati nell'organizzazione che utilizzano un sistema operativo diverso da Windows. È possibile verificarlo eseguendo il comando seguente da Skype for Business ServerManagement Shell:

    Get-CsMediaConfiguration

Supponendo che non siano state apportate modifiche alle impostazioni di configurazione dei supporti, dovresti ottenere informazioni simili alle seguenti:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Se la proprietà EnableQoS è impostata su False (come nell'output precedente), significa che qualità del servizio non è abilitata per computer e dispositivi che utilizzano un sistema operativo diverso da Windows.

Per abilitare la qualità del servizio nell'ambito globale, eseguire il comando seguente da Skype for Business Server Management Shell:

    Set-CsMediaConfiguration -EnableQoS $True

Il comando precedente abilita QoS nell'ambito globale, tuttavia è importante osservare che le impostazioni di configurazione dei supporti possono essere applicate anche nell'ambito del sito. Se è necessario abilitare qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration. Questo comando, ad esempio, abilita QoS per il sito di Redmond:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> È necessario abilitare QoS nell'ambito del sito? Dipende da questo. Le impostazioni assegnate all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale. Si supponga di avere QoS abilitato nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond). In tal caso, la qualità del servizio verrebbe disabilitata per il sito Redmond. ciò è dovuto al fatto che le impostazioni del sito hanno la precedenza. Per abilitare QoS per il sito Redmond, è necessario utilizzare le impostazioni di configurazione dei supporti applicate a tale sito.


Se si desidera abilitare QoS contemporaneamente per tutte le impostazioni di configurazione multimediale (indipendentemente dall'ambito), eseguire questo comando da LSkype for Business Server Management Shell:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Puoi disabilitare QoS per i dispositivi che utilizzano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su False. Ad esempio:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Questo consente di implementare QoS su alcune parti della rete, ad esempio nel sito di Redmond, e lasciarlo disabilitato su altre parti.

QoS può essere abilitato e disabilitato solo tramite Windows PowerShell. Queste opzioni non sono disponibili nel Pannello di controllo di Skype for Business Server.

> [!NOTE]
> I client Skype for Business per iOS versione 6.17 e successive ora supportano QoS.  Questa funzionalità QoS è applicabile solo ai client Skype for Business e ai dispositivi telefonici IP registrati direttamente in un server interno del pool Skype for Business o Lync su reti gestite. QoS non è applicabile per il traffico instradato su Internet.



