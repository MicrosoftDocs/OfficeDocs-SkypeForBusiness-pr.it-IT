---
title: Trasferire utenti da Skype for Business Server 2019 a teams
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
description: 'Riepilogo: informazioni su come eseguire la migrazione delle impostazioni utente e spostare gli utenti in teams.'
ms.openlocfilehash: c655d8ecaa5856a57d7e675676c0ba5e8c2c43d6
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464679"
---
# <a name="move-users-from-on-premises-to-teams"></a>Trasferire utenti da locale a teams

Quando un utente viene spostato da locale a teams only, l'utente Skype for Business Home viene spostato da locale a online e all'utente viene assegnato TeamsUpgradePolicy con Mode = TeamsOnly.  Dopo che un utente è stato spostato dalla modalità locale a TeamsOnly:

- Tutte le chiamate in arrivo e le chat di altri utenti (inviati da Skype for business o Teams) sbarcheranno nel client Teams dell'utente.
- L'utente sarà in grado di interagire con altri utenti che usano Skype for business (sia online che in locale).
- L'utente sarà in grado di comunicare con gli utenti nelle organizzazioni federate.
- Le nuove riunioni pianificate dall'utente sono riunioni di teams.
- L'utente può comunque partecipare a qualsiasi riunione Skype for business.
- Le riunioni preesistenti dell'utente pianificate per il futuro verranno migrate da locale a teams.
- I contatti esistenti nei locali sono disponibili in teams subito dopo l'accesso dell'utente per la prima volta.
- Gli utenti non possono avviare chiamate o chat da Skype for business, né programmare nuove riunioni in Skype for business. Se tentano di aprire il client Skype for business, verranno reindirizzati per l'uso di teams come illustrato di seguito. Se il client teams non è installato, verrà indirizzato alla versione Web di teams usando il browser.<br><br>
    ![Messaggio che reindirizza un utente in teams](../media/go-to-teams-page.png)

Prima di spostare qualsiasi utente, assicurati di rivedere i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud. Assicurati anche di rivedere le [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> L'archivio contatti unificato deve essere disabilitato nell'account SfB per il contatto da spostare in teams.


Esistono due metodi per trasferire un utente da locale a teams:

- Se si usa una versione precedente a Skype for Business Server 2015 CU8, la mossa richiede due passaggi (che possono essere eseguiti insieme come singolo passaggio, se necessario):
  - [Trasferire l'utente da Skype for Business Server (locale) a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Una volta che l'utente è stato ospitato in Skype for business online, assegna l'utente TeamsUpgradePolicy con Mode = TeamsOnly. Per concedere la modalità TeamsOnly, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for business online:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se si hanno strumenti di amministrazione da Skype for Business Server 2015 CU8 o versione successiva, è possibile usare il metodo precedente oppure eseguire questa operazione in un solo passaggio, come descritto di seguito. Inoltre, puoi facoltativamente specificare una notifica all'interno del client Skype for business prima di spostarle in teams only e facoltativamente avere il client teams scaricato in silenzio dal client Skype for business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Trasferire un utente direttamente da Skype for business in locale a teams only

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, così come in Skype for Business Server 2019, consentono di trasferire gli utenti dalla propria sede alla modalità solo teams in un solo passaggio usando il cmdlet Move-CsUser in PowerShell o Skype for business se Pannello di controllo di rver, come descritto di seguito.

### <a name="move-to-teams-using-move-csuser"></a>Passaggio a teams tramite Move-CsUser

Move-CsUser è disponibile nella finestra di PowerShell di Skype for Business Management Shell locale. I passaggi seguenti e le autorizzazioni necessarie corrispondono allo spostamento di un utente in Skype for business online, ma devi anche specificare l'opzione MoveToTeams e devi assicurarti che all'utente sia stata assegnata anche una licenza per Teams (oltre a Skype for business Online).

È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel tenant di Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile usare un singolo account con privilegi in entrambi gli ambienti oppure è possibile avviare una finestra di gestione di Skype for Business Server locale con le credenziali locali e usare il parametro per specificare le `-Credential` credenziali per un Office 365 account con il ruolo di amministratore di Office 365 necessario.

Per trasferire un utente in modalità solo teams tramite Move-CsUser:

- Specificare l'utente per lo stato di `Identity` trasferimento tramite il parametro.
- Specifica il parametro-target con il valore "sipfed. online. Lync. <span>com ".
- Specificare l' `MoveToTeams` opzione.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, usare il `-credential` parametro per fornire un account con autorizzazioni sufficienti in Office 365.
- Se l'account con autorizzazioni in Office 365 non si conclude con "on. Microsoft. <span>com ", devi specificare il `-HostedMigrationOverrideUrl` parametro, con il valore corretto come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

La sequenza di cmdlet seguente può essere usata per trasferire un utente in TeamsOnly e presuppone che la credenziale di Office 365 sia un account distinto e fornito come input per il prompt di Get-Credential.

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passaggio a teams tramite il pannello di controllo di Skype for Business Server

1. Aprire l'app Pannello di controllo di Skype for Business Server.
2. Nella barra di spostamento sinistra scegliere **utenti**.
3. Usare **trova** per individuare gli utenti che si desidera spostare in teams.
4. Selezionare l'utente o gli utenti e quindi, nell'elenco a discesa delle **azioni** sopra la lista, scegliere **Move users selected to teams**.
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Office 365 con un account che termina in onmicrosoft.com e disponga di autorizzazioni sufficienti.
7. Fare clic su **Avanti**e **** quindi su un'altra volta per trasferire l'utente.
8. Tieni presente che i messaggi di stato relativi a successo o errore vengono forniti nella parte superiore dell'app Pannello di controllo principale, non nella procedura guidata.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Avvisare gli utenti locali di Skype for business dell'imminente trasferimento in teams

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, così come in Skype for Business Server 2019, consentono di comunicare agli utenti di Skype for business locali il loro imminente trasferimento in teams. Quando si abilitano queste notifiche, gli utenti vedranno una notifica nel client Skype for business (Win32, Mac, Web e mobile), come illustrato di seguito. Se gli utenti fanno clic sul pulsante **prova** , il client teams verrà avviato se è installato; in caso contrario, gli utenti verranno spostati nella versione Web di Teams nel browser. Per impostazione predefinita, quando le notifiche sono abilitate, i client di Skype for business Win32 scaricano automaticamente il client teams in modo che il rich client sia disponibile prima di spostare l'utente in modalità solo Teams; Tuttavia, puoi anche disabilitare questo comportamento.  Le notifiche vengono configurate tramite la versione locale `TeamsUpgradePolicy`di e il download silenzioso per i client Win32 viene controllato tramite il cmdlet `TeamsUpgradeConfiguration` locale.

> [!TIP]
> Potrebbe essere necessario riavviare alcuni server per questo lavoro in Skype for business 2015 con CU8.

![Notifica delle prossime mosse ai team](../media/teams-upgrade-notification.png)

Per segnalare agli utenti locali che presto verranno aggiornati a teams, crea una nuova istanza di TeamsUpgradePolicy con NotifySfBUsers = true. Assegna quindi il criterio agli utenti che vuoi notificare, assegnando il criterio direttamente all'utente o impostando i criteri nel sito, nel pool o nel livello globale. I cmdlet seguenti consentono di creare e concedere un criterio a livello di utente:

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Il download automatico dei team tramite il client Win32 di Skype for business viene controllato tramite il cmdlet TeamsUpgradeConfiguration locale con il parametro DownloadTeams. La configurazione viene creata in un livello globale, del sito e del pool. Ad esempio, il comando seguente crea la configurazione per il sito Redmond1:

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

Per impostazione predefinita, il valore di DownloadTeams è true; Tuttavia, viene rispettato *solo* se NotifySfbUser = true per un utente specifico.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coesistenza con Skype for business](/microsoftteams/coexistence-chat-calls-presence)
