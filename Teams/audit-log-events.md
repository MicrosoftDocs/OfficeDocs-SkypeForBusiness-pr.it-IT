---
title: Cercare eventi in Microsoft Teams nel log di controllo
author: robmazz
ms.author: robmazz
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
description: Informazioni su come recuperare i dati di Microsoft Teams dal log di controllo nel Portale di conformità di Microsoft Purview.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7d94411132b575aa4754aae993f070a36718a2d
ms.sourcegitcommit: 6754f2d11da0afff067f0872acf778a83fd1595e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2022
ms.locfileid: "67808447"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Cercare eventi in Microsoft Teams nel log di controllo

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Il log di controllo consente di esaminare attività specifiche in tutti i servizi di Microsoft 365. Per Microsoft Teams, ecco alcune attività controllate:

- Creazione di team
- Eliminazione del team
- Canale aggiunto
- Canale eliminato
- Impostazione del canale modificata

Per un elenco completo delle attività di Teams controllate, vedere [Attività di Teams](#teams-activities) e [Turni nelle attività di Teams](#shifts-in-teams-activities).

> [!NOTE]
> Anche gli eventi di controllo dai canali privati vengono registrati così come sono per i team e i canali standard.

## <a name="turn-on-auditing-in-teams"></a>Attivare il controllo in Teams

Prima di poter esaminare i dati di controllo, è necessario attivare il controllo nel Portale di conformità di Microsoft Purview. Per altre informazioni, vedere [Attivare o disattivare il controllo](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

> [!IMPORTANT]
> I dati di controllo sono disponibili solo dal punto in cui è stato attivato il controllo.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperare i dati di Teams dal log di controllo

1. Per recuperare i log di controllo per le attività di Teams, passare a <https://compliance.microsoft.com> e selezionare **Controlla**.

2. Nella pagina **Cerca** filtrare le attività, le date e gli utenti da controllare.

3. Esportare i risultati in Excel per un'ulteriore analisi.

Per istruzioni dettagliate, vedere [Eseguire ricerche nel log di controllo nel centro conformità](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

> [!IMPORTANT]
> I dati di controllo sono visibili nel log di controllo solo se il controllo è attivato.

Il periodo di conservazione e di ricerca di un record di controllo nel log di controllo dipende dall'abbonamento a Microsoft 365 o Office 365 e in particolare dal tipo di licenza assegnata agli utenti. Per altre informazioni, vedere la [descrizione del servizio Centro conformità & sicurezza](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel log di controllo

Ecco i suggerimenti per cercare le attività di Teams nel log di controllo.

:::image type="content" alt-text="Screenshot della pagina di ricerca nel log di controllo nel Centro conformità" source="media/audit-log-search-page.png" lightbox="media/audit-log-search-page.png":::

- È possibile selezionare attività specifiche da cercare facendo clic sulla casella di controllo accanto a una o più attività. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È anche possibile usare la casella di ricerca per visualizzare le attività che contengono la parola chiave digitata.

  ![Screenshot dell'elenco a discesa attività nella pagina di ricerca del log di controllo](media/audit-log-search.png)

- Per visualizzare gli eventi per le attività eseguite con i cmdlet, selezionare **Mostra i risultati per tutte le attività** nell'elenco **Attività** . Se si conosce il nome dell'operazione per queste attività, digitarlo nella casella di ricerca per visualizzare l'attività e selezionarla.

- Per cancellare i criteri di ricerca correnti, fare clic su **Cancella tutto**. L'intervallo di date torna al valore predefinito degli ultimi sette giorni.

- Se vengono trovati 5.000 risultati, è probabile che siano presenti più di 5.000 eventi che soddisfa i criteri di ricerca. È possibile perfezionare i criteri di ricerca ed eseguire di nuovo la ricerca per restituire meno risultati oppure è possibile esportare tutti i risultati della ricerca selezionando **Esporta** > **Scarica tutti i risultati**. Per istruzioni dettagliate su come esportare i log di controllo, vedere [Esportare i risultati della ricerca in un file](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#step-3-export-the-search-results-to-a-file).

Guardare [questo video](https://www.youtube.com/embed/UBxaRySAxyE) per informazioni sull'uso della ricerca nel log audio. Unisciti a Ansuman Acharya, program manager di Teams, mentre dimostra come eseguire una ricerca nel log di controllo per Teams.

## <a name="teams-activities"></a>Attività di Teams

Ecco un elenco di tutti gli eventi registrati per le attività di utenti e amministratori in Teams nel log di controllo di Microsoft 365. La tabella include il nome descrittivo visualizzato nella colonna **Attività** e il nome dell'operazione corrispondente visualizzato nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca.

|Nome descrittivo|Operazione|Descrizione|
|---|---|---|
|Aggiunto bot al team|BotAddedToTeam|Un utente aggiunge un bot a un team.|
|Canale aggiunto|ChannelAdded|Un utente aggiunge un canale a un team.|
|Connettore aggiunto|ConnectorAdded|Un utente aggiunge un connettore a un canale.|
|Aggiunti dettagli sulla riunione <sup>2</sup> di Teams|MeetingDetail|Teams ha aggiunto informazioni su una riunione, tra cui l'ora di inizio, l'ora di fine e l'URL per partecipare alla riunione.|
|Aggiunta di informazioni sui partecipanti <sup>alla riunione 2</sup>|MeetingParticipantDetail|Teams ha aggiunto informazioni sui partecipanti a una riunione, tra cui l'ID utente di ogni partecipante, l'ora in cui un partecipante si è unito alla riunione e l'ora in cui un partecipante ha lasciato la riunione.|
|Membri aggiunti|MemberAdded|Un proprietario del team aggiunge membri a un team, un canale o una chat di gruppo.|
|Scheda aggiunta|TabAdded|Un utente aggiunge una scheda a un canale.|
|Impostazione del canale modificata|ChannelSettingChanged|L'operazione ChannelSettingChanged viene registrata quando le attività seguenti vengono eseguite da un membro del team. Per ognuna di queste attività, una descrizione dell'impostazione modificata (tra parentesi viene visualizzata nella colonna **Elemento** nei risultati della ricerca nel log di controllo. <ul><li>Cambia il nome di un canale del team (**nome del canale**)</li><li>Modifica della descrizione di un canale del team (**descrizione del canale**)</li> </ul>|
|Impostazione dell'organizzazione modificata|TeamsTenantSettingChanged|L'operazione TeamsTenantSettingChanged viene registrata quando le attività seguenti vengono eseguite da un amministratore globale nel interfaccia di amministrazione di Microsoft 365. Queste attività influiscono sulle impostazioni di Teams a livello di organizzazione. Per altre informazioni, vedere [Gestire le impostazioni di Teams per l'organizzazione](enable-features-office-365.md). <br>Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione modificata (tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo.<ul><li>Abilita o disabilita Teams per l'organizzazione (**Microsoft Teams**).</li><li>Abilita o disabilita l'interoperabilità tra Microsoft Teams e Skype for Business per l'organizzazione (**interoperabilità Skype for Business**).</li><li>Abilita o disabilita la visualizzazione organigramma nei client di Microsoft Teams (**visualizzazione organigramma**).</li><li>Consente o impedisce ai membri del team di pianificare riunioni private (**pianificazione di riunioni private**).</li><li>Consente o impedisce ai membri del team di pianificare riunioni di canale (**pianificazione delle riunioni di canale**).</li><li>Abilita o disabilita le videochiamate nelle riunioni di Teams (**Video per riunioni Skype**).</li><li>Abilita o disabilita la condivisione dello schermo nelle riunioni di Microsoft Teams per l'organizzazione (**condivisione dello schermo per le riunioni Skype**).</li><li>Abilita o impedisce l'aggiunta di immagini animate (chiamate Giphy) alle conversazioni di Teams (**immagini animate**).</li><li>Modifica l'impostazione di classificazione del contenuto per l'organizzazione (**classificazione del contenuto**). La classificazione del contenuto limita il tipo di immagine animata che può essere visualizzata nelle conversazioni.</li><li>Consente o impedisce ai membri del team di aggiungere immagini personalizzabili (chiamate meme personalizzati) da Internet alle conversazioni del team (**immagini personalizzabili da Internet**).</li><li>Consente o impedisce ai membri del team di aggiungere immagini modificabili (dette adesivi) alle conversazioni del team (**immagini modificabili**).</li><li>Consente o impedisce ai membri del team di usare bot nelle chat e nei canali di Microsoft Teams (**bot a livello di organizzazione).**</li><li>Abilita bot specifici per Microsoft Teams. Questo non include il T-Bot, ovvero il bot della Guida di Teams disponibile quando i bot sono abilitati per l'organizzazione (**singoli bot**).</li><li>Consente o impedisce ai membri del team di aggiungere estensioni o schede (**estensioni o schede**).</li><li>Abilita o disabilita il caricamento laterale dei bot proprietari per Microsoft Teams (**caricamento laterale dei bot**).</li><li>Consente o impedisce agli utenti di inviare messaggi di posta elettronica a un canale di Microsoft Teams (**e-mail di canale**).</li></ul>|
|Ruolo cambiato dei membri del team|MemberRoleChanged|Il proprietario di un team cambia il ruolo dei membri di un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente. <br><br>**1** - Indica il ruolo Membro.<br>**2** - Indica il ruolo Proprietario.<br>**3** - Indica il ruolo Guest.<br><br>La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.|
|Impostazione del team modificata|TeamSettingChanged|L'operazione TeamSettingChanged viene registrata quando le attività seguenti vengono eseguite da un proprietario del team. Per ognuna di queste attività, viene visualizzata una descrizione dell'impostazione modificata (tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo.<ul><li>Cambia il tipo di accesso per un team. I team possono essere impostati come privati o pubblici (**tipo di accesso team**). Quando un team è privato (impostazione predefinita), gli utenti possono accedere al team solo su invito. Quando un team è pubblico, è individuabile da chiunque.</li><li>Modifica la classificazione delle informazioni di un team (**classificazione del team**). Ad esempio, i dati del team possono essere classificati come ad alto impatto aziendale, medio o basso impatto aziendale.</li><li>Modifica il nome di un team (**nome del team**).</li><li>Modifica la descrizione del team (**descrizione del team**).</li><li>Modifiche apportate alle impostazioni del team. Per accedere a queste impostazioni, un proprietario del team può fare clic con il pulsante destro del mouse su un team, selezionare **Gestisci team** e quindi fare clic sulla scheda **Impostazioni** . Per queste attività, il nome dell'impostazione modificata viene visualizzato nella colonna **Elemento** nei risultati della ricerca nel log di controllo.</li></ul>|
|Creato una chat <sup>1, </sup> <sup>2</sup>|ChatCreata|È stata creata una chat di Teams.|
|Team creato|TeamCreato|Un utente crea un team.|
|È stato eliminato un messaggio|MessageDeleted|Un messaggio in una chat o in un canale è stato eliminato.|
|Eliminate tutte le app dell'organizzazione|DeletedAllOrganizationApps|Tutte le app dell'organizzazione sono state eliminate dal catalogo.|
|App eliminata|AppDeletedFromCatalog|Un'app è stata eliminata dal catalogo.|
|Canale eliminato|ChannelDeleted|Un utente elimina un canale da un team.|
|Team eliminato|TeamDeleted|Un proprietario del team elimina un team.|
|È stato modificato un messaggio con un collegamento URL in Teams|MessageEditedHasLink|Un utente modifica un messaggio e aggiunge un collegamento URL in Teams.|
|Messaggi esportati <sup>1, </sup> <sup>2</sup>|MessaggiEsportati|Sono stati esportati messaggi di chat o di canale.|
|Non è possibile convalidare l'invito al canale condiviso<sup>3</sup>|FailedValidation|Un utente risponde a un invito a un canale condiviso, ma la convalida dell'invito non è riuscita.|
|Chat recuperata <sup>1, </sup> <sup>2</sup>|ChatRetrieved|È stata recuperata una chat di Microsoft Teams.|
|Recupero di tutto il contenuto ospitato di un messaggio<sup>1, </sup> <sup>2</sup>|MessageHostedContentsListed|È stato recuperato tutto il contenuto ospitato in un messaggio, ad esempio immagini o frammenti di codice.|
|App installata|AppInstallato|È stata installata un'app.|
|Azione eseguita sulla scheda|PerformedCardAction|Un utente ha intrapreso un'azione su una scheda adattiva all'interno di una chat. Le schede adattive vengono in genere usate dai bot per consentire una visualizzazione ricca di informazioni e interazioni nelle chat. <br/><br/>**Nota:** Nel log di controllo saranno disponibili solo le azioni di input in linea in una scheda adattiva all'interno di una chat. Ad esempio, quando un utente invia una risposta a un sondaggio in una conversazione del canale su una scheda adattiva generata da un bot sondaggio. Le azioni utente, ad esempio "Visualizza risultato", che aprirà una finestra di dialogo o le azioni utente all'interno delle finestre di dialogo, non saranno disponibili nel log di controllo.|
|Pubblicato un nuovo messaggio <sup>1, </sup> <sup>2</sup>|MessageSent|È stato pubblicato un nuovo messaggio in una chat o in un canale.|
|App pubblicata|AppPublishedToCatalog|Al catalogo è stata aggiunta un'app.|
|Leggere un messaggio <sup>1, </sup> <sup>2</sup>|Messaggio Letto|È stato recuperato un messaggio di una chat o di un canale.|
|Leggere il contenuto ospitato di un messaggio <sup>1, </sup> <sup>2</sup>|MessageHostedContentRead|Il contenuto ospitato in un messaggio, ad esempio un'immagine o un frammento di codice, è stato recuperato.|
|Bot rimosso dal team|BotRemovedFromTeam|Un utente rimuove un bot da un team.|
|Connettore rimosso|Connettoreremoto|Un utente rimuove un connettore da un canale.|
|Membri rimossi|MembroRemoved|Un proprietario del team rimuove i membri da un team, un canale o una chat di gruppo.|
|Rimozione della condivisione del canale<sup>del team 3</sup>|TerminatedSharing|Il proprietario di un team o di un canale ha disabilitato la condivisione per un canale condiviso.|
|Condivisione ripristinata del canale del team<sup>3</sup>|SharingRestored|Il proprietario di un team o di un canale ha riattivata la condivisione per un canale condiviso.|
|Scheda Rimossa|TabRimuovere|Un utente rimuove una scheda da un canale.|
|Risposta all'invito per il canale condiviso<sup>3</sup>|InviteeResponded|Un utente ha risposto a un invito a un canale condiviso.|
|Risposta dell'invitato al canale condiviso<sup>3</sup>|ChannelOwnerResponded|Il proprietario di un canale ha risposto a una risposta di un utente che ha risposto a un invito a un canale condiviso.|
|Messaggi recuperati <sup>1, </sup> <sup>2</sup>|Messaggi elencati|Sono stati recuperati messaggi da una chat o da un canale.|
|Inviato un messaggio con un collegamento URL in Teams|MessageCreatedHasLink|Un utente invia un messaggio contenente un collegamento URL in Teams.|
|Notifica di modifica inviata per la creazione di messaggi <sup>1, </sup> <sup>2</sup>|MessageCreatedNotification|È stata inviata una notifica di modifica per notificare a un'applicazione listener sottoscritta un nuovo messaggio.|
|Notifica di modifica inviata per l'eliminazione <sup>dei messaggi 1, </sup> <sup>2</sup>|MessageDeletedNotification|È stata inviata una notifica di modifica per notificare a un'applicazione listener sottoscritta un messaggio eliminato.|
|Notifica di modifica inviata per l'aggiornamento <sup>del messaggio 1, </sup> <sup>2</sup>|MessageUpdatedNotification|È stata inviata una notifica di modifica per notificare a un listener sottoscritto un messaggio aggiornato.|
|Invito inviato per il canale condiviso<sup>3</sup>|InviteSent|Un proprietario o un membro del canale invia un invito a un canale condiviso. Gli inviti ai canali condivisi possono essere inviati a persone esterne all'organizzazione se i criteri del canale sono configurati per condividere il canale con utenti esterni.|
|Abbonato alle notifiche di modifica dei messaggi <sup>1, </sup> <sup>2</sup>|SubscribedToMessages|Un abbonamento è stato creato da un'applicazione listener per ricevere notifiche di modifica per i messaggi.|
|App disinstallata|App Non installata|Un'app è stata disinstallata.|
|App aggiornata|AppUpdatedInCatalog|Un'app è stata aggiornata nel catalogo.|
|Aggiornata una chat <sup>1, </sup> <sup>2</sup>|ChatUpdated|È stata aggiornata una chat di Teams.|
|Aggiornato un messaggio <sup>1, </sup> <sup>2</sup>|MessageUpdated|È stato aggiornato un messaggio di una chat o di un canale.|
|Connettore aggiornato|ConnectorUpdated|Un utente ha modificato un connettore in un canale.|
|Scheda aggiornata|TabUpdated|Un utente ha modificato una scheda in un canale.|
|App aggiornata|AppUpgraded|Un'app è stata aggiornata alla versione più recente nel catalogo.|
|Utente connesso a Teams|TeamsSessionStarted|Un utente accede a un client di Microsoft Teams. Questo evento non acquisisce le attività di aggiornamento dei token.|

> [!NOTE]
> <sup>1</sup> Un record di controllo per questo evento viene registrato solo quando l'operazione viene eseguita chiamando un API Graph Microsoft. Se l'operazione viene eseguita nel client di Teams, non verrà registrato un record di controllo<br/><sup>2</sup> Questo evento è disponibile solo in Audit (Premium). Questo significa che agli utenti deve essere assegnata la licenza appropriata prima che questi eventi vengano registrati nel log di controllo. Per altre informazioni sulle attività disponibili solo in Audit (Premium), vedi [Audit (Premium) in Microsoft Purview](/microsoft-365/compliance/advanced-audit#advanced-audit-events). Per i requisiti di licenza di controllo (Premium), vedere [Soluzioni di controllo in Microsoft 365](/microsoft-365/compliance/auditing-solutions-overview#licensing-requirements). <br/> <sup>3</sup> Questo evento è in anteprima pubblica.

## <a name="shifts-in-teams-activities"></a>Turni nelle attività di Teams

**(in anteprima)**

Se l'organizzazione usa l'app Turni in Teams, è possibile cercare nel log di controllo le attività correlate all'app Turni. Ecco un elenco di tutti gli eventi registrati per le attività di Turni in Teams nel log di controllo di Microsoft 365.

|Nome descrittivo|Operazione|Descrizione|
|---|---|---|
|Aggiunta di un gruppo di pianificazione|ScheduleGroupAdded|Un utente aggiunge correttamente un nuovo gruppo di pianificazione alla pianificazione.|
|Gruppo di pianificazione modificato|ScheduleGroupEdited|Un utente modifica correttamente un gruppo di pianificazione.|
|Gruppo di pianificazione eliminato|ScheduleGroupDeleted|Un utente elimina correttamente un gruppo di pianificazione dalla pianificazione.|
|Programma ritirato|ScheduleWithdrawn|Un utente ritira correttamente una pianificazione pubblicata.|
|Turno aggiunto|MaiuscAggiunta|Un utente aggiunge correttamente un turno.|
|Turno modificato|Maiusc Modificato|Un utente modifica correttamente un turno.|
|Turno eliminato|MaiuscEliminato|Un utente elimina correttamente un turno.|
|Permesso aggiunto|TimeOffAdded|Un utente aggiunge correttamente i permessi nella pianificazione.|
|Permesso modificato|TimeOffEdited|Un utente modifica correttamente i permessi.|
|Permesso eliminato|TimeOffDeleted|Un utente elimina correttamente i permessi.|
|Aggiunto turno aperto|OpenShiftAdded|Un utente aggiunge correttamente un turno aperto a un gruppo di pianificazione.|
|Turno aperto modificato|OpenShiftEdited|Un utente modifica correttamente un turno aperto in un gruppo di pianificazione.|
|Eliminato turno aperto|OpenShiftDeleted|Un utente elimina correttamente un turno aperto da un gruppo di pianificazione.|
|Pianificazione condivisa|ScheduleShared|Un utente ha condiviso correttamente una pianificazione del team per un intervallo di date.|
|Orologio con orologio|ClockedIn|Un utente esegue correttamente l'orologio con l'orologio.|
|Uscita con orologio|ClockedOut|Un utente esegue correttamente l'uscita utilizzando l'orologio.|
|Interruzione avviata con l'orologio|BreakStarted|Un utente avvia correttamente un'interruzione durante una sessione orologio attiva.|
|Interruzione terminata con orologio|BreakEnded|Un utente termina correttamente un'interruzione durante una sessione orologio attiva.|
|Aggiunta della voce Orologio|TimeClockEntryAdded|Un utente aggiunge correttamente una nuova voce orologio manuale nel Foglio attività.|
|Immissione orologio modificata|TimeClockEntryEdited|Un utente modifica correttamente una voce orologio nel Foglio attività.|
|Voce orologio eliminata|TimeClockEntryDeleted|Un utente elimina correttamente una voce Orologio nel Foglio attività.|
|Aggiunta della richiesta di turno|RequestAdded|Un utente ha aggiunto una richiesta di turno.|
|Risposta alla richiesta di turno|RequestRespondedTo|Un utente ha risposto a una richiesta di turno.|
|Richiesta di turno annullata|RequestCancelled|Un utente ha annullato una richiesta di turno.|
|Impostazione della pianificazione modificata|ScheduleSettingChanged|Un utente modifica un'impostazione nelle impostazioni di Turni.|
|Integrazione della forza lavoro aggiunta|WorkforceIntegrationAdded|L'app Turni è integrata con un sistema di terze parti.|
|Messaggio accettato fuori turno|OffShiftDialogAccepted|Un utente riconosce il messaggio fuori turno per accedere a Teams dopo le ore di turno.|

## <a name="office-365-management-activity-api"></a>API Management Activity di Office 365

È possibile usare l'API Office 365 Management Activity per recuperare informazioni sugli eventi di Teams. Per altre informazioni sullo schema dell'API Management Activity per Teams, vedere [Schema di Teams](/office/office-365-management-api/office-365-management-activity-api-schema#microsoft-teams-schema).

## <a name="attribution-in-teams-audit-logs"></a>Attribuzione nei log di controllo di Teams

Le modifiche dell'appartenenza a Teams (ad esempio gli utenti aggiunti o eliminati) apportate tramite Azure Active Directory (Azure AD), il portale di amministrazione di Microsoft 365 o Gruppi di Microsoft 365 API Graph verranno visualizzate nei messaggi di controllo di Teams e nel canale Generale con l'attribuzione a un proprietario esistente del team e non all'effettivo iniziatore dell'azione. In questi scenari, consultare i log di controllo di Azure AD o [del gruppo di Microsoft 365](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) per visualizzare le informazioni pertinenti.

## <a name="use-defender-for-cloud-apps-to-set-activity-policies"></a>Usare Defender per le app cloud per impostare i criteri attività

Con [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) integrazione, è possibile impostare criteri [attività](/cloud-app-security/user-activity-policies) per applicare un'ampia gamma di processi automatizzati usando le API del provider dell'app. Questi criteri consentono di monitorare attività specifiche eseguite da vari utenti o di seguire tassi inaspettatamente elevati di un determinato tipo di attività.

Dopo aver impostato un criterio di rilevamento attività, inizia a generare avvisi. Gli avvisi vengono generati solo per le attività che si verificano dopo la creazione del criterio. Ecco alcuni scenari di esempio su come usare i criteri attività in Defender for Cloud Apps per monitorare le attività di Teams.

### <a name="external-user-scenario"></a>Scenario utente esterno

Uno scenario su cui tenere sotto controllo, dal punto di vista aziendale, è l'aggiunta di utenti esterni all'ambiente di Teams. Se gli utenti esterni sono abilitati, è consigliabile monitorare la loro presenza.  Puoi usare [Defender for Cloud Apps per](/cloud-app-security/what-is-cloud-app-security) identificare potenziali minacce.

:::image type="content" alt-text="Criteri per monitorare l'aggiunta di utenti esterni." source="media/TeamsExternalUserAddPolicy.png" lightbox="media/TeamsExternalUserAddPolicy.png":::

Lo screenshot di questo criterio per monitorare l'aggiunta di utenti esterni consente di assegnare un nome al criterio, impostare la gravità in base alle esigenze aziendali, impostarla come (in questo caso) una singola attività, quindi stabilire i parametri che monitoreranno in modo specifico solo l'aggiunta di utenti non interni e limitare questa attività a Teams.

I risultati di questo criterio possono essere visualizzati nel log attività:

:::image type="content" alt-text="Eventi attivati dai criteri degli utenti esterni." source="media/TeamsExternalUserList.png" lightbox="media/TeamsExternalUserList.png":::

Qui è possibile esaminare le corrispondenze ai criteri impostati e apportare eventuali modifiche in base alle esigenze oppure esportare i risultati da usare altrove.

### <a name="mass-delete-scenario"></a>Scenario di eliminazione di massa

Come accennato in precedenza, è possibile monitorare gli scenari di eliminazione. È possibile creare un criterio che monitorerebbe l'eliminazione di massa dei siti di Teams. In questo esempio è configurato un criterio basato su avvisi per rilevare l'eliminazione di massa dei team in un intervallo di 30 minuti.

:::image type="content" alt-text="Criterio che mostra la configurazione di un criterio per il rilevamento dell'eliminazione del team di massa." source="media/TeamsMassDeletePolicy.png" lightbox="media/TeamsMassDeletePolicy.png":::

Come mostra lo screenshot, è possibile impostare molti parametri diversi per questo criterio per monitorare le eliminazioni di Teams, tra cui la gravità, l'azione singola o ripetuta e i parametri che lo limitano all'eliminazione di Teams e del sito. Questa operazione può essere eseguita indipendentemente da un modello oppure è possibile che sia stato creato un modello su cui basare questo criterio, a seconda delle esigenze dell'organizzazione.

Dopo aver definito un criterio adatto per l'azienda, è possibile esaminare i risultati nel log attività man mano che vengono attivati gli eventi:

:::image type="content" alt-text="Screenshot degli eventi attivati dalle eliminazioni di massa." source="media/TeamsMassDeleteList.png" lightbox="media/TeamsMassDeleteList.png":::

È possibile filtrare in base al criterio impostato per visualizzare i risultati del criterio. Se i risultati ottenuti nel log attività non sono soddisfacenti (ad esempio se vengono visualizzati molti risultati o niente), questo può essere utile per ottimizzare la query per renderla più pertinente a ciò che serve.

### <a name="alert-and-governance-scenario"></a>Scenario di avviso e governance

È possibile impostare avvisi e inviare messaggi di posta elettronica agli amministratori e ad altri utenti quando viene attivato un criterio attività. È possibile impostare azioni di governance automatizzate, ad esempio sospendere un utente o fare in modo che un utente accinga di nuovo in modo automatizzato. Questo esempio mostra come un account utente può essere sospeso quando viene attivato un criterio attività e determina che un utente ha eliminato due o più team in 30 minuti.

![Screenshot di avvisi e azioni di governance per un criterio attività.](media/audit-log-governance.png)

## <a name="use-defender-for-cloud-apps-to-set-anomaly-detection-policies"></a>Usare Defender per le app cloud per impostare criteri di rilevamento anomalie

I [criteri di rilevamento anomalie](/cloud-app-security/anomaly-detection-policy) in Defender per le app cloud forniscono analisi comportamentali di utenti ed entità predefinite (UEBA) e machine learning (ML) in modo da poter eseguire immediatamente il rilevamento avanzato delle minacce nell'ambiente cloud. Poiché sono abilitati automaticamente, i nuovi criteri di rilevamento anomalie forniscono risultati immediati fornendo rilevamenti immediati e prendendo di mira numerose anomalie comportamentali tra gli utenti e i computer e dispositivi connessi alla rete. Inoltre, i nuovi criteri espongono più dati dal motore di rilevamento di Defender for Cloud Apps, per aiutarti a velocizzare il processo di indagine e contenere minacce in corso.

Stiamo lavorando per integrare gli eventi di Teams nei criteri di rilevamento anomalie. Per il momento, è possibile configurare criteri di rilevamento anomalie per altri prodotti Office e intervenire sugli utenti che corrispondono a tali criteri.

## <a name="related-topics"></a>Argomenti correlati

- [Eseguire ricerche nel log di controllo nel Portale di conformità di Microsoft Purview](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
