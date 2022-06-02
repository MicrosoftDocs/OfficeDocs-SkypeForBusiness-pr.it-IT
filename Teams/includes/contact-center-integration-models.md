## <a name="integration-models-for-solution-providers"></a>Modelli di integrazione per provider di soluzioni

<a name="steps"></a>

I provider di soluzioni del centro contatti possono scegliere tra tre modelli per integrare la soluzione del centro contatti connesso in Teams:

- Se desideri utilizzare schede SBC certificate e Direct Routing per connettere una soluzione del centro contatti a Teams, vedi il [modello Connessione](?tabs=connect#steps).

- Se vuoi usare i bot di Azure e le API di comunicazione di Microsoft Graph per consentire ai provider di soluzioni di creare app Teams, vedi il [modello Extend](?tabs=extend#steps).

- Se desideri utilizzare un SDK che consenta ai provider di soluzioni di immettere esperienze native Teams nell'app, vedi il [modello Power](?tabs=power#steps). Le soluzioni di risparmio energia saranno possibili quando l'SDK sarà disponibile. Prossimamente.

### <a name="the-connect-model"></a>[**Modello Connessione**](#tab/connect)

Il modello Connessione utilizza gli SBC certificati Microsoft e il routing diretto per connettere le soluzioni del centro contatti a Teams infrastruttura del sistema telefonico, abilitando il routing avanzato, la configurazione e informazioni dettagliate sul sistema.

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

Il modello Extend si integra con il client Teams utilizzando la [piattaforma client Teams](/microsoftteams/platform/overview), [le API Teams Graph](/graph/api/resources/teams-api-overview) e [l'API per le comunicazioni cloud in Microsoft Graph](/graph/api/resources/communications-api-overview). Il modello Extend utilizza anche il sistema telefonico Teams per tutte le esperienze di controllo delle chiamate e delle chiamate del centro contatti e il provider di soluzioni del centro contatti funge da gestore di telefonia insieme a Microsoft 365.

Gli agenti possono usare Teams per la collaborazione interna e la comunicazione esterna e possono trarre vantaggio da note dinamiche contestuali che correlano i dati di più sistemi prima di avviare un impegno ed evitare costosi cambi di contesto.

Le organizzazioni possono progettare flussi di lavoro e configurazioni di routing avanzate fino all'individuo e misurare la qualità del sistema e delle interazioni.

**Caratteristiche in evidenza:**

Anche se queste funzionalità non sono un elenco completo delle funzionalità per questo modello di integrazione, le aree di interesse includono:

- API Teams Graph e API di comunicazione cloud per l'integrazione con Teams

- app basata su Teams per le esperienze dell'agente

- Teams come endpoint chiamante principale per gli agenti

- Teams chiamata client per tutti i controlli chiamata

- App Esperienza agente sia per Teams web che per il client mobile

- Analisi, gestione dei flussi di lavoro, esperienze basate sui ruoli per gli agenti nell'app CCaaS in Teams

- Esperienze di chat e collaborazione integrate con client Teams

- Mantenere le prestazioni e la qualità delle esperienze client Teams in tutte le app

### <a name="the-power-model"></a>[**Modello Power**](#tab/power)

Il modello Power consente ai provider di soluzioni di creare applicazioni vocali native basate su Azure usando l'infrastruttura per le chiamate Teams e la piattaforma client per offrire soluzioni moderne e intelligenti per la connessione collaborativa di clienti e agenti. L'obiettivo del modello Power è fornire un'esperienza di centro contatti con un'app e una sola schermata.


> [!NOTE]
> Prossimamente.
