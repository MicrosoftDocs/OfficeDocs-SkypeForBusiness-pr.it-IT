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
ms.openlocfilehash: 1b5a2f909a05ffd30902ca4ca32dc5b5621b3013e779cece3f0ffcd2dada731e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324705"
---
# <a name="move-users-from-on-premises-to-teams"></a>Spostare utenti da ambiente locale a Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Quando un utente viene spostato da locale Teams Solo, la home page dell'utente Skype for Business viene spostata da locale Skype for Business online e all'utente viene assegnato TeamsUpgradePolicy con mode=TeamsOnly.  Dopo lo spostamento di un utente dalla modalità locale alla modalità TeamsOnly:

- Tutte le chiamate in arrivo e le chat di altri utenti (sia inviate da Skype for Business che da Teams), verranno inviate nel client di Teams dell'utente.
- L'utente sarà in grado di interagire con altri utenti che usano Skype for Business (online o in locale).
- L'utente sarà in grado di comunicare con gli utenti nelle organizzazioni federate.
- Le nuove riunioni pianificate dall'utente vengono Teams riunioni.
- L'utente può comunque partecipare a Skype for Business riunioni.
- Le riunioni preesiste dell'utente pianificate per il futuro verranno migrate da locale a Teams.
- I contatti esistenti in locale sono disponibili in Teams subito dopo l'accesso dell'utente per la prima volta.
- Gli utenti non possono avviare chiamate o chat da Skype for Business, né possono pianificare nuove riunioni in Skype for Business. Se tentano di aprire il client Skype for Business, verranno reindirizzati per usare Teams come illustrato di seguito. Se il client Teams non è installato, verrà indirizzato alla versione Web di Teams utilizzando il browser.<br><br>
    ![Messaggio che reindirizza un utente a Teams](../media/go-to-teams-page.png)

Prima di spostare gli utenti, verificare i [prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud. Leggere inoltre le indicazioni sulla migrazione e [l'interoperabilità](/microsoftteams/migration-interop-guidance-for-teams-with-skype)per le organizzazioni che utilizzano Teams insieme a Skype for Business .


> [!NOTE]
> L'archivio contatti unificato deve essere disabilitato nell'account SfB locale per il contatto da spostare in Teams.

> [!IMPORTANT]
>Quando si sposta un utente dall'ambiente locale al cloud con Move-CsUser, agli utenti viene automaticamente assegnata la modalità TeamsOnly e le riunioni dall'organizzazione locale vengono convertite automaticamente Teams riunioni, indipendentemente dal fatto che il commutatore sia effettivamente `-MoveToTeams` specificato. Sono incluse le migrazioni da Lync Server 2013, che non hanno mai avuto il `-MoveToTeams` passaggio.  In precedenza, se questa opzione non è stata specificata, gli utenti passavano da Skype for Business Server locale a Skype for Business Online e la loro modalità rimaneva invariata. Questo è stato recentemente modificato in preparazione per il ritiro di Skype for Business Online.


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Spostare un utente direttamente da Skype for Business locale a Teams solo

Gli strumenti di amministrazione locali di Skype for Business Server e Lync Server 2013 consentono di spostare gli utenti dalla modalità locale alla modalità TeamsOnly in un unico passaggio utilizzando il cmdlet Move-CsUser in PowerShell o il Pannello di controllo di Skype for Business Server, come descritto di seguito. Non è più necessario specificare l'opzione e il comportamento per spostarsi direttamente da locale a Teams Solo ora è automatico, indipendentemente dalla versione di Skype for Business Server o `-MoveToTeams` Lync Server utilizzata. 

È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel servizio cloud (Microsoft 365 o Office 365), come descritto in [Credenziali amministrative necessarie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) È possibile utilizzare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e utilizzare il parametro per specificare le credenziali per un Microsoft 365 con il ruolo amministrativo `-Credential` necessario.

Inoltre, devi assicurarti che all'utente sia stata concessa una licenza per Teams (oltre a Skype for Business Online). Non disabilitare la licenza Skype for Business Online.

### <a name="move-to-teams-using-move-csuser"></a>Passare a Teams usando Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Server Management Shell locale o da una finestra di PowerShell di Lync Server Management Shell. Per spostare un utente in modalità TeamsOnly tramite Move-CsUser:
- Specificare l'utente da spostare utilizzando il `Identity` parametro .
- Specificare il `-Target` parametro con il valore "sipfed.online.lync. <span> com".
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che nel servizio cloud (Microsoft 365), utilizzare il parametro per fornire a un account autorizzazioni sufficienti `-credential` in Microsoft 365.
- Se l'account con autorizzazioni in Microsoft 365 non termina con "onmicrosoft. <span> com", è necessario specificare il parametro con il valore corretto come `-HostedMigrationOverrideUrl` descritto in Credenziali amministrative [obbligatorie.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

La sequenza di cmdlet seguente può essere utilizzata per spostare un utente in TeamsOnly e presuppone che la credenziale Microsoft 365 sia un account separato e fornita come input per il prompt Get-Credential. Il comportamento è lo stesso indipendentemente `-MoveToTeams` dal fatto che l'opzione sia specificata o meno.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Poiché esistono diverse circostanze che richiedono parametri diversi, il comando predefinito per la maggior parte dei casi è:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passare a Teams tramite Skype for Business Server Pannello di controllo

1. Apri l'Skype for Business Server del Pannello di controllo.
2. Nel riquadro di spostamento sinistro scegliere **Utenti**.
3. Usa **Trova** per individuare gli utenti che vuoi spostare in Teams.
4. Selezionare gli utenti e quindi,  nell'elenco a discesa Azione sopra l'elenco, scegliere Sposta gli utenti selezionati **in Teams** o Sposta gli utenti selezionati in **Skype for Business Online**.   Entrambe le opzioni ora spostano gli utenti direttamente in TeamsOnly.
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 con un account che termina con .onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare **clic su** Avanti e **quindi** su Avanti ancora una volta per spostare l'utente.
8. Tieni presente che i messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app principale del Pannello di controllo, non nella procedura guidata.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Informare Skype for Business utenti locali del passaggio imminente a Teams

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8 e in Skype for Business Server 2019 consentono di notificare agli utenti di Skype for Business locali il loro prossimo passaggio a Teams. Quando abiliti queste notifiche, gli utenti visualizzano una notifica nel client Skype for Business (Win32, Mac, Web e dispositivi mobili), come illustrato di seguito. Se gli utenti fa **clic sul** pulsante Prova, Teams il client verrà avviato se è installato. in caso contrario, gli utenti verranno spostati alla versione Web Teams nel browser. Per impostazione predefinita, quando le notifiche sono abilitate, i client Skype for Business Win32 scaricano automaticamente il client Teams in modo che il rich client sia disponibile prima di spostare l'utente in modalità TeamsOnly. tuttavia, è anche possibile disabilitare questo comportamento.  Le notifiche vengono configurate utilizzando la versione locale di e il download invisibile all'utente per i client Win32 viene controllato tramite il `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet locale.

> [!TIP]
> Per il funzionamento di alcuni server potrebbe essere necessario riavviare Skype for Business 2015 con CU8.

![Notifica dello spostamento in Teams](../media/teams-upgrade-notification.png)

Per notificare agli utenti locali che verranno presto aggiornati a Teams, creare una nuova istanza di TeamsUpgradePolicy con NotifySfBUsers=true. Assegnare quindi tale criterio agli utenti a cui si desidera inviare una notifica, assegnando il criterio direttamente all'utente o impostando il criterio a livello di sito, pool o globale. I cmdlet seguenti creano e concedono un criterio a livello di utente:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Il download automatico Teams tramite il client Win32 Skype for Business viene controllato tramite il cmdlet TeamsUpgradeConfiguration locale con il parametro DownloadTeams. Questa configurazione viene creata a livello globale, di sito e di pool. Ad esempio, il comando seguente crea la configurazione per il sito Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Per impostazione predefinita, il valore di DownloadTeams è True. tuttavia, viene *rispettato* solo se NotifySfbUser = True per un determinato utente.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Linee guida per la migrazione e l'interoperabilità di organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coesistenza con Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
