## <a name="integration-models-for-solution-providers"></a>Modelli di integrazione per i provider di soluzioni

<a name="steps"></a>

I provider di soluzioni del contact center possono scegliere tra tre modelli per integrare la soluzione del contact center connessa in Teams:

- Se si vogliono usare SBC certificati e Routing diretto per connettere una soluzione di contact center a Teams, vedere il modello [Connessione.](?tabs=connect#steps)

- Se si vogliono usare i bot di Azure e le API di comunicazione di Microsoft Graph per consentire ai provider di soluzioni di creare app Teams, vedere il modello [Distendi.](?tabs=extend#steps)

- Se si vuole usare un SDK che consente ai provider di soluzioni di inserire esperienze Teams native nell'app, vedere il [modello Power.](?tabs=power#steps) Le soluzioni di alimentazione saranno possibili quando l'SDK sarà disponibile verso la fine del 2021.

### <a name="the-connect-model"></a>[**Modello Connessione**](#tab/connect)

Il modello Connessione usa SBC certificati Microsoft e Routing diretto per connettere le soluzioni dei contact center all'infrastruttura del sistema telefonico di Teams, consentendo informazioni avanzate su routing, configurazione e sistema.

Gli agenti possono configurare assistenti virtuali automatizzati e code di routing basate sulle competenze per raccogliere informazioni e connettere i clienti con esperti in materia.

**Caratteristiche evidenziate:**

Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - Office 365 authN per gli agenti per connettersi al proprio tenant Microsoft dal client CCaaS integrato 

  - Vedere quando gli agenti sono disponibili con Teams

  - Trasferimenti e supporto per chiamate di gruppo con Teams 

  - Teams Graph api e API di comunicazione cloud per l'integrazione con Teams 

  - Trunking SIP multi-tenant per supportare diversi clienti nell'SBC del provider di soluzioni.  

  - Provider di soluzioni per l'uso [ <span class="underline">di Microsoft Certified Session Border Controller (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**Modello Distendi**](#tab/extend)

Il modello Extend si integra con il client Teams usando la piattaforma [client Teams](/microsoftteams/platform/overview), le API [Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e Cloud Communications API in [Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0). Il modello Extend usa anche il sistema telefonico Teams per tutte le chiamate al contact center e le esperienze di controllo delle chiamate e il provider di soluzioni del contact center funge da gestore di telefonia insieme a Microsoft 365.

Gli agenti possono usare Teams per la collaborazione interna e la comunicazione esterna e possono trarre vantaggio da note contestuali dinamiche che correlano i dati di più sistemi prima di avviare un impegno e quindi evitare costose opzioni di cambio di contesto.

Le organizzazioni possono progettare flussi di lavoro e configurazioni avanzate di routing fino all'individuo e misurare la qualità del sistema e delle interazioni.

**Caratteristiche evidenziate:**

Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - Teams Graph api e API di comunicazione cloud per l'integrazione con Teams 

  - Teams app basata su agenti 

  - Teams endpoint chiamante principale per gli agenti 

  - Teams client chiama per tutti i controlli di chiamata

  - App esperienza agente per client Teams Web e per dispositivi mobili

  - Analisi, gestione del flusso di lavoro, esperienze basate sui ruoli per gli agenti nell'app CCaaS in Teams

  - Esperienze di chat e collaborazione integrate con Teams client 

  - Mantenere le prestazioni e la qualità delle Teams client in tutte le app  

### <a name="the-power-model"></a>[**Il modello Power**](#tab/power)

Il modello Power consente ai provider di soluzioni di creare applicazioni vocali native basate su Azure usando l'infrastruttura di chiamata Teams e la piattaforma client per offrire soluzioni moderne e intelligenti per la connessione collaborativa con clienti e agenti. L'obiettivo del modello Power è offrire un'esperienza di contact center con un'unica app e uno schermo.

**Caratteristiche evidenziate:**

Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - Esperienze di agente formale abilitate in modo nativo per la comunicazione omnicanale tramite Teams SDK 

  - Usare Teams di collaborazione per la collaborazione con agenti e le interazioni con i clienti  

  - Provisioning rapido dei servizi cloud, distribuzione ovunque 

  - Controllo diretto delle conversazioni e interazione con gli utenti durante Teams conversazioni 

>[!NOTE]
> Il modello Power sarà disponibile verso la fine del 2021.
