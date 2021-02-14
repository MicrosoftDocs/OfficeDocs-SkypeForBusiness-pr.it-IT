---
title: Spostare gli utenti da Skype for Business Server 2019 a Teams
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
description: 'Riepilogo: informazioni su come eseguire la migrazione delle impostazioni utente e spostare gli utenti in Teams.'
ms.openlocfilehash: 49763d7674946eb179188554326863f4860252c3
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130647"
---
# <a name="move-users-from-on-premises-to-teams"></a>Spostare utenti da ambiente locale a Teams

Quando un utente viene spostato da locale a Solo Teams, la home page di Skype for Business dell'utente viene spostata da locale a online e all'utente viene assegnato TeamsUpgradePolicy con mode=TeamsOnly.  Dopo lo spostamento di un utente dalla modalità locale alla modalità Solo Teams:

- Tutte le chiamate in arrivo e le chat provenienti da altri utenti (se inviate da Skype for Business o Teams), verranno inviate nel client Teams dell'utente.
- L'utente sarà in grado di interagire con altri utenti che usano Skype for Business (online o locale).
- L'utente sarà in grado di comunicare con gli utenti delle organizzazioni federate.
- Le nuove riunioni pianificate dall'utente sono riunioni di Teams.
- L'utente può comunque partecipare a qualsiasi riunione Skype for Business.
- Le riunioni preesistnti dell'utente pianificate per il futuro verranno migrate dall'ambiente locale a Teams.
- I contatti esistenti in locale sono disponibili in Teams subito dopo l'accesso dell'utente per la prima volta.
- Gli utenti non possono avviare chiamate o chat da Skype for Business né pianificare nuove riunioni in Skype for Business. Se tentano di aprire il client Skype for Business, verranno reindirizzati all'uso di Teams, come illustrato di seguito. Se il client di Teams non è installato, verrà indirizzato alla versione Web di Teams usando il browser.<br><br>
    ![Messaggio che reindirizza un utente a Teams](../media/go-to-teams-page.png)

Prima di spostare gli utenti, assicurarsi di esaminare i [prerequisiti per](move-users-between-on-premises-and-cloud.md#prerequisites) spostare gli utenti nel cloud. Assicurarsi inoltre di consultare le indicazioni sulla migrazione [e l'interoperabilità](/microsoftteams/migration-interop-guidance-for-teams-with-skype)per le organizzazioni che usano Teams insieme a Skype for Business.


> [!NOTE]
> L'archivio contatti unificato deve essere disabilitato nell'account SfB locale per il contatto da spostare in Teams.


Esistono due metodi per spostare un utente dall'ambiente locale a Teams:

- Se si utilizza una versione precedente a Skype for Business Server 2015 CU8, lo spostamento richiede due passaggi (che possono essere scriptati per essere eseguite insieme come singolo passaggio, se lo si desidera):
  - [Spostare l'utente da Skype for Business Server (locale) a Skype for Business online.](move-users-from-on-premises-to-skype-for-business-online.md)
  - Una volta che l'utente si trova in Skype for Business online, assegnare all'utente TeamsUpgradePolicy con mode= TeamsOnly. Per concedere la modalità TeamsOnly, eseguire il cmdlet seguente da una finestra di PowerShell di Skype for Business online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below. Inoltre, è possibile facoltativamente fornire una notifica all'interno del client Skype for Business prima di spostarli in Solo Teams, nonché facoltativamente scaricare il client teams automaticamente dal client Skype for Business.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Spostare un utente direttamente da Skype for Business locale a Solo Teams

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, nonché in Skype for Business Server 2019, consentono di spostare gli utenti dalla modalità locale alla modalità Solo Teams in un singolo passaggio usando il cmdlet Move-CsUser in PowerShell o il Pannello di controllo di Skype for Business Server, come descritto di seguito.

### <a name="move-to-teams-using-move-csuser"></a>Passare a Teams usando Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Management Shell locale. I passaggi seguenti e le autorizzazioni necessarie sono gli stessi per spostare un utente in Skype for Business online, con la differenza che è necessario specificare anche l'opzione MoveToTeams ed è necessario assicurarsi che all'utente sia stata concessa anche una licenza per Teams (oltre a Skype for Business online).

È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel servizio cloud (Microsoft 365 o Office 365), come descritto in Credenziali amministrative [necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un account di `-Credential` Microsoft 365 o Office 365 con il ruolo amministrativo necessario.

Per spostare un utente in modalità Solo Teams con Move-CsUser:

- Specificare l'utente da spostare utilizzando il `Identity` parametro.
- Specificare il parametro -Target con il valore "sipfed.online.lync. <span> com".
- Specificare `MoveToTeams` l'opzione.
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che nel servizio cloud (Microsoft 365 o Office 365), utilizzare il parametro per fornire a un account autorizzazioni sufficienti `-credential` in Office 365.
- Se l'account con autorizzazioni in Microsoft 365 o Office 365 non termina con "onmicrosoft. <span> com", è necessario specificare il parametro, con il valore corretto come `-HostedMigrationOverrideUrl` descritto in Credenziali amministrative [obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La sequenza di cmdlet seguente può essere usata per spostare un utente in TeamsOnly e presuppone che le credenziali di Microsoft 365 o Office 365 siano un account separato e fornite come input per il prompt di Get-Credential.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passare a Teams usando il Pannello di controllo di Skype for Business Server

1. Apri l'app Del Pannello di controllo di Skype for Business Server.
2. Nel riquadro di spostamento sinistro scegliere **Utenti.**
3. Usare **Trova** per individuare gli utenti che si desidera spostare in Teams.
4. Selezionare gli utenti e quindi scegliere  Sposta utenti selezionati in Teams nell'elenco a discesa Azione sopra **l'elenco.**
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 o Office 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e quindi su **Avanti** ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Informare gli utenti locali di Skype for Business del prossimo passaggio a Teams

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8, nonché in Skype for Business Server 2019, consentono di notificare agli utenti di Skype for Business locali il loro prossimo passaggio a Teams. Quando abiliti queste notifiche, gli utenti visualizzano una notifica nel client Skype for Business (Win32, Mac, Web e mobile), come illustrato di seguito. Se gli utenti fa **clic sul pulsante Prova,** il client Teams verrà avviato se è installato. in caso contrario, gli utenti verranno spostati alla versione Web di Teams nel browser. Per impostazione predefinita, quando le notifiche sono abilitate, i client Skype for Business Win32 scaricano automaticamente il client Teams in modo che il rich client sia disponibile prima di spostare l'utente in modalità Solo Teams; Tuttavia, è anche possibile disabilitare questo comportamento.  Le notifiche vengono configurate utilizzando la versione locale di e il download invisibile all'utente per i client Win32 viene controllato tramite il `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet locale.

> [!TIP]
> Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.

![Notifica del prossimo passaggio a Teams](../media/teams-upgrade-notification.png)

Per informare gli utenti locali che saranno presto aggiornati a Teams, creare una nuova istanza di TeamsUpgradePolicy con NotifySfBUsers=true. Assegnare quindi il criterio agli utenti a cui si desidera inviare la notifica, assegnando il criterio direttamente all'utente o impostando il criterio a livello di sito, pool o globale. I cmdlet seguenti creano e concedono un criterio a livello di utente:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Il download automatico di Teams tramite il client Win32 di Skype for Business viene controllato tramite il cmdlet TeamsUpgradeConfiguration locale con il parametro DownloadTeams. Questa configurazione viene creata a livello globale, di sito e di pool. Ad esempio, il comando seguente crea la configurazione per il sito Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Per impostazione predefinita, il valore di DownloadTeams è True. tuttavia, viene *rispettato* solo se NotifySfbUser = True per un determinato utente.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Linee guida per la migrazione e l'interoperabilità di organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coesistenza con Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
