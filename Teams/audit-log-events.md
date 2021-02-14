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
description: Informazioni su come recuperare i dati di Microsoft Teams dal log di controllo nel Centro conformità di Microsoft 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54cdaf5e5d63b7067c51b8f8428ed609bf6dad28
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803454"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Cercare gli eventi nel log di controllo in Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Il log di controllo consente di analizzare attività specifiche in tutti i servizi di Microsoft 365. Per Microsoft Teams, ecco alcune attività che vengono controllati:

- Creazione di team
- Eliminazione del team
- Canale aggiunto
- Impostazione modificata

Per un elenco completo delle attività di Teams che vengono verificate, vedere le attività di [Teams](#teams-activities) e i turni nelle attività [di Teams (in anteprima).](#shifts-in-teams-activities)

> [!NOTE]
> Anche gli eventi di controllo di canali privati vengono registrati così come sono per i team e i canali standard.

## <a name="turn-on-auditing-in-teams"></a>Attivare il controllo in Teams

Prima di poter esaminare i dati di controllo, è necessario attivare il controllo nel [Centro & conformità.](https://protection.office.com) Per assistenza sull'attivazione del controllo, vedere Attivare o [disattivare la ricerca nel log di controllo.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)

> [!IMPORTANT]
> I dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperare i dati di Teams dal log di controllo

1. Per recuperare i log di controllo, passare al [Centro & conformità.](https://go.microsoft.com/fwlink/?linkid=855775) In **Cerca** selezionare **Ricerca log di controllo.**

2. Usare **la** ricerca per filtrare in base alle attività, alle date e agli utenti da controllare.

3. Esportare i risultati in Excel per un'ulteriore analisi.

> [!IMPORTANT]
> I dati di controllo sono visibili nel log di controllo solo se il controllo è attivato.

Il periodo di tempo per cui un record di controllo viene conservato ed è possibile eseguire ricerche nel log di controllo dipende dall'abbonamento a Microsoft 365 o Office 365 e in particolare dal tipo di licenza assegnato agli utenti. Per altre informazioni, vedere la [descrizione del servizio & conformità del Centro sicurezza e conformità.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel log di controllo

Ecco alcuni suggerimenti per la ricerca di attività di Teams nel log di controllo.

![Screenshot della pagina di ricerca nel log di controllo](media/audit-log-search-page.png)

- È possibile selezionare attività specifiche da cercare facendo clic sul nome dell'attività. Oppure è possibile cercare tutte le attività in un gruppo, ad esempio **le attività** su file e cartelle, facendo clic sul nome del gruppo. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È anche possibile usare la casella di ricerca per visualizzare le attività che contengono la parola chiave digitata.

  ![Screenshot della ricerca nel log di controllo](media/audit-log-search.png)

- Per visualizzare gli eventi per le attività eseguite con i cmdlet, selezionare Mostra **risultati per tutte le attività** nell'elenco Attività.  Se si conosce il nome dell'operazione per queste attività, cercare tutte le attività e quindi filtrare i risultati digitando il nome dell'operazione nella casella nella **colonna** Attività. Per altre informazioni, vedere [Il passaggio 3: Filtrare i risultati della ricerca.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance?view=o365-worldwide#step-3-filter-the-search-results)

- Per cancellare i criteri di ricerca correnti, fare clic su **Cancella.** L'intervallo di date torna al valore predefinito degli ultimi sette giorni. È anche possibile fare clic **su Cancella tutto per visualizzare i risultati per tutte le attività** e annullare tutte le attività selezionate.

- Se vengono trovati 5.000 risultati, è probabile che siano presenti più di 5.000 eventi che soddisfano i criteri di ricerca. È possibile perfezionare i criteri di ricerca ed eseguire di nuovo la ricerca in modo da restituire meno risultati oppure è possibile esportare tutti i risultati della ricerca selezionando Esporta risultati Scarica  >  **tutti i risultati.**

Guarda questo [video per](https://www.youtube.com/embed/UBxaRySAxyE) la ricerca nel log audio. Partecipa ad Ansuman Acharya, un program manager per Teams, come dimostra come eseguire una ricerca nel log di controllo per Teams.

## <a name="use-cloud-app-security-to-set-activity-policies"></a>Usare Cloud App Security per impostare criteri attività

Con [](https://docs.microsoft.com/cloud-app-security/user-activity-policies) [l'integrazione di Microsoft Cloud App Security,](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) è possibile impostare criteri attività per applicare un'ampia gamma di processi automatizzati usando le API del provider dell'app. Questi criteri consentono di monitorare specifiche attività eseguite da vari utenti o di seguire tariffe imprevistamente elevate di un determinato tipo di attività.

Dopo aver impostato un criterio di rilevamento attività, inizia a generare avvisi. Gli avvisi vengono generati solo per le attività che si verificano dopo la creazione del criterio. Ecco alcuni scenari di esempio su come usare i criteri attività in Cloud App Security per monitorare le attività di Teams.

### <a name="external-user-scenario"></a>Scenario di utenti esterni

Uno scenario da tenere sotto controllo, dal punto di vista aziendale, è l'aggiunta di utenti esterni all'ambiente di Teams. Se gli utenti esterni sono abilitati, è buona idea monitorare la loro presenza.  È possibile usare [Cloud App Security per](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) identificare le potenziali minacce.

![Screenshot di un elenco di eventi attivati da eliminazioni di massa](media/TeamsExternalUserAddPolicy.png)

La schermata di questo criterio per monitorare l'aggiunta di utenti esterni consente di assegnare un nome al criterio, impostare la gravità in base alle esigenze aziendali, impostarla come (in questo caso) una singola attività e quindi stabilire i parametri che monitoreranno specificamente l'aggiunta di utenti non interni e limitare questa attività a Teams.

I risultati di questo criterio possono essere visualizzati nel log attività:

![Screenshot di un elenco di eventi attivati da eliminazioni di massa](media/TeamsExternalUserList.png)

Qui è possibile esaminare le corrispondenze ai criteri impostati e apportare eventuali modifiche necessarie oppure esportare i risultati per usarli altrove.

### <a name="mass-delete-scenario"></a>Scenario eliminazione di massa

Come accennato in precedenza, è possibile monitorare gli scenari di eliminazione. È possibile creare un criterio che monitori l'eliminazione di massa dei siti di Teams. In questo esempio è configurato un criterio basato su avvisi per rilevare l'eliminazione di massa dei team nell'arco di 30 minuti.

![Screenshot della pagina di creazione dei criteri che mostra la configurazione di un criterio per il rilevamento dell'eliminazione di massa del team](media/TeamsMassDeletePolicy.png)

Come mostra lo screenshot, è possibile impostare molti parametri diversi per questo criterio per monitorare le eliminazioni di Teams, tra cui la gravità, l'azione singola o ripetuta e i parametri che limitano questo ai team e all'eliminazione dei siti. Questa operazione può essere eseguita indipendentemente da un modello oppure è possibile creare un modello su cui basare questo criterio, a seconda delle esigenze dell'organizzazione.

Dopo aver stabilito un criterio che funziona per la propria azienda, è possibile esaminare i risultati nel log attività quando vengono attivati eventi:

![Screenshot di un elenco di eventi attivati da eliminazioni di massa](media/TeamsMassDeleteList.png)

È possibile filtrare verso il basso in base ai criteri impostati per visualizzare i risultati. Se i risultati restituiti nel log attività non sono soddisfacente , ad esempio se vengono visualizzati molti risultati o niente, è possibile ottimizzare la query per renderla più pertinente per le attività che servono.

### <a name="alert-and-governance-scenario"></a>Scenario di avviso e governance

È possibile impostare avvisi e inviare messaggi di posta elettronica ad amministratori e altri utenti quando vengono attivati criteri attività. È possibile impostare azioni automatizzate di governance, ad esempio sospendere un utente o fare in modo che un utente possa accedere di nuovo in modo automatico. Questo esempio mostra in che modo un account utente può essere sospeso quando vengono attivati i criteri attività e determina che un utente ha eliminato due o più team in 30 minuti.

![Screenshot di avvisi e azioni di governance per un criterio attività](media/audit-log-governance.png)

## <a name="use-cloud-app-security-to-set-anomaly-detection-policies"></a>Usare Cloud App Security per impostare criteri di rilevamento anomalie

I criteri di rilevamento anomalie [in](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy) Cloud App Security forniscono analisi comportamentoale per utenti ed entità (UEBA) e machine learning (ML) che consentono di eseguire immediatamente il rilevamento delle minacce avanzato nell'ambiente cloud. Poiché sono abilitati automaticamente, i nuovi criteri di rilevamento anomalie forniscono risultati immediati fornendo rilevamenti immediati, rilevando numerose anomalie di comportamento tra gli utenti e i computer e dispositivi connessi alla rete. Inoltre, i nuovi criteri espongono più dati dal motore di rilevamento cloud App Security, per accelerare il processo di indagine e contenere minacce continue.

Stiamo lavorando per integrare eventi di Teams nei criteri di rilevamento anomalie. Per il momento, è possibile configurare criteri di rilevamento anomalie per altri prodotti di Office ed eseguire attività sugli utenti corrispondenti a tali criteri.

## <a name="teams-activities"></a>Attività di Teams

Ecco un elenco di tutti gli eventi registrati per le attività utente e amministratore in Teams nel log di controllo di Microsoft 365. La tabella include il nome descrittivo  visualizzato nella colonna Attività e il nome dell'operazione corrispondente visualizzato nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca.

|Nome descrittivo  |Operazione|Descrizione |
|---------|---------|---------|
|Bot aggiunto al team   |BotAddedToTeam        |Un utente aggiunge un bot a un team.        |
|Canale aggiunto   |ChannelAdded         |Un utente aggiunge un canale a un team.         |
|Connettore aggiunto  |ConnectorAdded          |Un utente aggiunge un connettore a un canale.        |
|Membri aggiunti    |MemberAdded         |Il proprietario di un team aggiunge membri a un team, un canale o una chat di gruppo.         |
|Aggiunta di una scheda    |TabAdded         |Un utente aggiunge una scheda a un canale.        |
|Impostazione del canale modificata    |ChannelSettingChanged         |L'operazione ChannelSettingChanged viene registrata quando le attività seguenti vengono eseguite da un membro del team. Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata  (tra parentesi) nella colonna Elemento nei risultati della ricerca nel log di controllo. <ul><li>Modifica il nome di un canale del team **(nome del canale)**</li><li>Cambia la descrizione di un canale del team **(descrizione del canale)**</li> </ul>      |
|Impostazione dell'organizzazione modificata   |TeamsTenantSettingChanged         |L'operazione TeamsTenantSettingChanged viene registrata quando le attività seguenti vengono eseguite da un amministratore globale nell'interfaccia di amministrazione di Microsoft 365. Queste attività influiscono sulle impostazioni di Teams a livello di organizzazione. Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione.](enable-features-office-365.md) <br>Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata  (visualizzata tra parentesi) nella colonna Elemento nei risultati della ricerca nel log di controllo.<ul><li>Abilita o disabilita Teams per l'organizzazione (**Microsoft Teams**).</li><li>Abilita o disabilita l'interoperabilità tra Microsoft Teams e Skype for Business per l'organizzazione **(interoperabilità di Skype for Business).**</li><li>Abilita o disabilita la visualizzazione organigramma nei client di Microsoft Teams **(visualizzazione organigramma).**</li><li>Consente o disabilita la possibilità per i membri del team di pianificare riunioni private **(pianificazione di riunioni private).**</li><li>Consente o disabilita la possibilità per i membri del team di pianificare riunioni di canale **(pianificazione di riunioni del canale).**</li><li>Abilita o disabilita le videochiamate nelle riunioni di Teams (**Video per le riunioni Skype**).</li><li>Abilita o disabilita la condivisione dello schermo nelle riunioni di Microsoft Teams per l'organizzazione (condivisione **dello schermo per le riunioni Skype).**</li><li>Consente o disabilita la possibilità di aggiungere immagini animate (denominate Giphy) alle conversazioni di Teams **(immagini animate).**</li><li>Modifica l'impostazione di valutazione del contenuto per l'organizzazione **(classificazione del contenuto).** La classificazione del contenuto limita il tipo di immagine animata che può essere visualizzata nelle conversazioni.</li><li>Consente o disabilita la possibilità per i membri del team di aggiungere immagini personalizzabili (denominate meme personalizzati) da Internet alle conversazioni del team (immagini personalizzabili **da Internet).**</li><li>Consente o disabilita la possibilità per i membri del team di aggiungere immagini modificabili (denominate adesivi) alle conversazioni del team **(immagini modificabili).**</li><li>Consente o disabilita la possibilità per i membri del team di usare bot nelle chat e nei canali di Microsoft Teams **(bot a livello di organizzazione).**</li><li>Abilita bot specifici per Microsoft Teams. Non include il bot T-Bot, ovvero il bot della Guida di Teams disponibile quando i bot sono abilitati per l'organizzazione **(singoli bot).**</li><li>Consente o disabilita la possibilità per i membri del team di aggiungere estensioni o schede **(estensioni o schede).**</li><li>Abilita o disabilita il caricamento laterale dei bot proprietari per Microsoft Teams **(caricamento laterale dei bot).**</li><li>Consente o disabilita la possibilità per gli utenti di inviare messaggi di posta elettronica a un canale di Microsoft Teams **(e-mail del canale).**</li></ul>|
|Ruolo modificato dei membri del team    |MemberRoleChanged         |Un proprietario del team cambia il ruolo dei membri di un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente. <br><br>**1** - Indica il ruolo Membro.<br>**2** - Indica il ruolo Proprietario.<br>**3** - Indica il ruolo Guest.<br><br>La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.        |
|Impostazione del team modificata    |TeamSettingChanged        |L'operazione TeamSettingChanged viene registrata quando le attività seguenti vengono eseguite da un proprietario del team. Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata  (visualizzata tra parentesi) nella colonna Elemento nei risultati della ricerca nel log di controllo.<ul><li>Cambia il tipo di accesso per un team. I team possono essere impostati come privati o pubblici **(tipo di accesso team).** Quando un team è privato (impostazione predefinita), gli utenti possono accedervi solo su invito. Quando un team è pubblico, è individuabile da chiunque.</li><li>Cambia la classificazione delle informazioni di un team **(classificazione del team).** Ad esempio, i dati del team possono essere classificati come ad alto impatto aziendale, medio o basso.</li><li>Cambia il nome di un team (**Nome team**).</li><li>Cambia la descrizione del team **(descrizione del team).**</li><li>Modifiche apportate alle impostazioni del team. Per accedere a queste impostazioni, un proprietario del team può fare clic con il pulsante destro del mouse su un team, scegliere Gestisci **team** e quindi fare clic **sulla scheda** Impostazioni. Per queste attività, il nome dell'impostazione modificata viene visualizzato nella colonna **Elemento** nei risultati della ricerca nel log di controllo.</li></ul>         |
|Team creato    |TeamCreated         |Un utente crea un team.         |
|Eliminate tutte le app dell'organizzazione|DeletedAllOrganizationApps           |Tutte le app dell'organizzazione sono state eliminate dal catalogo.     |
|App eliminata |AppDeletedFromCatalog           |Un'app è stata eliminata dal catalogo.     |
|Canale eliminato     |ChannelDeleted         |Un utente elimina un canale da un team.         |
|Team eliminato  |TeamDeleted            |Un proprietario del team elimina un team.      |
|App installata |AppInstalled         |È stata installata un'app.   |
|Azione eseguita sulla scheda|PerformedCardAction|Un utente ha intervenire su una scheda adattiva all'interno di una chat. Le schede adattive vengono in genere usate dai bot per consentire una visualizzazione più ricca di informazioni e interazioni nelle chat. <br/><br/>**Nota:** Nel log di controllo saranno disponibili solo le azioni di input in linea su una scheda adattiva all'interno di una chat. Ad esempio, quando un utente invia una risposta a un sondaggio in una conversazione di canale su una scheda adattiva generata da un bot sondaggio. Le azioni dell'utente, ad esempio "Visualizza risultato", che apre una finestra di dialogo, o le azioni utente all'interno delle finestre di dialogo non saranno disponibili nel log di controllo.|
|App pubblicata |AppPublishedToCatalog           |È stata aggiunta un'app al catalogo.     |
|Bot rimosso dal team   |BotRemovedFromTeam         |Un utente rimuove un bot da un team.       |
|Connettore rimosso     |ConnectorRemoved         |Un utente rimuove un connettore da un canale.         |
|Membri rimossi    |MemberRemoved        |Il proprietario di un team rimuove membri da un team, un canale o una chat di gruppo.         |
|Scheda rimossa    |TabRemoved         |Un utente rimuove una scheda da un canale.         |
|App disinstallata |AppUninstalled           |È stata disinstallata un'app.     |
|App aggiornata |AppUpdatedInCatalog           |Un'app è stata aggiornata nel catalogo.     |
|Connettore aggiornato    |ConnectorUpdated         |Un utente ha modificato un connettore in un canale.         |
|Scheda aggiornata   |TabUpdated         |Un utente ha modificato una scheda in un canale.         |
|App aggiornata |AppUpgraded           |Un'app è stata aggiornata alla versione più recente nel catalogo.     |
|Utente connesso a Teams     |TeamsSessionStarted         |Un utente accede a un client Microsoft Teams. Questo evento non acquisisce le attività di aggiornamento del token.         |

## <a name="shifts-in-teams-activities"></a>Turni nelle attività di Teams

**(in anteprima)**

Se l'organizzazione usa l'app Turni in Teams, è possibile cercare nel log di controllo le attività correlate all'app Turni. Ecco un elenco di tutti gli eventi registrati per le attività di Turni in Teams nel log di controllo di Microsoft 365.

|Nome descrittivo  |Operazione  |Descrizione  |
|---------|---------|---------|
|Gruppo di pianificazione aggiunto |ScheduleGroupAdded          |Un utente aggiunge correttamente un nuovo gruppo di pianificazione alla pianificazione.|
|Gruppo di pianificazione modificato     |ScheduleGroupEdited         |Un utente modifica correttamente un gruppo di pianificazione.          |
|Gruppo di pianificazione eliminato         |ScheduleGroupDeleted              |Un utente elimina correttamente un gruppo di pianificazione dalla pianificazione.|
|Withdrew schedule |ScheduleWithdrawn              |Un utente ritira correttamente una pianificazione pubblicata.|
|Turno aggiunto      |ShiftAdded          |Un utente aggiunge un turno correttamente.           |
|Turno modificato       |ShiftEdited       |Un utente modifica correttamente un turno.        |
|Turno eliminato          |ShiftDeleted          | Un utente elimina correttamente un turno.               |
|È stato aggiunto un periodo di riposo      |TimeOffAdded          |Un utente aggiunge i tempi di riposo alla pianificazione.          |
|Periodo di riposo modificato         |TimeOffEdited           |Un utente modifica correttamente i dati in un periodo di riposo.          |
|Periodo di riposo eliminato     |TimeOffDeleted              |Un utente elimina correttamente i dati in fase di riposo.           |
|Aggiunto turno aperto     |OpenShiftAdded          |Un utente aggiunge correttamente un turno aperto a un gruppo di pianificazione.          |
|Turno aperto modificato    |OpenShiftEdited          |Un utente modifica correttamente un turno aperto in un gruppo di pianificazione.          |
|Eliminato turno aperto      |OpenShiftDeleted          |Un utente elimina correttamente un turno aperto da un gruppo di pianificazione.         |
|Pianificazione condivisa     |ScheduleShared                  |Un utente ha condiviso correttamente la pianificazione di un team per un intervallo di date.          |
|Orologio in orologio         |ClockedIn          |L'orologio dell'utente usa l'orologio.          |
|Clock out using Time clock      |ClockedOut          |L'uscita dell'utente con l'orologio viene completata correttamente.          |
|Interruzione avviata con il time clock      |BreakStarted          |Un utente avvia correttamente una pausa durante una sessione di orologio di orologio attiva.          |
|Interruzione terminata con l'orologio    |BreakEnded          |Un utente termina correttamente una pausa durante una sessione di orologio di orologio attiva.          |
|Voce Orologio e orologio aggiunta     |TimeClockEntryAdded          |Un utente aggiunge correttamente una nuova voce orologio manuale in Scheda attività.          |
|Voce orologio di data/ora modificata     | TimeClockEntryEdited             |Un utente modifica correttamente una voce del time clock nella scheda attività.          |
|Voce Orologio e orologio eliminata    |TimeClockEntryDeleted              |Un utente elimina correttamente una voce del time clock nella scheda attività.          |
|Aggiunta di una richiesta di turno         |RequestAdded              |Un utente ha aggiunto una richiesta di turno.          |
|Risposta alla richiesta di turno     |RequestRespondedTo                  |Un utente ha risposto a una richiesta di turno.          |
|Richiesta di turno annullata         |RequestCancelled               |Un utente ha annullato una richiesta di turno.          |
|Impostazione della pianificazione modificata      |ScheduleSettingChanged          |Un utente modifica un'impostazione nelle impostazioni di Turni.         |
|Aggiunta dell'integrazione della forza lavoro      |WorkforceIntegrationAdded                  | L'app Turni è integrata con un sistema di terze parti.         |
|Messaggio fuori turno accettato         |OffShiftDialogAccepted          |Un utente riconosce il messaggio fuori turno per accedere a Teams dopo il turno di lavoro.           |

## <a name="office-365-management-activity-api"></a>Office 365 Management Activity API

È possibile usare l'API Management Activity di Office 365 per recuperare informazioni sugli eventi di Teams. Per altre informazioni sullo schema API management activity per Teams, vedere [Schema di Teams.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema)

## <a name="attribution-in-teams-audit-logs"></a>Attribution nei log di controllo di Teams

Le modifiche all'appartenenza a Teams (ad esempio gli utenti aggiunti o eliminati) apportate tramite Azure Active Directory (Azure AD), il portale di amministrazione di Microsoft 365 o l'API Microsoft 365 Groups Graph verranno visualizzate nei messaggi di controllo di Teams e nel canale Generale con un'attribuzione a un proprietario esistente del team e non all'effettivo avvio dell'azione. In questi scenari, consultare i log di controllo di Azure AD o del gruppo di [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) per visualizzare le informazioni pertinenti.

## <a name="related-topics"></a>Argomenti correlati

- [Eseguire ricerche nel log di controllo nel Centro conformità di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
