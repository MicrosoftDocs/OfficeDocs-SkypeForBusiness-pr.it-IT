---
title: Disabilitare l'ibrido per completare la migrazione al cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questa appendice include i passaggi dettagliati per disabilitare l'ibrido come parte del consolidamento del cloud per Teams e Skype for business.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185504"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Disabilitare l'ibrido per completare la migrazione al cloud

Dopo aver spostato tutti gli utenti dal locale al cloud, è possibile rimuovere la Commissione dalla distribuzione di Skype for business locale. Oltre a rimuovere qualsiasi hardware, un passaggio critico consiste nel separare logicamente la distribuzione locale da Office 365 disabilitando l'ibrido. La disattivazione dell'ibrido è costituita da 3 passaggi:

1. Aggiornare i record DNS in Office 365.
2. Disabilitare il dominio diviso nel tenant di Office 365.
3. Disabilitare la funzionalità in on-Prem per comunicare con Office 365.


Questa procedura dovrebbe essere eseguita insieme come unità. Di seguito sono riportati i dettagli.

> [!Note] 
> In rari casi, la modifica del DNS dal punto di riferimento locale a Office 365 per l'organizzazione può causare l'interruzione del funzionamento della Federazione con altre organizzazioni finché l'altra organizzazione non aggiorna la configurazione della Federazione:<ul><li>
Tutte le organizzazioni federate che usano il modello di federazione diretta precedente (noto anche come server partner consentito) dovranno aggiornare le relative voci di dominio consentite per la propria organizzazione per rimuovere l'FQDN del proxy. Questo modello di federazione legacy non è basato sui record SRV DNS, quindi tale configurazione diventa obsoleta quando l'organizzazione si sposta nel cloud. </li><li>Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed. online. Lync. <span>com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non è mai stata federata con un tenant ibrido o online. In questo caso, la Federazione con queste organizzazioni non funzionerà finché non Abilita il proprio provider di hosting.</li></ul>Se si sospetta che i partner federati possano usare la Federazione diretta o avere federati con qualsiasi organizzazione online o ibrida, è consigliabile inviare loro una comunicazione quando si preparano a completare la migrazione al cloud.

1.  *Aggiornare il DNS in Office 365.*
Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for business puntino a Office 365 anziché alla distribuzione locale. Specificamente

    |Tipo di record|Nome|TTL|Valore|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. online. Lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. Lync. <span>com|
    |CNAME| Lyncdiscover|   3600|   WEBDIR. online. Lync. <span>com|
    |CNAME| SIP|    3600|   sipdir. online. Lync. <span>com|
    |CNAME| soddisfano|   3600|   WEBDIR. online. Lync. <span>com|
    |CNAME| telefonica  |3600|  WEBDIR. online. Lync. <span>com|

2.  *Disabilitare lo spazio di indirizzi SIP condiviso in Office 365 tenant.*
Il comando seguente deve essere eseguito da una finestra di PowerShell di Skype for business online.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Disabilitare la funzionalità in on-Prem per comunicare con Office 365.*  
Il comando seguente deve essere eseguito da una finestra di PowerShell locale.  Se in precedenza è stata importata una sessione di Skype for business online, avviare una nuova sessione di PowerShell per Skype for business.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)