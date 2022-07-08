## <a name="integration-models-for-solution-providers"></a>Modelli di integrazione per provider di soluzioni

<a name="steps"></a>

Come provider di soluzioni del centro contatti, sono disponibili tre modelli tra cui scegliere per integrare la soluzione del centro contatti connessa in Teams:

- Se desideri utilizzare SBC certificati e Direct Routing per connettere una soluzione del centro contatti a Teams, vedi il [modello Connect](?tabs=connect#steps).

- Se si vogliono usare i bot di Azure e le API di comunicazione di Microsoft Graph per consentire ai provider di soluzioni di creare app di Teams, vedere il [modello Extend](?tabs=extend#steps).

- Se si vuole usare un SDK che consenta ai provider di soluzioni di immettere esperienze native di Teams nell'app, vedere il [modello Power](?tabs=power#steps). Le soluzioni di risparmio energia saranno possibili quando l'SDK sarà disponibile. Prossimamente.

### <a name="the-connect-model"></a>[**Il modello Connect**](#tab/connect)

Il modello Connect usa gli SBC certificati Microsoft e direct routing per connettere le soluzioni del centro contatti all'infrastruttura del sistema telefonico di Teams, abilitando il routing avanzato, la configurazione e le informazioni di sistema.

Gli agenti possono configurare assistenti virtuali automatizzati e code di routing basate su competenze per raccogliere informazioni e connettere i clienti con esperti in materia.

**Caratteristiche in evidenza:**

Anche se queste funzionalità non sono un elenco completo delle funzionalità per questo modello di integrazione, le aree di interesse includono:

- Office 365 autenticazione per gli agenti per connettersi al tenant Microsoft dal client CCaaS integrato

- Vedere quando gli agenti sono disponibili con Teams

- Trasferimenti e supporto per chiamate di gruppo con Teams

- API Teams Graph e API di comunicazione cloud per l'integrazione con Teams

- Il trunking SIP multi-tenant per supportare diversi clienti in SBC del provider di soluzioni.

- Provider di soluzioni per l'uso del [<span class="underline">controller di bordo di sessione certificato Microsoft (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**Modello Extend**](#tab/extend)

Il modello Extend si integra con il client Teams usando la [piattaforma client di Teams](/microsoftteams/platform/overview), [le API Teams Graph](/graph/api/resources/teams-api-overview) e [l'API per le comunicazioni cloud in Microsoft Graph](/graph/api/resources/communications-api-overview). Il modello Extend utilizza anche il sistema telefonico Teams per tutte le esperienze di controllo delle chiamate e delle chiamate del centro contatti e il provider di soluzioni del centro contatti funge da gestore di telefonia insieme a Microsoft 365.

Gli agenti possono usare Teams per la collaborazione interna e la comunicazione esterna e possono trarre vantaggio da note dinamiche contestuali che correlano i dati di più sistemi prima di avviare un impegno ed evitare costosi cambi di contesto.

Le organizzazioni possono progettare flussi di lavoro e configurazioni di routing avanzate fino all'individuo e misurare la qualità del sistema e delle interazioni.

**Caratteristiche in evidenza:**

Anche se queste funzionalità non sono un elenco completo delle funzionalità per questo modello di integrazione, le aree di interesse includono:

- API Teams Graph e API di comunicazione cloud per l'integrazione con Teams

- App basata su Teams per esperienze con gli agenti

- Teams come endpoint di chiamata principale per gli agenti

- Chiamata client di Teams per tutti i controlli di chiamata

- App Esperienza agente sia per il web di Teams che per il client mobile

- Analisi, gestione dei flussi di lavoro, esperienze basate sui ruoli per gli agenti nell'app CCaaS in Teams

- Esperienze di chat e collaborazione integrate con i client di Teams

- Preservare le prestazioni e la qualità delle esperienze client di Teams in tutte le app

> [!NOTE]
> Il bot agente non ha bisogno di una licenza del sistema telefonico. L'utente di Teams ha bisogno di una licenza del sistema telefonico e di un numero di telefono.

### <a name="the-power-model"></a>[**Modello Power**](#tab/power)

Il modello Power consente ai provider di soluzioni di creare applicazioni vocali native basate su Azure usando l'infrastruttura per le chiamate di Teams e la piattaforma client per offrire soluzioni moderne e intelligenti per la connessione collaborativa di clienti e agenti. L'obiettivo del modello Power è fornire un'esperienza di centro contatti con un'app e una sola schermata.


> [!NOTE]
> Prossimamente.
