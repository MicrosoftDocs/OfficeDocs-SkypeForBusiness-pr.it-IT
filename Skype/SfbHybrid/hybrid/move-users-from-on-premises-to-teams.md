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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: 'Riepilogo: informazioni su come eseguire la migrazione delle impostazioni utente e spostare gli utenti in Teams.'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705845"
---
# <a name="move-users-from-on-premises-to-teams"></a>Spostare utenti da ambiente locale a Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Quando un utente viene spostato da locale a Solo Teams, la home Skype for Business dell'utente viene spostata da locale a online e all'utente viene assegnato TeamsUpgradePolicy con mode=TeamsOnly.  Dopo lo spostamento di un utente dalla modalità locale alla modalità TeamsOnly:

- Tutte le chiamate in arrivo e le chat di altri utenti (inviate da Skype for Business o Teams) saranno disponibili nel client Teams dell'utente.
- L'utente sarà in grado di interagire con altri utenti che usano Skype for Business (online o in locale).
- L'utente sarà in grado di comunicare con gli utenti nelle organizzazioni federate.
- Le nuove riunioni pianificate dall'utente sono riunioni di Teams.
- L'utente può comunque partecipare a qualsiasi riunione Skype for Business. Tuttavia, a partire da ottobre 2022, solo gli utenti di Teams nelle organizzazioni ibride potranno partecipare alle riunioni Skype for Business in modo anonimo. Per informazioni dettagliate, vedere [Cosa aspettarsi dopo il ritiro](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement).
- Gli utenti’ che hanno già eseguito le riunioni pianificate per il futuro verranno migrati dall'ambiente locale a Teams.
- I contatti esistenti in locale sono disponibili in Teams poco dopo che l'utente ha eseguito l'accesso per la prima volta.
- Gli utenti non possono avviare chiamate o chat da Skype for Business, né possono pianificare nuove riunioni in Skype for Business. Se tentano di aprire il client Skype for Business, verranno reindirizzati per usare Teams come illustrato di seguito. Se il client di Teams non è installato, verrà indirizzato alla versione Web di Teams usando il browser.<br><br>
    ![Messaggio che reindirizza un utente a Teams.](../media/go-to-teams-page.png)

Prima di spostare gli utenti, assicurarsi di esaminare [i prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites) per spostare gli utenti nel cloud. Assicurarsi anche di esaminare le [indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).


> [!NOTE]
> Per spostare il contatto in Teams, l'archivio contatti unificato deve essere disabilitato nell'account SfB locale.

> [!IMPORTANT]
>
> - Quando si sposta un utente dall'ambiente locale al cloud con Move-CsUser, agli utenti viene assegnata automaticamente la modalità TeamsOnly e le riunioni dall'ambiente locale vengono convertite automaticamente in riunioni di Teams, indipendentemente dal fatto che il `-MoveToTeams` commutatore sia effettivamente specificato. Sono incluse le migrazioni da Lync Server 2013, che non hanno mai avuto l'opzione `-MoveToTeams` .  In precedenza, se questa opzione non veniva specificata, gli utenti passavano dalla home page in Skype for Business Server locale a Skype for Business Online e la modalità rimaneva invariata. Questo è stato modificato in preparazione al ritiro di Skype for Business Online.
> - Lo spostamento degli utenti tra la distribuzione locale e Teams *richiede* ora versioni minime aggiornate dei componenti locali Skype for Business Server o Lync Server che non si basano più sull'infrastruttura legacy Skype for Business Online. Per informazioni dettagliate, vedere [Prerequisiti](move-users-between-on-premises-and-cloud.md#prerequisites).

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Spostare un utente direttamente da Skype for Business locale a Solo Teams

Gli strumenti di amministrazione locali in Skype for Business Server e Lync Server 2013 consentono di spostare gli utenti dall'ambiente locale alla modalità TeamsOnly in un unico passaggio usando il cmdlet Move-CsUser in PowerShell o il Skype for Business Server Pannello di controllo, come descritto di seguito. Non è più necessario specificare il `-MoveToTeams` commutatore e il comportamento per passare direttamente dall'ambiente locale a Solo Teams è ora automatico, indipendentemente dalla versione di Skype for Business Server o Lync Server usata. 

È necessario disporre di privilegi sufficienti sia nell'ambiente locale che nel servizio cloud (Microsoft 365 o Office 365), come descritto in [Credenziali amministrative necessarie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). È possibile usare un singolo account con privilegi in entrambi gli ambienti oppure avviare una finestra di Skype for Business Server Management Shell locale con credenziali locali e usare il `-Credential` parametro per specificare le credenziali per microsoft 365 con il ruolo amministrativo necessario.

Inoltre, è necessario assicurarsi che all'utente sia stata concessa una licenza per Teams (oltre a Skype for Business Online). Non disabilitare la licenza Skype for Business Online.

### <a name="move-to-teams-using-move-csuser"></a>Passare a Teams usando Move-CsUser

Move-CsUser è disponibile da una finestra di PowerShell di Skype for Business Server Management Shell locale o da una finestra di PowerShell di Lync Server Management Shell. Per spostare un utente in modalità TeamsOnly usando Move-CsUser:
- Specificare l'utente da spostare usando il `Identity` parametro .
- Specificare il `-Target` parametro con il valore "sipfed.online.lync.<span> com" (o valore simile se il tenant è cloud per enti pubblici).
- Se non si dispone di un account con autorizzazioni sufficienti sia in locale che nel servizio cloud (Microsoft 365), usare il `-credential` parametro per fornire un account con autorizzazioni sufficienti in Microsoft 365.
- Se l'account con autorizzazioni in Microsoft 365 non termina con "onmicrosoft.<span> com", è necessario specificare il `-HostedMigrationOverrideUrl` parametro , con il valore corretto come descritto in [Credenziali amministrative necessarie](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).
- Assicurarsi che il computer che esegue gli strumenti di amministrazione locali usi l'cu più recente per la versione di Skype for Business Server o Lync Server 2013, per assicurarsi che OAuth venga usato per l'autenticazione. 

La sequenza di cmdlet seguente può essere usata per spostare un utente in TeamsOnly e presuppone che le credenziali di Microsoft 365 siano un account separato e fornite come input per la richiesta di Get-Credential. Il comportamento è lo stesso se `-MoveToTeams` l'opzione è specificata o meno.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Poiché esistono circostanze diverse che richiedono parametri diversi, il comando predefinito per la maggior parte dei casi è:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Passare a Teams usando il pannello di controllo di Skype for Business Server

1. Aprire l'app Skype for Business Server Pannello di controllo.
2. Nel riquadro di spostamento a sinistra scegliere **Utenti**.
3. Usare **Trova** per individuare gli utenti che si desidera spostare in Teams.
4. Selezionare gli utenti e quindi nell'elenco a discesa **Azione** sopra l'elenco scegliere **Sposta utenti selezionati in Teams** o **Sposta utenti selezionati in Skype for Business Online**.   Entrambe le opzioni ora spostano gli utenti direttamente in TeamsOnly.
5. Nella procedura guidata fare clic su **Avanti**.
6. Se richiesto, accedere a Microsoft 365 con un account che termina con onmicrosoft.com e dispone di autorizzazioni sufficienti.
7. Fare clic su **Avanti** e quindi su **Avanti** un'altra volta per spostare l'utente.
8. I messaggi di stato relativi all'esito positivo o negativo vengono forniti nella parte superiore dell'app Pannello di controllo principale, non nella procedura guidata.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Notificare al Skype for Business utenti locali il prossimo passaggio a Teams

Gli strumenti di amministrazione locali in Skype for Business Server 2015 con CU8 e in Skype for Business Server 2019 consentono di notificare agli utenti Skype for Business locali il prossimo passaggio a Teams. Quando abiliti queste notifiche, gli utenti visualizzeranno una notifica nel client Skype for Business (Win32, Mac, Web e mobile), come illustrato di seguito. Se gli utenti cliccano sul pulsante **Prova** , il client di Teams verrà avviato se è installato; in caso contrario, gli utenti verranno passati alla versione Web di Teams nel browser. Per impostazione predefinita, quando le notifiche sono abilitate, Win32 Skype for Business client scaricano automaticamente il client teams in modo che il client completo sia disponibile prima di spostare l'utente in modalità TeamsOnly. Tuttavia, è anche possibile disabilitare questo comportamento.  Le notifiche vengono configurate usando la versione locale di `TeamsUpgradePolicy`e il download invisibile all'utente per i client Win32 viene controllato tramite il cmdlet locale `TeamsUpgradeConfiguration` .


![Notifica del prossimo passaggio a Teams.](../media/teams-upgrade-notification.png)

Per notificare agli utenti locali che saranno presto aggiornati a Teams, creare una nuova istanza di TeamsUpgradePolicy con NotifySfBUsers=true. Assegnare quindi tale criterio agli utenti a cui si vuole inviare una notifica, assegnando il criterio direttamente all'utente o impostando il criterio a livello di sito, pool o globale. I cmdlet seguenti creano e concedono criteri a livello di utente:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Il download automatico di Teams tramite il client Skype for Business Win32 viene controllato tramite il cmdlet TeamsUpgradeConfiguration locale con il parametro DownloadTeams. Questa configurazione viene creata a livello globale, di sito e di pool. Ad esempio, il comando seguente crea la configurazione per il sito Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

Per impostazione predefinita, il valore di DownloadTeams è True; tuttavia, viene rispettato *solo* se NotifySfbUser = True per un determinato utente.

## <a name="see-also"></a>Vedere anche

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Linee guida per la migrazione e l'interoperabilità di organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Coesistenza con Skype for Business](/microsoftteams/coexistence-chat-calls-presence)
