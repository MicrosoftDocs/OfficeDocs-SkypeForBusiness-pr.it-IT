---
title: Uso del servizio MMS (Meeting Migration Service)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) è un servizio che viene eseguito in background e aggiorna automaticamente Skype for Business e Microsoft Teams riunioni per gli utenti.
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671642"
---
# <a name="using-the-meeting-migration-service-mms"></a>Uso del servizio MMS (Meeting Migration Service)

Il servizio MMS (Meeting Migration Service) è un servizio che aggiorna le riunioni esistenti di un utente nei seguenti scenari:

- Quando viene eseguita la migrazione di un utente dalla distribuzione locale al cloud.
- Quando un amministratore apporta una modifica alle impostazioni dei servizi di audioconferenza dell'utente
- Quando un utente online viene aggiornato alla sola Teams o quando la modalità di un utente in TeamsUpgradePolicy è impostata su SfBwithTeamsCollabAndMeetings
- Quando si usa PowerShell

Per impostazione predefinita, il servizio MMS viene attivato automaticamente in ognuno di questi casi. Inoltre, gli amministratori possono usare un cmdlet di PowerShell per attivare manualmente la migrazione delle riunioni per un determinato utente.

**Limitazioni**: non è possibile usare il servizio di migrazione delle riunioni se si applica una delle condizioni seguenti:

- La cassetta postale dell'utente è ospitata in Exchange locale.
- Viene eseguita la migrazione dell'utente dal cloud a Skype for Business Server locale.

## <a name="how-mms-works"></a>Funzionamento del servizio MMS

Quando viene attivato il servizio MMS per un determinato utente, una richiesta di migrazione per tale utente viene inserita in coda. Per evitare qualsiasi condizione di gara, la richiesta in coda viene deliberatamente elaborata solo dopo almeno 90 minuti. Una volta che MMS elabora la richiesta, esegue le seguenti attività:

1. Cerca nella cassetta postale dell'utente tutte le riunioni esistenti organizzate dall'utente e pianificate in futuro.
2. In base alle informazioni trovate nella cassetta postale dell'utente, aggiorna o pianifica nuove riunioni in Teams per l'utente, a seconda dello scenario esatto.
3. Nel messaggio di posta elettronica sostituisce il blocco della riunione online nei dettagli della riunione.
4. Invia la versione aggiornata della riunione a tutti i destinatari della riunione per conto dell'organizzatore della riunione. Gli invitati alla riunione riceveranno un aggiornamento della riunione con coordinate aggiornate nel messaggio di posta elettronica.

    ![Il blocco della riunione che viene aggiornato dal servizio MMS.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Dal momento in cui viene attivato il servizio MMS, in genere sono necessarie circa 2 ore prima che venga eseguita la migrazione delle riunioni dell'utente. Tuttavia, se l'utente ha un numero elevato di riunioni, potrebbe richiedere più tempo. Se mms rileva un errore durante la migrazione di una o più riunioni per l'utente, periodicamente riprova fino a 9 volte nell'arco di 24 ore.

**Note**:

- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato. Ciò significa che tutti i file allegati all'invito alla riunione verranno comunque inclusi.
- Viene eseguita la migrazione solo delle riunioni Skype for Business o Microsoft Teams pianificate facendo clic sul pulsante **Aggiungi Skype riunione** in Outlook sul Web o usando il componente aggiuntivo Riunione Skype per Outlook. Se un utente copia e incolla il Skype informazioni sulla riunione online da una riunione a una nuova riunione, la nuova riunione non verrà aggiornata perché non esiste alcuna riunione nel servizio originale.
- Il contenuto della riunione creato o allegato alla riunione (lavagne, sondaggi e così via) non verrà conservato dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note della riunione effettive archiviate in OneNote saranno ancora presenti; solo il collegamento alle note condivise viene sovrascritto.
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
- Alcuni caratteri UNICODE nel corpo dell'invito potrebbero essere aggiornati in modo non corretto con uno dei seguenti caratteri speciali: ï, £, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Attivazione del servizio MMS per un utente

In questa sezione viene descritto cosa accade quando viene attivato il servizio MMS in ognuno dei seguenti casi:

- Quando viene eseguita la migrazione di un utente dalla versione locale al cloud
- Quando un amministratore apporta una modifica alle impostazioni dei servizi di audioconferenza dell'utente
- Quando la modalità dell'utente in TeamsUpgradePolicy è impostata su TeamsOnly o SfBWithTeamsCollabAndMeetings (usando Powershell o il portale di Teams Amministrazione)
- Quando si usa il cmdlet di PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aggiornamento delle riunioni quando si sposta un utente locale nel cloud

Questo è lo scenario più comune in cui il servizio MMS consente di creare una transizione più fluida per gli utenti. Senza la migrazione delle riunioni, le riunioni esistenti organizzate da un utente in Skype for Business Server locale non funzionerebbero più quando l'utente viene spostato online. Pertanto, quando si usano gli strumenti di amministrazione locali (`Move-CsUser`o il Amministrazione Pannello di controllo) per spostare un utente nel cloud, le riunioni esistenti vengono automaticamente spostate nel cloud e convertite in TeamsOnly.

Se all'utente è stata assegnata una licenza di Audioconferenza prima di essere spostato nel cloud, le riunioni verranno create con le coordinate per l'accesso. Se si sposta un utente dall'ambiente locale al cloud e si prevede che tale utente usi Audioconferenza, è consigliabile assegnare l'audioconferenza prima di spostare l'utente in modo che venga attivata solo una migrazione delle riunioni.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni quando cambiano le impostazioni dei servizi di audioconferenza di un utente

Nei seguenti casi, il servizio MMS aggiornerà le riunioni esistenti Skype for Business e Microsoft Teams per aggiungere, rimuovere o modificare le coordinate di accesso:

- Quando si assegna o si rimuove una licenza del servizio Microsoft Audioconferenza a un utente e tale utente non è abilitato per un provider di servizi di audioconferenza di terze parti.
- Quando modifichi il provider di servizi di audioconferenza di un utente da qualsiasi altro provider a Microsoft, a condizione che all'utente venga assegnata una licenza Microsoft Audioconferenza. Per ulteriori informazioni, vedi [Assegnare Microsoft come provider di servizi di audioconferenza](./assign-microsoft-as-the-audio-conferencing-provider.md). Tieni inoltre presente che il supporto per i provider di servizi di audioconferenza di terze parti [ACP] è pianificato per la fine del ciclo di vita il 1° aprile 2019, come [annunciato in precedenza](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).
- Quando abiliti o disabiliti le audioconferenze per un utente.
- Quando si modifica o si reimposta l'ID conferenza per un utente configurato per l'uso delle riunioni pubbliche.
- Quando sposti l'utente in un nuovo bridge per i servizi di audioconferenza.
- Quando un numero di telefono da un bridge di audioconferenza non è assegnato. Si tratta di uno scenario complesso che richiede passaggi aggiuntivi. Per ulteriori informazioni, vedi [Modificare i numeri di telefono nel bridge di audioconferenza](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Non tutte le modifiche alle impostazioni dei servizi di audioconferenza attivano il servizio MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:

- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
- Quando si modifica l'URL della riunione dell'organizzazione usando il `Update-CsTenantMeetingUrl` comando.

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aggiornamento delle riunioni durante l'assegnazione di TeamsUpgradePolicy

Per impostazione predefinita, la migrazione delle riunioni viene attivata automaticamente quando a un utente viene concessa un'istanza con `TeamsUpgradePolicy` `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings`. Se non si vuole eseguire la migrazione delle riunioni quando si concede una di queste modalità, specificare `MigrateMeetingsToTeams $false` (`Grant-CsTeamsUpgradePolicy`se si usa PowerShell) o deselezionare la casella per eseguire la migrazione delle riunioni quando si imposta la modalità di coesistenza di un utente (se si usa il Teams portale di amministrazione).

Si noti anche quanto segue:

- La migrazione delle riunioni viene richiamata solo quando si concede `TeamsUpgradePolicy` l'autorizzazione per un utente specifico. Se si concede `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode=SfBWithTeamsCollabAndMeetings` a *livello di tenant* , la migrazione delle riunioni non viene richiamata.
- A un utente può essere concessa la modalità TeamsOnly solo se l'utente è ospitato online. Gli utenti ospitati in locale devono essere spostati usando `Move-CsUser` come descritto in precedenza.
- La concessione di una modalità diversa da TeamsOnly o SfBWithTeamsCollabAndMeetings non converte le riunioni Teams esistenti in riunioni Skype for Business.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Attivare manualmente la migrazione delle riunioni tramite il cmdlet di PowerShell

Oltre alle migrazioni automatiche delle riunioni, gli amministratori possono attivare manualmente la migrazione delle riunioni per un utente eseguendo il cmdlet `Start-CsExMeetingMigration`. Questo cmdlet accoda una richiesta di migrazione per l'utente specificato.  Oltre al parametro obbligatorio`Identity`, sono necessari due parametri facoltativi e `TargetMeetingType`, `SourceMeetingType` che consentono di specificare come eseguire la migrazione delle riunioni:

**TargetMeetingType:**

- Tramite `TargetMeetingType Current` specifica che Skype for Business riunioni rimangono Skype for Business e Teams riunioni restano Teams riunioni. Tuttavia, le coordinate dei servizi di audioconferenza potrebbero essere modificate e tutte le riunioni Skype for Business locali verranno spostate in Skype for Business Online. Questo è il valore predefinito per TargetMeetingType.
- L'uso `TargetMeetingType Teams` specifica che è necessario eseguire la migrazione di una riunione esistente a Teams, indipendentemente dal fatto che la riunione sia ospitata in Skype for Business online o in locale e indipendentemente dal fatto che siano necessari aggiornamenti per i servizi di audioconferenza.

**SourceMeetingType:**

- Using `SourceMeetingType SfB` indica che è necessario aggiornare solo le riunioni Skype for Business (locali o online).
- Using `SourceMeetingType Teams` indica che solo Teams riunioni devono essere aggiornate.
- Using `SourceMeetingType All` indica che le riunioni Skype for Business e Teams devono essere aggiornate. Questo è il valore predefinito per SourceMeetingType.

L'esempio seguente mostra come avviare la migrazione delle riunioni per ashaw@contoso.com degli utenti in modo che tutte le riunioni vengano migrate in Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>Gestione del servizio MMS

Usando Windows PowerShell, è possibile controllare lo stato delle migrazioni in corso, attivare manualmente la migrazione delle riunioni e disabilitare completamente la migrazione.

### <a name="check-the-status-of-meeting-migrations"></a>Controllare lo stato delle migrazioni delle riunioni

`Get-CsMeetingMigrationStatus` Il cmdlet consente di controllare lo stato delle migrazioni delle riunioni. Di seguito sono riportati alcuni esempi.

- Per ottenere uno stato di riepilogo di tutte le migrazioni MMS, eseguire il comando seguente, che fornisce una visualizzazione tabulare di tutti gli stati di migrazione:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- Per ottenere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, usare i `StartTime` parametri e `EndTime` . Ad esempio, il comando seguente restituirà tutti i dettagli su tutte le migrazioni che si sono verificate dal 1° ottobre 2018 all'8 ottobre 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- Per controllare lo stato della migrazione per un utente specifico, usare il `Identity` parametro. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

Se vengono visualizzate migrazioni non riuscite, intervenire per risolvere questi problemi il più presto possibile, in quanto le persone non saranno in grado di accedere alle riunioni organizzate da tali utenti finché non vengono risolte. Se `Get-CsMeetingMigrationStatus` viene visualizzata una migrazione in uno stato non riuscito, eseguire questa procedura:

1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. Per ogni utente interessato, esaminare il valore della proprietà LastMessage per determinare perché la migrazione della riunione non è riuscita e quali azioni correttive intraprendere. Dopo aver intrapreso un'azione correttiva, attivare di nuovo la migrazione delle riunioni per gli utenti interessati, usando la `Start-CsExMeetingMigration` cmldet di PowerShell, come descritto in precedenza.

3. Se la migrazione continua a non funzionare, sono disponibili due opzioni:

    - Far creare agli utenti nuove riunioni Skype.
    - [Contattare l'assistenza](/microsoft-365/Admin/contact-support-for-business-products).

Il `Get-CsMeetingMigrationStatus` cmdlet può essere usato per recuperare lo stato delle migrazioni che sono state attivate negli ultimi 150 giorni. I record per le migrazioni precedenti a 150 giorni vengono eliminati dal sistema.

### <a name="enabling-and-disabling-mms"></a>Attivazione e disattivazione del servizio MMS

Il servizio MMS è abilitato per impostazione predefinita per tutte le organizzazioni, ma può essere disabilitato nel modo seguente:

- Disabilita completamente per il tenant.
- Disabilita solo per le modifiche relative ai servizi di audioconferenza. In questo caso, il servizio MMS verrà comunque eseguito quando viene eseguita la migrazione di un utente dall'ambiente locale al cloud o quando concedi la modalità TeamsOnly o SfBWithTeamsCollabAndMeetings in `TeamsUpgradePolicy`.

Ad esempio, è possibile eseguire manualmente la migrazione di tutte le riunioni o disabilitare temporaneamente il servizio MMS apportando modifiche sostanziali alle impostazioni dei servizi di audioconferenza per l'organizzazione

Per verificare se il servizio MMS è abilitato per l'organizzazione, eseguire il comando seguente. MMS è abilitato se il `MeetingMigrationEnabled` parametro è `$true`.

```PowerShell
Get-CsTenantMigrationConfiguration
```

Se il servizio MMS è abilitato nell'organizzazione e vuoi verificare se è abilitato per gli aggiornamenti dei servizi di audioconferenza, controlla il valore del `AutomaticallyMigrateUserMeetings` parametro nell'output da `Get-CsOnlineDialInConferencingTenantSettings`. Per abilitare o disabilitare il servizio MMS per i servizi di audioconferenza, utilizzare `Set-CsOnlineDialInConferencingTenantSettings`. Ad esempio, per disabilitare il servizio MMS per i servizi di audioconferenza, esegui il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Argomenti correlati

[Prova o acquista Audioconferenza in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Spostare utenti tra locale e cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
