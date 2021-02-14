---
title: Spostare utenti tra ambiente locale e cloud
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
description: "Riepilogo: in una distribuzione locale di Skype for Business Server abilitata per la distribuzione ibrida, è possibile spostare gli utenti tra l'ambiente locale e il cloud (in Microsoft Teams o in Skype for Business online)."
ms.openlocfilehash: eede6062bd9d03a2d9d6062a6dacb861ce37e14c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221126"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Spostare utenti tra ambiente locale e cloud

In una distribuzione locale di Skype for Business Server abilitato per l'ibrido è possibile spostare gli utenti tra l'ambiente locale e il cloud (che si tratti di Microsoft Teams o di Skype for Business Online). A prescindere dal fatto che un utente si trovi in locale o nel cloud, la sua posizione è nota come abitazione Skype for Business dell'utente:

- Gli utenti ospitati in locale interagiscono con i server Skype for Business locali.
- Gli utenti disponibili online possono interagire con il servizio Skype for Business Online.

*Gli utenti di Teams hanno intrinsecamente una casa Skype for Business, indipendentemente dal fatto che usino Skype for Business o meno.* Se si dispone di utenti di Skype for Business locali che usano anche Teams (affiancati), tali utenti sono ospitati in locale. Gli utenti di Teams con Skype for Business in locale non hanno la possibilità di interagire con gli utenti di Skype for Business dal client di Teams, né possono comunicare da Teams con gli utenti di un'organizzazione federata. Tale funzionalità è disponibile solo dopo che l'utente è stato spostato da Skype for Business locale a online. Quando si sposta un utente in online, è possibile consentirgli di usare Skype for Business Online (e, facoltativamente, Teams) oppure è possibile renderlo Solo Teams. Se l'organizzazione usa già Teams, è consigliabile spostare gli utenti in modalità Solo Teams, per garantire il routing di tutte le chat e delle chiamate in arrivo al loro client Teams. Per ulteriori dettagli, vedere [Coesistenza](/microsoftteams/coexistence-chat-calls-presence) di Teams con Skype for Business e indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano [Teams insieme a Skype for Business.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>Prerequisiti

Prerequisiti per spostare un utente nel cloud (in modalità Solo Skype for Business o Solo Teams):

- L'organizzazione deve avere Azure AD Connect configurato correttamente ed eseguire la sincronizzazione di tutti gli attributi rilevanti per l'utente, come descritto in [Configurare Azure AD Connect.](configure-azure-ad-connect.md)
- Skype for Business ibrido deve essere configurato, come descritto in [Configurare Skype for Business ibrido.](configure-federation-with-skype-for-business-online.md)
- All'utente deve essere assegnata una licenza di Skype for Business Online (piano 2) e, se usa Teams, deve disporre anche di una licenza Teams.  Inoltre:
    - Se l'utente è abilitato per le conferenze telefoniche con accesso esterno in locale, per impostazione predefinita l'utente deve disporre anche di una licenza di audioconferenza assegnata in Microsoft 365 o Office 365 prima di eseguire lo spostamento online dell'utente. Dopo la migrazione al cloud l'utente dovrà eseguire il provisioning per le audioconferenze nel cloud. Se per qualche motivo si desidera spostare un utente nel cloud, ma non utilizzare la funzionalità di audioconferenza, è possibile ignorare questo controllo specificando il `BypassAudioConferencingCheck` parametro in `Move-CsUser` .
    - Se l'utente è abilitato per VoIP aziendale in locale, per impostazione predefinita l'utente deve disporre di una licenza sistema telefonico assegnata in Microsoft 365 o Office 365 prima di spostare l'utente online. Dopo la migrazione al cloud l'utente dovrà eseguire il provisioning per Sistema telefonico nel cloud. Se per qualche motivo si desidera spostare un utente nel cloud ma non utilizzare la funzionalità Sistema telefonico, è possibile ignorare questo controllo specificando il `BypassEnterpriseVoiceCheck` parametro in `Move-CsUser` .


## <a name="moving-users"></a>Spostamento degli utenti

Se un utente viene spostato da locale al cloud:

- L'utente inizia a usare i servizi di Skype for Business Online nel cloud per qualsiasi funzionalità di Skype for Business.
- Gli utenti di Teams diventano abilitati per l'interoperabilità con gli utenti di Skype for Business e possono anche essere federati con altre organizzazioni.
- I contatti locali vengono spostati nel cloud (Skype for Business o Teams).
- Le riunioni esistenti organizzate che sono pianificate in futuro vengono migrate online: se gli utenti vengono spostati direttamente in TeamsOnly (vedere di seguito), le riunioni vengono convertite in riunioni di Teams, in caso contrario le riunioni rimangono Skype for Business, ma verranno migrate in modo che siano ospitate online invece che in locale.  La migrazione delle riunioni avviene in modo asincrono e inizia circa 90 minuti dopo lo spostamento dell'utente.  Per determinare lo stato della migrazione di una riunione, è possibile usare [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Tenere presente che qualsiasi contenuto caricato prima della riunione non viene spostato.

Per spostare gli utenti tra l'ambiente locale e il cloud (in Teams o in Skype for Business online), utilizzare il cmdlet Move-CsUser o il Pannello di controllo dell'amministratore di Skype for Business, entrambi strumenti locali. Questi strumenti supportano tre diversi percorsi di spostamento:

- [Da Skype for Business Server (locale) a Skype for Business online.](move-users-from-on-premises-to-skype-for-business-online.md)
- [Da Skype for Business Server (locale)](move-users-from-on-premises-to-teams.md) direttamente a Solo Teams (che li sposta anche in Skype for Business online).  L'opzione per passare direttamente dall'ambiente locale a Solo Teams è disponibile in Skype for Business Server 2019 e nell'aggiornamento cumulativo 8 per Skype for Business Server 2015. Le organizzazioni che usano versioni precedenti di Skype for Business Server possono trasferire gli utenti a Solo Teams spostandoli prima in Skype for Business Online e quindi applicando la modalità di Solo Teams a questi utenti una volta che sono online.
- [Da online (solo Teams o meno) a locale.](move-users-from-the-cloud-to-on-premises.md)

## <a name="required-administrative-credentials"></a>Credenziali amministrative necessarie

Per spostare gli utenti tra l'ambiente locale e il cloud, è necessario utilizzare un account con privilegi sufficienti sia nell'ambiente Skype for Business Server locale che nell'organizzazione di Microsoft 365 o Office 365. È possibile usare un solo account che dispone di tutti i privilegi necessari oppure due account, nel qual caso si accederebbe agli strumenti locali con le credenziali locali e quindi in questi strumenti si fornirebbe credenziali aggiuntive per un account amministrativo di Microsoft 365 o Office 365.  

- Nell'ambiente locale l'utente che esegue lo spostamento deve avere il ruolo CSServerAdminstrator in Skype for Business Server.
- In Microsoft 365 e Office 365, l'utente che esegue lo spostamento deve essere un amministratore globale o disporre sia dei ruoli di amministratore di Skype for Business che di amministratore utente.  

    > [!Important]
    > - Se si usa il Pannello di controllo dell'amministratore di Skype for Business, verrà richiesto di fornire le credenziali per un account di Microsoft 365 o Office 365 con i ruoli appropriati, come indicato in precedenza. È necessario fornire un account che termina con .onmicrosoft.com. Se non è possibile, utilizzare il cmdlet Move-CsUser seguente.
    >- Se si usa Move-CsUser in PowerShell, è possibile utilizzare un account che termina con .onmicrosoft.com oppure qualsiasi account locale sincronizzato in Azure AD, purché nel cmdlet sia specificato anche il parametro HostedMigrationOverrideUrl. Il valore dell'URL di sostituzione della migrazione ospitata è una variante dell'URL seguente: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Nell'URL precedente sostituire XX con due o tre caratteri, come indicato di seguito:
    >   - In una sessione di PowerShell di Skype for Business online, eseguire il cmdlet seguente:<br>`Get-CsTenant|ft identity`
    >    - Il valore risultante sarà nel formato seguente:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Il codice a due o tre cifre è il codice XX contenuto nella sezione DC=lyncXX001. Se si tratta di un codice a due caratteri, sarà una cifra seguita da un numero (ad esempio 0a). Se si tratta di un codice di tre caratteri, saranno due lettere seguite da una cifra (ad esempio jp1). In tutti i casi, vedrai 001 subito dopo il codice XX.


## <a name="voice-configuration-requirements"></a>Requisiti di configurazione vocale

Se gli utenti sono configurati per VoIP aziendale in locale, sarà necessario coordinare l'aggiornamento della configurazione vocale quando vengono spostati online oppure, in alternativa, è possibile eseguirne la migrazione senza funzionalità di telefonia. Le opzioni disponibili dipendono dal fatto che l'utente utilizzi il client Teams o Skype for Business quando è online:

- È possibile aggiornare il provider di telefonia di un utente per l'utilizzo di [un Piano per chiamate Microsoft.](/microsoftteams/calling-plans-for-office-365) Si tratta di un'opzione che consente agli utenti di usare i client Teams o Skype for Business.
- È possibile continuare a usare il provider PSTN locale:
  - Gli utenti vocali che utilizzeranno Teams devono essere configurati per [l'instradamento diretto.](/microsoftteams/direct-routing-plan) L'instradamento diretto è disponibile solo dopo che l'utente è stato spostato da locale a online.
  - Gli utenti vocali che useranno il client Skype for Business dopo essere stati spostati online devono essere configurati per la funzionalità Skype for Business Hybrid Voice.

Per ulteriori informazioni sulle opzioni di telefonia in ambienti ibridi, oltre a una matrice di supporto, vedere Account utente in un ambiente ibrido [con connettività PSTN.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Altre considerazioni

I criteri (come quelli relativi al controllo del comportamento della messaggistica, delle riunioni e delle chiamate) negli ambienti locali e online sono indipendenti. È consigliabile configurare i criteri nell'ambiente e assegnarli all'utente prima di spostare l'utente dall'ambiente locale al cloud, in modo che abbia la configurazione corretta non appena viene eseguita la migrazione in linea.

## <a name="see-also"></a>Vedere anche

[Spostare utenti da ambiente locale a Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Spostare utenti da ambiente locale a Teams](move-users-from-on-premises-to-teams.md)

[Configurazione del servizio MMS (Meeting Migration Service)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Pianificare Instradamento diretto](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
