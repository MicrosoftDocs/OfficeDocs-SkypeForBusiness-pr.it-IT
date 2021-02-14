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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) è un servizio che viene eseguito in background e aggiorna automaticamente le riunioni di Skype for Business e Microsoft Teams per gli utenti. MMS è progettato per eliminare la necessità di eseguire lo strumento Meeting Migration Tool per aggiornare le riunioni di Skype for Business e Microsoft Teams.
ms.openlocfilehash: 9223102ef9c264fdafdb9f52ec74d6edb383f987
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47765348"
---
# <a name="using-the-meeting-migration-service-mms"></a>Uso del servizio MMS (Meeting Migration Service)

Il servizio MMS (Meeting Migration Service) è un servizio che aggiorna le riunioni esistenti di un utente negli scenari seguenti:

- Quando si esegue la migrazione di un utente dalla distribuzione locale al cloud, in Skype for Business Online o in TeamsOnly.
- Quando un amministratore apporta una modifica alle impostazioni per i servizi di audioconferenza 
- Quando un utente online viene aggiornato solo a Teams o quando la modalità di un utente in TeamsUpgradePolicy è impostata su SfBwithTeamsCollabAndMeetings
- Quando si usa PowerShell 


Per impostazione predefinita, il servizio MMS viene attivato automaticamente in ognuno di questi casi, anche se gli amministratori possono disabilitarlo a livello di tenant. Inoltre, gli amministratori possono usare un cmdlet di PowerShell per attivare manualmente la migrazione delle riunioni per un determinato utente.


**Limitazioni:** il servizio di migrazione delle riunioni non può essere usato se si verifica una delle condizioni seguenti:

- La cassetta postale dell'utente è ospitata in Exchange locale.
- È in corso la migrazione dell'utente dal cloud alla distribuzione locale di Skype for Business Server.

In queste situazioni, gli utenti finali possono invece usare lo strumento [Meeting Migration Tool](https://www.microsoft.com/download/details.aspx?id=51659) per eseguire la migrazione delle proprie riunioni.

## <a name="how-mms-works"></a>Come funziona il servizio MMS

Quando viene attivato il servizio MMS per un determinato utente, una richiesta di migrazione per quell'utente viene inserita in una coda. Per evitare condizioni di corsa, la richiesta in coda viene deliberatamente elaborata solo dopo che sono passati almeno 90 minuti. Dopo l'elaborazione della richiesta da parte del servizio MMS, vengono eseguite le attività seguenti:

1. Cerca nella cassetta postale dell'utente tutte le riunioni esistenti organizzate dall'utente e pianificate in futuro.
2. In base alle informazioni trovate nella cassetta postale dell'utente, aggiorna o pianifica nuove riunioni in Teams o Skype for Business online per quell'utente, a seconda dello scenario esatto.
3. Nel messaggio di posta elettronica sostituisce il blocco della riunione online nei dettagli della riunione.
4. Invia la versione aggiornata della riunione a tutti i destinatari della riunione per conto dell'organizzatore della riunione. Gli invitati riceveranno un aggiornamento della riunione con le coordinate aggiornate nel messaggio di posta elettronica. 

    ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Dal momento in cui viene attivato il servizio MMS, in genere sono necessari circa 2 ore prima che la migrazione delle riunioni dell'utente sia stata eseguita. Tuttavia, se l'utente ha un numero elevato di riunioni, potrebbe essere necessario più tempo. Se il servizio MMS riscontra un errore durante la migrazione di una o più riunioni per l'utente, verrà periodicamente riprovato fino a 9 volte nell'arco di 24 ore.

**Note:**

- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato. Ciò significa che tutti i file allegati all'invito alla riunione verranno comunque inclusi. 
- Vengono migrate solo le riunioni di Skype for Business o Microsoft Teams pianificate facendo clic sul pulsante Aggiungi riunione **Skype** in Outlook sul Web o usando il componente aggiuntivo Riunione Skype per Outlook. Se un utente copia e incolla le informazioni sulla riunione online Skype da una riunione a una nuova riunione, la nuova riunione non verrà aggiornata perché non c'è alcuna riunione nel servizio originale.
- Il contenuto della riunione creato o allegato alla riunione (lavagne, sondaggi e così via) non verrà conservato dopo l'esecuzione del servizio MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note effettive della riunione archiviate in OneNote saranno comunque presenti; è solo il collegamento alle note condivise che viene sovrascritto.
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
- Alcuni caratteri UNICODE nel corpo dell'invito potrebbero essere aggiornati erroneamente a uno dei seguenti caratteri speciali: ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Attivazione del servizio MMS per un utente

In questa sezione viene descritto cosa accade quando viene attivato il servizio MMS in ognuno dei casi seguenti:

- Quando viene eseguita la migrazione di un utente dalla distribuzione locale al cloud
- Quando un amministratore apporta una modifica alle impostazioni per i servizi di audioconferenza 
- Quando la modalità dell'utente in TeamsUpgradePolicy è impostata su TeamsOnly o SfBWithTeamsCollabAndMeetings (usando Powershell o il portale di amministrazione di Teams)
- Quando si usa il cmdlet di PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aggiornamento delle riunioni quando si sposta un utente locale nel cloud

Questo è lo scenario più comune in cui il servizio MMS consente di creare una transizione più agevole per gli utenti. Senza la migrazione delle riunioni, le riunioni esistenti organizzate da un utente in Skype for Business Server locale non funzioneranno più dopo lo spostamento online dell'utente. Di conseguenza, quando si usano gli strumenti di amministrazione locali (o il Pannello di controllo dell'amministratore) per spostare un utente nel cloud, le riunioni esistenti vengono automaticamente spostate nel cloud come `Move-CsUser` segue:

- Se si imposta l'opzione di accesso, le riunioni vengono migrate direttamente in Teams e `MoveToTeams` `Move-CsUser` l'utente sarà in modalità TeamsOnly. Per usare questo aggiornamento è necessario Skype for Business Server 2015 con CU8 o versione successiva. Questi utenti possono comunque partecipare a qualsiasi riunione Skype for Business a cui possono essere invitati usando il client Skype for Business o l'app per riunioni Skype.
- In caso contrario, le riunioni vengono migrate a Skype for Business online.

In entrambi i casi, se all'utente è stata assegnata una licenza per i servizi di audioconferenza prima di essere spostata nel cloud, le riunioni verranno create con coordinate per l'accesso esterno. Se si sposta un utente dalla distribuzione locale al cloud e si prevede di usare i servizi di audioconferenza, è consigliabile assegnare l'audioconferenza prima di spostare l'utente, in modo che venga attivata una sola migrazione delle riunioni.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni in caso di modifica delle impostazioni per i servizi di audioconferenza di un utente

Nei seguenti casi, il servizio MMS aggiornerà le riunioni esistenti di Skype for Business e Microsoft Teams per aggiungere, rimuovere o modificare le coordinate per l'accesso:

- Quando si assegna o si rimuove una licenza del servizio di audioconferenza Microsoft a un utente e tale utente non è abilitato per un provider di servizi di audioconferenza di terze parti.
- Quando cambi il provider di servizi di audioconferenza di un utente da qualsiasi altro provider a Microsoft, a condizione che all'utente sia assegnata una licenza per i servizi di audioconferenza Microsoft. Per ulteriori informazioni, consulta [Assegnare Microsoft come provider di servizi di audioconferenza.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider) Il supporto per i provider di servizi di audioconferenza di terze parti è pianificato per la fine del ciclo di vita il 1° aprile 2019, come annunciato [in precedenza.](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)
- Quando abiliti o disabiliti i servizi di audioconferenza per un utente.
- Quando si modifica o si reimposta l'ID conferenza di un utente configurato per l'uso di riunioni pubbliche.
- Quando si sposta l'utente in un nuovo bridge per audioconferenza.
- Quando un numero di telefono da un bridge per audioconferenza non è assegnato. Si tratta di uno scenario complesso che richiede passaggi aggiuntivi. Per ulteriori informazioni, consulta [Modificare i numeri di telefono nel bridge di audioconferenza.](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

Non tutte le modifiche alle impostazioni delle audioconferenze di un utente attivano il servizio MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:

- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
- Quando si modifica l'URL della riunione dell'organizzazione usando il `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aggiornamento delle riunioni durante l'assegnazione di TeamsUpgradePolicy

Per impostazione predefinita, la migrazione delle riunioni viene attivata automaticamente quando a un utente viene concessa un'istanza di `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings` . Se non si vuole eseguire la migrazione delle riunioni quando si concede una di queste modalità, specificare in (se si usa PowerShell) o deselezionare la casella per eseguire la migrazione delle riunioni quando si imposta la modalità di coesistenza di un utente (se si usa il portale di amministrazione di `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` Teams).

Tenere presente anche quanto segue:

- La migrazione delle riunioni viene richiamata solo quando si concede `TeamsUpgradePolicy` l'accesso a un utente specifico. Se si concede una migrazione delle riunioni con o a livello di tenant, la migrazione delle riunioni `TeamsUpgradePolicy` `mode=TeamsOnly` non viene `mode=SfBWithTeamsCollabAndMeetings` richiamata. 
- A un utente può essere concessa la modalità TeamsOnly solo se l'utente è ospitato online. Gli utenti ospitati in locale devono essere spostati come `Move-CsUser` descritto in precedenza.
- Se si concede una modalità diversa da TeamsOnly o SfBWithTeamsCollabAndMeetings, le riunioni esistenti di Teams non vengono convertite in riunioni Skype for Business.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Avviare manualmente la migrazione delle riunioni tramite il cmdlet di PowerShell

Oltre alle migrazioni automatiche delle riunioni, gli amministratori possono attivare manualmente la migrazione delle riunioni per un utente eseguendo il `Start-CsExMeetingMigration` cmdlet. Questo cmdlet accoda una richiesta di migrazione per l'utente specificato.  Oltre al parametro obbligatorio, accetta due parametri facoltativi, che consentono di specificare la modalità di migrazione `Identity` `SourceMeetingType` delle `TargetMeetingType` riunioni:

**TargetMeetingType:**

- L'uso specifica che le riunioni Skype for Business rimangono riunioni Skype for Business e le riunioni `TargetMeetingType Current` di Teams rimangono riunioni di Teams. Tuttavia, le coordinate dei servizi di audioconferenza potrebbero essere modificate e le riunioni Skype for Business locali vengono migrate a Skype for Business online. Questo è il valore predefinito per TargetMeetingType.
- L'uso specifica che qualsiasi riunione esistente deve essere migrata a Teams, indipendentemente dal fatto che la riunione sia ospitata in Skype for Business online o in locale, e indipendentemente dal fatto che siano necessari aggiornamenti per le `TargetMeetingType Teams` audioconferenze. 

**SourceMeetingType:**
- `SourceMeetingType SfB`L'uso indica che solo le riunioni Skype for Business (in locale o online) devono essere aggiornate.
- `SourceMeetingType Teams`L'uso indica che è necessario aggiornare solo le riunioni di Teams.
- L'uso indica che le riunioni di Skype for Business e `SourceMeetingType All` di Teams devono essere aggiornate. Questo è il valore predefinito per SourceMeetingType.
    

L'esempio seguente mostra come avviare la migrazione delle riunioni per gli utenti ashaw@contoso.com, in modo che tutte le riunioni siano migrate a Teams:

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gestione del servizio MMS

Con Windows PowerShell, è possibile controllare lo stato delle migrazioni in corso, attivare manualmente la migrazione delle riunioni e disabilitare completamente la migrazione. 

### <a name="check-the-status-of-meeting-migrations"></a>Controllare lo stato delle migrazioni delle riunioni

Usare il `Get-CsMeetingMigrationStatus` cmdlet per controllare lo stato delle migrazioni delle riunioni. Di seguito sono riportati alcuni esempi.

- Per ottenere un riepilogo di tutte le migrazioni MMS, eseguire il comando seguente, che fornisce una rappresentazione tabulare di tutti gli stati di migrazione:

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Per ottenere tutti i dettagli di tutte le migrazioni entro un periodo di tempo specifico, usare i `StartTime` parametri `EndTime` e. Ad esempio, il comando seguente restituisce tutti i dettagli su tutte le migrazioni che si sono verificati dal 1° ottobre 2018 al 8 ottobre 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Per controllare lo stato della migrazione per un utente specifico, usare il `Identity` parametro. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se si verificano migrazioni non riuscite, intervenire per risolvere questi problemi il più presto possibile, perché le persone non saranno in grado di accedere con accesso destro alle riunioni organizzate da tali utenti finché non vengono risolti. Se `Get-CsMeetingMigrationStatus` vengono visualizzate migrazioni non riuscite, procedere come segue:
 
1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Per ogni utente interessato, eseguire lo strumento di migrazione delle riunioni per eseguire manualmente la migrazione delle riunioni.

3. Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:

    - Far creare agli utenti nuove riunioni Skype.
    - [Contattare l'assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Attivazione e disattivazione del servizio MMS

MMS è abilitato per impostazione predefinita per tutte le organizzazioni, ma può essere disabilitato come segue:

- Disabilitare completamente per il tenant. 
- Disabilita solo per le modifiche relative ai servizi di audioconferenza. In questo caso, il servizio MMS verrà comunque eseguito quando si esegue la migrazione di un utente dalla distribuzione locale al cloud o quando si concede la modalità TeamsOnly o SfBWithTeamsCollabAndMeetings in `TeamsUpgradePolicy` .

Ad esempio, è possibile eseguire manualmente la migrazione di tutte le riunioni o disabilitare temporaneamente il servizio MMS apportando modifiche sostanziali alle impostazioni dei servizi di audioconferenza per l'organizzazione.

Per verificare se il servizio MMS è abilitato per l'organizzazione, eseguire il comando seguente. MMS è abilitato se `MeetingMigrationEnabled` il parametro è `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Per abilitare o disabilitare completamente il servizio MMS, usare il `Set-CsTenantMigrationConfiguration` comando. Ad esempio, per disabilitare il servizio MMS, eseguire il comando seguente:

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se il servizio MMS è abilitato nell'organizzazione e vuoi verificarlo per gli aggiornamenti delle audioconferenze, controlla il valore del parametro `AutomaticallyMigrateUserMeetings` nell'output di `Get-CsOnlineDialInConferencingTenantSettings` . Per abilitare o disabilitare il servizio MMS per i servizi di audioconferenza, utilizza `Set-CsOnlineDialInConferencingTenantSettings` . Ad esempio, per disabilitare il servizio MMS per i servizi di audioconferenza, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
