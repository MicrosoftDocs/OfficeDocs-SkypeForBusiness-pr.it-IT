## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="a9082-101">Modelli di integrazione per i provider di soluzioni</span><span class="sxs-lookup"><span data-stu-id="a9082-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="a9082-102">I provider di soluzioni del contact center possono scegliere tra tre modelli per integrare la soluzione di contact center connessa in Teams:</span><span class="sxs-lookup"><span data-stu-id="a9082-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="a9082-103">Se si vogliono usare SBC certificati e Routing diretto per connettere una soluzione di contact center a Teams, vedere il [modello Connetti](?tabs=connect#steps).</span><span class="sxs-lookup"><span data-stu-id="a9082-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="a9082-104">Se si vogliono usare i bot di Azure e le API di comunicazione di Microsoft Graph per consentire ai provider di soluzioni di creare app di Teams, vedere [il modello Distendi.](?tabs=extend#steps)</span><span class="sxs-lookup"><span data-stu-id="a9082-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="a9082-105">Se si vuole usare un SDK che consenta ai provider di soluzioni di inserire esperienze native di Teams nella propria app, vedere il [modello Power.](?tabs=power#steps)</span><span class="sxs-lookup"><span data-stu-id="a9082-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="a9082-106">Le soluzioni di alimentazione saranno possibili quando l'SDK sarà disponibile verso la fine del 2021.</span><span class="sxs-lookup"><span data-stu-id="a9082-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="a9082-107">**Modello Connect**</span><span class="sxs-lookup"><span data-stu-id="a9082-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="a9082-108">Il modello Connect usa SBC certificati Microsoft e Routing diretto per connettere le soluzioni dei contact center all'infrastruttura del sistema telefonico di Teams, consentendo informazioni avanzate su routing, configurazione e sistema.</span><span class="sxs-lookup"><span data-stu-id="a9082-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="a9082-109">Gli agenti possono configurare assistenti virtuali automatizzati e code di routing basate sulle competenze per raccogliere informazioni e connettere i clienti con esperti in materia.</span><span class="sxs-lookup"><span data-stu-id="a9082-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="a9082-110">**Caratteristiche evidenziate:**</span><span class="sxs-lookup"><span data-stu-id="a9082-110">**Feature highlights:**</span></span>

<span data-ttu-id="a9082-111">Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:</span><span class="sxs-lookup"><span data-stu-id="a9082-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="a9082-112">AuthN di Office 365 per gli agenti che si connettono al tenant Microsoft dal client CCaaS integrato</span><span class="sxs-lookup"><span data-stu-id="a9082-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="a9082-113">Vedere quando gli agenti sono disponibili con Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="a9082-114">Trasferimenti e supporto per le chiamate di gruppo con Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="a9082-115">API di Teams Graph e Cloud Communication API per l'integrazione con Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="a9082-116">Trunking SIP multi-tenant per supportare diversi clienti nell'SBC del provider di soluzioni.</span><span class="sxs-lookup"><span data-stu-id="a9082-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="a9082-117">Provider di soluzioni per l'uso [ <span class="underline">di Microsoft Certified Session Border Controller (SBC)</span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="a9082-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="a9082-118">**Modello Distendi**</span><span class="sxs-lookup"><span data-stu-id="a9082-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="a9082-119">Il modello Extend si integra con il client Teams usando la piattaforma [client Teams,](/microsoftteams/platform/overview)le [API di Teams Graph](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) e [l'API Cloud Communications in Microsoft Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="a9082-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="a9082-120">Il modello Extend usa anche il sistema telefonico Teams per tutte le chiamate al contact center e le esperienze di controllo delle chiamate e il provider di soluzioni del contact center funge da gestore di telefonia insieme a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9082-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="a9082-121">Gli agenti possono usare Teams per la collaborazione interna e la comunicazione esterna e possono trarre vantaggio da note dinamiche e contestuali che mettono in correlazione i dati di più sistemi prima di avviare un impegno e quindi evitare costose opzioni di cambio di contesto.</span><span class="sxs-lookup"><span data-stu-id="a9082-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="a9082-122">Le organizzazioni possono progettare flussi di lavoro e configurazioni avanzate di routing fino all'individuo e misurare la qualità del sistema e delle interazioni.</span><span class="sxs-lookup"><span data-stu-id="a9082-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="a9082-123">**Caratteristiche evidenziate:**</span><span class="sxs-lookup"><span data-stu-id="a9082-123">**Feature highlights:**</span></span>

<span data-ttu-id="a9082-124">Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:</span><span class="sxs-lookup"><span data-stu-id="a9082-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="a9082-125">API di Teams Graph e Cloud Communication API per l'integrazione con Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="a9082-126">App basata su Teams per le esperienze degli agenti</span><span class="sxs-lookup"><span data-stu-id="a9082-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="a9082-127">Teams come endpoint chiamante principale per gli agenti</span><span class="sxs-lookup"><span data-stu-id="a9082-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="a9082-128">Chiamate client di Teams per tutti i controlli di chiamata</span><span class="sxs-lookup"><span data-stu-id="a9082-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="a9082-129">App esperienza agente sia per il web di Teams che per il client per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="a9082-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="a9082-130">Analisi, gestione del flusso di lavoro, esperienze basate sui ruoli per gli agenti nell'app CCaaS in Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="a9082-131">Esperienze di chat e collaborazione integrate con i client di Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="a9082-132">Mantenere le prestazioni e la qualità delle esperienze client di Teams in tutte le app</span><span class="sxs-lookup"><span data-stu-id="a9082-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="a9082-133">**Il modello Power**</span><span class="sxs-lookup"><span data-stu-id="a9082-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="a9082-134">Il modello Power consente ai provider di soluzioni di creare applicazioni vocali native basate su Azure usando l'infrastruttura di chiamata di Teams e la piattaforma client per offrire soluzioni moderne e intelligenti per la collaborazione tra clienti e agenti.</span><span class="sxs-lookup"><span data-stu-id="a9082-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="a9082-135">L'obiettivo del modello Power è offrire un'esperienza di contact center con un'unica app e uno schermo.</span><span class="sxs-lookup"><span data-stu-id="a9082-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="a9082-136">**Caratteristiche evidenziate:**</span><span class="sxs-lookup"><span data-stu-id="a9082-136">**Feature highlights:**</span></span>

<span data-ttu-id="a9082-137">Anche se queste caratteristiche non sono un elenco completo di funzionalità per questo modello di integrazione, le aree di interesse includono:</span><span class="sxs-lookup"><span data-stu-id="a9082-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="a9082-138">Esperienze formali degli agenti abilitate in modo nativo per la comunicazione omnicanale tramite Teams SDK</span><span class="sxs-lookup"><span data-stu-id="a9082-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="a9082-139">Usare i servizi di collaborazione di Teams per la collaborazione con agenti e le interazioni con i clienti</span><span class="sxs-lookup"><span data-stu-id="a9082-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="a9082-140">Provisioning rapido dei servizi cloud, distribuzione ovunque</span><span class="sxs-lookup"><span data-stu-id="a9082-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="a9082-141">Controllo diretto delle conversazioni e interazione con gli utenti durante le conversazioni di Teams</span><span class="sxs-lookup"><span data-stu-id="a9082-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="a9082-142">Il modello Power sarà disponibile verso la fine del 2021.</span><span class="sxs-lookup"><span data-stu-id="a9082-142">The Power model will be available towards the end of 2021.</span></span>
