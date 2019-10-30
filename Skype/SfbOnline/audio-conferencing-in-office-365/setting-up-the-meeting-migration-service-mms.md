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
f1keywords: None
ms.custom:
- Audio Conferencing
description: Il servizio di migrazione delle riunioni (MMS) è un servizio che viene eseguito in background e aggiorna automaticamente le riunioni di Skype for business e Microsoft teams per gli utenti. MMS è progettato per eliminare la necessità per gli utenti di eseguire lo strumento di migrazione delle riunioni per aggiornare le riunioni di Skype for business e Microsoft teams.
ms.openlocfilehash: 3f643f20937fd13b0d9576640487da30f17dd7bf
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772280"
---
# <a name="using-the-meeting-migration-service-mms"></a>Uso del servizio di migrazione delle riunioni (MMS)

Il servizio di migrazione delle riunioni (MMS) è un servizio che aggiorna le riunioni esistenti di un utente negli scenari seguenti:

- Quando un utente viene migrato dal locale al cloud (sia Skype for business online che TeamsOnly).
- Quando un amministratore apporta una modifica alle impostazioni di conferenza audio dell'utente 
- Quando un utente online viene aggiornato solo ai team oppure quando la modalità di un utente in TeamsUpgradePolicy è impostata su SfBwithTeamsCollabAndMeetings
- Quando si usa PowerShell 


Per impostazione predefinita, MMS viene attivato automaticamente in ognuno di questi casi, anche se gli amministratori possono disabilitarlo a livello di tenant. Inoltre, gli amministratori possono usare un cmdlet di PowerShell per attivare manualmente la migrazione delle riunioni per un utente specifico.


**Limitazioni**: il servizio di migrazione delle riunioni non può essere usato se si applica una delle opzioni seguenti:

- La cassetta postale dell'utente è ospitata in Exchange locale.
- L'utente viene migrato dal cloud a Skype for Business Server locale.

In questi casi, gli utenti finali possono usare lo [strumento di migrazione delle riunioni](https://www.microsoft.com/en-us/download/details.aspx?id=51659) per eseguire la migrazione delle proprie riunioni.

## <a name="how-mms-works"></a>Funzionamento di MMS

Quando viene attivato MMS per un utente specifico, viene inserita in una coda una richiesta di migrazione per l'utente. Per evitare qualsiasi condizione di competizione, la richiesta in coda non viene elaborata intenzionalmente fino a quando non si sono verificati almeno 90 minuti. Quando MMS elabora la richiesta, esegue le attività seguenti:

1. Esegue la ricerca nella cassetta postale dell'utente per tutte le riunioni esistenti organizzate dall'utente e pianificate in futuro.
2. In base alle informazioni contenute nella cassetta postale dell'utente, aggiorna o Pianifica nuove riunioni in teams o in Skype for business online per l'utente, a seconda dello scenario esatto.
3. Nel messaggio di posta elettronica sostituisce il blocco riunione online nei dettagli della riunione.
4. Invia la versione aggiornata di tale riunione a tutti i destinatari delle riunioni per conto dell'organizzatore della riunione. Gli invitati alla riunione riceveranno un aggiornamento delle riunioni con le coordinate della riunione aggiornate nel messaggio di posta elettronica. 

    ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Dal momento in cui viene attivato MMS, in genere dura circa 2 ore fino alla migrazione delle riunioni dell'utente. Tuttavia, se l'utente ha un numero elevato di riunioni, potrebbe essere necessario più tempo. Se MMS incontra un errore durante la migrazione di una o più riunioni per l'utente, ritenterà periodicamente fino a 9 volte nell'arco di 24 ore.

**Note**:

- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.
- Solo le riunioni di Skype for business o Microsoft teams programmate facendo clic sul pulsante **Aggiungi riunione Skype** in Outlook sul Web o usando il componente aggiuntivo riunione Skype per Outlook vengono migrati. Se un utente copia e incolla le informazioni sulla riunione Skype online da una riunione a una nuova riunione, la nuova riunione non verrà aggiornata perché non è presente alcuna riunione nel servizio originale.
- Il contenuto della riunione creato o allegato alla riunione (lavagne, sondaggi e così via) non verrà mantenuto dopo l'esecuzione di MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Tieni presente che le note della riunione effettive archiviate in OneNote saranno ancora presenti; è solo il collegamento alle note condivise che vengono sovrascritte.
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
- Alcuni caratteri UNICODE nel corpo dell'invito potrebbero essere aggiornati in modo errato su uno dei caratteri speciali seguenti: ï, ¿, ½.

## <a name="triggering-mms-for-a-user"></a>Attivazione di MMS per un utente

Questa sezione descrive cosa accade quando il MMS viene attivato in ognuno dei casi seguenti:

- Quando un utente viene migrato dal locale al cloud
- Quando un amministratore apporta una modifica alle impostazioni di conferenza audio dell'utente 
- Quando la modalità dell'utente in TeamsUpgradePolicy è impostata su TeamsOnly o SfBWithTeamsCollabAndMeetings (usando PowerShell o il portale di amministrazione di Teams)
- Quando si usa il cmdlet di PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aggiornamento delle riunioni quando si trasferisce un utente locale nel cloud

Questo è lo scenario più comune in cui MMS consente di creare una transizione più fluida per gli utenti. Senza la migrazione delle riunioni, le riunioni esistenti organizzate da un utente in Skype for Business Server locale non funzionano più quando l'utente viene spostato online. Pertanto, quando si usano gli strumenti di amministrazione locali ( `Move-CsUser` o il pannello di controllo dell'amministratore) per spostare un utente nel cloud, le riunioni esistenti vengono automaticamente spostate nel cloud come segue:

- Se `Move-CsUser` viene `MoveToTeams` specificato l'opzione, le riunioni vengono migrate direttamente a teams e l'utente sarà in modalità TeamsOnly. L'uso di questo switch richiede Skype for Business Server 2015 con CU8 o versioni successive. Questi utenti possono comunque partecipare a qualsiasi riunione Skype for business a cui possono essere invitati, usando il client Skype for business o l'app riunione Skype.
- In caso contrario, le riunioni vengono migrate in Skype for business online.

In entrambi i casi, se all'utente è stata assegnata una licenza di audioconferenza prima di essere spostata nel cloud, le riunioni verranno create con le coordinate di accesso esterno. Se si sposta un utente da locale al cloud e si vuole che l'utente usi i servizi di audioconferenza, è consigliabile prima di tutto assegnare la conferenza audio prima di spostarla in modo che venga attivata solo una migrazione di una riunione.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni quando cambiano le impostazioni di conferenza audio di un utente

Nei casi seguenti, MMS aggiornerà le riunioni esistenti di Skype for business e Microsoft teams per aggiungere, rimuovere o modificare le coordinate di accesso esterno:

- Quando si assegna o si rimuove una licenza di servizio di audioconferenza Microsoft per un utente e tale utente non è abilitato per un provider di servizi di audioconferenza di terze parti.
- Quando si modifica il provider di servizi di audioconferenza di un utente da qualsiasi altro provider in Microsoft, a condizione che all'utente sia assegnata una licenza per Microsoft Audio Conferencing. Per altre informazioni, vedere [assegnare Microsoft come provider di servizi di audioconferenza](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Si noti inoltre che il supporto per i provider di servizi di audioconferenza di terze parti [ACP] è programmato per la fine del ciclo di vita del 1 ° aprile 2019, come [annunciato in precedenza](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Quando si abilitano o si disabilitano i servizi di audioconferenza per un utente.
- Quando si cambia o si reimposta l'ID conferenza per un utente configurato per l'utilizzo di riunioni pubbliche.
- Quando si trasferisce l'utente in un nuovo Bridge di audioconferenza.
- Quando un numero di telefono da un Bridge di audioconferenza non è assegnato. Si tratta di uno scenario complesso che richiede passaggi aggiuntivi. Per altre informazioni, vedere [modificare i numeri di telefono nel Bridge di audioconferenza](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Non tutte le modifiche apportate alle impostazioni di audioconferenza di un utente attivano MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:

- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
- Quando si modifica l'URL della riunione dell'organizzazione usando `Update-CsTenantMeetingUrl` il comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aggiornamento delle riunioni durante l'assegnazione di TeamsUpgradePolicy

Per impostazione predefinita, la migrazione delle `TeamsUpgradePolicy` riunioni viene attivata automaticamente quando a un utente viene assegnata `mode=TeamsOnly` un' `mode= SfBWithTeamsCollabAndMeetings`istanza with o. Se non si vuole eseguire la migrazione delle riunioni quando si concede una di queste modalità, specificare `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (se si usa PowerShell) o deselezionare la casella per eseguire la migrazione delle riunioni quando si imposta la modalità di coesistenza di un utente (se si usa il portale di amministrazione di Teams).

Tenere inoltre presente quanto segue:

- La migrazione delle riunioni viene richiamata solo `TeamsUpgradePolicy` quando si concede un utente specifico. Se si concede `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode=SfBWithTeamsCollabAndMeetings` su una base a *livello di tenant* , la migrazione delle riunioni non viene richiamata.
- Un utente può concedere solo la modalità TeamsOnly se l'utente è ospitato online. Gli utenti ospitati in locale devono essere spostati usando `Move-CsUser` come descritto in precedenza.
- La concessione di una modalità diversa da TeamsOnly o SfBWithTeamsCollabAndMeetings non converte le riunioni di team esistenti in riunioni Skype for business.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Attivare manualmente la migrazione delle riunioni tramite il cmdlet di PowerShell

Oltre alle migrazioni automatiche delle riunioni, gli amministratori possono attivare manualmente la migrazione delle riunioni per un utente eseguendo il `Start-CsExMeetingMigration`cmdlet. Questo cmdlet accoda una richiesta di migrazione per l'utente specificato.  Oltre al parametro obbligatorio `Identity` , sono necessari due parametri facoltativi `SourceMeetingType` e `TargetMeetingType`, che consentono di specificare come eseguire la migrazione delle riunioni:

**TargetMeetingType:**

- Usando `TargetMeetingType Current` specifica che le riunioni di Skype for business rimangono riunioni di Skype for business e le riunioni di team rimangono riunioni di teams. Le coordinate per i servizi di audioconferenza potrebbero tuttavia essere modificate e tutte le riunioni Skype for business locali verranno migrate in Skype for business online. Questo è il valore predefinito per TargetMeetingType.
- L' `TargetMeetingType Teams` uso di specifica che deve essere eseguita la migrazione di una riunione esistente a teams, indipendentemente dal fatto che la riunione sia ospitata in Skype for business online o in locale e indipendentemente dal fatto che siano necessari aggiornamenti per le conferenze audio. 

**SourceMeetingType:**
- L' `SourceMeetingType SfB` uso indica che devono essere aggiornate solo le riunioni di Skype for business (sia in locale che online).
- L' `SourceMeetingType Teams` uso indica che devono essere aggiornate solo le riunioni di teams.
- L' `SourceMeetingType All` uso indica che le riunioni di skyep for business e di teams devono essere aggiornate. Questo è il valore predefinito per SourceMeetingType.
    

L'esempio seguente illustra come avviare la migrazione delle riunioni per gli utenti di ashaw@contoso.com in modo che tutte le riunioni vengano migrate in teams:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gestione del servizio MMS

Usando Windows PowerShell, è possibile controllare lo stato delle migrazioni in corso, attivare manualmente la migrazione delle riunioni e disabilitare completamente la migrazione. 

### <a name="check-the-status-of-meeting-migrations"></a>Controllare lo stato delle migrazioni delle riunioni

Puoi usare il `Get-CsMeetingMigrationStatus` cmdlet per verificare lo stato delle migrazioni delle riunioni. Di seguito sono riportati alcuni esempi.

- Per ottenere uno stato di riepilogo di tutte le migrazioni MMS, eseguire il comando seguente che fornisce una visualizzazione tabulare di tutti gli Stati di migrazione:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Per ottenere i dettagli completi di tutte le migrazioni entro un determinato periodo di tempo, `StartTime` usare `EndTime` i parametri e. Ad esempio, il comando seguente restituirà tutti i dettagli di tutte le migrazioni che si sono verificate dal 1 ° ottobre 2018 all'8 ottobre 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Per controllare lo stato della migrazione per un utente specifico, usa il `Identity` parametro. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se vengono visualizzate eventuali migrazioni non riuscite, eseguire le operazioni necessarie per risolvere questi problemi il prima possibile, poiché gli utenti non potranno accedere alle riunioni organizzate da questi ultimi fino a quando non vengono risolti. Se `Get-CsMeetingMigrationStatus` Mostra le migrazioni in uno stato non riuscito, eseguire la procedura seguente:
 
1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Per ogni utente interessato, Esegui lo strumento di migrazione delle riunioni per eseguire manualmente la migrazione delle riunioni.

3. Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:

    - Far creare agli utenti nuove riunioni Skype.
    - [Contattare l'assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Attivazione e disattivazione del servizio MMS

MMS è abilitato per impostazione predefinita per tutte le organizzazioni, ma può essere disabilitato nel modo seguente:

- Disabilitare completamente per il tenant. 
- Disabilitare solo le modifiche relative ai servizi di audioconferenza. In questo caso, MMS verrà comunque eseguito quando un utente viene migrato da locale al cloud o quando si concede la modalità TeamsOnly o SfBWithTeamsCollabAndMeetings `TeamsUpgradePolicy`.

Ad esempio, è possibile eseguire manualmente la migrazione di tutte le riunioni o disabilitare temporaneamente il MMS mentre si apportano modifiche sostanziali alle impostazioni dei servizi di audioconferenza per l'organizzazione

Per verificare se MMS è abilitato per l'organizzazione, eseguire il comando seguente. MMS è abilitato se il `MeetingMigrationEnabled` parametro è `$true`.
```
Get-CsTenantMigrationConfiguration
```
Per abilitare o disabilitare completamente MMS, usare il `Set-CsTenantMigrationConfiguration` comando. Ad esempio, per disabilitare MMS, eseguire il comando seguente:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se MMS è abilitato nell'organizzazione e si vuole verificare se è abilitato per gli aggiornamenti di audioconferenza, controllare il valore del `AutomaticallyMigrateUserMeetings` parametro nell'output from. `Get-CsOnlineDialInConferencingTenantSettings` Per abilitare o disabilitare MMS per i servizi di audioconferenza `Set-CsOnlineDialInConferencingTenantSettings`, usare. Ad esempio, per disabilitare MMS per i servizi di audioconferenza, eseguire il comando seguente:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
