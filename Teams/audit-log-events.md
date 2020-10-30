---
title: Eseguire una ricerca nel log di controllo per gli eventi in Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anwara
search.appverid: MET150
description: Informazioni su come recuperare i dati di Microsoft teams dal log di controllo nel centro conformità Microsoft 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54cdaf5e5d63b7067c51b8f8428ed609bf6dad28
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803454"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Eseguire una ricerca nel log di controllo per gli eventi in Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Il log di controllo consente di analizzare attività specifiche nei servizi Microsoft 365. Per Microsoft teams, Ecco alcune delle attività che vengono controllate:

- Creazione di Team
- Eliminazione del team
- Canale aggiunto
- Impostazione modificata

Per un elenco completo delle attività di teams controllate, vedere [attività di Team](#teams-activities) e [turni nelle attività di Teams (in anteprima)](#shifts-in-teams-activities).

> [!NOTE]
> Gli eventi di controllo dei canali privati vengono registrati anche per i team e i canali standard.

## <a name="turn-on-auditing-in-teams"></a>Attivare il controllo in teams

Prima di poter esaminare i dati di controllo, è necessario attivare prima di tutto il controllo nel [centro conformità & sicurezza](https://protection.office.com). Per informazioni sull'attivazione del controllo, leggere [attivare o disattivare la ricerca nel log di controllo](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> I dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperare i dati di teams dal log di controllo

1. Per recuperare i log di controllo, accedere al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=855775). In **ricerca** selezionare **Ricerca log di controllo** .

2. Usare la **ricerca** per filtrare in base alle attività, alle date e agli utenti che si desidera controllare.

3. Esportare i risultati in Excel per un'ulteriore analisi.

> [!IMPORTANT]
> I dati di controllo sono visibili solo nel log di controllo se è attivato il controllo.

Il periodo di tempo in cui un record di controllo viene mantenuto e la ricerca nel log di controllo dipende dall'abbonamento a Microsoft 365 o Office 365 e, in particolare, al tipo di licenza assegnato agli utenti. Per altre informazioni, vedere la [Descrizione del servizio Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel log di controllo

Ecco alcuni suggerimenti per la ricerca di attività in teams nel log di controllo.

![Screenshot della pagina di ricerca del log di controllo](media/audit-log-search-page.png)

- È possibile selezionare attività specifiche da cercare facendo clic sul nome dell'attività. In alternativa, è possibile cercare tutte le attività di un gruppo, ad esempio **attività di file e cartelle** , facendo clic sul nome del gruppo. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È anche possibile usare la casella di ricerca per visualizzare le attività che contengono la parola chiave digitata.

  ![Screenshot della ricerca nel log di controllo](media/audit-log-search.png)

- Per visualizzare gli eventi per le attività eseguite tramite cmdlet, selezionare **Mostra risultati per tutte le attività** nell'elenco **attività** . Se si conosce il nome dell'operazione per queste attività, cercare tutte le attività e quindi filtrare i risultati digitando il nome dell'operazione nella casella della colonna **attività** . Per altre informazioni, vedere [passaggio 3: filtrare i risultati della ricerca](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results).

- Per cancellare i criteri di ricerca correnti, fare clic su **Cancella** . L'intervallo di date restituisce l'impostazione predefinita degli ultimi sette giorni. È anche possibile fare clic su **Cancella tutto per visualizzare i risultati per tutte le attività** per annullare tutte le attività selezionate.

- Se vengono trovati risultati di 5.000, è probabile che siano presenti più eventi di 5.000 che soddisfano i criteri di ricerca. È possibile affinare i criteri di ricerca e rieseguire la ricerca per restituire meno risultati oppure esportare tutti i risultati della ricerca selezionando **Esporta risultati** per  >  **scaricare tutti i risultati** .

Guarda [questo video per l'](https://www.youtube.com/embed/UBxaRySAxyE) uso della ricerca nel log audio. Unisciti a un responsabile di programma per Teams, come dimostra come eseguire una ricerca nel log di controllo per i team.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Usare la sicurezza delle app cloud per impostare i criteri di attività

Usando l'integrazione di [sicurezza delle app di Microsoft Cloud](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) , puoi impostare i [criteri di attività](https://docs.microsoft.com/cloud-app-security/user-activity-policies) per applicare una vasta gamma di processi automatizzati usando le API del provider di app. Questi criteri consentono di monitorare le attività specifiche svolte da diversi utenti o di seguire tariffe inaspettatamente elevate di un determinato tipo di attività.

Dopo aver impostato un criterio di rilevamento attività, viene avviata la generazione di avvisi. Gli avvisi vengono generati solo per le attività che si verificano dopo la creazione dei criteri. Ecco alcuni esempi di scenari in cui è possibile usare i criteri di attività nella sicurezza delle app cloud per monitorare le attività dei team.

### <a name="external-user-scenario"></a>Scenario utente esterno

Uno scenario in cui è consigliabile tenersi d'occhio, da un punto di vista aziendale, è l'aggiunta di utenti esterni all'ambiente teams. Se gli utenti esterni sono abilitati, è consigliabile monitorarne la presenza.  Puoi usare la [sicurezza delle app Cloud](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) per identificare potenziali minacce.

![Screenshot di un elenco di eventi attivati dalle eliminazioni di massa](media/TeamsExternalUserAddPolicy.png)

Lo screenshot di questo criterio per il monitoraggio dell'aggiunta di utenti esterni consente di assegnare un nome al criterio, impostare la gravità in base alle esigenze aziendali, impostarlo come (in questo caso) una singola attività e quindi stabilire i parametri che verranno monitorati in modo specifico solo l'aggiunta di utenti non interni e limitare l'attività ai team.

I risultati di questo criterio possono essere visualizzati nel registro attività:

![Screenshot di un elenco di eventi attivati dalle eliminazioni di massa](media/TeamsExternalUserList.png)

Qui puoi rivedere le corrispondenze ai criteri impostati e apportare le eventuali modifiche necessarie oppure esportare i risultati per usarli altrove.

### <a name="mass-delete-scenario"></a>Scenario di eliminazione di massa

Come accennato in precedenza, è possibile monitorare gli scenari di eliminazione. È possibile creare un criterio che monitora l'eliminazione di massa dei siti di teams. In questo esempio viene configurato un criterio basato sugli avvisi per rilevare l'eliminazione di massa dei team in un intervallo di 30 minuti.

![Screenshot della pagina di creazione dei criteri che mostra l'impostazione di un criterio per il rilevamento dell'eliminazione di massa del team](media/TeamsMassDeletePolicy.png)

Come Mostra la schermata, è possibile impostare molti parametri diversi per questo criterio per monitorare le eliminazioni dei team, tra cui gravità, azione singola o ripetuta e parametri che limitano questa operazione ai team e all'eliminazione del sito. Questa operazione può essere eseguita indipendentemente da un modello oppure è possibile che sia stato creato un modello per basare il criterio in base alle esigenze dell'organizzazione.

Dopo aver stabilito un criterio che funziona per l'azienda, è possibile esaminare i risultati nel log attività come vengono attivati gli eventi:

![Screenshot di un elenco di eventi attivati dalle eliminazioni di massa](media/TeamsMassDeleteList.png)

È possibile filtrare i criteri impostati per visualizzare i risultati di tale criterio. Se i risultati ottenuti nel registro attività non sono soddisfacenti (si possono vedere molti risultati o niente affatto), potrebbe essere utile ottimizzare la query per renderla più pertinente a ciò che è necessario.

### <a name="alert-and-governance-scenario"></a>Scenario di avviso e governance

Quando viene attivato un criterio di attività, è possibile impostare avvisi e inviare messaggi di posta elettronica agli amministratori e agli altri utenti. Puoi impostare azioni di governance automatizzate come la sospensione di un utente o la possibilità di accedere di nuovo in modo automatizzato a un utente. Questo esempio Mostra come un account utente può essere sospeso quando viene attivato un criterio di attività e determina che un utente ha eliminato due o più team in 30 minuti.

![Screenshot di avvisi e azioni di governance per un criterio di attività](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Usare la sicurezza delle app cloud per impostare i criteri di rilevamento anomalie

I [criteri di rilevamento delle anomalie](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy) nella sicurezza delle app cloud consentono di usare le funzionalità utente e l'analisi comportamentale (Ueba) e l'apprendimento automatico (ml) in modo da poter eseguire immediatamente il rilevamento avanzato delle minacce nell'ambiente cloud. Dato che sono abilitati automaticamente, i nuovi criteri di rilevamento delle anomalie forniscono risultati immediati fornendo rilevamenti immediati, con l'obiettivo di numerose anomalie comportamentali tra gli utenti e i computer e i dispositivi connessi alla rete. I nuovi criteri espongono inoltre altri dati dal motore di rilevamento della sicurezza delle app cloud per velocizzare il processo di analisi e contenere le minacce in corso.

Stiamo lavorando per integrare gli eventi dei team in criteri di rilevamento delle anomalie. Per il momento, puoi configurare i criteri di rilevamento delle anomalie per gli altri prodotti di Office e ottenere elementi di azione per gli utenti che soddisfano tali criteri.

## <a name="teams-activities"></a>Attività Teams

Ecco un elenco di tutti gli eventi registrati per le attività utente e amministratore in teams nel log di controllo di Microsoft 365. La tabella include il nome descrittivo visualizzato nella colonna **attività** e il nome dell'operazione corrispondente che viene visualizzata nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca.

|Nome descrittivo  |Operazione|Descrizione |
|---------|---------|---------|
|Aggiunta di un bot al team   |BotAddedToTeam        |Un utente aggiunge un bot a un team.        |
|Canale aggiunto   |ChannelAdded         |Un utente aggiunge un canale a un team.         |
|Connettore aggiunto  |ConnectorAdded          |Un utente aggiunge un connettore a un canale.        |
|Membri aggiunti    |MemberAdded         |Un proprietario del team aggiunge membri a un team, un canale o una chat di gruppo.         |
|Scheda aggiunta    |TabAdded         |Un utente aggiunge una tabulazione a un canale.        |
|Impostazione del canale modificata    |ChannelSettingChanged         |L'operazione ChannelSettingChanged viene registrata quando si esegue l'esecuzione delle attività seguenti da parte di un membro del team. Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione modificata (mostrata tra parentesi nella colonna **elemento** nei risultati della ricerca del log di controllo. <ul><li>Modifica il nome di un canale del team ( **nome canale** )</li><li>Modifica la descrizione di un canale del team ( **Descrizione del canale** )</li> </ul>      |
|Impostazione dell'organizzazione modificata   |TeamsTenantSettingChanged         |L'operazione TeamsTenantSettingChanged viene registrata quando le attività seguenti vengono eseguite da un amministratore globale nell'interfaccia di amministrazione di Microsoft 365. Queste attività influiscono sulle impostazioni di team a livello di organizzazione. Per altre informazioni, vedere [gestire le impostazioni dei team per l'organizzazione](enable-features-office-365.md). <br>Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata (visualizzata tra parentesi) nella colonna **elemento** nei risultati della ricerca del log di controllo.<ul><li>Abilita o Disabilita team per l'organizzazione ( **Microsoft teams** ).</li><li>Abilita o Disabilita l'interoperabilità tra Microsoft teams e Skype for business per l'organizzazione ( **interoperabilità Skype for business** ).</li><li>Abilita o Disabilita la visualizzazione organigramma nei client di Microsoft Teams ( **visualizzazione** organigramma).</li><li>Abilita o Disabilita la possibilità per i membri del team di pianificare riunioni private ( **pianificazione di riunioni private** ).</li><li>Abilita o Disabilita la possibilità per i membri del team di pianificare le riunioni di canale ( **pianificazione delle riunioni di canale** ).</li><li>Abilita o Disabilita le chiamate video nelle riunioni del team ( **video per riunioni Skype** ).</li><li>Abilita o Disabilita la condivisione dello schermo in Meetup di Microsoft teams per l'organizzazione ( **condivisione dello schermo per riunioni Skype** ).</li><li>Abilita o Disabilita la possibilità di aggiungere immagini animate (dette Giphy) alle conversazioni del team ( **Immagini animate** ).</li><li>Modifica l'impostazione di classificazione del contenuto per l'organizzazione ( **classificazione del contenuto** ). La classificazione del contenuto limita il tipo di immagine animata che può essere visualizzata nelle conversazioni.</li><li>Abilita o Disabilita la possibilità per i membri del team di aggiungere immagini personalizzabili (dette meme personalizzati) da Internet alle conversazioni del team ( **Immagini personalizzabili da Internet** ).</li><li>Abilita o Disabilita la possibilità per i membri del team di aggiungere immagini modificabili (dette adesivi) alle conversazioni del team ( **immagini modificabili** ).</li><li>Abilita o Disabilita la possibilità per i membri del team di usare i bot in chat e canali di Microsoft Teams ( **bot a livello di organizzazione)** .</li><li>Abilita bot specifici per Microsoft teams. Questo non include il T-bot, che è il bot della Guida di teams disponibile quando i bot sono abilitati per l'organizzazione ( **singoli bot** ).</li><li>Abilita o Disabilita la possibilità per i membri del team di aggiungere estensioni o schede ( **estensioni o schede** ).</li><li>Abilita o Disabilita il caricamento laterale di bot proprietari per Microsoft Teams ( **caricamento laterale dei bot** ).</li><li>Abilita o Disabilita la possibilità per gli utenti di inviare messaggi di posta elettronica a un canale di Microsoft Teams ( **canale di posta elettronica** ).</li></ul>|
|Ruolo modificato dei membri del team    |MemberRoleChanged         |Un proprietario del team modifica il ruolo dei membri in un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente. <br><br>**1** -indica il ruolo del membro.<br>**2** -indica il ruolo del proprietario.<br>**3** -indica il ruolo Guest.<br><br>La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.        |
|Impostazioni del team modificate    |TeamSettingChanged        |L'operazione TeamSettingChanged viene registrata quando si esegue l'esecuzione delle attività seguenti da parte di un proprietario del team. Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata (visualizzata tra parentesi) nella colonna **elemento** nei risultati della ricerca del log di controllo.<ul><li>Modifica il tipo di accesso per un team. I team possono essere impostati come privati o pubblici ( **tipo di accesso al team** ). Quando un team è privato (impostazione predefinita), gli utenti possono accedere al team solo su invito. Quando un team è pubblico, è individuabile da chiunque.</li><li>Modifica la classificazione delle informazioni di un team ( **classificazione del team** ). I dati del team, ad esempio, possono essere classificati come un impatto elevato, un impatto medio delle aziende o un impatto minimo sulle aziende.</li><li>Modifica il nome di un team ( **nome del team** ).</li><li>Modifica la descrizione del team ( **Descrizione del team** ).</li><li>Modifiche apportate alle impostazioni del team. Per accedere a queste impostazioni, il proprietario del team può fare clic con il pulsante destro del mouse su un team, scegliere **Gestisci team** e quindi fare clic sulla scheda **Impostazioni** . Per queste attività, il nome dell'impostazione modificata viene visualizzato nella colonna **elemento** nei risultati della ricerca del log di controllo.</li></ul>         |
|Team creato    |TeamCreated         |Un utente crea un team.         |
|Eliminate tutte le app dell'organizzazione|DeletedAllOrganizationApps           |Eliminate tutte le app dell'organizzazione dal catalogo.     |
|App eliminata |AppDeletedFromCatalog           |Un'app è stata eliminata dal catalogo.     |
|Canale eliminato     |ChannelDeleted         |Un utente elimina un canale da un team.         |
|Team eliminato  |TeamDeleted            |Un proprietario del team Elimina un team.      |
|App installata |AppInstalled         |È stata installata un'app.   |
|Azione eseguita sulla scheda|PerformedCardAction|Un utente ha intrapreso un'azione su una scheda adattiva all'interno di una chat. Le schede adattive vengono in genere usate dai bot per consentire l'ampia visualizzazione delle informazioni e l'interazione nelle chat. <br/><br/>**Nota:** Solo le azioni di input in linea su una scheda adattiva all'interno di una chat saranno disponibili nel log di controllo. Ad esempio, quando un utente invia una risposta al sondaggio in una conversazione di canale su una scheda adattiva generata da un bot di sondaggio. Le azioni degli utenti, ad esempio "Visualizza risultato", che apriranno una finestra di dialogo o le azioni degli utenti all'interno di finestre di dialogo non saranno disponibili nel log di controllo.|
|App pubblicata |AppPublishedToCatalog           |Un'app è stata aggiunta al catalogo.     |
|Bot rimosso dal team   |BotRemovedFromTeam         |Un utente rimuove un bot da un team.       |
|Connettore rimosso     |ConnectorRemoved         |Un utente rimuove un connettore da un canale.         |
|Membri rimossi    |MemberRemoved        |Un proprietario del team rimuove i membri da un team, un canale o una chat di gruppo.         |
|Scheda rimosso    |TabRemoved         |Un utente rimuove una tabulazione da un canale.         |
|App disinstallata |AppUninstalled           |È stata disinstallata un'app.     |
|App aggiornata |AppUpdatedInCatalog           |Un'app è stata aggiornata nel catalogo.     |
|Connettore aggiornato    |ConnectorUpdated         |Un utente ha modificato un connettore in un canale.         |
|Scheda aggiornamento   |TabUpdated         |Un utente ha modificato una tabulazione in un canale.         |
|App aggiornata |AppUpgraded           |Un'app è stata aggiornata alla versione più recente del catalogo.     |
|L'utente ha eseguito l'accesso a teams     |TeamsSessionStarted         |Un utente accede a un client Microsoft teams. Questo evento non acquisisce le attività di aggiornamento del token.         |

## <a name="shifts-in-teams-activities"></a>Turni nelle attività di Teams

**(in anteprima)**

Se l'organizzazione usa l'app turni in teams, è possibile eseguire una ricerca nel log di controllo per le attività correlate all'app turni. Ecco un elenco di tutti gli eventi che vengono registrati per le attività di turni in teams nel log di controllo di Microsoft 365.

|Nome descrittivo  |Operazione  |Descrizione  |
|---------|---------|---------|
|Gruppo di pianificazione aggiunto |ScheduleGroupAdded          |Un utente aggiunge correttamente un nuovo gruppo di pianificazione alla programmazione.|
|Gruppo di pianificazione modificato     |ScheduleGroupEdited         |Un utente modifica correttamente un gruppo di pianificazione.          |
|Gruppo pianificazione eliminata         |ScheduleGroupDeleted              |Un utente elimina correttamente un gruppo di pianificazione dalla pianificazione.|
|Pianificazione ritirata |ScheduleWithdrawn              |Un utente ritira correttamente una programmazione pubblicata.|
|Aggiunta di un turno      |ShiftAdded          |Un utente aggiunge correttamente un turno.           |
|Turno modificato       |ShiftEdited       |Un utente modifica correttamente un turno.        |
|Spostamento eliminato          |ShiftDeleted          | Un utente elimina correttamente un turno.               |
|Aggiunta di una pausa      |TimeOffAdded          |Un utente aggiunge correttamente una pausa nella programmazione.          |
|Timeout modificato         |TimeOffEdited           |Un utente modifica correttamente il tempo.          |
|Timeout eliminata     |TimeOffDeleted              |Un utente elimina correttamente il tempo.           |
|Aggiunta di un turno aperto     |OpenShiftAdded          |Un utente aggiunge correttamente un turno aperto a un gruppo di pianificazione.          |
|Modifica open Shift    |OpenShiftEdited          |Un utente modifica correttamente un turno aperto in un gruppo di pianificazione.          |
|Elimina turno aperto      |OpenShiftDeleted          |Un utente elimina correttamente un turno aperto da un gruppo di pianificazione.         |
|Pianificazione condivisa     |ScheduleShared                  |Un utente ha condiviso correttamente una pianificazione del team per un intervallo di date.          |
|Clock in uso dell'ora         |ClockedIn          |Un utente ha correttamente l'orologio usando l'ora.          |
|Temporizzato con l'ora      |ClockedOut          |Un utente ha correttamente l'orologio usando il cronometro.          |
|Interruzione iniziata con l'ora      |BreakStarted          |Un utente avvia un'interruzione durante una sessione di clock del tempo attiva.          |
|Interruzione terminata con l'ora    |BreakEnded          |Un utente termina un'interruzione durante una sessione di clock del tempo attiva.          |
|Aggiunta dell'ora di clock     |TimeClockEntryAdded          |Un utente aggiunge correttamente una nuova voce di clock manuale nel foglio di tempo.          |
|Voce dell'ora di clock modificata     | TimeClockEntryEdited             |Un utente modifica correttamente una voce di clock nel foglio di tempo.          |
|Voce dell'ora di clock eliminata    |TimeClockEntryDeleted              |Un utente elimina correttamente una voce dell'ora di clock nel foglio di tempo.          |
|Richiesta di spostamento aggiunta         |RequestAdded              |Un utente ha aggiunto una richiesta di spostamento.          |
|Risposta alla richiesta di spostamento     |RequestRespondedTo                  |Un utente ha risposto a una richiesta di spostamento.          |
|Richiesta di spostamento annullata         |RequestCancelled               |Un utente ha annullato una richiesta di spostamento.          |
|Impostazione di pianificazione modificata      |ScheduleSettingChanged          |Un utente modifica un'impostazione nelle impostazioni di turni.         |
|Integrazione della forza lavoro aggiunta      |WorkforceIntegrationAdded                  | L'app turni è integrata con un sistema di terze parti.         |
|Messaggio di fuori turno accettato         |OffShiftDialogAccepted          |Un utente riconosce il messaggio di spostamento disattivato per accedere ai team dopo il turno di ore.           |

## <a name="office-365-management-activity-api"></a>API di attività di gestione di Office 365

Puoi usare l'API di gestione attività di Office 365 per recuperare informazioni sugli eventi teams. Per altre informazioni sullo schema dell'API di gestione attività per i team, vedere [schema teams](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Attribuzione nei log di controllo di Teams

Le modifiche apportate all'appartenenza a teams (ad esempio utenti aggiunti o eliminati) effettuate tramite Azure Active Directory (Azure AD), il portale di amministrazione di Microsoft 365 o l'API di Microsoft 365 groups verranno visualizzate nei messaggi di controllo dei team e nel canale generale con l'attribuzione di un proprietario esistente del team e non con l'effettivo iniziatore dell'azione. In questi scenari, consulta i log di controllo di gruppo di Azure AD o [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) per visualizzare le informazioni pertinenti.

## <a name="related-topics"></a>Argomenti correlati

- [Eseguire ricerche nel log di controllo nel centro conformità di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
