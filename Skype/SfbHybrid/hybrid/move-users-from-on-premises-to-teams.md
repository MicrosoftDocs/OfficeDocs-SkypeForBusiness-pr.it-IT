---
title: Spostare gli utenti da Skype for Business Server 2019 a teams
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
description: 'Riepilogo: informazioni su come eseguire la migrazione delle impostazioni utente e spostare gli utenti in team.'
ms.openlocfilehash: c719741323c0e1bc8435adf10364356d069e8774
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726746"
---
# <a name="move-users-from-on-premises-to-teams"></a>Spostare gli utenti da locale a teams

Quando un utente viene spostato da solo in locale a teams, la Home page di Skype for business dell'utente viene spostata da locale a online e all'utente viene assegnato TeamsUpgradePolicy con Mode = TeamsOnly.  Dopo lo spostamento di un utente dalla modalità locale a TeamsOnly:

- Tutte le chiamate in arrivo e le chat provenienti da altri utenti (se inviate da Skype for business o Teams), sbarcheranno nel client Teams dell'utente.
- L'utente sarà in grado di interagire con altri utenti che utilizzano Skype for business (sia online che locale).
- L'utente sarà in grado di comunicare con gli utenti in organizzazioni federative.
- Le nuove riunioni pianificate dall'utente sono riunioni di team.
- L'utente può ancora partecipare a qualsiasi riunione Skype for business.
- Le riunioni preesistenti dell'utente pianificate per il futuro verranno migrate da locali a team.
- I contatti esistenti nei locali sono disponibili nei team subito dopo l'accesso dell'utente per la prima volta.
- Gli utenti non possono avviare chiamate o chat da Skype for business e non possono programmare nuove riunioni in Skype for business. Se si tenta di aprire il client Skype for business, verranno reindirizzati per l'utilizzo di team come illustrato di seguito. Se il client teams non è installato, verrà indirizzato alla versione Web dei team che utilizzano il browser.<br><br>
    ![Messaggio che reindirizza un utente a un team](../media/go-to-teams-page.png)

Prima di spostare gli utenti, assicurarsi di esaminare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud. È inoltre necessario esaminare [la migrazione e le linee guida per l'interoperabilità per le organizzazioni che utilizzano Team insieme a Skype for business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> L'archivio contatti unificato dovrebbe essere disattivato nell'account di questo per il contatto da spostare in teams.


Esistono due metodi per spostare un utente da locale a teams:

- Se si utilizza una versione precedente a quella di Skype for Business Server 2015 CU8, lo spostamento richiede due passaggi (che possono essere eseguiti insieme come un singolo passaggio, se lo si desidera):
  - [Spostare l'utente da Skype for Business Server (in locale) a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md).
  - Una volta che l'utente è ospitato in Skype for business online, assegnare l'utente TeamsUpgradePolicy con Mode = TeamsOnly. Per concedere la modalità TeamsOnly, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for business online:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Se si dispone di strumenti di amministrazione di Skype for Business Server 2015 CU8 o versione successiva, è possibile utilizzare il metodo sopra riportato oppure è possibile eseguire questa operazione in un solo passaggio, come descritto di seguito. Inoltre, è facoltativamente possibile fornire una notifica all'interno del client Skype for business prima di spostarli in teams only e, facoltativamente, far scaricare il client del team in modo invisibile all'utente dal client Skype for business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Spostare un utente direttamente da Skype for business in locale solo ai team

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, così come in Skype for Business Server 2019, consentono di spostare gli utenti da locali a modalità solo team in un solo passaggio utilizzando il cmdlet Move-CsUser in PowerShell o Skype for business se Pannello di controllo di rver, come descritto di seguito.

### <a name="move-to-teams-using-move-csuser"></a>Passare ai team tramite Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell della shell di gestione di Skype for business locale. I passaggi riportati di seguito e le autorizzazioni necessarie sono gli stessi che lo spostamento di un utente in Skype for business online, tranne per il fatto che è necessario specificare anche l'opzione MoveToTeams ed è necessario assicurarsi che all'utente sia stata assegnata anche una licenza per i team (oltre a Skype for business Online).

È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel tenant di Office 365, come descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile utilizzare un singolo account che disponga di privilegi in entrambi gli ambienti oppure è possibile avviare una finestra della shell di gestione di Skype for Business Server locale con le credenziali locali e utilizzare il `-Credential` parametro per specificare le credenziali di un account di Office 365 con il ruolo amministrativo di Office 365 necessario.

Per spostare un utente in modalità solo teams tramite Move-CsUser:

- Specificare l'utente da spostare tramite il `Identity` parametro.
- Specificare il parametro-target con il valore "sipfed. online. Lync. <span>com ".
- Specificare l' `MoveToTeams` opzione.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che in Office 365, utilizzare il `-credential` parametro per fornire un account con autorizzazioni sufficienti in Office 365.
- Se l'account con le autorizzazioni in Office 365 non termina in "onmicrosoft. <span>com ", è necessario specificare il `-HostedMigrationOverrideUrl` parametro con il valore corretto descritto in [credenziali amministrative obbligatorie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

È possibile utilizzare la sequenza di cmdlet seguente per spostare un utente in TeamsOnly e si presuppone che la credenziale Office 365 sia un account separato e fornito come input per il prompt di Get-Credential.

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passare ai team con il pannello di controllo di Skype for Business Server

1. Aprire l'app del pannello di controllo di Skype for Business Server.
2. Nella barra di spostamento a sinistra, scegliere **utenti**.
3. Utilizzare **trova** per individuare gli utenti che si desidera spostare in teams.
4. Selezionare l'utente o gli utenti e quindi, nell'elenco a discesa **azione** in alto nell'elenchi, scegliere **Sposta gli elementi selezionati in teams**.
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Office 365, con un account che termina con. onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare clic su **Avanti**e **quindi su Avanti per** spostare l'utente.
8. Si noti che i messaggi di stato relativi a esito positivo o negativo sono forniti nella parte superiore dell'app del pannello di controllo principale, non nella procedura guidata.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Avvisare gli utenti di Skype for business in locale del passaggio imminente ai team

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, così come in Skype for Business Server 2019, consentono di notificare agli utenti di Skype for business locali il trasferimento imminente ai team. Quando si abilitano queste notifiche, gli utenti visualizzeranno una notifica nel client Skype for business (Win32, Mac, Web e mobile) come illustrato di seguito. Se gli utenti fanno clic sul pulsante **prova** , il client teams verrà avviato se è installato; in caso contrario, gli utenti verranno spostati nella versione Web dei team nel browser. Per impostazione predefinita, quando le notifiche sono abilitate, i client Win32 Skype for business scaricano automaticamente il client del team in modo che il client RTF sia disponibile prima di spostare l'utente in modalità solo teams. Tuttavia, è anche possibile disabilitare questo comportamento.  Le notifiche vengono configurate tramite la versione locale `TeamsUpgradePolicy`di e il download silenzioso per i client Win32 è controllato tramite il cmdlet `TeamsUpgradeConfiguration` locale.

> [!TIP]
> Potrebbe essere necessario riavviare alcuni server affinché funzionino in Skype for business 2015 con CU8.

![Notifica del passaggio imminente ai team](../media/teams-upgrade-notification.png)

Per informare gli utenti locali che verranno presto aggiornati ai team, creare una nuova istanza di TeamsUpgradePolicy con NotifySfBUsers = true. Assegnare quindi il criterio agli utenti che si desidera inviare una notifica, assegnando il criterio direttamente all'utente o impostando il criterio a livello di sito, pool o globale. I seguenti cmdlet consentono di creare e concedere un criterio a livello di utente:

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Il download automatico dei team tramite il client Win32 di Skype for business è controllato tramite il cmdlet TeamsUpgradeConfiguration locale con il parametro DownloadTeams. Questa configurazione viene creata su un livello globale, di sito e di pool. Ad esempio, il comando seguente consente di creare la configurazione per il sito Redmond1:

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

Per impostazione predefinita, il valore di DownloadTeams è true. Tuttavia, viene rispettato *solo* se NotifySfbUser = true per un utente specificato.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Linee guida sulla migrazione e sull'interoperabilità per le organizzazioni che utilizzano Team insieme a Skype for business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coesistenza con Skype for business](/microsoftteams/coexistence-chat-calls-presence)
