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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: "Riepilogo: in una distribuzione locale di Skype for Business Server abilitata per l'ambiente ibrido, è possibile spostare gli utenti tra l'ambiente locale e il cloud."
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304004"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Spostare utenti tra ambiente locale e cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In una distribuzione locale di Skype for Business Server abilitata per l'ambiente ibrido, è possibile spostare gli utenti tra l'ambiente locale e Teams. A prescindere dal fatto che un utente si trovi in locale o nel cloud, la sua posizione è nota come abitazione Skype for Business dell'utente:

- Gli utenti ospitati in locale interagiscono con i server Skype for Business locali.
- Gli utenti che sono ospitati online possono interagire con il servizio Teams.

*Teams utenti hanno intrinsecamente una casa Skype for Business, indipendentemente dal fatto che usino o meno Skype for Business.* Se si dispone di utenti Skype for Business locali che usano anche Teams (affiancati), tali utenti sono ospitati in locale. Teams gli utenti con Skype for Business locale non possono interagire con gli utenti Skype for Business dal client Teams né possono comunicare da Teams con gli utenti di un'organizzazione federata. Tale funzionalità è completamente disponibile solo dopo che l'utente viene spostato da Skype for Business locale a online e reso TeamsOnly. È consigliabile spostare gli utenti in modalità TeamsOnly, in modo da garantire che il routing di tutte le chat e le chiamate in ingresso venga eseguito nel client Teams. Per altre informazioni, vedere [Teams coesistenza con Skype for Business](/microsoftteams/coexistence-chat-calls-presence) e [Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Prerequisiti

Prerequisiti per spostare un utente in modalità TeamsOnly:

- L'organizzazione deve avere Azure AD Connessione configurato correttamente e sincronizzare tutti gli attributi pertinenti per l'utente, come descritto in [Configurare Azure AD Connessione](configure-azure-ad-connect.md).
- Skype for Business ibrido deve essere configurato, come descritto in [Configurare Skype for Business ibrido](configure-federation-with-skype-for-business-online.md).
- All'utente deve essere assegnata una licenza per Teams e Skype for Business Online (piano 2). Anche dopo il ritiro di Skype for Business Online, è ancora necessaria la licenza Skype for Business Online.  Inoltre:
    - Se l'utente è abilitato per le conferenze telefoniche con accesso esterno in locale, l'utente deve avere anche una licenza di Audioconferenza assegnata in Teams prima di spostare l'utente online. Dopo la migrazione al cloud l'utente dovrà eseguire il provisioning per le audioconferenze nel cloud. 
    - Se l'utente è abilitato per VoIP aziendale in locale, l'utente deve avere una licenza di Sistema telefonico assegnata in Teams prima di spostare l'utente online. Dopo la migrazione al cloud, verrà effettuato il provisioning dell'utente per Sistema telefonico nel cloud. 


## <a name="moving-users"></a>Spostamento degli utenti

Se un utente viene spostato da locale al cloud:

- Teams utenti diventano abilitati per l'interoperabilità con gli utenti Skype for Business e, se si tratta di TeamsOnly, possono anche eseguire la federazione con altre organizzazioni.

- I contatti locali vengono spostati in Teams.

- Le riunioni esistenti organizzate che verranno pianificate in futuro vengono convertite in riunioni Teams. La migrazione delle riunioni avviene in modo asincrono e inizia circa 90 minuti dopo lo spostamento dell'utente.  Per determinare lo stato della migrazione di una riunione, è possibile usare [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms). Qualsiasi contenuto caricato prima della riunione non viene spostato.

Per spostare gli utenti in Teams, usare il cmdlet Move-CsUser o Skype for Business Admin Pannello di controllo, entrambi strumenti locali. Questi strumenti supportano i percorsi di spostamento seguenti:

- [Da Skype for Business Server (locale) direttamente a solo Teams](move-users-from-on-premises-to-teams.md).  Il comportamento di spostamento direttamente dall'ambiente locale a Teams Solo è ora automatico, indipendentemente dalla versione di Skype for Business Server o Lync Server usata. Non è più necessario specificare l'opzione `-MoveToTeams` per ottenere questo comportamento.  
- [Da online (solo Teams o meno) a locale](move-users-from-the-cloud-to-on-premises.md).

> [!NOTE] 
> Non è più necessario specificare l'opzione -MoveToTeams in Move-CsUser per spostare gli utenti direttamente dall'ambiente locale a TeamsOnly. In precedenza, se questa opzione non veniva specificata, gli utenti passavano dalla home page in Skype for Business Server locale a Skype for Business Online e la modalità rimaneva invariata. Ora, quando si sposta un utente dall'ambiente locale al cloud con Move-CsUser, agli utenti viene assegnata automaticamente la modalità TeamsOnly e le riunioni dall'ambiente locale vengono convertite automaticamente in riunioni Teams, proprio come se fosse stato specificato il `-MoveToTeams` commutatore, indipendentemente dal fatto che l'opzione sia stata effettivamente specificata. 
> 

## <a name="required-administrative-credentials"></a>Credenziali amministrative necessarie

Per spostare gli utenti tra l'ambiente locale e il cloud, è necessario usare un account con privilegi sufficienti sia nell'ambiente Skype for Business Server locale che nell'organizzazione Teams. È possibile usare un account con tutti i privilegi necessari oppure due account. Se si usano due account, si accede agli strumenti locali usando le credenziali locali e quindi in tali strumenti si forniscono credenziali aggiuntive per un account amministrativo Teams.  

- Nell'ambiente locale, l'utente che esegue lo spostamento deve avere i ruoli CSServerAdministrator, CsUserAdministrator e RTCUniversalUserAdmins in Skype for Business Server.
- In Teams, l'utente che esegue lo spostamento deve essere membro di almeno uno dei ruoli seguenti:
  - Ruolo amministratore globale
  - ruolo amministratore Teams
  - Skype for Business ruolo Amministratore.  

    > [!Important]
    > - Se si usa il Pannello di controllo amministratore Skype for Business, verrà richiesto di specificare le credenziali per un account Microsoft 365 con i ruoli appropriati, come indicato in precedenza. È necessario fornire un account che termina con onmicrosoft.com. Se ciò non è possibile, usare il cmdlet Move-CsUser.
    >- Se si usa Move-CsUser in PowerShell, è possibile usare un account che termina con onmicrosoft.com oppure qualsiasi account locale sincronizzato in Azure AD, a condizione di specificare anche il parametro HostedMigrationOverrideUrl nel cmdlet. Il valore dell'URL di override della migrazione ospitata è una variante dell'URL seguente: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Nell'URL precedente sostituire XX con due o tre caratteri, determinati come segue:
    >   - In una sessione di PowerShell Teams eseguire il cmdlet seguente:<br>`Get-CsTenant | ft ServiceInstance`
    >   - Il valore risultante sarà nel formato seguente:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - Il codice a due o tre caratteri è il codice XX contenuto nella sezione AAAA-XX-ZZ. Se si tratta di un codice a due caratteri, sarà una cifra seguita da un numero (ad esempio 4A). Se si tratta di un codice di tre caratteri, saranno due lettere seguite da una cifra (ad esempio JP1). Un esempio è NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Requisiti di configurazione vocale

Se gli utenti sono configurati per la voce aziendale in locale, è necessario coordinare l'aggiornamento della configurazione vocale quando si passa alla modalità online. In alternativa, è possibile eseguirne la migrazione senza funzionalità di telefonia. Le opzioni disponibili dipendono dal fatto che l'utente userà il client Teams o Skype for Business una volta online:

- È possibile aggiornare il provider di telefonia di un utente per usare un [piano per chiamate Microsoft](/microsoftteams/calling-plans-for-office-365). Si tratta di un'opzione che indica se gli utenti useranno client Teams o Skype for Business.
- È possibile continuare a usare il provider PSTN locale:
  - Gli utenti vocali che useranno Teams devono essere configurati per [l'instradamento diretto](/microsoftteams/direct-routing-plan). Il routing diretto è disponibile solo dopo lo spostamento dell'utente dall'ambiente locale a quello online.
  - Gli utenti vocali che useranno il client Skype for Business dopo lo spostamento online devono essere configurati per Skype for Business Hybrid funzionalità Voce.

Per altre informazioni sulle opzioni di telefonia negli ambienti ibridi, inclusa una matrice di supporto, vedere [Account utente in un ambiente ibrido con connettività PSTN](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Altre considerazioni

I criteri (come quelli relativi al controllo del comportamento della messaggistica, delle riunioni e delle chiamate) negli ambienti locali e online sono indipendenti. È consigliabile configurare eventuali criteri nell'ambiente e assegnarli all'utente prima di spostare l'utente dall'ambiente locale al cloud, in modo che dispongano della configurazione corretta non appena viene eseguita la migrazione online.

## <a name="see-also"></a>Vedere anche

[Spostare utenti da ambiente locale a Teams](move-users-from-on-premises-to-teams.md)

[Configurazione del servizio MMS (Meeting Migration Service)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Pianificare Instradamento diretto](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
