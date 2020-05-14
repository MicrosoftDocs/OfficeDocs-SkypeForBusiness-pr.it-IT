---
title: Testare le impostazioni di configurazione del trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. '
ms.openlocfilehash: bed342de3f602499f16b9f27ee0726f10d2c867e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "42048189"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Testare le impostazioni di configurazione del trunk SIP in Skype for Business Server

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:

- Se abilitare il bypass multimediale nei trunk.
- Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).
- Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN). Gli amministratori possono anche utilizzare il cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) per verificare che un trunk sia in grado di convertire un numero come composto da un utente in un numero che può essere gestito dal gateway.

Le impostazioni di configurazione dei trunk possono essere verificate solo utilizzando Windows PowerShell e il cmdlet Test-CsTrunkConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

**Per testare le impostazioni di configurazione del trunk SIP**

Il comando seguente verifica che le impostazioni di configurazione dei trunk per il sito Redmond siano in grado di convertire correttamente il numero composto 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
