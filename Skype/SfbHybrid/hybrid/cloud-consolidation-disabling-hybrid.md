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
description: In questa appendice sono riportati i passaggi dettagliati per la disabilitazione dell'ibrido come parte del consolidamento cloud per Teams e Skype for business.
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924967"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Disabilitare l'ibrido per completare la migrazione al cloud

Dopo aver spostato tutti gli utenti da locale al cloud, è possibile rimuovere le autorizzazioni per la distribuzione di Skype for business locale. Oltre a rimuovere qualsiasi hardware, un passaggio critico consiste nel separare logicamente la distribuzione locale da Office 365 disabilitando l'ambiente ibrido. La disattivazione dell'ibrido è costituita da tre passaggi:

1. Aggiornare i record DNS in modo che puntino a Office 365.
2. Disabilitare il dominio diviso nel tenant di Office 365.
3. Disabilitare la funzionalità in on-Prem per comunicare con Office 365.


Questi passaggi devono essere eseguiti insieme come unità. I dettagli sono riportati di seguito. Inoltre, linee guida per la gestione dei numeri di telefono per gli utenti migrati, una volta disconnessa la distribuzione locale.

> [!Note] 
> In rari casi, la modifica del DNS dal punto di vista locale a Office 365 per l'organizzazione può causare la Federazione con alcune altre organizzazioni di smettere di funzionare fino a quando l'altra organizzazione non aggiorna la configurazione della Federazione:<ul><li>
Qualsiasi organizzazione federata che utilizza il modello di Federazione diretto meno recente (noto anche come server partner consentito) dovrà aggiornare le voci di dominio consentite per la propria azienda per rimuovere il nome FQDN del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi tale configurazione diventerà obsoleta dopo lo spostamento dell'organizzazione nel cloud. </li><li>Qualsiasi organizzazione federata che non disponga di un provider di hosting abilitato per sipfed. online. Lync. <span>com sarà necessario aggiornare la propria configurazione per abilitarlo. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non è mai stata federata con nessun tenant ibrido o online. In tal caso, la Federazione con queste organizzazioni non funzionerà finché non Abilita il proprio provider di hosting.</li></ul>Se si sospetta che uno qualsiasi dei partner federati possa utilizzare la Federazione diretta o che sia federato con qualsiasi organizzazione online o ibrida, è consigliabile inviare loro una comunicazione durante la preparazione per completare la migrazione nel cloud.

1.  *Aggiornare il DNS in modo che punti a Office 365.*
Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record Skype for business puntino a Office 365 anziché alla distribuzione locale. In particolare:

    |Tipo di record|Name|TTL|Value|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. online. Lync. <span>com|
    |SRV|_sip._tls|3600|100 1 443 sipdir. online. Lync. <span>com|
    |CNAME| lyncdiscover|   3600|   WEBDIR. online. Lync. <span>com|
    |Record CNAME| sip|    3600|   sipdir. online. Lync. <span>com|
    |Record CNAME| soddisfare|   3600|   WEBDIR. online. Lync. <span>com|
    |Record CNAME| Dialin  |3600|  WEBDIR. online. Lync. <span>com|

2.  *Disabilitare lo spazio degli indirizzi SIP condiviso in Office 365 tenant.*
Il comando seguente deve essere effettuato da una finestra di PowerShell di Skype for business online.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Disabilitare la funzionalità in on-Prem per comunicare con Office 365.*  
Il comando seguente deve essere effettuato da una finestra di PowerShell locale.  Se in precedenza è stata importata una sessione di Skype for business online, avviare una nuova sessione di Windows PowerShell per Skype for business.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gestione dei numeri di telefono per gli utenti di cui è stata eseguita la migrazione da locale

Gli amministratori possono gestire gli utenti precedentemente spostati da Skype for Business Server locale al cloud, anche dopo che la distribuzione locale è stata disattivata. Esistono 2 diverse possibilità:
1.  Se l'utente dispone di un lineURI locale prima dello spostamento (presumibilmente perché l'utente è stato abilitato per VoIP aziendale), se si desidera modificare il lineURI, è necessario eseguire questa operazione nell'annuncio locale e lasciare il flusso di valore fino a AAD. Questo non richiede Skype for Business Server locale. È invece possibile modificare questo attributo msRTCSIP-line direttamente in Active Directory locale, utilizzando lo snap-in MMC utenti e computer di Active Directory o tramite PowerShell. Se si utilizza lo snap-in MMC, aprire alla pagina delle proprietà dell'utente e fare clic su Attribute Editor Tab e find msRTCSIP-line.

2.  Se l'utente non ha un valore per lineURI on-Prem prima dello spostamento, è possibile modificare la LineURI utilizzando i parametri-onpremLineUri nel cmdlet Set-CsUser nel modulo di PowerShell di Skype for business online.

## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)
