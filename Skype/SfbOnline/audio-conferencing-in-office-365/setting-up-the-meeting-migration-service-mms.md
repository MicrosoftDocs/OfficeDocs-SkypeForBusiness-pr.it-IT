---
title: Utilizzare il servizio di migrazione Meeting MMS)
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Migrazione servizio MMS delle riunioni è un servizio che viene eseguito in background e vengono aggiornati automaticamente Skype per le riunioni aziendali e Teams Microsoft per gli utenti. MMS è progettato per eliminare la necessità di agli utenti di eseguire lo strumento di migrazione di riunioni per aggiornare i Skype per le riunioni aziendali e Teams Microsoft.
ms.openlocfilehash: 90953f1352f54a8411513a78ccfda8bfb5356883
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229242"
---
# <a name="using-the-meeting-migration-service-mms"></a>Utilizzare il servizio di migrazione Meeting MMS)

La riunione migrazione servizio MMS è servizio per l'aggiornamento di riunioni esistenti di un utente nei casi seguenti:

- Quando un utente viene eseguita la migrazione da locale per il cloud (se Skype Business online o TeamsOnly).
- Quando un amministratore apporta una modifica per le impostazioni dell'utente audioconferenze con accesso esterno 
- Quando un utente in linea viene aggiornato per team solo o quando la modalità di un utente in TeamsUpgradePolicy è impostata su SfBwithTeamsCollabAndMeetings (solo i clienti scegliere)
- Quando si utilizza PowerShell 


Per impostazione predefinita, MMS viene attivata automaticamente in ognuno di questi casi, anche se gli amministratori possono disabilitare a livello di tenant. Inoltre, gli amministratori è possono utilizzare un cmdlet di PowerShell attivare manualmente la migrazione di riunioni per un utente specificato.

> [!NOTE]
> La possibilità di convertire Skype per le riunioni Business alle riunioni di team e la possibilità di aggiornare riunioni team esistenti per modificare le impostazioni di audioconferenza è attualmente limitato ai clienti di scegliere solo. Microsoft prevede che rendere disponibile questa funzionalità per tutti i clienti rimasta in maggio 2019.

**Limitazioni**: la riunione non è possibile utilizzare il servizio di migrazione se nelle situazioni seguenti:

- Cassetta postale dell'utente è ospitata in Exchange locale.
- L'utente viene eseguita la migrazione dal cloud a Skype per Business Server locale.

In questi casi, gli utenti finali possono utilizzare lo [Strumento di migrazione di riunioni](https://www.microsoft.com/en-us/download/details.aspx?id=51659) per migrare le proprie riunioni invece.

## <a name="how-mms-works"></a>Funzionamento di MMS

Se MMS è attivato per un determinato utente, viene effettuata una richiesta di migrazione per l'utente in una coda. Per evitare qualsiasi race condition, le richieste in coda intenzionalmente non viene elaborata fino a quando non hanno lasciato almeno 90 minuti. Una volta MMS elabora la richiesta, esegue le attività seguenti:

1. Esegue la ricerca della cassetta postale dell'utente per tutte le riunioni organizzate dall'utente e pianificate in futuro.
2. In base alle informazioni disponibili nella cassetta postale dell'utente, aggiornato o pianifica le nuove riunioni in team o Skype Business online di quell'utente, a seconda dello scenario.
3. Nel messaggio di posta elettronica, che sostituisce il blocco di riunione in linea nei dettagli della riunione.
4. Invia la versione aggiornata di tale riunione a tutti i destinatari di riunione per conto di organizzatore della riunione. Invitati riceverà aggiornamento di una riunione con Live meeting aggiornato coordinate nella loro posta elettronica. 

    ![Il blocco della riunione che viene aggiornato da MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Dal momento in cui che viene attivato MMS, in genere necessario circa 2 ore fino a quando non vengono eseguita la migrazione di riunioni dell'utente. Tuttavia, se l'utente dispone di un numero elevato di riunioni, può richiedere più tempo. Se MMS rileva un errore di migrazione di uno o più riunioni dell'utente, verrà periodicamente tentativi fino a 9 tramite l'intervallo di 24 ore.

**Note**:

- Il servizio MMS sostituisce tutto il contenuto del blocco di informazioni sulla riunione online quando la riunione viene migrata. Pertanto, se un utente ha modificato tale blocco, le modifiche verranno sovrascritte. Qualsiasi contenuto nei dettagli della riunione al di fuori del blocco di informazioni sulla riunione online non sarà influenzato.
- Viene eseguita la migrazione solo il Skype per Business o Microsoft Teams riunioni pianificate facendo clic sul pulsante **Aggiungi Skype riunione** in Outlook sul Web oppure utilizzando il componente aggiuntivo riunione Skype per Outlook. Se un utente copia e Incolla le informazioni sulla riunione in linea di Skype da una riunione a una nuova riunione, tale nuova riunione non vengono aggiornati in quanto non esiste alcun riunione nel servizio originale.
- Contenuto che è stato creato o associato alla riunione (lavagne, sondaggi e così via) della riunione non verrà mantenuta dopo l'esecuzione del MMS. Se gli organizzatori della riunione hanno allegato contenuti alle riunioni in anticipo, il contenuto dovrà essere ricreato dopo l'esecuzione del servizio MMS.
- Il collegamento alle note della riunione condiviso nella voce del calendario e dall'interno della riunione Skype verrà a sua volta sovrascritto. Si noti che le note delle riunioni effettivo archiviate in OneNote ancora essere è solo il collegamento alle note condivise che viene sovrascritto.
- Le riunioni con più di 250 partecipanti (incluso l'organizzatore) non possono essere migrate.
- Solo alcuni caratteri UNICODE nel corpo dell'invito potrebbe essere aggiornati in modo errato a uno dei caratteri speciali seguenti: ï, tempo, ½,.

## <a name="triggering-mms-for-a-user"></a>Attivazione del MMS per un utente

In questa sezione viene descritto il comportamento quando viene attivata MMS in ognuno dei casi seguenti:

- Quando un utente viene eseguita la migrazione in locale nel cloud
- Quando un amministratore apporta una modifica per le impostazioni dell'utente audioconferenze con accesso esterno 
- Quando la modalità dell'utente in TeamsUpgradePolicy è impostata su TeamsOnly o SfBWithTeamsCollabAndMeetings (solo i clienti scegliere)
- Quando si utilizza PowerShell 

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Aggiornamento delle riunioni quando si sposta un utente locale al cloud

Questo è lo scenario più comune dove MMS consente di creare una transizione più uniforme per gli utenti. Senza la migrazione di riunioni, riunioni esistenti organizzate da un utente in Skype Business Server locali potrebbero non funzionano più dopo lo spostamento dell'utente è online. Pertanto, quando si utilizzano gli strumenti di amministrazione locale (il `Move-CsUser` o il pannello di controllo Admin) per spostare un utente nel cloud, riunioni esistenti vengono automaticamente spostate nel cloud come indicato di seguito:

- Se il `MoveToTeams` passare `Move-CsUser` è specificato, vengono eseguita la migrazione di riunioni direttamente al team. Utilizzo di questa opzione richiede Skype per Business Server con CU8 o versione successiva.
- In caso contrario le riunioni vengono migrate in Skype Business online.

In entrambi i casi, se l'utente è stata assegnata una licenza di conferenze Audio prima di essere spostati nel cloud, le riunioni saranno create con le coordinate dial-in. Se si sposta un utente in locale al cloud che si prevede di quell'utente da utilizzare per conferenze Audio, è consigliabile assegnare all'audioconferenza innanzitutto prima di spostare l'utente in modo che la migrazione di riunioni solo 1 viene attivata.

> [!NOTE]
> Attualmente la possibilità di eseguire la migrazione di riunioni direttamente al team tramite l'opzione MoveToTeams è disponibile solo in TOCCO. Se non è un cliente di scegliere e viene specificata l'opzione MoveToTeams, verrà spostato l'utente alla modalità TeamsOnly, ma verranno spostate le riunioni Skype Business online. Anche se l'utente è in modalità TeamsOnly, qualsiasi Skype per le riunioni aziendali possono comunque partecipare.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Aggiornamento delle riunioni quando modificano le impostazioni di conferenza audio di un utente

Nei casi seguenti, MMS aggiornerà Skype esistente per le riunioni aziendali e Teams Microsoft per aggiungere, rimuovere o modificare le coordinate telefonica:

- Quando si assegnare o rimuovere una licenza di servizio di audioconferenza Microsoft a un utente e l'utente non è abilitati per un provider di servizi di conferenza audio di terze parti.
- Quando si modifica il provider di servizi di conferenza audio di un utente da qualsiasi altro provider per forniti da Microsoft, l'utente viene assegnata una licenza di Microsoft audioconferenze con accesso esterno. Per ulteriori informazioni, vedere [Microsoft assegnare come provider di servizi di conferenza audio](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Si noti inoltre che il supporto per il provider di audioconferenza di terze parti [ACP] pianificato per la fine del ciclo di vita su 1 aprile 2019, come [annunciato in precedenza](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Quando si attiva o disattiva audioconferenze con accesso esterno di un utente.
- Quando si modifica o Reimposta l'ID conferenza per un utente configurato per utilizzare le riunioni pubbliche.
- Quando l'utente si passa a un ponte per conferenze audio nuovo.
- Quando un numero di telefono da un ponte per conferenze audio è non assegnato. Si tratta di uno scenario complesso che richiede passaggi aggiuntivi. Per ulteriori informazioni, vedere [modificare i numeri di telefono del ponte per conferenze audio](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Non tutte le modifiche alle impostazioni di conferenza audio di un utente attivano MMS. In particolare, le seguenti due modifiche non faranno aggiornare le riunioni dal servizio MMS:

- Quando si modifica l'indirizzo SIP per l'organizzatore della riunione (il nome utente SIP o il dominio SIP)
- Quando si modifica l'organizzazione della riunione URL tramite il `Update-CsTenantMeetingUrl` comando.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Aggiornamento delle riunioni durante l'assegnazione TeamsUpgradePolicy

> [!NOTE]
> In questa sezione viene descritta funzionalità che è attualmente disponibile per i clienti di scegliere solo. Microsoft prevede che rendere disponibile questa funzionalità per tutti i clienti rimasta in maggio 2019.

Per impostazione predefinita, la migrazione delle riunioni verrà automaticamente attivata quando un utente viene concesso a un'istanza di `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode= SfBWithTeamsCollabAndMeetings`. Se non si desidera eseguire la migrazione di riunioni quando è necessario concedere una di queste modalità, quindi specificare `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy`.

Tenere inoltre presente quanto segue:

- Migrazione della riunione viene richiamata solo quando si concede `TeamsUpgradePolicy` per uno specifico utente. Se si concede `TeamsUpgradePolicy` con `mode=TeamsOnly` o `mode=SfBWithTeamsCollabAndMeetings` in base a livello di tenant, la migrazione della riunione non viene richiamata.
- Un utente può essere concesso solo TeamsOnly modalità se l'utente è ospitato in linea. Gli utenti che sono ospitati in locale devono essere spostati mediante `Move-CsUser` come descritto in precedenza.
- Concessione di una modalità diverso da TeamsOnly o SfBWithTeamsCollabAndMeetings non converte riunioni team esistenti Skype per le riunioni di Business.

### <a name="trigger-meeting-migration-manually-via-powershell"></a>Migrazione di riunioni trigger manualmente tramite PowerShell

Oltre alle migrazioni riunione automatica, gli amministratori possono attivare manualmente la migrazione di riunioni per un utente eseguendo il cmdlet `Start-CsExMeetingMigration`. Questo cmdlet Accoda una richiesta di migrazione per l'utente specificato. Il nuovo `TargetMeetingType` parametro (che è attualmente limitata ai partecipanti al programma di adozione della tecnologia) consente di specificare la modalità eseguire la migrazione di riunioni: 

- Utilizzo di `TargetMeetingType Current` specifica che Skype per le riunioni Business mantenere Skype per riunioni aziendali e riunioni team rimangono riunioni team. Coordina tuttavia audioconferenze con accesso esterno può essere modificata e qualsiasi Skype locale per le riunioni aziendali verrà migrati a Skype Business online.
- Utilizzo di `TargetMeetingType Teams` specifica che le riunioni esistenti devono eseguire la migrazione di team, indipendentemente dal fatto che la riunione è ospitata in Skype per Business online o locale e indipendentemente dal fatto che sono necessari aggiornamenti audioconferenze con accesso esterno. 

Nell'esempio seguente viene illustrato come avviare la migrazione di riunione per utente ashaw@contoso.com in modo che tutte le riunioni vengono migrate in team:

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

> [!NOTE]
> Il cmdlet Start-CsExMeetingMigration è disponibile per tutti i clienti, ma TargetMeetingTypeParameter nuovo attualmente è solo funzionale per i clienti TOCCO. 


## <a name="managing-mms"></a>Gestione del servizio MMS

Utilizzando Windows PowerShell, è possibile controllare lo stato di migrazione in corso, manualmente attivano la migrazione di riunioni e disabilitare completamente la migrazione. 

### <a name="check-the-status-of-meeting-migrations"></a>Controllare lo stato della migrazione della riunione

Si utilizza il `Get-CsMeetingMigrationStatus` cmdlet per controllare lo stato della migrazione della riunione. Di seguito sono riportati alcuni esempi.

- Per ottenere lo stato di riepilogo di tutte le migrazioni MMS, eseguire il seguente comando che offre una visualizzazione tabulare di tutti gli stati di migrazione:

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Per ottenere dettagli completi di tutte le migrazioni all'interno di un periodo di tempo specifico, utilizzare la `StartTime` e `EndTime` parametri. Ad esempio, il comando seguente restituirà tutti i dettagli su tutte le migrazioni che si sono verificati da 1 ottobre 2018 a 8 ottobre 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Per controllare lo stato della migrazione di un utente specifico, utilizzare la `Identity` parametro. Ad esempio, il seguente comando restituirà lo stato dell';utente ashaw@contoso.com:

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Se viene visualizzato qualsiasi migrazione non riusciti, eseguire l'azione necessaria per risolvere questi problemi presto, poiché utenti saranno in grado di componente aggiuntivo per le riunioni organizzate dagli utenti fino a quando non si risolverli. Se `Get-CsMeetingMigrationStatus` Mostra le migrazioni nello stato di errore, eseguire la procedura seguente:
 
1. Determinare quali utenti sono interessati. Eseguire il seguente comando per ottenere l';elenco degli utenti interessati e l';errore specifico che è stato segnalato:

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. Per ogni utente interessato, eseguire lo strumento di migrazione di riunioni per migrare manualmente le riunioni.

3. Se la migrazione continua a non funzionare con lo Strumento di migrazione riunioni, si hanno due opzioni:

    - Far creare agli utenti nuove riunioni Skype.
    - [Contattare l'assistenza](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Attivazione e disattivazione del servizio MMS

MMS è attivata per impostazione predefinita per tutte le organizzazioni, ma può essere disattivata nel modo seguente:

- Disattivare completamente per il tenant. 
- Disabilitare solo le modifiche relative alla conferenza. In questo caso, MMS sarà sempre eseguita quando un utente verrà migrato in locale al cloud o quando si concede modalità TeamsOnly o SfBWithTeamsCollabAndMeetings in `TeamsUpgradePolicy`.

Ad esempio, è possibile eseguire la migrazione di tutte le riunioni o disabilitare temporaneamente MMS durante l'esecuzione di modifiche sostanziali per le impostazioni di conferenza audio per la propria organizzazione manualmente

Per verificare se MMS è abilitata per l'organizzazione, eseguire il comando seguente. MMS è abilitata se il `MeetingMigrationEnabled` parametro `$true`.
```
Get-CsTenantMigrationConfiguration
```
Per abilitare o disabilitare completamente MMS, utilizzare la `Set-CsTenantMigrationConfiguration` comando. Per disabilitare MMS, ad esempio, eseguire il comando seguente:

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Se MMS è attivato nell'organizzazione e si desidera verificare se è attivata per gli aggiornamenti di audioconferenza, selezionare il valore del `AutomaticallyMigrateUserMeetings` parametro di output da `Get-CsOnlineDialInConferencingTenantSettings`. Per abilitare o disabilitare MMS per le conferenze audio, utilizzare `Set-CsOnlineDialInConferencingTenantSettings`. Ad esempio, per disabilitare MMS per le conferenze audio, eseguire il comando seguente:

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Spostare gli utenti tra organizzazioni locali e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
