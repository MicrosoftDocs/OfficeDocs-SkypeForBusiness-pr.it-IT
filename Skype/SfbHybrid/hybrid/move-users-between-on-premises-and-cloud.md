---
title: Trasferire utenti tra locale e cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: "Riepilogo: in una distribuzione locale di Skype for Business Server abilitato per l'ibrido, è possibile trasferire gli utenti tra l'ambiente locale e il cloud (sia a Microsoft teams che a Skype for business online)."
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185456"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Trasferire utenti tra locale e cloud

In una distribuzione locale di Skype for Business Server abilitato per l'ibrido, è possibile trasferire gli utenti tra l'ambiente locale e il cloud (sia Microsoft teams che Skype for business online). Se un utente si trova in locale o nel cloud è noto come Home page di Skype for business dell'utente:

- Gli utenti ospitati in locale interagiscono con i server Skype for business locale.
- Gli utenti ospitati online possono interagire con il servizio Skype for business online.

*Gli utenti di teams hanno intrinsecamente una Home page di Skype for business, se usano Skype for business o no.* Se gli utenti di Skype for business sono locali che usano Team (affiancati), questi utenti vengono assegnati in locale. Gli utenti di teams con Skype for business in locale non hanno la possibilità di interagire con gli utenti di Skype for business dal client teams, né possono comunicare da team con utenti di un'organizzazione federata. Questa funzionalità è disponibile solo dopo che l'utente è stato spostato da Skype for business in locale a online. Quando si sposta un utente in online, è possibile consentire loro di usare Skype for business online (e, facoltativamente, Teams) oppure di renderli solo teams. Se l'organizzazione usa già teams, è consigliabile spostarli in modalità solo teams, garantendo così che il routing di tutte le chat in arrivo e le chiamate sia atterrato nel client teams. Per altre informazioni, Vedi coesistenza di [team con le linee guida di Skype for business](/microsoftteams/coexistence-chat-calls-presence) e di [migrazione e interoperabilità per le organizzazioni che usano team insieme a Skype for business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Prerequisiti

Prerequisiti per trasferire un utente nel cloud (solo in Skype for business o solo in modalità Teams):

- L'organizzazione deve avere Azure AD Connect configurata correttamente e sincronizzare tutti gli attributi rilevanti per l'utente, come descritto in [configurare Azure ad Connect](configure-azure-ad-connect.md).
- Skype for business Hybrid deve essere configurato, come descritto in [Configurare Skype for business Hybrid](configure-federation-with-skype-for-business-online.md).
- All'utente deve essere assegnata una licenza per Skype for business online (piano 2) e, se utilizzerà teams, deve avere anche una licenza di teams.  Inoltre:
    - Se l'utente è abilitato per i servizi di conferenza telefonica con accesso esterno in locale, per impostazione predefinita l'utente deve avere anche una licenza di audioconferenza assegnata in Office 365 prima di eseguire lo stato di trasferimento online dell'utente. Una volta migrata nel cloud, l'utente verrà provisioning per i servizi di audioconferenza nel cloud. Se per qualche motivo si vuole trasferire un utente nel cloud, ma non usare la funzionalità di conferenza audio, è possibile eseguire l'override del controllo specificando `BypassAudioConferencingCheck` il `Move-CsUser`parametro.
    - Se l'utente è abilitato per VoIP aziendale in locale, per impostazione predefinita l'utente deve avere una licenza di sistema telefonico assegnata in Office 365 prima di trasferire l'utente online. Una volta migrata nel cloud, l'utente verrà provisioning per il sistema telefonico nel cloud. Se per qualche motivo si vuole trasferire un utente nel cloud ma non usare la funzionalità del sistema telefonico, è possibile eseguire l'override del controllo specificando `BypassEnterpriseVoiceCheck`il `Move-CsUser`parametro.


## <a name="moving-users"></a>Spostamento degli utenti

Quando un utente viene spostato da locale al cloud:

- L'utente inizia a usare i servizi Skype for business online nel cloud per qualsiasi funzionalità di Skype for business.
- Gli utenti di teams diventano abilitati per l'interoperabilità con gli utenti di Skype for business e possono anche essere federati con altre organizzazioni.
- I contatti provenienti da locale vengono spostati nel cloud (Skype for business o Teams).
- Le riunioni esistenti organizzate in futuro verranno migrate in online: se gli utenti vengono spostati direttamente in TeamsOnly (vedere di seguito), le riunioni vengono convertite in riunioni di teams, altrimenti le riunioni rimarranno Skype for business, ma verranno migrate in modo che siano ospitata online anziché locale.  La migrazione delle riunioni avviene in modo asincrono e inizia circa 90 minuti dopo lo spostamento dell'utente.  Per determinare lo stato della migrazione delle riunioni, è possibile usare [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tieni presente che il contenuto caricato prima della riunione non viene spostato.

Per trasferire gli utenti tra locale e cloud (sia in team che in Skype for business online), usare il cmdlet Move-CsUser o il pannello di controllo dell'amministratore di Skype for business, entrambi strumenti locali. Questi strumenti supportano tre diversi percorsi di movimento:

- [Da Skype for Business Server (locale) a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Da Skype for Business Server (locale) direttamente a teams only](move-users-from-on-premises-to-teams.md) (che li sposta anche in Skype for business online).  L'opzione per il passaggio direttamente da locale a teams è disponibile solo in Skype for Business Server 2019 e nell'aggiornamento cumulativo 8 per Skype for Business Server 2015. Le organizzazioni che usano versioni precedenti di Skype for Business Server possono spostare gli utenti in teams solo prima di trasferirli in Skype for business online e quindi applicare la modalità TeamsOnly a questi utenti quando sono online.
- [Da online (solo per i team o meno), in locale](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Credenziali amministrative obbligatorie

Per trasferire gli utenti tra i locali e il cloud, è necessario usare un account con privilegi sufficienti sia nell'ambiente di Skype for Business Server locale che nel tenant di Office 365. È possibile usare un account che disponga di tutti i privilegi necessari oppure due account, in questo caso si accederà agli strumenti locali usando le credenziali locali e quindi in questi strumenti si forniranno credenziali aggiuntive per una versione di Office 365 account amministrativo.  

- Nell'ambiente locale, l'utente che esegue lo stato di trasferimento deve avere il ruolo CSServerAdminstrator in Skype for Business Server.
- In Office 365 l'utente che esegue lo sposta deve essere un amministratore globale oppure deve avere ruoli di amministratore e amministratore di Skype for business.  

    > [!Important]
    > - Se si usa il pannello di controllo di amministrazione di Skype for business, verrà richiesto di specificare le credenziali per un account di Office 365 con i ruoli appropriati, come indicato sopra. Devi fornire un account che finisca in onmicrosoft.com. Se non è possibile, usare il cmdlet Move-CsUser.
    >- Se si usa Move-CsUser in PowerShell, è possibile usare un account che termina con. onmicrosoft.com oppure usare qualsiasi account locale sincronizzato in Azure AD, purché venga specificato anche il parametro HostedMigrationOverrideUrl nel cmdlet. . Il valore dell'URL di override della migrazione ospitata è una variante dell'URL seguente:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Nell'URL precedente sostituire il XX con due o tre caratteri, determinato nel modo seguente:
    >   - In una sessione di PowerShell per Skype for business online eseguire il cmdlet seguente:<br>`Get-CsTenant|ft identity`
    >    - Il valore risultante sarà il formato seguente:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Il codice a due o tre cifre è il XX contenuto nella sezione DC = lyncXX001. Se si tratta di un codice a due caratteri, sarà una cifra seguita da un numero (ad esempio 0A). Se si tratta di un codice di tre caratteri, saranno due lettere seguite da una cifra (ad esempio JP1). In tutti i casi si vedrà 001 subito dopo il codice XX.


## <a name="voice-configuration-requirements"></a>Requisiti per la configurazione vocale

Se gli utenti sono configurati per Enterprise Voice in locale, sarà necessario coordinare l'aggiornamento della configurazione vocale quando si spostano in online oppure, in alternativa, è possibile eseguirne la migrazione senza funzionalità di telefonia. Le opzioni disponibili variano a seconda che l'utente stia usando i team o il client Skype for business una volta online:

- Puoi aggiornare il provider di telefonia di un utente per usare un [piano di chiamata Microsoft](/microsoftteams/calling-plans-for-office-365). Si tratta di un'opzione che consente agli utenti di usare team o client Skype for business.
- È possibile continuare a usare il provider PSTN locale:
  - Gli utenti vocali che utilizzeranno team devono essere configurati per il [routing diretto](/microsoftteams/direct-routing-plan). Il routing diretto è disponibile solo dopo che l'utente è stato spostato da locale a online.
  - Gli utenti vocali che utilizzeranno il client Skype for business dopo essere stati spostati online devono essere configurati per la funzionalità vocale ibrida di Skype for business.

Per altre informazioni sulle opzioni di telefonia in ambienti ibridi e una matrice di supporto, vedere [account utente in un ambiente ibrido con connettività PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Altre considerazioni

I criteri, ad esempio per controllare la messaggistica, la riunione e il comportamento delle chiamate, in ambienti locali e online sono indipendenti. Puoi prendere in considerazione la possibilità di configurare i criteri nell'ambiente e assegnarli all'utente prima di spostare l'utente da locale a cloud, in modo che dispongano della configurazione corretta non appena vengono migrati in online.

## <a name="see-also"></a>Vedere anche

[Trasferire utenti da locali a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md)

[Trasferire utenti da locale a teams](move-users-from-on-premises-to-teams.md)

[Configurazione del servizio MMS (Meeting Migration Service)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Pianificare il routing diretto](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
