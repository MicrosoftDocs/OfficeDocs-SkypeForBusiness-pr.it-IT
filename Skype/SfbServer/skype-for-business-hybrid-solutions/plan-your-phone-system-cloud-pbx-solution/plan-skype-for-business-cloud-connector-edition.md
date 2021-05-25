---
title: Pianificare la Skype for Business Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: Informazioni su Skype for Business Cloud Connector Edition, un set di macchine virtuali (VM) in pacchetto che implementano la connettività PSTN locale con Sistema telefonico (Cloud PBX).
ms.openlocfilehash: 4d4573b89f743ea8224905687869cb607a85c00d
ms.sourcegitcommit: 330e60ff3549cd5cff5b52ad95dc4259e4e8de13
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52628805"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Pianificare la Skype for Business Cloud Connector Edition

> [!Important]
> Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business Online. Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto](/MicrosoftTeams/direct-routing-landing-page).

Informazioni su Skype for Business Cloud Connector Edition, un set di macchine virtuali (VM) in pacchetto che implementano la connettività PSTN locale con Sistema telefonico (Cloud PBX).

Cloud Connector Edition potrebbe essere la soluzione giusta per l'organizzazione se non si dispone già di lync server o Skype for Business Server distribuzione. Se si sta ancora esaminando la soluzione Sistema telefonico più giusta per la propria azienda, vedere [Soluzioni di telefonia Microsoft](/microsoftteams/cloud-voice-landing-page).

In questo documento vengono descritti i requisiti di Cloud Connector Edition e le topologie supportate e viene illustrato come pianificare la distribuzione di Cloud Connector Edition. Leggere questo articolo prima di configurare l'ambiente Cloud Connector. Quando si è pronti per distribuire e configurare Cloud Connector Edition, vedere [Configure and manage Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2.1 è ora disponibile. Se non è stato ancora eseguito l'aggiornamento alla versione 2.1, vedere [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). È possibile trovare il file di installazione all'indirizzo [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> Microsoft supporta la versione precedente di Cloud Connector Edition per 60 giorni dopo il rilascio di una nuova versione. Microsoft supporterà la versione 2.0.1 per 60 giorni dopo il rilascio della 2.1 per consentire l'aggiornamento. Tutte le versioni precedenti alla 2.0.1 non sono più supportate.

Cloud Connector Edition è un'offerta ibrida costituita da un set di macchine virtuali in pacchetto che implementano la connettività PSTN locale con Sistema telefonico. Distribuendo una topologia di Skype for Business Server minima in un ambiente virtualizzato, gli utenti dell'organizzazione ospitati nel cloud possono ricevere i servizi PBX dal cloud Microsoft, ma la connettività PSTN viene fornita tramite l'infrastruttura vocale locale esistente.

![Diagramma della topologia che mostra il gateway Cloud PBX che connette Cloud PBX a una distribuzione locale di Skype for Business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Poiché Cloud Connector consente di integrare i servizi Sistema telefonico con l'ambiente di telefonia esistente, ad esempio PBX, dispositivi analogici e call center, è possibile implementare una migrazione in più fasi dalla soluzione di telefonia esistente a Sistema telefonico.

Si supponga, ad esempio, che la società abbia un call center sofisticato con funzionalità specifiche che Sistema telefonico non fornisce. È possibile scegliere di lasciare agli utenti del servizio clienti la soluzione esistente, ma spostare altri utenti in Sistema telefonico.

Cloud Connector fornirà il routing tra gli utenti ospitati in locale e online ed è possibile scegliere di usare il proprio provider PSTN con Sistema telefonico.

Durante la pianificazione della distribuzione di Cloud Connector Edition, tenere presente quanto segue:

- Per usare Cloud Connector per sfruttare le soluzioni vocali cloud, è necessario iscriversi a un'organizzazione Microsoft 365 o Office 365 che include Sistema telefonico. Se non si dispone ancora di un'organizzazione Microsoft 365 o Office 365, è possibile imparare a iscriversi qui: [Microsoft 365 for Business](https://products.office.com/business/office). Tieni presente che dovrai iscriverti a un piano che include Skype for Business Online.

- Per registrare le appliance di Cloud Connector con il servizio Skype for Business Online ed eseguire vari cmdlet, Cloud Connector 2.0 e versioni successive richiede un account Microsoft 365 o Office 365 dedicato con i diritti di amministratore tenant di Skype for Business. Le versioni di Cloud Connector precedenti alla 2.0 richiedono un account Microsoft 365 o Office 365 con diritti di amministratore globale tenant.

- Cloud Connector non richiede una distribuzione completa Skype for Business Server locale.

    Attualmente, Cloud Connector non può coesistere con Lync o Skype for Business server locali. Se si desidera spostare gli utenti lync o Skype for Business esistenti in Microsoft 365 e continuare a fornire telefonia locale agli utenti, prendere in considerazione Sistema telefonico con connettività locale utilizzando una distribuzione di Skype for Business Server esistente. Per ulteriori informazioni, vedere [Plan your Sistema telefonico (Cloud PBX) solution](/microsoftteams/cloud-voice-landing-page.md) e Plan Sistema telefonico with [on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Se si dispone di una distribuzione precedente di Skype for Business o Lync Server ed è stato esteso lo schema, non è necessario pulire lo schema per la distribuzione del connettore cloud, purché tutti i componenti di Skype for Business o Lync Server sono stati rimossi dall'ambiente.

- Gli utenti sono ospitati online.

- Se l'organizzazione ha configurato la sincronizzazione della directory (DirSync), tutti gli account degli utenti pianificati per la voce ibrida devono prima essere creati nella distribuzione locale e quindi sincronizzati nel cloud.

- Se necessario, è possibile mantenere l'operatore PSTN corrente.

- Se si desidera fornire servizi di conferenza telefonica con accesso esterno agli utenti ospitati in Cloud Connector, è possibile acquistare la licenza di conferenza PSTN o pagare mentre si passa all'offerta di audioconferenza da Microsoft.

- Per le escalation delle chiamate è necessaria anche la licenza di audioconferenza (o l'offerta con pagamento in base all'offerta). Se un utente Skype for Business riceve una chiamata da un utente PSTN esterno e desidera aggiungere un altro partecipante a tale chiamata (inoltrare la chiamata a una conferenza), l'escalation verrà eseguita tramite il servizio Audioconferenza Microsoft.

- Cloud Connector 2.0 e versioni successive ora supporta il bypass multimediale. Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente all'hop successivo PSTN (Public Switched Telephone Network), un gateway o session border controller (SBC), ed eliminare il componente Cloud Connector Edition dal percorso multimediale. Per ulteriori informazioni, vedere [Plan for media bypass in Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)

- Cloud Connector 2.1 e versioni successive supporta il monitoraggio di Cloud Connector tramite Operations Management Suite (OMS). Per ulteriori informazioni, vedere [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Cloud Connector è disponibile in tutti i paesi in cui Office 365 Enterprise E5 è disponibile.

Sezioni dell'articolo:

- [Componenti di Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologie Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisiti per la distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informazioni da raccogliere prima della distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considerazioni sul dial plan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considerazioni sulla disponibilità elevata](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flusso multimediale del connettore cloud](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Monitoraggio e risoluzione dei problemi](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Ulteriori informazioni](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componenti di Cloud Connector Edition
<a name="BKMK_Components"> </a>

Con Cloud Connector Edition, si distribuisce un set di macchine virtuali in pacchetto che contengono una topologia di Skype for Business Server minima, costituita da un componente Edge, un componente Mediation e un ruolo dell'archivio di gestione centrale ( CMS). Verrà inoltre installato un controller di dominio, necessario per il funzionamento interno del connettore cloud. Questi servizi sono configurati per la distribuzione ibrida con l'organizzazione Microsoft 365 o Office 365 che include Skype for Business Online Services.

![Componenti di Cloud Connector Edition](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

I componenti del connettore cloud offrono le funzionalità seguenti:

- **Componente perimetrale** - La comunicazione tra la topologia locale e i servizi online passa attraverso il componente Edge, che include i componenti seguenti:

  - **Access Edge** - Fornisce il routing SIP tra la distribuzione locale e Skype for Business Online.

  - **Media Relay** - Fornisce il routing dei supporti tra il componente Mediation Server e altri endpoint multimediali.

  - **Autenticazione media Relay /MRAS** - Genera token per l'accesso all'inoltro multimediale.

- **Routing in uscita** - Fornisce il bilanciamento del carico del traffico vocale tra gateway o SBC connessi a un dispositivo Cloud Connector. Le chiamate verranno suddivise in modo uniforme tra tutti i gateway o SBC connessi all'appliance Cloud Connector.

    Fornisce il routing ai gateway in base ai criteri. Sono supportati solo i criteri globali basati sui numeri PSTN di destinazione (in uscita).

- **Ruolo Archivio di gestione centrale** - Include l'archivio di configurazione per i componenti della topologia, incluso il trasferimento file cms.

- **Replica dell'archivio di gestione centrale** - Sincronizza le informazioni di configurazione dal database cms globale nel server dei ruoli cms.

- **Controller di** dominio - Servizi di dominio Active Directory cloud Connector per archiviare tutte le impostazioni globali e i gruppi necessari per distribuire i componenti del connettore cloud. Verrà creata una foresta per ogni appliance del connettore cloud. Il controller di dominio non deve avere connessioni con Active Directory di produzione. I servizi Active Directory includono:

  - Active Directory Domain Services

  - Servizi certificati Active Directory per emettere certificati interni

- **Componente mediation** : implementa il protocollo di mapping gateway SIP e multimediale tra Skype for Business gateway PSTN. Include una replica CMS che sincronizza la configurazione dal database cms globale.

## <a name="cloud-connector-edition-topologies"></a>Topologie Cloud Connector Edition
<a name="BKMK_Topologies"> </a>

Ai fini di questa discussione, verrà fatto riferimento ai siti PSTN. Un sito PSTN è una combinazione di appliance Cloud Connector, distribuite nella stessa posizione e con gateway PSTN comuni connessi. I siti PSTN consentono di:

- Fornire connettività ai gateway più vicini agli utenti.

- Consentire la scalabilità distribuendo più appliance Cloud Connector all'interno di uno o più siti PSTN.

- Consentire la disponibilità elevata distribuendo più appliance Cloud Connector all'interno di un singolo sito PSTN.

In questo argomento vengono presentati i siti PSTN. Per ulteriori informazioni sulla pianificazione dei siti PSTN, vedere [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

È possibile distribuire le topologie del connettore cloud seguenti:

- Un singolo appliance Cloud Connector Edition per ogni sito PSTN. Questa topologia è consigliata solo a scopo di valutazione perché non offre disponibilità elevata.

- Più appliance Cloud Connector Edition per sito PSTN per garantire disponibilità elevata.

- Più siti PSTN con più appliance Cloud Connector Edition per offrire scalabilità con disponibilità elevata. È possibile distribuire fino a 200 siti.

Quando si pianifica la topologia, considerare quanto segue:

- Con Cloud Connector 2.0 e versioni successive, un sito PSTN può avere fino a 16 appliance Cloud Connector. Le versioni precedenti supportano fino a quattro appliance per sito.

- Esistono due tipi di configurazioni hardware testate con Cloud Connector:

  - La versione più grande è in grado di gestire grandi volumi di chiamate simultanee ed è supportata in tutti i tipi di ambienti di produzione.

  - La versione più piccola è progettata per l'esecuzione su hardware di fascia bassa e può essere utilizzata a scopo di valutazione o per siti con volumi di chiamata bassi. Se si distribuisce una versione più piccola di Cloud Connector, è comunque necessario tenere conto dei requisiti hardware di classe di produzione (ad esempio, alimentatori doppi).

- Se si dispone di Cloud Connector versione 2.0 o successiva e si distribuisce la configurazione massima di 16 appliance (con hardware più grande), il sito PSTN può gestire fino a 8.000 chiamate simultanee. Se si distribuisce la versione più piccola, il limite supportato è 800.

    È inoltre necessario dedicare alcuni dispositivi per la disponibilità elevata. La raccomandazione minima è che un dispositivo deve essere riservato alla disponibilità elevata.

  - Con la versione 2, se si distribuisce una configurazione 15+1, il sito PSTN può gestire fino a 7.500 chiamate simultanee.

  - Se si dispone di una versione precedente e si distribuisce la configurazione massima di 3 + 1 (con hardware più grande), il sito PSTN può gestire fino a 1500 chiamate simultanee. Se si distribuisce la versione più piccola, il limite supportato è 150.

-  Se è necessario disporre di più chiamate per ogni sito PSTN, è possibile implementare la scalabilità verticale distribuendo altri siti PSTN nella stessa posizione.

> [!NOTE]
> Se non specificato, i diagrammi e gli esempi seguenti presuppongono l'uso della versione più grande di Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Appliance Single Cloud Connector all'interno di un singolo sito PSTN

Nel diagramma seguente viene illustrata una singola appliance Cloud Connector Edition all'interno di un singolo sito PSTN. Si noti che Cloud Connector è costituito da quattro macchine virtuali installate in un computer host fisico all'interno di una rete perimetrale per motivi di sicurezza.

![One Cloud Connector with One PSTN Site](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Più appliance Cloud Connector all'interno di un singolo sito PSTN

 Per scopi di scalabilità e disponibilità elevata, è possibile scegliere di disporre di più edizioni di Cloud Connector all'interno di un singolo sito PSTN, come illustrato nel diagramma seguente. Tenere in considerazione gli aspetti seguenti:

- Le chiamate vengono distribuite in ordine casuale tra i connettori cloud in un pool.

- Ai fini della pianificazione della capacità, è necessario considerare la possibilità di gestire il carico se uno o più connettori cloud passano offline, in base ai calcoli seguenti:

  - **N+1 caselle.** Per la versione più grande di Cloud Connector, le caselle N+1 supportano 500 N chiamate simultanee con disponibilità del \* 99,8%.

    Per la versione più piccola di Cloud Connector, le caselle N+1 supportano 50 N chiamate simultanee con una disponibilità del \* 99,8%.

  - **N+2 caselle.** Per la versione più grande di Cloud Connector, le caselle N+2 supportano 500 N chiamate simultanee con una disponibilità del \* 99,9%.

    Per la versione più piccola di Cloud Connector, le caselle N+2 supportano 50 N chiamate simultanee con una disponibilità del \* 99,9%.

![Due connettori cloud all'interno di 1 sito PSTN](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Più siti PSTN con uno o più connettori cloud per sito

È inoltre possibile scegliere di avere più siti PSTN con una o più edizioni di Cloud Connector in ogni sito. Se il sito PSTN raggiunge il limite di chiamate simultanee, è possibile aggiungere un altro sito PSTN per gestire il carico.

Più siti PSTN consentono inoltre di fornire connettività ai gateway più vicini agli utenti. Si supponga, ad esempio, di disporre di gateway PSTN a Seattle e Amsterdam. È possibile distribuire due siti PSTN, uno a Seattle, uno ad Amsterdam, e assegnare agli utenti di utilizzare il sito PSTN più vicino a loro. Gli utenti da Seattle verranno instradati al sito e ai gateway PSTN di Seattle, mentre gli utenti di Amsterdam verranno instradati al sito PSTN di Amsterdam e ai gateway:

![Cloud Connector Edition all'interno di 2 siti PSTN](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisiti per la distribuzione
<a name="BKMK_Requirements"> </a>

Prima di distribuire Cloud Connector Edition, assicurarsi di disporre degli elementi seguenti per l'ambiente:

- **Per il computer host -** Le macchine virtuali del connettore cloud devono essere distribuite su hardware dedicato che esegue Windows Server 2012 R2 Datacenter Edition (inglese) con il ruolo Hyper-V abilitato.

    Per la versione 2.0 e successive, la scheda di rete del computer host associata al commutatore Corpnet di Skype for Business deve disporre di un indirizzo IP configurato nella stessa subnet dei computer di rete aziendali del connettore cloud.

- Per le versioni 2.1 e successive, l'appliance host deve .NET Framework 4.6.1 o versione successiva.

- **Per le macchine virtuali -** Un Windows Server 2012 ISO R2 (in inglese) (.iso). L'ISO verrà convertito in dischi rigidi virtuali per le macchine virtuali che verranno eseguite Skype for Business Cloud Connector Edition.

- L'hardware necessario per supportare l'installazione delle 4 macchine virtuali per ogni edizione del connettore cloud nella distribuzione. Sono consigliate le configurazioni seguenti:

  - Processore doppio a 64 bit, sei core (12 core reali), 2,50 gigahertz (GHz) o superiore

  - 64 gigabyte (GB) DI RAM ECC

  - Quattro dischi SAS 6 Gbps da 600 GB (o superiori) da 10 K RPM da 128 M cache, configurati in una configurazione RAID 5

  - Tre schede di rete RJ45 ad alta velocità effettiva da 1 Gbps

- Se si sceglie di distribuire la versione più piccola di Cloud Connector Edition che supporta fino a 50 chiamate simultanee, sarà necessario l'hardware seguente:

  - Intel i7 4790 quad core con Intel 4600 Graphics (non sono necessarie grafica di fascia alta)

  - 32 GB DDR3-1600 non ECC

  - 2: 1 TB 7200RPM SATA III (6 Gbps) in RAID 0

  - 2: Ethernet da 1 Gbps (RJ45)

- Se nel computer host è necessario un server proxy per l'esplorazione di Internet, è necessario apportare le modifiche di configurazione seguenti:

  - Per ignorare il proxy, specificare le impostazioni proxy WinHTTP impostate con il server proxy e un elenco di bypass che include "192.168.213". \* rete utilizzata dai servizi Cloud Connector Managements e Skype for Business subnet Corpnet, come definito nel file CloudConnector.ini. In caso contrario, la connettività di gestione avrà esito negativo e impedirà la distribuzione e il ripristino automatico di Cloud Connector. Di seguito è riportato un comando di configurazione winhttp di esempio: netsh winhttp set proxy "10.10.10.175:8080" bypass-list=" \* .local;1. \* ; 172.20. \* ;192.168.218. \* ' \<local\> ".

  - Specificare le impostazioni proxy per computer anziché per utente. In caso contrario, i download del connettore cloud avranno esito negativo. È possibile specificare le impostazioni proxy per computer con una modifica al Registro di sistema o con l'impostazione di Criteri di gruppo come segue:

  - **Registro di sistema:** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword: 000000000

  - **Criteri di gruppo:** Modelli amministrativi computer Windows componenti di Internet Explorer: Effettuare impostazioni \> proxy per computer \> \> (anziché per utente)

- PBX/trunk qualificato o SBC/Gateway qualificato (è consigliato un minimo di due gateway).

    Cloud Connector supporta gli stessi session border controller (SBC) certificati per Skype for Business. Per ulteriori informazioni, vedere [Telephony Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md).

- Un account amministratore del server locale con le autorizzazioni per installare e configurare Hyper-V nei server host. L'account deve disporre delle autorizzazioni di amministratore nel server locale in cui è installato e configurato Hyper-V.

- Durante la distribuzione verrà richiesto di creare un account di amministratore di dominio con le autorizzazioni per creare e pubblicare la topologia nel dominio del connettore cloud.

- I record DNS esterni, definiti nel file CloudConnector.ini incluso nel pacchetto di installazione:

  - Record DNS esterno per il servizio Access Edge del componente Edge; ad esempio ap. \<Domain Name\> . È necessario un record per ogni sito PSTN. Questo record deve contenere gli indirizzi IP di tutti i bordi del sito.

- Organizzazione Microsoft 365 o Office 365 con tutti i record DNS e SRV necessari creati.

    > [!IMPORTANT]
    > Quando si integra il tenant con Cloud Connector Edition, l'utilizzo del suffisso di dominio predefinito, .onmicrosoft.com, come dominio SIP per l'organizzazione non è supportato. > Non è possibile utilizzare sip.\<Domain Name\> come nome dell'interfaccia proxy di Accesso edge del connettore cloud perché questo record DNS viene utilizzato da Microsoft 365 e Office 365.

- Certificato per l'edge esterno ottenuto da un'autorità di certificazione (CA) pubblica.

- Le regole del firewall per consentire il traffico attraverso le porte necessarie sono state completate.

- Una connessione Internet per il computer host e le macchine virtuali. Cloud Connector scarica parte del software da Internet; pertanto, è necessario fornire informazioni sul gateway e sul server DNS in modo che il computer host Cloud Connector e le macchine virtuali possano connettersi a Internet e scaricare il software necessario.

- Un modulo di PowerShell remoto tenant installato nel computer host.

- Le Skype for Business di amministratore per eseguire Remote PowerShell.

    > [!IMPORTANT]
    > L'account amministratore NON DEVE avere l'autenticazione a più fattori abilitata.

> [!NOTE]
> La distribuzione di Cloud Connector è supportata solo nella Microsoft Hyper-V virtualizzata. Altre piattaforme, ad esempio VMware e Amazon Web Services, non sono supportate.

> [!NOTE]
> Le indicazioni hardware minime per l'esecuzione di Cloud Connector si basano sulla capacità hardware di base (core, MHz, gigabyte e così via) con un buffer per contenere problemi di prestazioni immateriali nell'architettura di qualsiasi computer. Microsoft ha eseguito test di carico dei casi peggiori sull'hardware disponibile in commercio, in base alle indicazioni minime. La qualità multimediale e le prestazioni del sistema vengono verificate. I partner ufficiali dell'appliance Cloud Connector di Microsoft hanno implementazioni hardware specifiche del connettore cloud su cui hanno testato in modo indipendente le prestazioni e sono in grado di soddisfare i requisiti di carico e qualità del proprio hardware.

> [!NOTE]
> I dispositivi prodotti da AudioCodes e Sonus hanno modificato il codice ed eseguiti Windows Server Standard Edition dei server. Questi dispositivi sono supportati.

## <a name="information-you-need-to-gather-before-deployment"></a>Informazioni da raccogliere prima della distribuzione
<a name="BKMK_PlanDeployment"> </a>

Prima di iniziare la distribuzione, è necessario determinare le dimensioni della distribuzione, i domini SIP che vengono gestiti e le informazioni di configurazione per ogni sito PSTN che si prevede di distribuire. Per iniziare, è necessario:

- Identificare tutti i domini SIP che verranno serviti da questa distribuzione in base agli URI SIP in uso nella società.

- Determinare il numero di siti PSTN da distribuire.

- Verificare di disporre dell'hardware necessario per supportare le quattro macchine virtuali che verranno installate per ogni edizione del connettore cloud.

Per ogni sito PSTN che si intende distribuire, è necessario:

- Creare nomi per tutti i componenti in ogni appliance Cloud Connector (vedere [Determine deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definire intervalli di porte (vedere [Porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Creare record DNS esterni per il componente Edge (vedere [Requisiti per la distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determinare i requisiti del certificato per il componente Edge (vedere [Requisiti dei certificati](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Porte e protocolli
<a name="BKMB_Ports"> </a>

Quando si definiscono gli intervalli di porte multimediali, tenere presente quanto segue:

- I client usano sempre l'intervallo di porte da 50000 a 50019 per il traffico multimediale: questo intervallo è predefinito in Skype for Business Online e non può essere modificato.

- Per impostazione predefinita, il componente Mediation utilizzerà l'intervallo di porte da 49 152 a 57 500 per il traffico multimediale. Tuttavia, la connessione viene stabilita tramite firewall interno e, per motivi di sicurezza, è possibile limitare questo intervallo di porte nella topologia. Saranno necessarie fino a quattro porte per chiamata. Se si desidera limitare il numero di porte tra il componente Mediation Server e il gateway PSTN, sarà inoltre necessario configurare l'intervallo di porte corrispondente nel gateway.

- È necessario distribuire Cloud Connector in una rete perimetrale. Ciò significa che saranno disponibili due firewall:

  - Il primo firewall è esterno tra Internet e la rete perimetrale.

  - Il secondo firewall è interno tra la rete perimetrale e la rete interna.

    I client possono essere in Internet o nella rete interna:

  - I client in Internet si connetteranno alla rete PSTN tramite il firewall esterno tramite il componente Edge.

  - I client nella rete interna si connetteranno tramite il firewall interno al componente Mediation nella rete perimetrale, che connetterà il traffico al gateway SBC o PSTN.

    Ciò significa che è necessario aprire le porte in entrambi i firewall.

Nelle tabelle seguenti vengono descritte le porte e gli intervalli di porte per i firewall esterni e interni.

Questa tabella mostra le porte e gli intervalli di porte per abilitare la comunicazione tra i client nella rete interna e il componente Mediation:

**Firewall interno**



|**IP di origine**|**IP destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Componente Mediation Connector Cloud  <br/> |SBC/PSTN Gateway  <br/> |Qualsiasi  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN Gateway  <br/> |Componente Mediation Connector Cloud  <br/> |Qualsiasi  <br/> |TCP 5068/ TLS 5067  <br/> |
|Componente Mediation Connector Cloud  <br/> |SBC/PSTN Gateway  <br/> |UDP 49 152 - 57 500  <br/> |Any\*\*\*  <br/> |
|SBC/PSTN Gateway  <br/> |Componente Mediation Connector Cloud  <br/> |Any\*\*\*  <br/> |UDP 49 152 - 57 500  <br/> |
|Componente Mediation Connector Cloud  <br/> |Client interni  <br/> |TCP 49 152 - 57 500\*  <br/> |TCP 50.000-50.019  <br/> (Facoltativo)  <br/> |
|Componente Mediation Connector Cloud  <br/> |Client interni  <br/> |UDP 49 152 - 57 500\*  <br/> |UDP 50.000-50.019  <br/> |
|Client interni  <br/> |Componente Mediation Connector Cloud  <br/> |TCP 50.000-50.019  <br/> |TCP 49 152 - 57 500\*  <br/> |
|Client interni  <br/> |Componente Mediation Connector Cloud  <br/> |UDP 50.000-50.019  <br/> |UDP 49 152 -57 500\*  <br/> |

\* Questo è l'intervallo di porte predefinito nel componente Mediation Server. Per un flusso di chiamate ottimale, sono necessarie quattro porte per chiamata.

\*\* Questa porta deve essere configurata nel gateway SBC/PSTN. 5060 è un esempio. È possibile configurare altre porte sul gateway SBC/PSTN.

\*\*\* Tieni presente che puoi anche limitare l'intervallo di porte sul tuo SBC/Gateway, se consentito dal produttore di SBC/Gateway.

Per motivi di sicurezza, è possibile limitare l'intervallo di porte per il componente Mediation Utilizzando il cmdlet [Set-CsMediationServer.](/powershell/module/skype/set-csmediationserver?)

Ad esempio, il comando seguente limita il numero di porte che il componente Mediation utilizzerà per il traffico multimediale a 50 000 - 51 000 per l'audio (ingresso e uscita). Il componente Mediation sarà in grado di gestire 250 chiamate simultanee con questa configurazione. Tenere presente che è anche possibile limitare questo intervallo nel gateway SBC/PSTN:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Per recuperare il nome del componente Mediation Server e visualizzare le porte predefinite, è possibile utilizzare il cmdlet [Get-CsService](/powershell/module/skype/get-csservice?) nel modo seguente:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

La tabella seguente mostra le porte e gli intervalli di porte per abilitare la comunicazione tra il componente Edge del connettore cloud e il firewall esterno. Questa tabella mostra un suggerimento minimo.

In questo caso, tutto il traffico multimediale verso Internet verrà fluire tramite l'edge online come segue: Punto finale dell'utente-- \> Online Edge-- \> Cloud Connector Edge:

**Firewall esterno - Configurazione minima**



|**IP di origine**|**IP destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |Porta TCP 80  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |UDP 53  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 53  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore cloud  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore cloud  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |TCP 50.000-59.999  <br/> |TCP 443  <br/> |

La tabella seguente mostra le porte e gli intervalli di porte per abilitare la comunicazione tra il componente Edge del connettore cloud e il firewall esterno. Questa tabella mostra la soluzione consigliata.

In questo caso, tutto il traffico multimediale per il punto finale in Internet può fluire direttamente al componente Cloud Connector Edge. Il percorso multimediale sarà Punto finale utente - \> Cloud Connector Edge.

> [!NOTE]
> Questa soluzione non funzionerà se l'estremità finale dell'utente si trova dietro un NAT simmetrico.

**Firewall esterno - Configurazione consigliata**


|**IP di origine**|**IP destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP(MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |Porta TCP 80  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |UDP 53  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 53  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |TCP 50.000-59.999  <br/> |Qualsiasi  <br/> |
|Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |Qualsiasi  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |TCP 443; TCP 50.000-59.999  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore cloud  <br/> |Qualsiasi  <br/> |UDP 3478; UDP 50.000 - 59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisiti di connettività Internet host
<a name="BKMB_Ports"> </a>

Il computer host deve essere in grado di raggiungere risorse esterne per installare, aggiornare e gestire correttamente Cloud Connector. La tabella seguente mostra le destinazioni e le porte necessarie tra il computer host e le risorse esterne.

|Direction  <br/> |IP origine  <br/> |IP destinazione  <br/> |Porta di origine  <br/> |Porta di destinazione  <br/> |Protocollo  <br/> |Finalità  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|In uscita  <br/> |IP host del connettore cloud  <br/> |any  <br/> |any  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|In uscita  <br/> |IP host del connettore cloud  <br/> |any  <br/> |any  <br/> |80, 443  <br/> |TCP  <br/> |Elenco di revoche di certificati (CRL)  <br/> |
|In uscita  <br/> |IP host del connettore cloud  <br/> |any  <br/> |any  <br/> |80, 443  <br/> |TCP  <br/> |Aggiornamento del connettore cloud  <br/> Skype for Business Online  <br/> Amministratore PowerShell  <br/> Windows Update  <br/> |

Se sono necessarie regole più restrittive, fare riferimento agli URL allowlist seguenti:

- [URL dell'elenco di revoche](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) di certificati Office 365 [url e intervalli di indirizzi IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Aggiornamento: [Come configurare un firewall per gli aggiornamenti software](https://technet.microsoft.com/library/bb693717.aspx)

- Skype for Business PowerShell per l'amministratore online: \* .online.lync.com

    Se è necessaria un'esclusione proxy per questa destinazione, sarà necessario aggiungerla all'elenco di esclusione WinHTTP.

- Aggiornamento del connettore cloud: [Area download](https://aka.ms/CloudConnectorInstaller) [https://go.microsoft.com](https://go.microsoft.com) , e [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Risoluzione dei nomi DNS per il componente Edge
<a name="BKMB_Ports"> </a>

Il componente Edge deve risolvere i nomi esterni dei servizi Microsoft 365 o Office 365 e i nomi interni di altri componenti di Cloud Connector.

Ogni componente Edge è un computer multi-homed con interfacce esterne ed interne. Cloud Connector distribuisce i server DNS nel componente Controller di dominio all'interno della rete perimetrale. È possibile puntare il server perimetrale al server DNS all'interno del perimetro per tutte le risoluzioni dei nomi, ma è necessario abilitare il server DNS del connettore cloud per risolvere i nomi esterni impostando una zona DNS contenente uno o più record A DNS per le query esterne che fanno riferimento a ricerche di nomi ad altri server DNS pubblici.

Nel file .ini, se si imposta il nome FQDN per i gateway dallo stesso spazio di dominio del dominio SIP, la zona autorevole per questo dominio SIP verrà creata nel server DNS all'interno del perimetro. Se il server perimetrale punta a questo server DNS per risolvere i nomi, Edge non risolverà mai il _sipfederationtls.\<yourdomain\> Record DNS, necessario per il flusso delle chiamate. In questo caso, Microsoft consiglia di fornire un server DNS sull'interfaccia esterna perimetrale per risolvere le ricerche dei nomi Internet e ogni componente Edge deve utilizzare un file HOST per risolvere altri nomi di componenti del connettore cloud in indirizzi IP.

> [!NOTE]
> Per motivi di sicurezza, è consigliabile non puntare il server DNS del connettore cloud ai server interni nel dominio di produzione per la risoluzione dei nomi.

### <a name="determine-deployment-parameters"></a>Determinare i parametri di distribuzione
<a name="BKMK_SiteParams"> </a>

Prima di tutto è necessario definire i seguenti parametri di distribuzione comuni:


|**Elemento**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Domini SIP  <br/> |URI SIP in uso dagli utenti della società. Fornire tutti i domini SIP che verranno serviti da questa distribuzione. È possibile avere più di un dominio SIP.  <br/> ||
|Numero di siti PSTN  <br/> |Numero di siti PSTN che verranno distribuiti.  <br/> ||

Per ogni sito PSTN che si intende distribuire, è necessario raccogliere le informazioni seguenti prima di iniziare la distribuzione. Dovrai fornire queste informazioni quando aggiornerai il file CloudConnector.ini file.

Quando si configurano le informazioni sul gateway, tenere presente quanto segue:

- Se si dispone di un solo gateway, rimuovere la sezione nel file .ini per il secondo gateway. Se sono presenti più di due gateway, seguire il formato esistente per aggiungerne di nuovi.

- Verificare che l'indirizzo IP e la porta dei gateway siano corretti.

- Per supportare l'ha a livello di gateway PSTN, mantenere il gateway secondario o aggiungere altri gateway.

(Facoltativo) Per limitare i numeri di chiamata in uscita, aggiornare il valore LocalRoute.



|**Parametri sito**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Nome dominio macchina virtuale  <br/> |Nome di dominio per i componenti interni di Cloud Connector. Questo dominio deve essere diverso dal dominio di produzione. Il nome deve essere lo stesso in tutte le appliance Cloud Connector.  <br/> Nome nel file .ini: "VirtualMachineDomain"  <br/> |È preferibile il dominio .local.  <br/> |
|Nome controller di dominio del connettore cloud  <br/> |Nome del controller di dominio.  <br/> Nome nel file .ini: "ServerName"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> |
|IP/subnet mask del controller di dominio del connettore cloud  <br/> |Indirizzo IP del controller di dominio.  <br/> Nome nel file .ini: "IP"  <br/> ||
|fqdn del servizio Microsoft 365 o Office 365 online  <br/> |Deve essere l'impostazione predefinita nella maggior parte dei casi per l'istanza Microsoft 365 o Office 365 a livello mondiale.  <br/> Nome nel file .ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Skype for Business del sito; ad esempio Seattle.  <br/> Nome nel .ini file: "SiteName"  <br/> Per la versione 1.4.1 e successive, il nome del sito deve essere diverso per ogni sito e il nome deve corrispondere al sito PSTN, se esistente, definito in Microsoft 365 o Office 365. Si noti che i siti PSTN verranno creati automaticamente durante la registrazione del primo dispositivo in un sito.  <br/> ||
|HardwareType  <br/> Versione 1.4.1 e successive  <br/> |Tipo di hardware. Il valore predefinito è Normal. Puoi anche impostare Minimum.  <br/> ||
|Country Code  <br/> |Codice paese per la composizione.  <br/> Nome nel file .ini: "CountryCode"  <br/> ||
|Città  <br/> |Città (facoltativo).  <br/> Nome nel file .ini: "Città"  <br/> ||
|Stato  <br/> |Stato (facoltativo).  <br/> Nome nel file .ini: "State"  <br/> ||
|Indirizzo IP macchina virtuale di base  <br/> |L'indirizzo IP della macchina virtuale di base temporanea che verrà usata per creare il VHDX per tutte le macchine virtuali cloud Connector. Questo IP deve essere nella stessa subnet di rete aziendale perimetrale definita nel passaggio successivo e richiede l'accesso a Internet. Assicurarsi di definire il gateway predefinito aziendale e il DNS instradabile a Internet.  <br/> Nome nel file .ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Versione 1.4.1 e successive  <br/> |L'indirizzo del Windows Server Update Services (WSUS), un server Intranet per ospitare gli aggiornamenti da Microsoft Update.  <br/> È possibile lasciare vuoto se WSUS non è necessario.  <br/> ||
|Subnet mask per la rete interna  <br/> |Cloud Connector configura una rete IP per la comunicazione interna tra i componenti di Cloud Connector. Edge deve inoltre essere connesso a un'altra subnet che consente la connettività Internet.  <br/> Nome nel file .ini: "CorpnetIPPrefixLength" in "Parametri per un pool di rete VM"  <br/> ||
|Subnet mask per la rete esterna  <br/> |Per la rete esterna del componente Edge.  <br/> Nome nel file .ini: "InternetIPPrefix" in "Parametri per un pool di rete VM"  <br/> ||
|Nome del commutatore per la rete interna  <br/> |Nome del commutatore che verrà utilizzato per la rete interna del connettore cloud.  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file .ini: "CorpnetSwitchName" in "Parametri per un pool di rete VM  <br/> ||
|Nome del commutatore per la rete esterna  <br/> |Nome del commutatore che verrà utilizzato per la rete cloud connector esterna.  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file .ini: "InternetSwitchName" in "Parametri per un pool di rete VM  <br/> ||
|Gateway predefinito per la rete interna  <br/> |Questo gateway deve fornire l'accesso a Internet (Internet richiede anche l'impostazione del server DNS) e verrà configurato sulle interfacce interne dei componenti del connettore cloud.  <br/> Nome nel file .ini: "CorpnetDefaultGateway" in "Parametri per un pool di rete VM  <br/> ||
|Gateway predefinito per l'interfaccia esterna del componente Edge  <br/> |Verrà configurato nell'interfaccia esterna del componente Edge.  <br/> Nome nel file .ini: "InternetDefaultGateway" in "Parametri per un pool di rete VM  <br/> ||
|Server DNS per la rete interna  <br/> |Verrà configurato nell'interfaccia interna della macchina virtuale temporanea. Deve fornire la risoluzione dei nomi per i nomi Internet. Senza fornire un server DNS, la connessione Internet avrà esito negativo e la distribuzione non verrà completata.  <br/> Nome nel file .ini: "CorpnetDNSIPAddress" in "Parametri per un pool di rete VM  <br/> ||
|Server DNS per l'interfaccia esterna del componente Edge  <br/> |Verrà configurato nell'interfaccia esterna di Edge.  <br/> Nome nel file .ini: "InternetDNSIPAddress" in "Parametri per un pool di rete VM  <br/> ||
|Nome del commutatore di gestione  <br/> |L'opzione di gestione è un commutatore temporaneo che verrà creato automaticamente e che verrà utilizzato per la configurazione del connettore cloud durante la distribuzione. Verrà disconnesso automaticamente dopo la distribuzione. Deve essere una subnet diversa da qualsiasi altra rete utilizzata in Cloud Connector.  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file .ini: "ManagementSwitchName" in "Parametri per un pool di rete VM  <br/> ||
|Indirizzo subnet di gestione/subnet mask  <br/> |La subnet di gestione è una subnet temporanea che verrà creata automaticamente e che verrà utilizzata per la configurazione di Cloud Connector durante la distribuzione. Verrà rimosso automaticamente dopo la distribuzione. Deve essere una subnet diversa da qualsiasi altra rete utilizzata in Cloud Connector.  <br/> Nomi nel file .ini: "ManagementIPPrefix" e "ManagementIPPrefixLength" in "Parameters for a pool of VM network  <br/> ||
|Computer dell'archivio di gestione centrale  <br/> |Fqdn singolo utilizzato per l'archivio di gestione centrale (CMS). Il nome di dominio ACTIVE verrà utilizzato per generare il nome di dominio completo.  <br/> Nome nel file .ini: "ServerName" in "Parameters for Primary Central Management Service  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> (Nome pool CMS = Nome server)  <br/> |
|Indirizzo IP del computer CMS  <br/> |Indirizzo IP per il server CMS (interno nella rete perimetrale).  <br/> Nome nel file INI: "IP" in "Parametri per il servizio di gestione centrale principale  <br/> ||
|Nome condivisione file  <br/> |Nome condivisione file da creare nel server CMS per i Skype for Business di replica (ad esempio, CmsFileStore).  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file .ini: "CmsFileStore" in "Parametri per il servizio di gestione centrale principale"  <br/> ||
|Nome pool di componenti Mediation Server  <br/> |Nome pool del componente Mediation Server. Immettere solo il nome Netbios. Il nome di dominio ACTIVE verrà utilizzato per generare il nome di dominio completo.  <br/> Nome nel .ini file: "PoolName" in "Parametri per un pool di Mediation Server"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> |
|Nome componente Mediation Server  <br/> |Nome componente del componente Mediation 1. Immettere solo il nome Netbios. Il nome di dominio ACTIVE verrà utilizzato per generare il nome di dominio completo.  <br/> Nome nel .ini file: "ServerName" in "Parametri per un pool di Mediation Server"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> |
|Mediation component Machine IP address  <br/> |IP Corpnet interno per il componente Mediation Server (interno nella rete perimetrale).  <br/> Nome nel .ini file: "IP" in "Parametri per un pool di Mediation Server"  <br/> ||
|Nome interno pool di server perimetrali  <br/> |Nome pool del componente edge. Immettere solo il nome Netbios. Il nome di dominio ACTIVE verrà utilizzato per generare il nome di dominio completo.  <br/> Nome nel file .ini: "InternalPoolName" in "Parametri per un pool di server perimetrali"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> |
|Nome interno del server perimetrale  <br/> |Nome componente del componente Edge. Immettere solo il nome Netbios. Il nome di dominio ACTIVE verrà utilizzato per generare il nome di dominio completo.  <br/> Nome nel file .ini: "InternalServerName" in "Parametri per un pool di server perimetrali"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> |
|IP interno del server perimetrale  <br/> |IP della rete perimetrale interna del componente Edge per comunicare con altri componenti del connettore cloud.  <br/> Nome nel file .ini: "InternalServerIPs" in "Parametri per un pool di server perimetrali"  <br/> ||
|Nome esterno pool di accesso  <br/> |Nome di Access Edge; ad esempio AP. Questo nome deve corrispondere al nome fornito per il certificato SSL. Immettere solo il nome Netbios. Il nome di dominio SIP verrà utilizzato per generare il nome di dominio completo. Verrà utilizzato un nome di pool esterno per tutti i componenti perimetrali nel pool. È necessario un pool di Accesso edge per ogni sito PSTN.  <br/> Nome nel file .ini: "ExternalSIPPoolName" in "Parametri per un pool di server perimetrali"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> "sip" è riservato e pertanto non può essere utilizzato come nome.  <br/> Il nome FQDN generato deve corrispondere al nome fornito per il certificato SSL.  <br/> |
|IP esterno di Access Edge  <br/> |IP esterno del componente Edge - IP pubblico se non è disponibile alcun NAT o IP convertito (specificare entrambi gli indirizzi se mappati).  <br/> Nome nel file .ini: "ExternalSIPIPs" in "Parametri per un pool di server perimetrali"  <br/> ||
|Nome Media Relay  <br/> |Nome di Audio Video Media Relay Edge; ad esempio MR. Verrà utilizzato un nome di pool esterno per tutti i componenti perimetrali di un pool. Un pool Edge Media Relay è necessario per ogni sito PSTN.  <br/> Nome nel file .ini: "ExternalMRFQDNPoolName" in "Parametri per un pool di server perimetrali"  <br/> |Deve contenere al massimo 15 caratteri. Immettere solo il nome Netbios.  <br/> |
|IP esterno di Media Relay Edge  <br/> |Attualmente è supportato un solo IP, quindi questo sarà lo stesso IP di Access Edge, ip pubblico o mappato (specificare entrambi gli indirizzi se mappati). Può essere lo stesso indirizzo del componente Edge IP esterno di Access Edge. Nota se Edge è dietro NAT, devi anche specificare il valore per il parametro successivo.  <br/> Nome nel file .ini: "ExternalMRIPs" in "Parametri per un pool di server perimetrali"  <br/> ||
|IP esterno di Media Relay Edge (se Edge è dietro NAT)  <br/> |Se edge è dietro NAT, devi anche specificare l'indirizzo pubblico del dispositivo NAT.  <br/> Nome nel file .ini: "ExternalMRPublicIPs" in "Parametri per un pool di server perimetrali"  <br/> ||
|Modello e make-and-model di Voice Gateway 1  <br/> |Specificare la definizione e il modello del gateway SBC/Voice. Si noti che è possibile connettere un dispositivo o un trunk SIP dall'elenco dei dispositivi testati in [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) .  <br/> ||
|Modello e configurazione di Voice Gateway 2 (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Specificare la definizione e il modello del gateway vocale. Tieni presente che puoi connettere un dispositivo dall'elenco dei dispositivi testati all'indirizzo [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) .  <br/> ||
|Nome gateway vocale 1  <br/> |Utilizzato per generare il nome di dominio completo del computer con Dominio AD. Obbligatorio se verrà utilizzato TLS tra il componente Mediation Server e Il gateway vocale. Se non si prevede di utilizzare FQDN, ad esempio TLS non è necessario o Gateway vocale non supporta la connessione tramite FQDN (solo IP), specificare.  <br/> ||
|Nome gateway vocale 2 (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Utilizzato per generare il nome di dominio completo del computer con Dominio AD. Obbligatorio se verrà utilizzato TLS tra il componente Mediation Server e Il gateway vocale. Se non si prevede di utilizzare FQDN, ad esempio TLS non è necessario o Gateway vocale non supporta la connessione tramite FQDN (solo IP), specificare.  <br/> ||
|Indirizzo IP gateway vocale 1  <br/> |Indirizzo IP del gateway vocale.  <br/> ||
|Indirizzo IP di Voice Gateway 2 (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Indirizzo IP del gateway vocale.  <br/> ||
|Porta gateway vocale 1 # (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Porta su cui il trunk SIP del gateway vocale sarà in ascolto, ad esempio 5060.  <br/> ||
|Porta Gateway vocale 2 #  <br/> |Porta su cui il trunk SIP del gateway vocale sarà in ascolto, ad esempio 5060.  <br/> ||
|Protocollo Gateway vocale 1 per il traffico SIP  <br/> |TCP o TLS.  <br/> ||
|Protocollo Gateway vocale 2 per il traffico SIP (copiare questa riga se si dispone di più di 2 gateway)  <br/> |TCP o TLS.  <br/> ||
|Intervallo di porte multimediali esterne per il traffico da e verso il componente Edge  <br/> |Intervallo di porte TCP/UDP per il traffico multimediale da e verso l'interfaccia esterna del perimetro. Deve sempre iniziare da 50 000. Per ulteriori informazioni, vedere "Porte e protocolli".  <br/> |50000 - 59 999  <br/> |
|Intervallo di porte multimediali per comunicare con/dal componente Mediation tramite il firewall interno  <br/> |Intervallo di porte UDP che verrà utilizzato dal componente Mediation Server per comunicare con client e gateway (consigliato 4 porte per chiamata).  <br/> ||
|Intervallo di porte multimediali per comunicare con/da Skype for Business client tramite firewall interno  <br/> |A scopo di pianificazione, non è possibile modificare. Le porte devono essere aperte nel firewall interno per comunicare tra Skype for Business client all'interno della rete interna e con il componente Mediation.  <br/> |50 000- 50 019  <br/> |
|Password certificato pubblico  <br/> |Deve essere specificato nello script.  <br/> ||
|Password di amministratore in modalità provvisoria  <br/> Solo versione 1.4.2  <br/> |Password di amministratore in modalità provvisoria per il dominio CC interno.  <br/> ||
|Password di amministratore del dominio del connettore cloud  <br/> Solo versione 1.4.2  <br/> |Password per l'amministratore di dominio del connettore cloud (diverso dal dominio di produzione). Il nome utente è Administrator. Non è possibile modificare il nome utente.  <br/> ||
|Password amministratore macchine virtuali  <br/> Solo versione 1.4.2  <br/> |Usato per configurare la rete di gestione durante la distribuzione.  <br/> Il nome utente è Administrator. Non è possibile modificare il nome utente.  <br/> ||
|CABackupFile  <br/> Versione 2.0 e successive  <br/> |Utilizzato per salvare il servizio Autorità di certificazione dal server Active Directory in un file quando si distribuiscono più appliance in un sito Cloud Connector. Assicurati di usare la stessa password per tutte le appliance all'interno di un sito Cloud Connector per importare correttamente il file di backup della CA in un nuovo accessorio aggiunto.  <br/> ||
|CCEService  <br/> Versione 2.0 e successive  <br/> |Utilizzato per il servizio di gestione del connettore cloud; deve accedere alla directory del sito di Cloud Connector. Assicurati di usare la stessa password per tutte le appliance all'interno di un sito Cloud Connector.  <br/> ||
|Microsoft 365 o Office 365 Tenant Admin  <br/> | L'account viene utilizzato da Cloud Connector per aggiornare e gestire le impostazioni del tenant per Cloud Connector: <br/>  Versione 2.0 e successive: credenziali per un account Microsoft 365 o Office 365 con diritti Skype for Business amministratore. <br/>  Versioni precedenti alla 2.0: credenziali per un account Microsoft 365 o Office 365 con diritti di amministratore tenant globale. <br/> ||
|Abilitare il supporto REFER  <br/> |In questo modo verrà definito se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per l'IP/PBX. Il valore predefinito è True. Se il gateway IP/PBX supporta il supporto REFER, lasciare true. In caso contrario, questo valore deve essere modificato in False. Se non si è certi che il gateway supporti REFER, vedere [Qualified IP-PBXs and Gateways](../../../SfbPartnerCertification/certification/infra-gateways.md).   <br/> ||
|EnableFastFailoverTimer  <br/> Versione 2.0 e successive  <br/> |Con il valore predefinito "True", se il gateway non risponde alle chiamate in uscita entro 10 secondi, verrà instradato al successivo gateway disponibile. se non sono presenti trunk aggiuntivi, la chiamata verrà interrotta automaticamente.  <br/> Tuttavia, in un'organizzazione con reti lente e risposte gateway o quando il processo di definizione delle chiamate richiede più di 10 secondi, ciò potrebbe causare l'annullamento inutilmente delle chiamate.  <br/> Quando si effettuano chiamate verso alcuni paesi, ad esempio gli Emirati Arabi Uniti o l'Afghanistan, il processo di definizione delle chiamate può richiedere più di 10 secondi. Se si verificano problemi simili, sarà necessario impostare il valore su False. Non dimenticare di modificare l'impostazione corrispondente nel SBC o nel gateway connesso.  <br/> Il valore può essere True o False. Il valore predefinito è True.  <br/> ||
|ForwardCallHistory  <br/> Versione 2.0 e successive  <br/> | Questo parametro viene utilizzato per attivare le intestazioni SIP utilizzate per segnalare il chiamante iniziale negli scenari di squillo simultaneo, inoltro di chiamata e trasferimento di chiamata. Se si imposta il parametro su True, verranno attivate due intestazioni SIP: <br/>  History-Info <br/>  Referred-By <br/>  L'intestazione History-Info viene utilizzata per il retargeting delle richieste SIP e "fornisce un meccanismo standard per l'acquisizione delle informazioni della cronologia delle richieste per consentire un'ampia gamma di servizi per reti e utenti finali" ([RFC 4244 - Sezione 1.1).](http://www.ietf.org/rfc/rfc4244.txt) Per le interfacce trunk del connettore cloud, questo viene utilizzato negli scenari di inoltro di chiamata e anello simultaneo.  <br/>  Il valore può essere True o False. Il valore predefinito è False. <br/> ||
|INOLTRO PAI  <br/> Versione 2.0 e successive  <br/> |PAI è un'estensione privata di SIP che consente ai server SIP di asserire l'identità degli utenti autenticati. Per il provider trunk SIP, l'interfaccia PAI può essere utilizzata a scopo di fatturazione se History-Info e Referred-By non sono presenti. Quando forward P-Asserted-Identity è abilitato nella configurazione, il Mediation Server inoltra le intestazioni PAI con URI Tel SIP dal connettore &amp; cloud nel trunk SIP. Il Mediation Server inolterà le intestazioni PAI con i numeri E.164 dell'URI tel ricevuti solo nel &amp; trunk SIP al connettore cloud. Il Mediation Server inoltra inoltre tutte le intestazioni privacy ricevute in entrambe le direzioni. Se la richiesta SIP inviata dal Mediation Server include un'intestazione Privacy nel formato "Privacy: id" insieme all'intestazione PAI, l'identità asserita deve essere mantenuta privata all'esterno del dominio di trust di rete.  <br/> Il valore può essere True o False. Il valore predefinito è False.  <br/> ||

### <a name="certificate-requirements"></a>Requisiti per i certificati
<a name="BKMK_Certs"> </a>

Ogni componente Edge richiede un certificato da un'autorità di certificazione pubblica. I certificati devono disporre di una chiave privata esportabile da copiare tra i componenti di Edge. Per soddisfare i requisiti del certificato, è necessario scegliere tra le opzioni seguenti e specificare il nome soggetto (SN) e il nome alternativo soggetto (SAN) per il certificato.

 **Se si dispone di un singolo dominio SIP:**

- **Opzione 1.** Il nome soggetto deve contenere il nome del pool assegnato ai componenti perimetrali. Si noti che il nome soggetto non può essere sip.sipdomain.com perché questo nome è riservato per il componente Skype for Business Edge online. La san deve contenere sip.sipdomain.com e il nome del pool di server perimetrali di accesso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opzione 2.** Se si desidera utilizzare un singolo certificato con caratteri jolly in tutti i server del pool di server perimetrali distribuiti, è possibile utilizzare una voce SAN con caratteri jolly di .sipdomain.com anziché il nome del pool di server perimetrali nel \* certificato. Il nome del soggetto può essere il nome del pool di server perimetrali di accesso di uno dei pool di server perimetrali distribuiti:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Non è necessario creare una voce DNS esterna per sip. \<sipdomain\> . com perché questo nome appartiene alla distribuzione Microsoft 365 o Office 365 distribuzione.

> [!NOTE]
> Se si desidera utilizzare un singolo certificato per tutti i pool di server perimetrali distribuiti nell'organizzazione e non è possibile utilizzare un certificato con caratteri jolly come definito nell'opzione 2, sarà necessario includere il nome di dominio completo per tutti i pool di server perimetrali distribuiti nel nome SAN nel certificato.

 **Se si dispone di più domini SIP:**

Sarà necessario aggiungere un sip.sipdomain.com per ogni dominio SIP e il nome dei pool di access Edge per ogni dominio ( può essere un pool fisico ma con nomi diversi). Di seguito è riportato un esempio di voci SN e SAN in uno scenario con più domini SIP:

- **Opzione 1.** Il nome soggetto deve contenere il nome del pool assegnato per i componenti perimetrali. Si noti che il nome soggetto non può essere sip.sipdomain.com perché questo nome è riservato per il componente Skype for Business Edge online. La san deve contenere sip.sipdomain.com e il nome del pool di server perimetrali di accesso:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opzione 2.</strong> Se si desidera utilizzare un singolo certificato con caratteri jolly in tutti i server del pool di server perimetrali distribuiti, è possibile utilizzare una voce SAN con caratteri jolly di .sipdomain.com anziché il nome del pool di server perimetrali nel \* certificato. Il nome del soggetto può essere il nome del pool di server perimetrali di accesso di uno dei pool di server perimetrali distribuiti:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Non è necessario creare una voce DNS esterna per sip. \<sipdomain\> . com perché questo nome appartiene alla distribuzione Microsoft 365 o Office 365 distribuzione.

Ai fini della distribuzione, è possibile utilizzare la tabella seguente:

|**Opzione**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Quale opzione verrà utilizzata per la distribuzione?  <br/> |Opzione 1 o 2  <br/> ||
|SN  <br/> |Fornire il SN per il certificato  <br/> ||
|SAN  <br/> |Fornisce la san per il certificato  <br/> ||

Se si utilizza TLS tra il gateway e Mediation Server, sarà necessario ottenere il certificato radice o la catena di certificati completa per il certificato assegnato al gateway.

## <a name="dial-plan-considerations"></a>Considerazioni sul dial plan
<a name="BKMK_DailPlan"> </a>

Cloud Connector richiede l'uso di un dial plan online. Per ulteriori informazioni su come configurare un dial plan online, vedere [Che cos'è il dial plan?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considerazioni sulla disponibilità elevata
<a name="BKMK_HA"> </a>

Quando si distribuisce Cloud Connector Edition per la disponibilità elevata, si distribuiscono almeno due appliance che fungono da backup reciproco. Ogni appliance è costituita da quattro componenti: Edge, Mediation, Central Management Store (CMS) e controller di dominio.

In generale, se un componente all'interno di un'appliance si verifica un problema, Cloud Connector Edition può continuare a gestire le chiamate, ma è necessario considerare quanto segue:

- **Considerazioni sui componenti mediation, CMS e controller di dominio**

    Si supponga che il componente CMS o controller di dominio in un'appliance si insedi. L'appliance può comunque gestire le chiamate in ingresso e in uscita, ma se si riavvia un componente Mediation quando il controller di dominio o il componente CMS non è raggiungibile, l'aggregazione non funzionerà. Lo stesso vale per il riavvio del componente CMS quando il controller di dominio non è disponibile.

    **Suggerimento:** Prima di riavviare i componenti, verificare la disponibilità degli altri componenti nell'appliance.

- **Considerazioni sui componenti perimetrali**

    Se il componente Edge in un'appliance non è disponibile, il comportamento per le chiamate in ingresso e in uscita sarà diverso nel modo seguente:

  - **Chiamata in** uscita: chiamata dall'utente in Internet a una rete PSTN.

    Il meccanismo di distribuzione delle chiamate nel cloud identificherà che un componente Edge non è disponibile e instraderà tutte le chiamate a un'altra appliance, in modo che la chiamata in uscita sia riuscita.

  - **Chiamata in ingresso:** chiamata dalla rete PSTN a un utente che si trova in una rete locale o in Internet.

     Se il componente Edge dell'appliance che ha ricevuto la chiamata non funziona, le chiamate in ingresso a questa appliance non avranno esito positivo perché il componente Mediation non è in grado di reindirizzare la chiamata al componente Edge nell'altra appliance.

    **Suggerimento:** Disporre di un sistema di monitoraggio. Dopo aver identificato un malfunzionamento del componente Edge, arrestare tutti i componenti nell'appliance in cui il componente Edge non è disponibile.

## <a name="cloud-connector-media-flow"></a>Flusso multimediale del connettore cloud
<a name="BKMK_MediaFlow"> </a>

I diagrammi seguenti delineano il flusso di una chiamata in uscita e in ingresso tramite Cloud Connector Edition. Si tratta di informazioni utili per comprendere come viene stabilita la connettività.

Nel primo diagramma, un utente interno inserisce una chiamata in uscita nel modo seguente:

1. Dave, un utente che si è domiciliato online, ma ora nella rete interna, chiama un utente PSTN esterno.

2. Il traffico SIP viene instradato Skype for Business Online.

3. Skype for Business Online esegue una ricerca inversa del numero. La ricerca inversa dei numeri ha esito negativo perché questo numero non appartiene a nessuno nell'Skype for Business organizzazione.

4. La chiamata viene instradata al componente Edge (sip e flusso multimediale prima tramite Edge online; I contenuti multimediali verranno inviati al componente Mediation Server tramite il firewall interno).

5. Se la route esiste, il componente Edge inoltra il traffico al componente Mediation Nella rete perimetrale.

6. Il componente Mediation invia il traffico al gateway PSTN.

![Flusso multimediale in uscita per Cloud Connector](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Nel diagramma successivo, un utente interno riceve una chiamata in ingresso come segue:

1. Il gateway PSTN riceve una chiamata per l'utente Dave che si trova online, ma ora si trova nella rete interna.

2. Il traffico SIP viene instradato al componente Mediation Server.

3. Il componente Mediation invia il traffico SIP al componente Edge e quindi passa a Skype for Business Online.

4. Skype for Business Online esegue una ricerca inversa del numero e rileva che si tratta dell'utente Dave.

5. La segnalazione SIP passa a tutti i punti di presenza di Dave.

6. Il traffico multimediale verrà stabilito tra il gateway e il componente Mediation Server e tra il componente Mediation Server e il punto finale.

![Media Flow in ingresso per Cloud Connector](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Monitoraggio e risoluzione dei problemi
<a name="BKMK_Monitor"> </a>

Il meccanismo di monitoraggio e risoluzione dei problemi viene installato automaticamente con ogni appliance Cloud Connector. Il meccanismo rileva gli eventi seguenti:

- Una o più macchine virtuali di un'appliance Cloud Connector non sono connesse a un commutatore virtuale interno o Internet.

- Una o più macchine virtuali di un'appliance Cloud Connector sono in stato salvato o arrestato.

- Servizi non in esecuzione.

  Se viene rilevato uno dei seguenti eventi, l'intero dispositivo Cloud Connector viene svuotato e contrassegnato come offline per impedire il tentativo di stabilire chiamate a un dispositivo malfunzionante. Le funzionalità di ripristino automatico del connettore cloud ripristinano successivamente i servizi e contrassegnano l'appliance come online. Se il ripristino automatico non riesce per qualche motivo, vedi [Risolvere i problemi relativi alla distribuzione di Cloud Connector.](troubleshoot-your-cloud-connector-deployment.md)

  - Nella macchina virtuale Archivio di gestione centrale:

     - Skype for Business Master Replicator Agent

     - Skype for Business Replica Replicator Agent

  - Nella macchina virtuale Mediation Server:

     - Skype for Business Replica Replicator Agent

     - Skype for Business Server Mediation

  - Nella macchina virtuale del server perimetrale

     - Skype for Business Replica Replicator Agent

     -  Skype for Business Server Access Edge

     - Skype for Business Server Audio/Video Edge

     - Skype for Business Server Autenticazione audio/video

     - Skype for Business Server Web Conferencing Edge

- Regola in ingresso Windows firewall per "CS RTCSRV" su Edge, "CS RTCMEDSRV" nel Mediation Server è disabilitato.

Cloud Connector 2.1 e versioni successive supporta il monitoraggio di Cloud Connector tramite Operations Management Suite (OMS). Per ulteriori informazioni, vedere [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_MoreInfo"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Soluzioni di telefonia Microsoft](/microsoftteams/cloud-voice-landing-page)

- [Configurare e gestire Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Distribuire il bypass multimediale in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)
