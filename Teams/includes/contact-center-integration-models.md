## <a name="integration-models-for-solution-providers"></a>Modelli di integrazione per i provider di soluzioni

<a name="steps"></a>

I provider di soluzioni del contact center possono scegliere tra tre modelli per integrare la soluzione di contact center connessa in Teams:

- Se si vogliono usare SBC certificati e Routing diretto per connettere una soluzione di contact center a Teams, vedere il [modello Connetti](?tabs=connect#steps).

- Se si vogliono usare i bot di Azure e le API di comunicazione di Microsoft Graph per consentire ai provider di soluzioni di creare app di Teams, vedere [il modello Distendi.](?tabs=extend#steps)

- Se si vuole usare un SDK che consenta ai provider di soluzioni di inserire esperienze native di Teams nella propria app, vedere il [modello Power.](?tabs=power#steps) Le soluzioni di alimentazione saranno possibili quando l'SDK sarà disponibile verso la fine del 2021.

### <a name="the-connect-model"></a>[**Modello Connect**](#tab/connect)

Il modello Connect usa SBC certificati Microsoft e Routing diretto per connettere le soluzioni dei contact center all'infrastruttura del sistema telefonico di Teams, consentendo informazioni avanzate su routing, configurazione e sistema.

Gli agenti possono configurare assistenti virtuali automatizzati e code di routing basate sulle competenze per raccogliere informazioni e connettere i clienti con esperti in materia.

**Caratteristiche evidenziate:**

Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - AuthN di Office 365 per gli agenti che si connettono al tenant Microsoft dal client CCaaS integrato 

  - Vedere quando gli agenti sono disponibili con Teams

  - Trasferimenti e supporto per le chiamate di gruppo con Teams 

  - API di Teams Graph e Cloud Communication API per l'integrazione con Teams 

  - Trunking SIP multi-tenant per supportare diversi clienti nell'SBC del provider di soluzioni.  

  - Provider di soluzioni per l'uso [ <span class="underline">di Microsoft Certified Session Border Controller (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**Modello Distendi**](#tab/extend)

Il modello Extend si integra con il client Teams usando la piattaforma [client Teams,](/microsoftteams/platform/overview)le [API di Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e [l'API Cloud Communications in Microsoft Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) Il modello Extend usa anche il sistema telefonico Teams per tutte le chiamate al contact center e le esperienze di controllo delle chiamate e il provider di soluzioni del contact center funge da gestore di telefonia insieme a Microsoft 365.

Gli agenti possono usare Teams per la collaborazione interna e la comunicazione esterna e possono trarre vantaggio da note dinamiche e contestuali che mettono in correlazione i dati di più sistemi prima di avviare un impegno e quindi evitare costose opzioni di cambio di contesto.

Le organizzazioni possono progettare flussi di lavoro e configurazioni avanzate di routing fino all'individuo e misurare la qualità del sistema e delle interazioni.

**Caratteristiche evidenziate:**

Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - API di Teams Graph e Cloud Communication API per l'integrazione con Teams 

  - App basata su Teams per le esperienze degli agenti 

  - Teams come endpoint chiamante principale per gli agenti 

  - Chiamate client di Teams per tutti i controlli di chiamata

  - App esperienza agente sia per il web di Teams che per il client per dispositivi mobili

  - Analisi, gestione del flusso di lavoro, esperienze basate sui ruoli per gli agenti nell'app CCaaS in Teams

  - Esperienze di chat e collaborazione integrate con i client di Teams 

  - Mantenere le prestazioni e la qualità delle esperienze client di Teams in tutte le app  

### <a name="the-power-model"></a>[**Il modello Power**](#tab/power)

Il modello Power consente ai provider di soluzioni di creare applicazioni vocali native basate su Azure usando l'infrastruttura di chiamata di Teams e la piattaforma client per offrire soluzioni moderne e intelligenti per la collaborazione tra clienti e agenti. L'obiettivo del modello Power è offrire un'esperienza di contact center con un'unica app e uno schermo.

**Caratteristiche evidenziate:**

Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:

  - Esperienze formali degli agenti abilitate in modo nativo per la comunicazione omnicanale tramite Teams SDK 

  - Usare i servizi di collaborazione di Teams per la collaborazione con agenti e le interazioni con i clienti  

  - Provisioning rapido dei servizi cloud, distribuzione ovunque 

  - Controllo diretto delle conversazioni e interazione con gli utenti durante le conversazioni di Teams 

>[!NOTE]
> Il modello Power sarà disponibile verso la fine del 2021.
