---
title: Uso del servizio di migrazione delle riunioni (MMS)
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Servizio di migrazione delle riunioni (MMS) è un servizio che viene eseguito in background e aggiorna automaticamente Skype for Business e Microsoft Teams riunioni per gli utenti. MMS è progettato per eliminare la necessità per gli utenti di eseguire lo strumento di migrazione delle riunioni per aggiornare le riunioni Skype for Business e Microsoft Teams riunioni.
ms.openlocfilehash: 68a3ef384c67835b25ff5db7ee6dfccf8b2ca1a7
ms.sourcegitcommit: a8965ff7b05ff600e3c426a4fff5fdba8b4c8b0b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2021
ms.locfileid: "58523867"
---
# <a name="using-the-meeting-migration-service-mms"></a>Uso del servizio di migrazione delle riunioni (MMS)

Il servizio di migrazione delle riunioni (MMS) è un servizio che aggiorna le riunioni esistenti di un utente negli scenari seguenti:

- Quando si esegue la migrazione di un utente dalla versione locale al cloud (Skype for Business Online o TeamsOnly).
- Quando un amministratore apporta una modifica alle impostazioni di audioconferenza dell'utente 
- Quando un utente online viene aggiornato a Teams o quando la modalità di un utente in TeamsUpgradePolicy è impostata su SfBwithTeamsCollabAndMeetings
- Quando si usa PowerShell 


Per impostazione predefinita, MMS viene attivato automaticamente in ognuno di questi casi, anche se gli amministratori possono disabilitarlo a livello di tenant. Inoltre, gli amministratori possono usare un cmdlet di PowerShell per attivare manualmente la migrazione delle riunioni per un determinato utente.


**Limitazioni:** il servizio di migrazione delle riunioni non può essere usato se si applica una delle condizioni seguenti:

- La cassetta postale dell'utente è ospitata in Exchange locale.
- È in corso la migrazione dell'utente dal cloud Skype for Business Server locale.


## <a name="how-mms-works"></a>Funzionamento di MMS

Quando MMS viene attivato per un determinato utente, una richiesta di migrazione per tale utente viene inserita in una coda. Per evitare condizioni di gara, la richiesta in coda viene deliberatamente elaborata solo dopo almeno 90 minuti. Dopo che MMS elabora la richiesta, esegue le attività seguenti:

1. Cerca nella cassetta postale dell'utente tutte le riunioni esistenti organizzate da quell'utente e pianificate in futuro.
2. In base alle informazioni disponibili nella cassetta postale dell'utente, aggiorna o pianifica nuove riunioni in Teams o Skype for Business Online per tale utente, a seconda dello scenario esatto.
3. Nel messaggio di posta elettronica sostituisce il blocco della riunione online nei dettagli della riunione.
4. Invia la versione aggiornata della riunione a tutti i destinatari della riunione per conto dell'organizzatore della riunione. Gli invitati riceveranno un aggiornamento della riunione con le coordinate aggiornate della riunione nel messaggio di posta elettronica. 

    ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Dal momento dell'attivazione del servizio MMS, la migrazione delle riunioni dell'utente richiede in genere circa 2 ore. Tuttavia, se l'utente ha un numero elevato di riunioni, potrebbe essere necessario più tempo. Se mms rileva un errore durante la migrazione di una o più riunioni per l'utente, ritenterà periodicamente fino a 9 volte nell'arco di 24 ore.

**Note**:

- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato. Questo significa che tutti i file allegati all'invito alla riunione verranno comunque inclusi. 
- Viene eseguita la migrazione solo delle riunioni Skype for Business o Microsoft Teams pianificate facendo clic sul pulsante Aggiungi riunione **Skype** in Outlook sul Web o usando il componente aggiuntivo Riunione Skype per Outlook. Se un utente copia e incolla le informazioni Skype riunione online da una riunione a una nuova riunione, la nuova riunione non verrà aggiornata perché non è presente alcuna riunione nel servizio originale.
- Il contenuto della riunione creato o allegato alla riunione (lavagne, sondaggi e così via) non verrà mantenuto dopo l'esecuzione di MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note della riunione effettive archiviate in OneNote saranno ancora presenti; è solo il collegamento alle note condivise che viene sovrascritto.
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
- Alcuni caratteri UNICODE nel corpo dell'invito potrebbero essere aggiornati in modo non corretto a uno dei caratteri speciali seguenti: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Attivazione di MMS per un utente

Questa sezione descrive cosa succede quando mms viene attivato in ognuno dei casi seguenti:

- Quando viene eseguita la migrazione di un utente da locale al cloud
- Quando un amministratore apporta una modifica alle impostazioni di audioconferenza dell'utente 
- Quando la modalità dell'utente in TeamsUpgradePolicy è impostata su TeamsOnly o SfBWithTeamsCollabAndMeetings (usando Powershell o il portale di amministrazione di Teams)
- Quando si usa il cmdlet powershell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aggiornamento delle riunioni quando si sposta un utente locale nel cloud

Questo è lo scenario più comune in cui MMS consente di creare una transizione più fluida per gli utenti. Senza la migrazione delle riunioni, le riunioni esistenti organizzate da un utente in Skype for Business Server locale non funzioneranno più dopo lo spostamento online dell'utente. Pertanto, quando si usano gli strumenti di amministrazione locali (o il Pannello di controllo dell'amministratore) per spostare un utente nel cloud, le riunioni esistenti vengono spostate automaticamente nel cloud nel `Move-CsUser` modo seguente:

- Se viene specificato l'interruttore, le riunioni vengono migrate direttamente Teams e l'utente `MoveToTeams` `Move-CsUser` sarà in modalità TeamsOnly. L'uso di questo parametro richiede Skype for Business Server 2015 con CU8 o versione successiva. Questi utenti possono comunque partecipare a Skype for Business riunione a cui possono essere invitati, usando il client Skype for Business o l'app Riunione Skype.
- In caso contrario, viene eseguita la migrazione delle riunioni a Skype for Business Online.

In entrambi i casi, se all'utente è stata assegnata una licenza di audioconferenza prima di essere spostata nel cloud, le riunioni verranno create con coordinate di accesso esterno. Se si sposta un utente dall'ambiente locale al cloud e si prevede che l'utente usi le audioconferenze, è consigliabile assegnare prima l'audioconferenza prima di spostare l'utente in modo che venga attivata solo la migrazione di una riunione.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni in caso di modifica delle impostazioni di audioconferenza di un utente

Nei casi seguenti, MMS aggiornerà le riunioni Skype for Business e Microsoft Teams per aggiungere, rimuovere o modificare le coordinate di accesso remoto:

- Quando si assegna o si rimuove una licenza del servizio di audioconferenza Microsoft a un utente e tale utente non è abilitato per un provider di servizi di audioconferenza di terze parti.
- Quando si cambia il provider di servizi di audioconferenza di un utente da qualsiasi altro provider a Microsoft, purché all'utente sia assegnata una licenza di audioconferenza Microsoft. Per altre informazioni, vedere [Assegnare Microsoft come provider di servizi di audioconferenza.](./assign-microsoft-as-the-audio-conferencing-provider.md) Si noti anche che il supporto per i provider di servizi di audioconferenza di terze parti [ACP] è previsto per la fine del ciclo di vita il 1° aprile 2019, come [annunciato in precedenza.](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- Quando si abilitano o si disabilitano le audioconferenze per un utente.
- Quando si modifica o si reimposta l'ID conferenza per un utente configurato per l'uso di riunioni pubbliche.
- Quando si sposta l'utente in un nuovo bridge di audioconferenza.
- Quando un numero di telefono da un bridge di audioconferenza non è assegnato. Si tratta di uno scenario complesso che richiede passaggi aggiuntivi. Per altre informazioni, vedere [Modificare i numeri di telefono nel bridge di audioconferenza.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

Non tutte le modifiche alle impostazioni di audioconferenza di un utente attivano il servizio MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:

- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
- Quando si modifica l'URL della riunione dell'organizzazione usando il `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aggiornamento delle riunioni durante l'assegnazione di TeamsUpgradePolicy

Per impostazione predefinita, la migrazione delle riunioni viene attivata automaticamente quando a un utente viene concessa un'istanza `TeamsUpgradePolicy` di con `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings` . Se non si vuole eseguire la migrazione delle riunioni quando si concede una di queste modalità, specificare in (se si usa PowerShell) o deselezionare la casella per eseguire la migrazione delle riunioni quando si imposta la modalità di coesistenza di un utente (se si usa il portale di amministrazione di `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` Teams).

Tenere presente anche quanto segue:

- La migrazione delle riunioni viene richiamata solo quando si concede `TeamsUpgradePolicy` un'autorizzazione per un utente specifico. Se si concede una concessione a livello di tenant o a livello di tenant, la `TeamsUpgradePolicy` migrazione delle riunioni non viene `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` richiamata. 
- A un utente può essere concessa la modalità TeamsOnly solo se l'utente è disponibile online. Gli utenti ospitati in locale devono essere spostati usando `Move-CsUser` come descritto in precedenza.
- La concessione di una modalità diversa da TeamsOnly o SfBWithTeamsCollabAndMeetings non converte le riunioni Teams esistenti in Skype for Business riunioni.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Attivare manualmente la migrazione delle riunioni tramite il cmdlet di PowerShell

Oltre alle migrazioni automatiche delle riunioni, gli amministratori possono attivare manualmente la migrazione delle riunioni per un utente eseguendo il cmdlet `Start-CsExMeetingMigration` . Questo cmdlet accoda una richiesta di migrazione per l'utente specificato.  Oltre al parametro `Identity` obbligatorio, accetta due parametri facoltativi, e , che consentono di specificare come `SourceMeetingType` eseguire la migrazione delle `TargetMeetingType` riunioni:

**TargetMeetingType:**

- L'uso specifica che Skype for Business riunioni rimangono Skype for Business e Teams `TargetMeetingType Current` riunioni rimangono Teams riunioni. Tuttavia, le coordinate delle audioconferenze potrebbero essere cambiate e le riunioni locali Skype for Business in Skype for Business Online. Questo è il valore predefinito per TargetMeetingType.
- Usando specifica che è necessario eseguire la migrazione di qualsiasi riunione esistente a Teams, indipendentemente dal fatto che la riunione sia ospitata in Skype for Business online o locale e indipendentemente dal fatto che siano necessari aggiornamenti per le `TargetMeetingType Teams` audioconferenze. 

**SourceMeetingType:**
- L'uso indica che Skype for Business le riunioni , sia locali che `SourceMeetingType SfB` online, devono essere aggiornate.
- Usando `SourceMeetingType Teams` indica che è necessario aggiornare solo Teams riunioni.
- `SourceMeetingType All`L'uso indica che le Skype for Business e le Teams devono essere aggiornate. Questo è il valore predefinito per SourceMeetingType.
    

L'esempio seguente mostra come avviare la migrazione delle riunioni per gli utenti ashaw@contoso.com in modo che tutte le riunioni siano migrate in Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gestione del servizio MMS

Usando Windows PowerShell, è possibile controllare lo stato delle migrazioni in corso, attivare manualmente la migrazione delle riunioni e disabilitare del tutto la migrazione. 

### <a name="check-the-status-of-meeting-migrations"></a>Controllare lo stato delle migrazioni alle riunioni

Usare il `Get-CsMeetingMigrationStatus` cmdlet per controllare lo stato delle migrazioni delle riunioni. Di seguito sono riportati alcuni esempi.

- Per ottenere uno stato di riepilogo di tutte le migrazioni MMS, eseguire il comando seguente che fornisce una visualizzazione tabulare di tutti gli stati di migrazione:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Per ottenere dettagli completi di tutte le migrazioni in un periodo di tempo specifico, usare i `StartTime` parametri e `EndTime` . Ad esempio, il comando seguente restituisce i dettagli completi su tutte le migrazioni che si sono verificate dal 1° ottobre 2018 all'8 ottobre 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Per verificare lo stato della migrazione per un utente specifico, usare il `Identity` parametro . Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se vengono visualizzati errori di migrazione, intervenire per risolvere questi problemi il più presto possibile, in quanto gli utenti non saranno in grado di accedere con accesso remoto alle riunioni organizzate da tali utenti finché non vengono risolti. Se `Get-CsMeetingMigrationStatus` vengono visualizzate migrazioni in uno stato non riuscito, eseguire questa procedura:
 
1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l'elenco degli utenti interessati e l'errore specifico che è stato segnalato:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Per ogni utente interessato, eseguire lo Strumento di migrazione delle riunioni per eseguire manualmente la migrazione delle riunioni.

3. Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:

    - Far creare agli utenti nuove riunioni Skype.
    - [Contattare l'assistenza](/microsoft-365/Admin/contact-support-for-business-products).

Il cmdlet può essere usato per recuperare lo stato delle migrazioni `Get-CsMeetingMigrationStatus` attivate negli ultimi 150 giorni. I record per le migrazioni precedenti a 150 giorni vengono eliminati dal sistema.

### <a name="enabling-and-disabling-mms"></a>Attivazione e disattivazione del servizio MMS

MMS è abilitato per impostazione predefinita per tutte le organizzazioni, ma può essere disabilitato nel modo seguente:

- Disabilitare completamente per il tenant. 
- Disabilitare solo per le modifiche relative alle audioconferenze. In questo caso, MMS verrà comunque eseguito quando si esegue la migrazione di un utente da locale al cloud o quando si concede la modalità TeamsOnly o SfBWithTeamsCollabAndMeetings in `TeamsUpgradePolicy` .

Ad esempio, è possibile eseguire manualmente la migrazione di tutte le riunioni o disabilitare temporaneamente MMS apportando modifiche sostanziali alle impostazioni di audioconferenza per l'organizzazione

Per verificare se MMS è abilitato per l'organizzazione, eseguire il comando seguente. MMS è abilitato se il `MeetingMigrationEnabled` parametro è `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Per abilitare o disabilitare completamente MMS, usare il `Set-CsTenantMigrationConfiguration` comando. Ad esempio, per disabilitare MMS, eseguire il comando seguente:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se MMS è abilitato nell'organizzazione e si vuole verificare se è abilitato per gli aggiornamenti delle audioconferenze, controllare il valore del parametro `AutomaticallyMigrateUserMeetings` nell'output da `Get-CsOnlineDialInConferencingTenantSettings` . Per abilitare o disabilitare MMS per le audioconferenze, usare `Set-CsOnlineDialInConferencingTenantSettings` . Ad esempio, per disabilitare MMS per le audioconferenze, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Spostare utenti tra locale e cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
