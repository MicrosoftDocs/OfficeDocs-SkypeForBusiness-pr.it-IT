---
title: Spostare gli utenti nel cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Spostare gli utenti prima di rimuovere un Skype for Business locale.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420811"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a>Spostare gli utenti necessari prima di rimuovere le autorizzazioni dell'ambiente locale

In questo articolo viene descritto come spostare gli utenti necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale. Questo è il passaggio 1 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:

- **Passaggio 1. Spostare tutti gli utenti necessari da locale a online.** (Questo articolo)

- Passaggio 2. [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).

- Passaggio 3. [Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md) Tenere presente che tutti gli endpoint di applicazioni ibride esistenti non saranno individuabili tra il momento in cui si esegue il passaggio 2 precedente fino a quando non si completa questo passaggio. È consigliabile pianificare entrambi i passaggi 2 e 3 nella stessa finestra di manutenzione.

- Passaggio 4. [Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Spostare tutti gli utenti necessari dall'ambiente locale al cloud

Tutti gli utenti che continueranno a utilizzare dopo aver completato la migrazione devono prima essere spostati dall'ambiente locale al cloud. Gli utenti vengono spostati utilizzando gli strumenti di amministrazione locali. Per informazioni dettagliate, vedere [Move users between on-premises and cloud.](move-users-between-on-premises-and-cloud.md)

Sebbene sia possibile per gli utenti con account di Skype for Business Server locali utilizzare Teams, questi utenti non dispongono della funzionalità completa di Teams. Questi utenti non possono interagire o federatire con altri utenti che usano ancora Skype for Business (online o locale). Né questi utenti possono ricevere chiamate PSTN nel Teams client. Pertanto, è necessario spostare questi utenti online. Questo passaggio garantisce inoltre che tutti i contatti o le riunioni creati in Skype for Business Server siano migrati in Teams.

Per verificare se nella distribuzione locale sono presenti utenti rimanenti, eseguire il cmdlet seguente in una finestra Skype for Business Server PowerShell.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Se vengono restituiti utenti, esaminare l'output per determinare se gli account devono essere spostati nel cloud e, per tali utenti, attenersi alla procedura [riportata di seguito.](move-users-between-on-premises-and-cloud.md) Per gli account utente che non sono più necessari, eseguire il cmdlet di PowerShell Skype for Business Server seguente:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> L'Disable-CsUser rimuoverà tutti gli Skype for Business per tutti gli utenti che soddisfano i criteri di filtro. Prima di procedere, verificare che questi account non siano più necessari in futuro.


A questo punto è possibile [disabilitare la configurazione ibrida.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>Vedere anche

- [Rimuovi le autorizzazioni dell'ambiente locale Skype for Business](decommission-on-prem-overview.md)

- [Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md)

- [Spostare gli endpoint dell'applicazione ibrida da locale a online](decommission-move-on-prem-endpoints.md)

- [Rimuovere la distribuzione locale di Skype for Business](decommission-remove-on-prem.md)




