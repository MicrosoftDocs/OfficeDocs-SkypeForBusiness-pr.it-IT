---
title: Verificare le impostazioni di configurazione del trunk SIP in Skype for Business Server
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
description: 'Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. '
ms.openlocfilehash: 911947b33f0e609b4dd532ec5cc2c3d56a08618c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816936"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Verificare le impostazioni di configurazione del trunk SIP in Skype for Business Server

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:

- Se il bypass multimediale deve essere abilitato nei trunk.
- Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN). Gli amministratori possono anche usare il cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) per verificare che un trunk sia in grado di convertire un numero come composto da un utente in un numero che può essere gestito dal gateway.

Le impostazioni di configurazione trunk possono essere testate solo usando Windows PowerShell e il cmdlet Test-CsTrunkConfiguration. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. 

**Per testare le impostazioni di configurazione del trunk SIP**

Questo comando verifica che le impostazioni di configurazione del trunk per il sito Redmond possano convertire correttamente il numero composto da 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
