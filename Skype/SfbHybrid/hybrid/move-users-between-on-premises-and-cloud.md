---
title: Spostare gli utenti tra l'ambiente locale e il cloud
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
ms.custom: ''
description: "Riepilogo: in una distribuzione locale di Skype for Business Server abilitato per l'ibrido, è possibile spostare gli utenti tra l'ambiente locale e il cloud (se Microsoft teams o Skype for business online).."
ms.openlocfilehash: 0f0a29ab88f17c80227e6dc6968be85457dc799e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726766"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Spostare gli utenti tra l'ambiente locale e il cloud

In una distribuzione locale di Skype for Business Server abilitato per il sistema ibrido, è possibile spostare gli utenti tra l'ambiente locale e il cloud (se Microsoft teams o Skype for business online). Se un utente si trova in locale o nel cloud è noto come Home page di Skype for business dell'utente:

- Gli utenti ospitati in locale interagiscono con i server Skype for business locali.
- Gli utenti ospitati online possono interagire con il servizio Skype for business online.

*Gli utenti dei team hanno intrinsecamente una Home page di Skype for business, sia che utilizzino Skype for business o meno.* Se si dispone di utenti Skype for business locali che utilizzano anche team (affiancati), tali utenti sono ospitati in locale. Gli utenti di teams con Skype for business in locale non hanno la possibilità di interagire con gli utenti di Skype for business dal proprio client teams, né possono comunicare da team con utenti in un'organizzazione federata. Tale funzionalità è disponibile solo dopo che l'utente è stato spostato da Skype for business in locale a online. Quando si sposta un utente in online, è possibile consentire loro di usare Skype for business online (e, facoltativamente, Teams) oppure è possibile renderli solo team. Se l'organizzazione sta già utilizzando teams, è consigliabile spostarli in modalità solo teams, in modo da garantire che il routing di tutte le chat e le chiamate in arrivo atterri nel client del team. Per ulteriori informazioni, vedere [coesistenza di team con Skype for business](/microsoftteams/coexistence-chat-calls-presence) e [linee guida per la migrazione e l'interoperabilità per le organizzazioni che utilizzano Team insieme a Skype for business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Prerequisiti

Prerequisiti per spostare un utente nel cloud (se solo in Skype for business o solo in modalità Teams):

- L'organizzazione deve disporre di Azure AD Connect configurata in modo appropriato e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [Configure Azure ad Connect](configure-azure-ad-connect.md).
- È necessario configurare l'ambiente ibrido di Skype for business, come descritto in [Configure Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).
- All'utente deve essere assegnata una licenza per Skype for business online (piano 2) e, se utilizza Team, deve disporre anche di una licenza per i team.  Inoltre:
    - Se l'utente è abilitato per le conferenze telefoniche con accesso esterno in locale, per impostazione predefinita, l'utente deve disporre anche di una licenza di audioconferenza assegnata in Office 365 prima di eseguire lo spostamento online dell'utente. Dopo aver eseguito la migrazione nel cloud, l'utente verrà eseguito il provisioning per le conferenze audio nel cloud. Se per qualche motivo si desidera spostare un utente nel cloud, ma non utilizzare la funzionalità di audioconferenza, è possibile ignorare questo controllo specificando il `BypassAudioConferencingCheck` parametro in. `Move-CsUser`
    - Se l'utente è abilitato per VoIP aziendale in locale, per impostazione predefinita l'utente deve disporre di una licenza di sistema telefonico assegnata in Office 365 prima di spostare l'utente online. Dopo aver eseguito la migrazione nel cloud, l'utente verrà sottoposto a provisioning per il sistema telefonico nel cloud. Se per qualche motivo si desidera spostare un utente nel cloud ma non utilizzare la funzionalità del sistema telefonico, è possibile ignorare questo controllo specificando il `BypassEnterpriseVoiceCheck`parametro in `Move-CsUser`.


## <a name="moving-users"></a>Spostamento degli utenti

Quando un utente viene spostato da locale al cloud:

- L'utente inizia a utilizzare i servizi Skype for business online nel cloud per qualsiasi funzionalità Skype for business.
- Gli utenti di teams diventano abilitati per l'interoperabilità con gli utenti di Skype for business e possono anche essere federati con altre organizzazioni.
- I contatti provenienti da locali vengono spostati nel cloud (Skype for business o Teams).
- Le riunioni esistenti che sono state organizzate in futuro sono state migrate in online: se gli utenti vengono spostati direttamente su TeamsOnly (vedere di seguito), le riunioni vengono convertite in riunioni di Team, altrimenti le riunioni rimarranno Skype for business, ma verranno migrate in modo che siano Hosted online invece di locale.  La migrazione delle riunioni avviene in modo asincrono e inizia circa 90 minuti dopo lo spostamento dell'utente.  Per determinare lo stato della migrazione delle riunioni, è possibile utilizzare [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Si noti che qualsiasi contenuto caricato prima della riunione non viene spostato.

Per spostare gli utenti tra i locali e il cloud (sia che si tratti di team o di Skype for business online), utilizzare il cmdlet Move-CsUser o il pannello di controllo di amministrazione di Skype for business, entrambi strumenti locali. Questi strumenti supportano tre diversi percorsi di spostamento:

- [Da Skype for Business Server (in locale) a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Da Skype for Business Server (in locale) direttamente a teams](move-users-from-on-premises-to-teams.md) (che li trasferisce anche in Skype for business online).  L'opzione per spostarsi direttamente da locale a teams è disponibile solo in Skype for Business Server 2019 e nell'aggiornamento cumulativo 8 per Skype for Business Server 2015. Le organizzazioni che utilizzano le versioni precedenti di Skype for Business Server possono spostare gli utenti in teams solo spostando questi ultimi in Skype for business online e quindi applicando la modalità TeamsOnly a questi utenti una volta che sono online.
- [Da online (se solo team o meno), per locali](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenziali amministrative obbligatorie

Per spostare gli utenti tra i locali e il cloud, è necessario utilizzare un account con privilegi sufficienti sia nell'ambiente Skype for Business Server locale che nel tenant di Office 365. È possibile utilizzare un account con tutti i privilegi necessari oppure due account, in questo caso è possibile accedere agli strumenti locali con le credenziali locali e quindi in questi strumenti è necessario fornire credenziali aggiuntive per un Office 365 account amministrativo.  

- Nell'ambiente locale, l'utente che esegue lo spostamento deve disporre del ruolo CSServerAdminstrator in Skype for Business Server.
- In Office 365, l'utente che esegue lo spostamento deve essere un amministratore globale o deve disporre di entrambi i ruoli di amministratore di Skype for business e amministratore dell'utente.  

    > [!Important]
    > - Se si utilizza il pannello di controllo di amministrazione di Skype for business, verrà richiesto di fornire le credenziali per un account di Office 365 con i ruoli corretti, come indicato in alto. È necessario fornire un account che termina con. onmicrosoft.com. Se non è possibile, utilizzare il cmdlet Move-CsUser.
    >- Se si utilizza Move-CsUser in PowerShell, è possibile utilizzare un account che termina con. onmicrosoft.com oppure è possibile utilizzare qualsiasi account locale sincronizzato in Azure AD, a condizione che sia specificato anche il parametro HostedMigrationOverrideUrl nel cmdlet. . Il valore dell'URL di sostituzione della migrazione ospitata è una variante dell'URL seguente:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Nell'URL sopra riportato, sostituire il XX con due o tre caratteri, determinato come indicato di seguito:
    >   - In una sessione di PowerShell di Skype for business online, eseguire il cmdlet seguente:<br>`Get-CsTenant|ft identity`
    >    - Il valore risultante avrà il formato seguente:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Il codice a due o tre cifre è il XX contenuto nella sezione DC = lyncXX001. Se si tratta di un codice a due caratteri, sarà una cifra seguita da un numero, ad esempio 0A. Se si tratta di un codice a tre caratteri, saranno due lettere seguite da una cifra (ad esempio JP1). In tutti i casi, si vedrà 001 subito dopo il codice XX.


## <a name="voice-configuration-requirements"></a>Requisiti per la configurazione vocale

Se gli utenti sono configurati per VoIP aziendale in locale, è necessario coordinare l'aggiornamento della configurazione vocale quando vengono spostati in online o, in alternativa, è possibile eseguirne la migrazione senza funzionalità di telefonia. Le opzioni disponibili dipendono dal fatto che l'utente utilizzerà i team o il client Skype for business una volta che sono online:

- È possibile aggiornare il provider di telefonia di un utente per l'utilizzo di un [piano di chiamata Microsoft](/microsoftteams/calling-plans-for-office-365). Si tratta di un'opzione che consente agli utenti di utilizzare Team o client Skype for business.
- È possibile continuare a utilizzare il provider PSTN locale:
  - Gli utenti vocali che utilizzeranno i team devono essere configurati per il [routing diretto](/microsoftteams/direct-routing-plan). Il routing diretto è disponibile solo dopo che l'utente è stato spostato da locale a online.
  - Gli utenti vocali che utilizzeranno il client Skype for business dopo che sono stati spostati online devono essere configurati per le funzionalità vocali ibride di Skype for business.

Per ulteriori informazioni sulle opzioni di telefonia negli ambienti ibridi, oltre a una matrice di supporto, vedere [account utente in un ambiente ibrido con connettività PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Altre considerazioni

I criteri (ad esempio, per controllare il comportamento di messaggistica, riunione e chiamata) in ambienti locali e online sono indipendenti. È possibile prendere in considerazione la possibilità di configurare i criteri nell'ambiente e di assegnarli all'utente prima di spostare tale utente da locale al cloud, in modo che dispongano della configurazione corretta non appena viene eseguita la migrazione in linea.

## <a name="see-also"></a>Vedere anche

[Spostare gli utenti da locale a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md)

[Spostare gli utenti da locale a teams](move-users-from-on-premises-to-teams.md)

[Configurazione del servizio di migrazione delle riunioni (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Pianificare il routing diretto](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
