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
description: Informazioni su come abilitare QoS per i dispositivi usati nell'organizzazione che usano un sistema operativo diverso da Windows.
ms.openlocfilehash: 81350ae252252a85bd3f88a000d6cd78d85408e43ca56335517de7b50bb6fd49
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590930"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Abilitazione di QoS in Skype for Business Server per i dispositivi non basati su Windows


Quando si installa Skype for Business Server, la qualità del servizio (QoS) non verrà abilitata per i dispositivi utilizzati nell'organizzazione che utilizzano un sistema operativo diverso da Windows. È possibile verificarlo eseguendo il comando seguente dall'Skype for Business ServerManagement Shell:

**Get-CsMediaConfiguration**

Presupponendo che non siano state apportate modifiche alle impostazioni di configurazione dei supporti, è consigliabile ottenere informazioni simili alle seguenti:

Identity : Global<br/>
EnableQoS : False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

Se la proprietà EnableQoS è impostata su False (come nell'output precedente), significa che qualità del servizio non è abilitata per computer e dispositivi che utilizzano un sistema operativo diverso da Windows.

Per abilitare qualità del servizio nell'ambito globale, eseguire il comando seguente da Skype for Business Server Management Shell:

**Set-CsMediaConfiguration -EnableQoS $True**

Il comando precedente abilita QoS nell'ambito globale, tuttavia è importante osservare che le impostazioni di configurazione dei supporti possono essere applicate anche nell'ambito del sito. Se è necessario abilitare qualità del servizio per un sito, è necessario includere l'identità delle impostazioni di configurazione quando si chiama Set-CsMediaConfiguration. Questo comando, ad esempio, abilita QoS per il sito di Redmond:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> È necessario abilitare QoS nell'ambito del sito? Dipende. Impostazioni assegnati all'ambito del sito hanno la precedenza sulle impostazioni assegnate all'ambito globale. Si supponga di avere QoS abilitato nell'ambito globale ma disabilitato nell'ambito del sito (per il sito Redmond). In tal caso, la qualità del servizio verrebbe disabilitata per il sito Redmond. ciò è dovuto al fatto che le impostazioni del sito hanno la precedenza. Per abilitare QoS per il sito Redmond, è necessario utilizzare le impostazioni di configurazione dei supporti applicate a tale sito.


Se si desidera abilitare contemporaneamente QoS per tutte le impostazioni di configurazione dei supporti (indipendentemente dall'ambito), eseguire questo comando dall'interno di LSkype for Business Server Management Shell:

**Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True**

Puoi disabilitare QoS per i dispositivi che usano un sistema operativo diverso da Windows impostando il valore della proprietà EnableQoS su False. Ad esempio:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

Questo consente di implementare QoS su alcune parti della rete, ad esempio nel sito di Redmond, e lasciarlo disabilitato su altre parti.

QoS può essere abilitato e disabilitato solo tramite Windows PowerShell. Queste opzioni non sono disponibili nel Pannello Skype for Business Server controllo.

> [!NOTE]
> Skype for Business client per iOS versione 6.17 e successive ora supportano QoS.  Questa funzionalità QoS è applicabile solo ai client Skype for Business e ai dispositivi telefonici IP registrati direttamente in un server Skype for Business o lync pool interno su reti gestite. QoS non è applicabile per il traffico instradato su Internet.
