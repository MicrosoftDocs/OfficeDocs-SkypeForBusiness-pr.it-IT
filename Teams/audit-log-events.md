---
title: Cercare gli eventi nel log di controllo in Microsoft Teams
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
description: Informazioni su come recuperare Microsoft Teams dati dal log di controllo nel Centro conformità Microsoft 365.
appliesto:
  - Microsoft Teams
---

# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Cercare gli eventi nel log di controllo in Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Il log di controllo consente di analizzare attività specifiche in Microsoft 365 servizi. Per Microsoft Teams, ecco alcune delle attività che vengono verificate:

- Creazione di team
- Eliminazione del team
- Canale aggiunto
- Canale eliminato
- Impostazione del canale modificata

Per un elenco completo delle Teams di lavoro che vengono verificate, vedere Teams attività [](#teams-activities) e turni [nelle Teams attività](#shifts-in-teams-activities).

> [!NOTE]
> Anche gli eventi di controllo dei canali privati vengono registrati così come sono per i team e i canali standard.

## <a name="turn-on-auditing-in-teams"></a>Attivare il controllo in Teams

Prima di esaminare i dati di controllo, è necessario attivare il controllo nel Centro conformità Microsoft 365. Per altre informazioni, vedere [Attivare o disattivare il controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> I dati di controllo sono disponibili solo dal punto in cui è stato attivato il controllo.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperare Teams dati dal log di controllo

1. Per recuperare i log di controllo Teams attività, passare a <https://compliance.microsoft.com> e selezionare **Controllo**.

2. Nella pagina **Cerca** filtrare le attività, le date e gli utenti da controllare.

3. Esportare i risultati in Excel per un'ulteriore analisi.

Per istruzioni dettagliate, vedere Eseguire una ricerca [nel log di controllo nel Centro conformità](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> I dati di controllo sono visibili nel log di controllo solo se il controllo è attivato.

La durata della conservazione e della ricerca di un record di controllo nel log di controllo dipende dall'abbonamento a Microsoft 365 o Office 365 e in particolare dal tipo di licenza assegnato agli utenti. Per altre informazioni, vedere la descrizione [del servizio Centro sicurezza & conformità](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Suggerimenti ricerca nel log di controllo

Ecco alcuni suggerimenti per cercare Teams attività nel log di controllo.

:::image type="content" alt-text="Screenshot della pagina di ricerca nel log di controllo nel Centro conformità" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- È possibile selezionare attività specifiche da cercare facendo clic sulla casella di controllo accanto a una o più attività. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È anche possibile usare la casella di ricerca per visualizzare le attività che contengono la parola chiave digitata.

  ![Screenshot dell'elenco a discesa delle attività nella pagina di ricerca nel log di controllo](media/audit-log-search.png)

- Per visualizzare gli eventi per le attività eseguite con i cmdlet, selezionare **Mostra risultati per tutte le attività** **nell'elenco** Attività. Se si conosce il nome dell'operazione per queste attività, digitarlo nella casella di ricerca per visualizzare l'attività e quindi selezionarla.

- Per cancellare i criteri di ricerca correnti, fare clic **su Cancella tutto**. L'intervallo di date torna al valore predefinito degli ultimi sette giorni.

- Se vengono trovati 5.000 risultati, è probabile che siano presenti più di 5.000 eventi che soddisfano i criteri di ricerca. È possibile perfezionare i criteri di ricerca ed eseguire di nuovo la ricerca per restituire meno risultati oppure esportare tutti i risultati della ricerca selezionando **EsportaScarica** >  **tutti i risultati**. Per istruzioni dettagliate sull'esportazione dei log di controllo, vedere [Esportare i risultati della ricerca in un file](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Guarda questo [video per l'uso](https://www.youtube.com/embed/UBxaRySAxyE) della ricerca nel log audio. Partecipa a Ansuman Acharya, un program manager per Teams, come dimostra come eseguire una ricerca nel log di controllo per Teams.

## <a name="teams-activities"></a>Teams attività

Ecco un elenco di tutti gli eventi registrati per le attività di utente e amministratore in Teams nel log Microsoft 365 di controllo. La tabella include il nome descrittivo visualizzato nella colonna Attività e il  nome dell'operazione corrispondente visualizzata nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca.

|Nome descrittivo  |Operazione |Descrizione |
|:---------|:---------|:---------|
|Bot aggiunto al team   |BotAddedToTeam        |Un utente aggiunge un bot a un team.        |
|Canale aggiunto   |ChannelAdded         |Un utente aggiunge un canale a un team.         |
|Connettore aggiunto  |ConnectorAdded          |Un utente aggiunge un connettore a un canale.        |
|Sono stati aggiunti dettagli Teams riunione <sup>2</sup>|Dettagli riunione|Teams aggiunte informazioni su una riunione, tra cui l'ora di inizio, l'ora di fine e l'URL per partecipare alla riunione.|
|Aggiunte informazioni sui partecipanti alla riunione <sup>2</sup>|MeetingParticipantDetail|Teams sono state aggiunte informazioni sui partecipanti a una riunione, tra cui l'ID utente di ogni partecipante, l'ora in cui un partecipante ha partecipato alla riunione e l'ora in cui un partecipante ha lasciato la riunione.|
|Membri aggiunti    |MemberAdded         |Il proprietario del team aggiunge membri a un team, un canale o una chat di gruppo.         |
|Scheda Aggiunta    |TabAdded         |Un utente aggiunge una scheda a un canale.        |
|Impostazione del canale modificata    |ChannelSettingChanged         |L'operazione ChannelSettingChanged viene registrata quando un membro del team esegue le attività seguenti. Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione modificata (visualizzata tra parentesi nella colonna **Elemento** nei risultati della ricerca nel log di controllo. <ul><li>Modifica il nome di un canale del team (**nome del canale**)</li><li>Modifica la descrizione di un canale del team (**descrizione del canale**)</li> </ul>      |
|Impostazione dell'organizzazione modificata   |TeamsTenantSettingChanged         |L'operazione TeamsTenantSettingChanged viene registrata quando le attività seguenti vengono eseguite da un amministratore globale nella interfaccia di amministrazione di Microsoft 365. Queste attività influiscono sulle impostazioni Teams a livello di organizzazione. Per altre informazioni, vedere [Gestire le Teams per l'organizzazione](enable-features-office-365.md). <br>Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione modificata (visualizzata tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo.<ul><li>Abilita o disabilita la Teams per l'organizzazione (**Microsoft Teams**).</li><li>Abilita o disabilita l'interoperabilità tra Microsoft Teams e Skype for Business per l'organizzazione (**Skype for Business interoperabilità**).</li><li>Abilita o disabilita la visualizzazione organigramma nei Microsoft Teams client (**visualizzazione Organigramma**).</li><li>Abilita o disabilita la possibilità per i membri del team di pianificare riunioni private (**pianificazione di riunioni private**).</li><li>Abilita o disabilita la possibilità per i membri del team di pianificare le riunioni del canale (**pianificazione delle riunioni del canale**).</li><li>Abilita o disabilita le videochiamate Teams riunioni (**Video per Skype riunioni**).</li><li>Abilita o disabilita la condivisione dello schermo Microsoft Teams riunioni per l'organizzazione (**condivisione dello schermo** per Skype riunioni).</li><li>Abilita o disabilita la possibilità di aggiungere immagini animate (denominate Giphys) Teams conversazioni (**immagini animate**).</li><li>Modifica l'impostazione della classificazione del contenuto per l'organizzazione (**Classificazione contenuto**). La classificazione del contenuto limita il tipo di immagine animata che può essere visualizzata nelle conversazioni.</li><li>Abilita o disabilita la possibilità per i membri del team di aggiungere immagini personalizzabili (denominate meme personalizzati) da Internet alle conversazioni del team (immagini personalizzabili **da Internet**).</li><li>Abilita o disabilita la possibilità per i membri del team di aggiungere immagini modificabili (detti adesivi) alle conversazioni del team (**immagini modificabili**).</li><li>Abilita o disabilita la possibilità per i membri del team di usare bot in chat e canali Microsoft Teams (bot a livello **di organizzazione)**</li><li>Abilita bot specifici per Microsoft Teams. Questo non include il T-Bot, che Teams bot della Guida disponibile quando i bot sono abilitati per l'organizzazione (**singoli bot**).</li><li>Abilita o disabilita la possibilità per i membri del team di aggiungere estensioni o schede (**estensioni o schede**).</li><li>Abilita o disabilita il side-loading dei bot proprietari per Microsoft Teams (**caricamento laterale dei bot**).</li><li>Abilita o disabilita la possibilità per gli utenti di inviare messaggi di posta elettronica a un Microsoft Teams canale (**posta elettronica del canale**).</li></ul>|
|Ruolo modificato dei membri nel team    |MemberRoleChanged         |Il proprietario di un team cambia il ruolo dei membri in un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente. <br><br>**1** - Indica il ruolo membro.<br>**2** - Indica il ruolo di proprietario.<br>**3** - Indica il ruolo Guest.<br><br>La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.        |
|Impostazione del team modificata    |TeamSettingChanged        |L'operazione TeamSettingChanged viene registrata quando il proprietario del team esegue le attività seguenti. Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione modificata (visualizzata tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo.<ul><li>Modifica il tipo di accesso per un team. Teams può essere impostato come privato o pubblico (**tipo di accesso team**). Quando un team è privato (impostazione predefinita), gli utenti possono accedere al team solo su invito. Quando un team è pubblico, è individuabile da chiunque.</li><li>Modifica la classificazione delle informazioni di un team (**classificazione del team**). Ad esempio, i dati del team possono essere classificati come ad alto impatto aziendale, a medio impatto aziendale o a basso impatto aziendale.</li><li>Modifica il nome di un team (**nome del team**).</li><li>Modifica la descrizione del team (**Descrizione del team**).</li><li>Modifiche apportate alle impostazioni del team. Per accedere a queste impostazioni, il proprietario del team può fare clic con il pulsante destro del mouse su un team, scegliere **Gestisci** **team** e quindi fare clic sulla Impostazioni gruppo. Per queste attività, il nome dell'impostazione modificata viene visualizzato nella colonna **Elemento** nei risultati della ricerca nel log di controllo.</li></ul>         |
|È stata creata una chat <sup>1, </sup> <sup>2</sup>|    ChatCreated|    È stata Teams una chat.|
|Team creato    |TeamCreated         |Un utente crea un team.         |
|È stato eliminato un messaggio  |MessageDeleted |Un messaggio in una chat o in un canale è stato eliminato.|
|Tutte le app dell'organizzazione sono state eliminate|DeletedAllOrganizationApps           |Tutte le app dell'organizzazione sono state eliminate dal catalogo.     |
|App eliminata |AppDeletedFromCatalog           |Un'app è stata eliminata dal catalogo.     |
|Canale eliminato     |ChannelDeleted         |Un utente elimina un canale da un team.         |
|Team eliminato  |TeamDeleted            |Il proprietario del team elimina un team.      |
|È stato modificato un messaggio con un collegamento URL in Teams     |MessageEditedHasLink         |Un utente modifica un messaggio e aggiunge un collegamento URL in Teams.         |
|Messaggi esportati <sup>1, </sup> <sup>2</sup> |    MessagesExported |I messaggi della chat o del canale sono stati esportati.|
|Chat recuperata <sup>1, </sup> <sup>2</sup>   |ChatRetrieved  |È stata Microsoft Teams una chat.|
|È stato recuperato tutto il contenuto ospitato di un <sup>messaggio1, </sup> <sup>2</sup> |MessageHostedContentsListed    |Tutto il contenuto ospitato in un messaggio, ad esempio immagini o frammenti di codice, è stato recuperato.|
|App installata |AppInstalled         |È stata installata un'app.   |
|Azione eseguita sulla scheda|PerformedCardAction|Un utente ha fatto un'azione su una scheda adattiva all'interno di una chat. Le schede adattive vengono in genere usate dai bot per consentire la visualizzazione di informazioni e interazioni nelle chat. <br/><br/>**Nota:** Solo le azioni di input in linea in una scheda adattiva all'interno di una chat saranno disponibili nel log di controllo. Ad esempio, quando un utente invia una risposta al sondaggio in una conversazione di canale su una scheda adattiva generata da un bot Sondaggio. Le azioni utente, ad esempio "Visualizza risultato", che apriranno una finestra di dialogo o le azioni degli utenti all'interno delle finestre di dialogo non saranno disponibili nel log di controllo.|
|Pubblicato un nuovo messaggio <sup>1, </sup> <sup>2</sup>   |MessageSent|   Un nuovo messaggio è stato pubblicato in una chat o in un canale.|
|App pubblicata |AppPublishedToCatalog           |È stata aggiunta un'app al catalogo.     |
|Leggere un messaggio <sup>1, </sup> <sup>2</sup> |MessageRead    |È stato recuperato un messaggio di una chat o di un canale.|
|Leggere il contenuto ospitato di un messaggio <sup>1, </sup> <sup>2</sup>   |MessageHostedContentRead   |Il contenuto ospitato in un messaggio, ad esempio un'immagine o un frammento di codice, è stato recuperato.|
|Bot rimosso dal team   |BotRemovedFromTeam         |Un utente rimuove un bot da un team.       |
|Connettore rimosso     |ConnectorRemoved         |Un utente rimuove un connettore da un canale.         |
|Membri rimossi    |MemberRemoved        |Il proprietario del team rimuove i membri da un team, un canale o una chat di gruppo.         |
|Scheda Rimossa    |TabRemoved         |Un utente rimuove una scheda da un canale.         |
|Messaggi recuperati <sup>1, </sup> <sup>2</sup> |MessagesListed |I messaggi provenienti da una chat o da un canale sono stati recuperati.|
|È stato inviato un messaggio con un collegamento URL in Teams |MessageCreatedHasLink|Un utente invia un messaggio contenente un collegamento URL in Teams.|
|Notifica di modifica inviata per la creazione <sup>di messaggi 1, </sup> <sup>2</sup>  |MessageCreatedNotification |È stata inviata una notifica di modifica per inviare una notifica a un'applicazione listener sottoscritta di un nuovo messaggio.|
|Notifica di modifica inviata per l'eliminazione <sup>del messaggio 1, </sup> <sup>2</sup>  |MessageDeletedNotification |È stata inviata una notifica di modifica per inviare una notifica a un'applicazione listener sottoscritta di un messaggio eliminato.|
|Notifica di modifica inviata per l'aggiornamento <sup>del messaggio 1, </sup> <sup>2</sup>    |MessageUpdatedNotification |È stata inviata una notifica di modifica per notificare a un'applicazione listener sottoscritta un messaggio aggiornato.|
|Sottoscritto alle notifiche di modifica dei <sup>messaggi 1, </sup> <sup>2</sup> |SubscribedToMessages   |Un abbonamento è stato creato da un'applicazione listener per ricevere le notifiche di modifica per i messaggi.|
|App disinstallata |AppUninstalled           |Un'app è stata disinstallata.     |
|App aggiornata |AppUpdatedInCatalog           |Un'app è stata aggiornata nel catalogo.     |
|È stata aggiornata una chat <sup>1, </sup> <sup>2</sup> |ChatUpdated    |Una Teams chat è stata aggiornata.|
|È stato aggiornato un <sup>messaggio 1, </sup> <sup>2</sup>  |MessageUpdated |È stato aggiornato un messaggio di una chat o di un canale.|
|Connettore aggiornato    |ConnectorUpdated         |Un utente ha modificato un connettore in un canale.         |
|Scheda Aggiornata   |TabUpdated         |Un utente ha modificato una scheda in un canale.         |
|App aggiornata |AppUpgraded           |Un'app è stata aggiornata alla versione più recente nel catalogo.     |
|Utente connesso a Teams     |TeamsSessionStarted         |Un utente accede a un Microsoft Teams client. Questo evento non acquisisce le attività di aggiornamento del token.         |


> [!NOTE]
> <sup>1</sup> Un record di controllo per questo evento viene registrato solo quando l'operazione viene eseguita chiamando un'API Graph Microsoft. Se l'operazione viene eseguita nel client Teams, non verrà registrato un record di controllo<br/><br/><sup>2</sup> Questo evento è disponibile solo in Controllo avanzato. Questo significa che agli utenti deve essere assegnata la licenza appropriata prima che questi eventi siano registrati nel log di controllo. Per altre informazioni sulle attività disponibili solo in Controllo avanzato, vedere [Controllo avanzato in Microsoft 365](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Per i requisiti di licenza di controllo avanzati, vedere Soluzioni di controllo [in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements).

## <a name="shifts-in-teams-activities"></a>Turni nelle Teams lavoro

**(in anteprima)**

Se l'organizzazione usa l'app Turni in Teams, è possibile cercare nel log di controllo le attività correlate all'app Turni. Ecco un elenco di tutti gli eventi registrati per le attività turni Teams nel log Microsoft 365 di controllo.

|Nome descrittivo  |Operazione  |Descrizione  |
|---------|---------|---------|
|Gruppo di pianificazione aggiunto |ScheduleGroupAdded          |Un utente aggiunge correttamente un nuovo gruppo di pianificazione alla pianificazione.|
|Gruppo di pianificazione modificato     |ScheduleGroupEdited         |Un utente modifica correttamente un gruppo di pianificazione.          |
|Gruppo di pianificazione eliminato         |ScheduleGroupDeleted              |Un utente elimina correttamente un gruppo di pianificazione dalla pianificazione.|
|Ritira la pianificazione |ScheduleWithdrawn              |Un utente ritira correttamente una pianificazione pubblicata.|
|Turno aggiunto      |MaiuscAggiungere          |Un utente aggiunge correttamente un turno.           |
|Turno modificato       |MAIUSCModificato       |Un utente modifica correttamente un turno.        |
|Turno eliminato          |MAIUSCDeleted          | Un utente elimina correttamente un turno.               |
|Periodo di riposo aggiunto      |TimeOffAdded          |Un utente aggiunge correttamente un periodo di riposo nella pianificazione.          |
|Periodo di riposo modificato         |TimeOffEdited           |Un utente modifica correttamente il periodo di riposo.          |
|Periodo di riposo eliminato     |TimeOffDeleted              |Un utente elimina correttamente i tempi di riposo.           |
|Aggiunto turno aperto     |OpenShiftAdded          |Un utente aggiunge correttamente un turno aperto a un gruppo di pianificazione.          |
|Turno aperto modificato    |OpenShiftEdited          |Un utente modifica correttamente un turno aperto in un gruppo di pianificazione.          |
|Turno aperto eliminato      |OpenShiftDeleted          |Un utente elimina correttamente un turno aperto da un gruppo di pianificazione.         |
|Pianificazione condivisa     |ScheduleShared                  |Un utente ha condiviso correttamente una pianificazione del team per un intervallo di date.          |
|Orologio in uso con l'orologio         |ClockedIn          |Un utente usa correttamente l'orologio.          |
|Uscita con l'orologio      |ClockedOut          |Un utente esce correttamente usando l'orologio.          |
|Inizio dell'interruzione con l'orologio      |BreakStarted          |Un utente avvia correttamente un'interruzione durante una sessione di orologio a tempo attiva.          |
|Interruzione terminata con l'orologio    |BreakEnded          |Un utente termina correttamente un'interruzione durante una sessione di orologio a tempo attiva.          |
|Aggiunta dell'immissione dell'orologio     |TimeClockEntryAdded          |Un utente aggiunge correttamente una nuova voce manuale dell'orologio nel foglio attività.          |
|Immissione dell'orologio modificata     | TimeClockEntryEdited             |Un utente modifica correttamente una voce dell'orologio nel foglio attività.          |
|Voce ora eliminata    |TimeClockEntryDeleted              |Un utente elimina correttamente una voce dell'orologio nel foglio attività.          |
|Richiesta di turno aggiunta         |RequestAdded              |Un utente ha aggiunto una richiesta di turno.          |
|Ha risposto alla richiesta di turno     |RequestRespondedTo                  |Un utente ha risposto a una richiesta di turno.          |
|Richiesta di turno annullata         |RequestCancelled               |Un utente ha annullato una richiesta di turno.          |
|Impostazione di pianificazione modificata      |ScheduleSettingChanged          |Un utente modifica un'impostazione nelle impostazioni di Turni.         |
|Aggiunta dell'integrazione della forza lavoro      |WorkforceIntegrationAdded                  | L'app Turni è integrata con un sistema di terze parti.         |
|Messaggio di turno disattivato accettato         |OffShiftDialogAccepted          |Un utente riconosce il messaggio fuori turno per accedere Teams dopo l'orario di lavoro.           |

## <a name="office-365-management-activity-api"></a>api Office 365 Gestione attività

È possibile usare l'API Office 365 di gestione per recuperare informazioni sugli Teams eventi. Per altre informazioni sullo schema dell'API attività di gestione per Teams, vedere Teams [schema](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Attribuzione nei log Teams di controllo

Le modifiche all'appartenenza Teams (ad esempio gli utenti aggiunti o eliminati) apportate tramite Azure Active Directory (Azure AD), il portale di amministrazione di Microsoft 365 o l'API Graph gruppi di Microsoft 365 verranno visualizzate in Teams  controllare i messaggi e nel canale Generale con un'attribuzione a un proprietario esistente del team e non all'iniziatore effettivo dell'azione. In questi scenari, consultare Azure AD o [Microsoft 365 di](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) controllo del gruppo per visualizzare le informazioni pertinenti.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Usare Defender per le app cloud per impostare i criteri di attività

Usando [l'integrazione di Microsoft Defender per le](/cloud-app-security/what-is-cloud-app-security) app cloud[](/cloud-app-security/user-activity-policies), è possibile impostare criteri di attività per applicare un'ampia gamma di processi automatizzati usando le API del provider di app. Questi criteri consentono di monitorare attività specifiche eseguite da vari utenti o di seguire tassi inaspettatamente elevati di un determinato tipo di attività.

Dopo aver impostato un criterio di rilevamento delle attività, inizia a generare avvisi. Gli avvisi vengono generati solo per le attività che si verificano dopo la creazione del criterio. Ecco alcuni scenari di esempio che illustrano come usare i criteri attività in Defender per le app cloud per monitorare Teams attività.

### <a name="external-user-scenario"></a>Scenario utente esterno

Uno scenario da tenere sotto controllo, dal punto di vista aziendale, è l'aggiunta di utenti esterni all'ambiente Teams aziendale. Se gli utenti esterni sono abilitati, è buona idea monitorare la loro presenza.  È possibile usare [Defender per le app cloud](/cloud-app-security/what-is-cloud-app-security) per identificare potenziali minacce.

:::image type="content" alt-text="Criteri per monitorare l'aggiunta di utenti esterni." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

Lo screenshot di questo criterio per monitorare l'aggiunta di utenti esterni consente di assegnare un nome al criterio, impostare la gravità in base alle esigenze aziendali, impostarlo come (in questo caso) una singola attività e quindi stabilire i parametri che monitoreranno specificamente solo l'aggiunta di utenti non interni e limitare questa attività a Teams.

I risultati di questo criterio possono essere visualizzati nel log attività:

:::image type="content" alt-text="Eventi attivati dai criteri degli utenti esterni." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Qui è possibile rivedere le corrispondenze ai criteri impostati e apportare eventuali modifiche in base alle esigenze oppure esportare i risultati per usarli altrove.

### <a name="mass-delete-scenario"></a>Scenario di eliminazione di massa

Come accennato in precedenza, è possibile monitorare gli scenari di eliminazione. È possibile creare criteri che monitorino l'eliminazione di massa Teams siti. In questo esempio vengono impostati criteri basati su avvisi per rilevare l'eliminazione di massa dei team in un intervallo di 30 minuti.

:::image type="content" alt-text="Criterio che mostra la configurazione di un criterio per il rilevamento dell'eliminazione di massa del team." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Come illustrato nella schermata, è possibile impostare molti parametri diversi per questo criterio per monitorare le eliminazioni di Teams, tra cui la gravità, l'azione singola o ripetuta e i parametri che limitano l'eliminazione Teams siti. Questa operazione può essere eseguita indipendentemente da un modello oppure potrebbe essere creato un modello su cui basare questo criterio, a seconda delle esigenze dell'organizzazione.

Dopo aver stabilito un criterio che funziona per l'azienda, è possibile esaminare i risultati nel log attività quando vengono attivati gli eventi:

:::image type="content" alt-text="Eventi dello screenshot attivati da eliminazioni di massa." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

È possibile filtrare fino al criterio impostato per visualizzare i risultati di tale criterio. Se i risultati visualizzati nel log attività non sono soddisfacenti, ad esempio se sono presenti molti risultati o niente, è possibile ottimizzare la query per renderla più pertinente per le attività da eseguire.

### <a name="alert-and-governance-scenario"></a>Scenario di avviso e governance

È possibile impostare avvisi e inviare messaggi di posta elettronica agli amministratori e ad altri utenti quando viene attivato un criterio attività. È possibile impostare azioni di governance automatizzate, ad esempio sospendere un utente o fare in modo che un utente eserciti di nuovo l'accesso in modo automatico. Questo esempio mostra come è possibile sospendere un account utente quando viene attivato un criterio attività e determina che un utente ha eliminato due o più team in 30 minuti.

![Screenshot di avvisi e azioni di governance per un criterio attività.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Usare Defender per le app cloud per impostare criteri di rilevamento anomalie

I criteri di rilevamento delle anomalie [in Defender](/cloud-app-security/anomaly-detection-policy) per le app cloud forniscono analisi del comportamento delle entità e degli utenti predefinite (UEBA) e machine learning (ML) in modo da poter eseguire immediatamente il rilevamento avanzato delle minacce nell'ambiente cloud. Poiché sono abilitati automaticamente, i nuovi criteri di rilevamento delle anomalie forniscono risultati immediati fornendo rilevamenti immediati, mirando a numerose anomalie comportamentali tra gli utenti e i computer e i dispositivi connessi alla rete. Inoltre, i nuovi criteri espongono più dati dal motore di rilevamento defender per le app cloud, per velocizzare il processo di indagine e contenere le minacce in corso.

Stiamo lavorando per integrare gli eventi Teams nei criteri di rilevamento anomalie. Per il momento, è possibile configurare criteri di rilevamento anomalie per altri prodotti Office ed eseguire azioni sugli utenti che soddisfano tali criteri.

## <a name="related-topics"></a>Argomenti correlati

- [Cercare nel log di controllo nel Centro conformità Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
