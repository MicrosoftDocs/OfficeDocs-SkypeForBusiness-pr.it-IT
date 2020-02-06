---
title: Pianificare per Skype for Business Cloud Connector Edition
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
description: Trovare informazioni su Skype for Business Cloud Connector Edition, un set di macchine virtuali in pacchetto (VM) che implementano la connettività PSTN locale con il sistema telefonico in Office 365 (cloud PBX).
ms.openlocfilehash: 20ea88b230fe0fd9a590c489cb6f0017a2c27209
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814464"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Pianificare per Skype for Business Cloud Connector Edition

Trovare informazioni su Skype for Business Cloud Connector Edition, un set di macchine virtuali in pacchetto (VM) che implementano la connettività PSTN locale con il sistema telefonico in Office 365 (cloud PBX).

Cloud Connector Edition potrebbe essere la soluzione ideale per la tua organizzazione se non hai già una distribuzione di Lync Server o Skype for Business Server esistente. Se si sta ancora esaminando quale sistema telefonico nella soluzione Office 365 è adatto per la propria azienda, vedere soluzioni per la [telefonia Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions).

Questo documento descrive i requisiti di Cloud Connector Edition e le topologie supportate e consente di pianificare la distribuzione di Cloud Connector Edition. Assicurarsi di leggere questo argomento prima di configurare l'ambiente del connettore Cloud. Quando si è pronti per la distribuzione e la configurazione di Cloud Connector Edition, vedere [configurare e gestire Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2,1 è ora disponibile. Se non è stato ancora aggiornato a 2,1, vedere [eseguire l'aggiornamento a una nuova versione di Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). È possibile trovare il file di installazione [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)su.

> [!NOTE]
> Microsoft supporta la versione precedente di Cloud Connector Edition per 60 giorni dopo il rilascio di una nuova versione. Microsoft sosterrà la versione 2.0.1 per 60 giorni dopo il rilascio di 2,1 per consentire il tempo necessario per l'aggiornamento. Tutte le versioni precedenti a 2.0.1 non sono più supportate.

Cloud Connector Edition è un'offerta ibrida costituita da un set di macchine virtuali con pacchetto (VM) che implementano la connettività PSTN locale con il sistema telefonico in Office 365. Distribuendo una topologia minima di Skype for Business Server in un ambiente virtualizzato, gli utenti dell'organizzazione ospitati nel cloud possono ricevere servizi PBX da Microsoft Cloud, ma la connettività PSTN viene fornita tramite la voce locale esistente infrastruttura.

![Diagramma di topologia che mostra il gateway cloud PBX che connette cloud PBX a una distribuzione locale di Skype for business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Poiché Cloud Connector consente di integrare il sistema telefonico nei servizi di Office 365 con l'ambiente di telefonia esistente, ad esempio PBX, dispositivi analogici e Call Center, è possibile implementare una migrazione a fasi dalla soluzione di telefonia esistente al telefono Sistema in Office 365.

Supponiamo ad esempio che la tua azienda disponga di un Call Center sofisticato con funzionalità specifiche che il sistema telefonico in Office 365 non offre. È possibile scegliere di uscire dagli utenti del centro chiamate con la soluzione esistente, ma di trasferire altri utenti nel sistema telefonico in Office 365.

Cloud Connector offrirà il routing tra gli utenti ospitati in locale e online ed è possibile scegliere di usare il proprio provider PSTN con sistema telefonico in Office 365.

Quando si pianifica la distribuzione di Cloud Connector Edition, tenere presente quanto segue:

- Per usare Cloud Connector per sfruttare le soluzioni cloud Voice, è necessario iscriversi a un tenant di Office 365 che include il sistema telefonico in Office 365. Se non si ha ancora un tenant di Office 365, è possibile imparare a iscriversi qui: [Office 365 for business](https://products.office.com/en-us/business/office). Tieni presente che devi iscriverti a un piano che include Skype for business online.

- Per registrare gli elettrodomestici con il Cloud Connector con il servizio Skype for business online e per eseguire diversi cmdlet, Cloud Connector 2,0 e versioni successive richiede un account di Office 365 dedicato con i diritti di amministratore del tenant di Skype for business. Le versioni dei connettori cloud precedenti a 2,0 richiedono un account di Office 365 dedicato con i diritti di amministratore globale del tenant.

- Cloud Connector non richiede una distribuzione completa di Skype for Business Server in locale.

    Attualmente, Cloud Connector non può coesistere con i server locali di Lync o Skype for business. Se si vuole trasferire gli utenti di Lync o Skype for business esistenti in Office 365 e garantire la telefonia locale agli utenti, considerare il sistema telefonico in Office 365 con la connettività locale usando una distribuzione di Skype for Business Server esistente. Per altre informazioni, vedere [pianificare il sistema telefonico in office 365 (cloud PBX) soluzione](plan-your-phone-system-cloud-pbx-solution.md) e [pianificare il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Se si ha una distribuzione precedente di Skype for business o Lync Server e si è esteso lo schema, non è necessario pulire lo schema per la distribuzione di Cloud Connector, purché siano stati rimossi tutti i componenti di Skype for business o Lync Server dall'ambiente.

- Gli utenti sono ospitati online.

- Se l'organizzazione ha configurato la sincronizzazione della directory (DirSync), tutti gli account degli utenti pianificati per la voce ibrida devono essere creati prima nella distribuzione locale e quindi sincronizzati con il cloud.

- Se necessario, è possibile conservare il gestore PSTN corrente.

- Se si vuole fornire servizi di conferenza telefonica con accesso esterno agli utenti ospitati su cloud Connector, è possibile acquistare una licenza di conferenza PSTN o pagare mentre si passa all'offerta di audioconferenza da Microsoft.

- Per le escalation delle chiamate è necessaria anche la licenza per i servizi di audioconferenza (o pay-to-go). Se un utente di Skype for business riceve una chiamata da un utente PSTN esterno e vuole aggiungere un altro partecipante alla chiamata (inoltrare la chiamata a una conferenza), l'escalation verrà eseguita tramite il servizio di audioconferenza Microsoft.

- Il Cloud Connector 2,0 e versioni successive ora supporta il bypass multimediale. Il bypass multimediale consente a un client di inviare elementi multimediali direttamente alla rete PSTN (Public Switched Telephone Network) Next Hop, ovvero un gateway o un border controller (SBC), ed eliminare il componente cloud Connector Edition dal percorso multimediale. Per altre informazioni, vedere [pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2,1 e versioni successive supporta il monitoraggio del connettore cloud tramite le Operations Management Suite (OMS). Per altre informazioni, vedere [monitorare il connettore cloud tramite Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Cloud Connector è disponibile in tutti i paesi in cui è disponibile Office 365 Enterprise E5.

Questo argomento contiene le sezioni seguenti:

- [Componenti di Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologie a Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisiti per la distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informazioni che è necessario raccogliere prima della distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considerazioni sul dial plan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considerazioni sulla disponibilità elevata](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flusso multimediale Cloud Connector](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Monitoraggio e risoluzione dei problemi](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Per altre informazioni](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componenti di Cloud Connector Edition
<a name="BKMK_Components"> </a>

Con Cloud Connector Edition devi distribuire un set di VM con pacchetto che contengono una topologia di Skype for Business Server minima, costituita da un componente Edge, un componente di mediazione e un ruolo CMS (Central Management store). Si installerà anche un controller di dominio, necessario per il funzionamento interno del connettore Cloud. Questi servizi sono configurati per Hybrid con il tenant di Office 365 che include i servizi Skype for business online.

![Componenti di Cloud Connector Edition](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

I componenti del connettore Cloud includono le funzionalità seguenti:

- **Componente perimetrale** : la comunicazione tra la topologia locale e i servizi online passa attraverso il componente Edge, che include i componenti seguenti.

  - **Access Edge** : fornisce il routing SIP tra la distribuzione locale e Skype for business online.

  - **Media Relay** : fornisce il routing dei contenuti multimediali tra il componente di mediazione e gli altri endpoint multimediali.

  - **Media Relay Authentication/MRA** -genera i token per l'accesso all'inoltro multimediale.

- **Routing in uscita** : fornisce il bilanciamento del carico del traffico vocale tra gateway o SBCS connesso a un dispositivo di connessione cloud. Le chiamate verranno divise uniformemente tra tutti i gateway o SBCs connessi all'appliance del connettore Cloud.

    Fornisce il routing ai gateway in base ai criteri. Sono supportati solo i criteri globali basati sui numeri PSTN di destinazione (in uscita).

- **Ruolo di Central Management store (CMS)** -include l'archivio di configurazione per i componenti della topologia, incluso il trasferimento di file CMS.

- **Replica di Central Management store (CMS)** -sincronizza le informazioni di configurazione dal DB CMS globale nel server dei ruoli di CMS.

- **Domain controller** -Cloud Connector Active Directory Domain Services per archiviare tutte le impostazioni globali e i gruppi necessari per distribuire i componenti di Cloud Connector. Verrà creata una foresta per ogni accessorio Cloud Connector. Il controller di dominio non deve avere connessioni con la produzione Active Directory. I servizi Active Directory includono:

  - Active Directory Domain Services

  - Servizi certificati Active Directory per emettere certificati interni

- **Componente di mediazione** : implementa il protocollo di mapping dei gateway SIP e media tra Skype for business e i gateway PSTN. Include una replica CMS che sincronizza la configurazione dal database CMS globale.

## <a name="cloud-connector-edition-topologies"></a>Topologie a Cloud Connector Edition
<a name="BKMK_Topologies"> </a>

Ai fini della discussione, faremo riferimento a siti PSTN. Un sito PSTN è una combinazione di appliance di connettori cloud, distribuiti nella stessa posizione e con gateway PSTN comuni connessi. I siti PSTN consentono di:

- Fornisci connettività ai gateway più vicini agli utenti.

- Consentire la scalabilità distribuendo più appliance di connettori cloud in uno o più siti PSTN.

- Consentire l'elevata disponibilità distribuendo più dispositivi cloud Connector all'interno di un singolo sito PSTN.

Questo argomento introduce i siti PSTN. Per altre informazioni sulla pianificazione dei siti PSTN, vedere [pianificare i siti PSTN di Cloud Connector Edition](plan-for-cloud-connector-edition-pstn-sites.md).

È possibile distribuire le topologie di Cloud Connector seguenti:

- Un singolo Appliance Cloud Connector Edition per sito PSTN. Questa topologia è consigliata per scopi di valutazione solo perché non offre disponibilità elevata.

- Più appliance di Cloud Connector Edition per sito PSTN per ottenere una disponibilità elevata.

- Più siti PSTN con più appliance di Cloud Connector Edition per assicurare la scalabilità con elevata disponibilità. È possibile distribuire fino a siti di 200.

Quando si pianifica la topologia, tenere presente quanto segue:

- Con Cloud Connector 2,0 e versioni successive, un sito PSTN può avere fino a 16 appliance di connettori cloud. Le versioni precedenti supportano fino a 4 Appliance per sito.

- Esistono due tipi di configurazioni hardware testate con Cloud Connector:

  - La versione più grande è in grado di gestire grandi volumi di chiamate simultanee ed è supportata in tutti i tipi di ambiente di produzione.

  - La versione più piccola è progettata per l'esecuzione su hardware di fascia inferiore e può essere usata per scopi di valutazione o per siti con volumi di chiamate bassi. Se si distribuisce una versione più piccola di Cloud Connector, è comunque necessario essere consapevoli dei requisiti hardware della classe di produzione, ad esempio gli alimentatori duali.

- Se si ha Cloud Connector versione 2,0 o successiva e si distribuisce la configurazione massima di 16 Appliance (con hardware più grande), il sito PSTN può gestire fino a 8.000 chiamate simultanee. Se si distribuisce la versione più piccola, il limite supportato è 800.

    Devi anche dedicare alcuni elettrodomestici per una disponibilità elevata. La raccomandazione minima è che un dispositivo debba essere riservato per l'elevata disponibilità.

  - Con la versione 2, se si distribuisce una configurazione di 15 + 1, il sito PSTN può gestire fino a 7.500 chiamate simultanee.

  - Se si ha una versione precedente e si distribuisce la configurazione massima 3 + 1 (con hardware più grande), il sito PSTN può gestire fino a 1500 chiamate simultanee. Se si distribuisce la versione più piccola, il limite supportato è 150.

-  Se è necessario avere più chiamate per sito PSTN, è possibile eseguire una scalabilità verticale distribuendo altri siti PSTN nella stessa posizione.

> [!NOTE]
> A meno che non venga notato, i diagrammi e gli esempi seguenti presuppongono l'uso della versione più grande di Cloud Connector.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Accessorio per il connettore Cloud singolo all'interno di un singolo sito PSTN

Il diagramma seguente mostra un singolo accessorio Cloud Connector Edition all'interno di un singolo sito PSTN. Tieni presente che Cloud Connector è costituito da quattro VM installate in un computer host fisico che si trova all'interno di una rete perimetrale per motivi di sicurezza.

![Un connettore Cloud con un sito PSTN](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Più appliance di connettori cloud all'interno di un singolo sito PSTN

 Per scopi di scalabilità e disponibilità elevata, è possibile scegliere di avere più edizioni di Cloud Connector all'interno di un singolo sito PSTN, come illustrato nel diagramma seguente. Tenere presente quanto segue:

- Le chiamate vengono distribuite in ordine casuale tra connettori cloud in un pool.

- Per scopi di pianificazione della capacità, è necessario considerare la possibilità di gestire il carico se uno o più connettori cloud sono offline, in base ai calcoli seguenti:

  - **Caselle N + 1.** Per la versione più grande di Cloud Connector, le caselle N + 1\*supportano le chiamate simultanee di 500 n con la disponibilità di 99,8%.

    Per la versione più piccola di Cloud Connector, le caselle N + 1\*supportano le chiamate simultanee di 50 n con la disponibilità di 99,8%.

  - **Caselle N + 2.** Per la versione più grande di Cloud Connector, le caselle N + 2\*supportano le chiamate simultanee di 500 n con la disponibilità di 99,9%.

    Per la versione più piccola di Cloud Connector, le caselle N + 2\*supportano le chiamate simultanee di 50 n con la disponibilità di 99,9%.

![Due connettori cloud all'interno di 1 sito PSTN](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Più siti PSTN con uno o più connettori cloud per sito

È anche possibile scegliere di avere più siti PSTN con una o più edizioni di Cloud Connector in ogni sito. Se il sito PSTN raggiunge il limite delle chiamate simultanee, è possibile aggiungere un altro sito PSTN per gestire il caricamento.

Più siti PSTN consentono anche di garantire la connettività ai gateway più vicini agli utenti. Supponiamo ad esempio di avere gateway PSTN in Seattle e Amsterdam. È possibile distribuire due siti PSTN, uno a Seattle, uno ad Amsterdam, e assegnare agli utenti l'uso del sito PSTN più vicino. Gli utenti di Seattle verranno instradati al sito e ai gateway PSTN di Seattle, mentre gli utenti di Amsterdam verranno instradati al sito PSTN di Amsterdam e ai gateway:

![Cloud Connector Edition all'interno di 2 siti PSTN](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisiti per la distribuzione
<a name="BKMK_Requirements"> </a>

Prima di distribuire Cloud Connector Edition, verificare di avere gli elementi seguenti per l'ambiente:

- **Per il computer host-** Il Cloud Connector VM deve essere distribuito su hardware dedicato con Windows Server 2012 R2 Datacenter Edition (in inglese) con il ruolo Hyper-V abilitato.

    Per la versione 2,0 e successive, la scheda di rete del computer host associata all'opzione di Corpnet di Skype for business deve avere un indirizzo IP configurato nella stessa subnet delle macchine della rete aziendale di Cloud Connector.

- Per le versioni 2,1 e successive, l'accessorio host deve avere .NET Framework 4.6.1 o versione successiva installata.

- **Per le macchine virtuali-** Un'immagine ISO di Windows Server 2012 R2 (Inglese) (. ISO). L'ISO verrà convertito in VHD per le macchine virtuali che eseguiranno Skype for Business Cloud Connector Edition.

- L'hardware necessario per supportare l'installazione delle 4 VM per ogni versione di Cloud Connector nella distribuzione. Sono consigliate le configurazioni seguenti:

  - processore duale a 64 bit, sei core (12 core reali), 2,50 gigahertz (GHz) o superiore

  - RAM ECC di 64 gigabyte (GB)

  - 4 600 GB (o superiore) 10K RPM 128M cache SAS 6Gbps dischi, configurati in una configurazione RAID 5

  - Tre schede di rete a throughput elevato da 1 Gbps RJ45

- Se si sceglie di distribuire la versione più piccola di Cloud Connector Edition che supporta fino a 50 chiamate simultanee, sarà necessario l'hardware seguente:

  - Intel i7 4790 quad-core con grafica Intel 4600 (non sono necessari elementi grafici di fascia alta)

  - 32 GB DDR3-1600 non ECC

  - 2:1TB 7200RPM SATA III (6 Gbps) in RAID 0

  - 2:1 Gbps Ethernet (RJ45)

- Se nel computer host è necessario un server proxy per l'esplorazione di Internet, è necessario apportare le modifiche seguenti alla configurazione:

  - Per ignorare il proxy, specificare le impostazioni proxy WinHTTP impostate con il server proxy e un elenco di bypass incluso il 192.168.213. \*"rete usata dai servizi di gestione dei Cloud Connector e dalla subnet di Skype for business corpnet definita nel file CloudConnector. ini. In caso contrario, la connettività di gestione non riuscirà e impedirà la distribuzione e il ripristino automatico di Cloud Connector. Di seguito è riportato un esempio di comando di configurazione WinHTTP: netsh winhttp set proxy "10.10.10.175:8080" bypass-\*list = ". local; 1. \*; 172,20. \*; 192.168.218. \*"\<Local\>".

  - Specificare le impostazioni proxy per ogni computer anziché per ogni utente. In caso contrario, il download di Cloud Connector non riesce. È possibile specificare le impostazioni proxy per ogni computer con una modifica del registro di sistema o con l'impostazione di criteri di gruppo come indicato di seguito:

  - **Registro di sistema:** HKEY_LOCAL_MACHINE impostazioni \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD: 00000000

  - **Criteri di gruppo:** Modelli\>\>amministrativi per computer Windows\> Components Internet Explorer: impostare le impostazioni proxy per ogni computer (anziché per ogni utente)

- Qualificato PBX/trunk o SBC/gateway qualificati (è consigliabile un minimo di due gateway).

    Cloud Connector supporta gli stessi controller di bordo della sessione (SBCs) certificati per Skype for business. Per altre informazioni, Vedi l' [infrastruttura per la telefonia per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Un account di amministratore del server locale con le autorizzazioni per installare e configurare Hyper-V nei server host. L'account deve avere le autorizzazioni di amministratore nel server locale in cui è installato e configurato Hyper-V.

- Durante la distribuzione verrà richiesto di creare un account di amministratore di dominio con le autorizzazioni per creare e pubblicare la topologia nel dominio del connettore Cloud.

- I record DNS esterni, definiti nel file CloudConnector. ini incluso nel pacchetto di installazione:

  - Record DNS esterno per il servizio Edge di Access del componente Edge; ad esempio, AP.\<Domain Name\>. È necessario un record per ogni sito PSTN. Questo record deve contenere indirizzi IP di tutti i bordi per il sito.

- Un tenant di Office 365 con tutti i record DNS e SRV necessari creati.

    > [!IMPORTANT]
    > Quando si integra il tenant con Cloud Connector Edition, l'uso del suffisso di dominio predefinito, onmicrosoft.com, come dominio SIP per l'organizzazione, non è supportato. > non è possibile usare SIP. \<Nome\> di dominio come nome dell'interfaccia proxy di Access Edge di Cloud Connector perché questo record DNS viene usato da Office 365.

- Certificato per il bordo esterno ottenuto da un'autorità di certificazione pubblica (CA).

- Le regole del firewall per consentire il traffico tra le porte necessarie sono state completate.

- Una connessione Internet per il computer host e per le VM. Cloud Connector Scarica alcuni software da Internet; di conseguenza, devi specificare le informazioni sul server gateway e DNS in modo che il computer host Cloud Connector e le VM possano connettersi a Internet e scaricare il software necessario.

- Un modulo di PowerShell remoto tenant installato nel computer host.

- Le credenziali di amministratore di Office 365 Skype for business per eseguire Remote PowerShell.

    > [!IMPORTANT]
    > L'account di amministratore non deve avere l'autenticazione a più fattori abilitata.

> [!NOTE]
> La distribuzione di Cloud Connector è supportata solo nella piattaforma virtualizzata Microsoft Hyper-V. Altre piattaforme, ad esempio VMware e Amazon Web Services, non sono supportate.

> [!NOTE]
> Le indicazioni minime hardware per l'esecuzione di Cloud Connector si basano sulla capacità hardware di base (core, MHz, Gigabyte e così via) con un certo buffer che consente di includere problemi di prestazioni immateriali sepolti nell'architettura di qualsiasi computer. Microsoft ha eseguito test di carico più sfavorevoli sull'hardware disponibile in commercio che soddisfa le indicazioni minime. La qualità del supporto e le prestazioni del sistema vengono verificate. I partner ufficiali di appliance Cloud Connector di Microsoft dispongono di implementazioni hardware specifiche per il connettore Cloud in cui hanno prestazioni testate in modo indipendente e si distinguono dall'idoneità del proprio hardware per soddisfare i requisiti di carico e qualità.

> [!NOTE]
> I dispositivi prodotti da AudioCodes e Sonus hanno modificato il codice ed eseguito in Windows Server Standard Edition of servers. Questi dispositivi sono supportati.

## <a name="information-you-need-to-gather-before-deployment"></a>Informazioni che è necessario raccogliere prima della distribuzione
<a name="BKMK_PlanDeployment"> </a>

Prima di iniziare la distribuzione, è necessario determinare le dimensioni della distribuzione, i domini SIP in fase di manutenzione e le informazioni di configurazione per ogni sito PSTN che si prevede di distribuire. Per iniziare, dovrai:

- Identifica tutti i domini SIP che verranno serviti da questa distribuzione in base agli URI SIP in uso nella tua azienda.

- Determinare il numero di siti PSTN che è necessario distribuire.

- Verificare di avere l'hardware necessario per supportare le quattro VM da installare per ogni versione di Cloud Connector.

Per ogni sito PSTN che si prevede di distribuire, è necessario:

- Creare nomi per tutti i componenti di ogni accessorio Cloud Connector (vedere [determinare i parametri di distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definire gli intervalli di porte (vedere [porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Creare record DNS esterni per il componente Edge (vedere [requisiti per la distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determinare i requisiti di certificato per il componente Edge (vedere [requisiti dei certificati](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Porte e protocolli
<a name="BKMB_Ports"> </a>

Quando si definiscono gli intervalli della porta multimediale, tenere presente quanto segue:

- I client usano sempre l'intervallo di porte da 50000 a 50019 per il traffico multimediale: questo intervallo è predefinito in Skype for business online e non può essere modificato.

- Per impostazione predefinita, il componente di mediazione utilizzerà l'intervallo di porte da 49 152 a 57 500 per il traffico multimediale. Tuttavia, la connessione viene stabilita tramite firewall interno e, per motivi di sicurezza, è possibile limitare l'intervallo di porte nella topologia. Sarà necessario un massimo di 4 porte per chiamata. Se si vuole limitare il numero di porte tra il componente di mediazione e il gateway PSTN, sarà necessario configurare anche l'intervallo di porte corrispondente nel gateway.

- È necessario distribuire il connettore Cloud in una rete perimetrale. In questo modo si avranno due firewall:

  - Il primo firewall è esterno tra Internet e la rete perimetrale.

  - Il secondo firewall è interno tra la rete perimetrale e la rete interna.

    I client possono essere in Internet o nella rete interna:

  - I client in Internet si connetteranno alla rete PSTN tramite il firewall esterno attraverso il componente Edge.

  - I client della rete interna si connetteranno tramite il firewall interno al componente di mediazione nella rete perimetrale, che consentirà di connettere il traffico al gateway SBC o PSTN.

    Questo significa che devi aprire le porte in entrambi i firewall.

Le tabelle seguenti descrivono le porte e gli intervalli di porta per i firewall esterni e interni.

Questa tabella mostra le porte e gli intervalli di porta per consentire la comunicazione tra i client nella rete interna e il componente di mediazione:

**Firewall interno**



|**IP di origine**|**IP di destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Componente di mediazione Cloud Connector  <br/> |SBC/gateway PSTN  <br/> |Qualsiasi  <br/> |TCP 5060\*\*  <br/> |
|SBC/gateway PSTN  <br/> |Componente di mediazione Cloud Connector  <br/> |Qualsiasi  <br/> |TCP 5068/TLS 5067  <br/> |
|Componente di mediazione Cloud Connector  <br/> |SBC/gateway PSTN  <br/> |UDP 49 152-57 500  <br/> |Qualsiasi\*\*\*  <br/> |
|SBC/gateway PSTN  <br/> |Componente di mediazione Cloud Connector  <br/> |Qualsiasi\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Componente di mediazione Cloud Connector  <br/> |Client interni  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50019  <br/> Opzionale  <br/> |
|Componente di mediazione Cloud Connector  <br/> |Client interni  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50019  <br/> |
|Client interni  <br/> |Componente di mediazione Cloud Connector  <br/> |TCP 50000-50019  <br/> |TCP 49 152-57 500\*  <br/> |
|Client interni  <br/> |Componente di mediazione Cloud Connector  <br/> |UDP 50000-50019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Questo è l'intervallo di porte predefinito nel componente di mediazione. Per un flusso di chiamata ottimale, sono necessarie quattro porte per chiamata.

\*\*Questa porta deve essere configurata nel gateway SBC/PSTN; 5060 è un esempio. È possibile configurare altre porte nel gateway SBC/PSTN.

\*\*\*Tieni presente che puoi anche limitare l'intervallo di porte sul tuo SBC/gateway, se consentito dal produttore di SBC/gateway.

Per motivi di sicurezza, puoi limitare l'intervallo di porte per il componente di mediazione usando il cmdlet [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Ad esempio, il comando seguente limita il numero di porte che il componente di mediazione userà per il traffico multimediale in 50 000-51 000 per l'audio (in e out). Il componente di mediazione sarà in grado di gestire le chiamate simultanee di 250 con questa configurazione. Tieni presente che potresti anche voler limitare questo intervallo nel gateway SBC/PSTN:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Per recuperare il nome del componente di mediazione e vedere le porte predefinite, è possibile usare il cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) come indicato di seguito:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

La tabella seguente mostra le porte e gli intervalli di porte per consentire la comunicazione tra il componente bordo connettore cloud al firewall esterno. Questa tabella mostra una raccomandazione minima.

In questo caso, tutto il traffico multimediale a Internet scorrerà tramite il bordo online come segue: punto finale dell'utente-\>-Edge online-\>-bordo del connettore Cloud:

**Firewall esterno-configurazione minima**



|**IP di origine**|**IP di destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Qualsiasi  <br/> |Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 80  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |UDP 53  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 53  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna bordo connettore Cloud  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna bordo connettore Cloud  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |

La tabella seguente mostra le porte e gli intervalli di porte per consentire la comunicazione tra il componente bordo connettore cloud al firewall esterno. Questa tabella mostra la soluzione consigliata.

In questo caso, tutto il traffico multimediale per il punto finale in Internet può fluire direttamente sul componente bordo connettore Cloud. Il percorso dell'elemento multimediale sarà Edge del connettore\> cloud di fine utente.

> [!NOTE]
> Questa soluzione non funziona se il punto finale dell'utente si trova dietro un NAT simmetrico.

**Firewall esterno-configurazione consigliata**


|**IP di origine**|**IP di destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Qualsiasi  <br/> |Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 80  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |UDP 53  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 53  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 50000-59.999  <br/> |Qualsiasi  <br/> |
|Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |UDP 3478; UDP 50000-59.999  <br/> |Qualsiasi  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 443; TCP 50000-59.999  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna bordo connettore Cloud  <br/> |Qualsiasi  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisiti di connettività Internet host
<a name="BKMB_Ports"> </a>

Il computer host deve essere in grado di raggiungere risorse esterne per installare, aggiornare e gestire Cloud Connector correttamente. La tabella seguente mostra le destinazioni e le porte necessarie tra il computer host e le risorse esterne.

|Direzione  <br/> |IP di origine  <br/> |IP di destinazione  <br/> |Porta di origine  <br/> |Porta di destinazione  <br/> |Protocollo  <br/> |Scopo  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Outbound  <br/> |IPs host connettore Cloud  <br/> |qualsiasi  <br/> |qualsiasi  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|Outbound  <br/> |IPs host connettore Cloud  <br/> |qualsiasi  <br/> |qualsiasi  <br/> |80, 443  <br/> |TCP  <br/> |Elenco di revoche di certificati (CRL)  <br/> |
|Outbound  <br/> |IPs ospitante Cloud Connector  <br/> |qualsiasi  <br/> |qualsiasi  <br/> |80, 443  <br/> |TCP  <br/> |Aggiornamento del connettore Cloud  <br/> Skype for business online  <br/> Amministratore di PowerShell  <br/> Windows Update  <br/> |

Se sono necessarie regole più restrittive, vedere gli URL di whitelist seguenti:

- [URL dell'elenco di revoche di certificati](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) in [url di Office 365 e intervalli di indirizzi IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [come configurare un firewall per gli aggiornamenti software](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- PowerShell per gli amministratori di Skype for \*business online:. online.Lync.com

    Se è necessaria un'esclusione proxy per questa destinazione, sarà necessario aggiungerla all'elenco di esclusione di WinHTTP.

- Aggiornamento del connettore Cloud: [https://go.microsoft.com](https://go.microsoft.com) [Centro download](https://aka.ms/CloudConnectorInstaller)e[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Risoluzione dei nomi DNS per il componente Edge
<a name="BKMB_Ports"> </a>

Il componente Edge deve risolvere i nomi esterni dei servizi di Office 365 e i nomi interni di altri componenti del connettore Cloud.

Ogni componente Edge è un computer multihomed con interfacce esterne e interne. Cloud Connector distribuisce i server DNS nel componente controller di dominio all'interno della rete perimetrale. È possibile puntare il server Edge al server DNS all'interno del perimetro per tutte le risoluzioni dei nomi, ma è necessario abilitare il server DNS per il Cloud Connector per risolvere i nomi esterni impostando una zona DNS contenente uno o più record DNS per le query esterne che fanno riferimento al nome. ricerche ad altri server DNS pubblici.

Nel file ini, se si imposta il nome FQDN per i gateway dallo stesso spazio di dominio del dominio SIP, l'area autorevole per il dominio SIP verrà creata nel server DNS all'interno del perimetro. Se Edge Server fa riferimento a questo server DNS per la risoluzione dei nomi, Edge non risolverà mai la _sipfederationtls. \<record\> DNS di dominio, necessario per il flusso delle chiamate. In questo caso, Microsoft consiglia di specificare un server DNS nell'interfaccia esterna Edge per risolvere le ricerche di nomi Internet e ogni componente Edge deve usare un file HOST per risolvere altri nomi di componenti del connettore Cloud in indirizzi IP.

> [!NOTE]
> Per motivi di sicurezza, è consigliabile non puntare il server DNS per il Cloud Connector ai server interni nel dominio di produzione per la risoluzione dei nomi.

### <a name="determine-deployment-parameters"></a>Determinare i parametri di distribuzione
<a name="BKMK_SiteParams"> </a>

Prima di tutto è necessario definire i parametri di distribuzione comuni seguenti:


|**Elemento**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Domini SIP  <br/> |URI SIP in uso dagli utenti della società. Fornisci tutti i domini SIP che verranno serviti da questa distribuzione. Puoi avere più di un dominio SIP.  <br/> ||
|Numero di siti PSTN  <br/> |Numero di siti PSTN che verrà distribuito.  <br/> ||

Per ogni sito PSTN che si intende distribuire, sarà necessario raccogliere le informazioni seguenti prima di iniziare la distribuzione. Quando si aggiorna il file CloudConnector. ini, sarà necessario specificare queste informazioni.

Quando si configurano le informazioni sul gateway, tenere presente quanto segue:

- Se si ha un solo gateway, rimuovere la sezione nel file ini per il secondo gateway. Se sono presenti più di due gateway, seguire il formato esistente per aggiungerne di nuovi.

- Verificare che l'indirizzo IP e la porta dei gateway siano corretti.

- Per supportare l'HA a livello di gateway PSTN, Mantieni il gateway secondario o Aggiungi altri gateway.

Opzionale Per limitare i numeri delle chiamate in uscita, aggiornare il valore LocalRoute.



|**Parametri del sito**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Nome di dominio macchina virtuale  <br/> |Nome di dominio per i componenti interni di Cloud Connector. Questo dominio deve essere diverso dal dominio di produzione. Il nome deve essere lo stesso in tutti gli elettrodomestici per il Cloud Connector.  <br/> Nome in file ini: "VirtualMachineDomain"  <br/> |è preferibile il dominio locale.  <br/> |
|Nome del controller di dominio cloud Connector  <br/> |Nome del controller di dominio.  <br/> Nome nel file ini: "ServerName"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> |
|IP/subnet mask del controller di dominio cloud Connector  <br/> |Indirizzo IP del controller di dominio.  <br/> Nome nel file ini: "IP"  <br/> ||
|FQDN del servizio online Office 365  <br/> |Deve essere l'impostazione predefinita nella maggior parte dei casi per l'istanza di Office 365 a livello mondiale.  <br/> Nome in file ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Nome del sito di Skype for business; ad esempio, Seattle.  <br/> Nome in file ini: "nomesito"  <br/> Per il rilascio 1.4.1 e versioni successive, il nome del sito deve essere diverso per ogni sito e il nome deve corrispondere al sito PSTN, se esistente, definito in Office 365. Tieni presente che i siti PSTN verranno creati automaticamente durante la registrazione del primo appliance in un sito.  <br/> ||
|HardwareType  <br/> Rilascio 1.4.1 e versioni successive  <br/> |Tipo di hardware. Il valore predefinito è Normal. È anche possibile impostare su Minimum.  <br/> ||
|Codice paese  <br/> |Codice paese per la chiamata.  <br/> Nome in file ini: "CountryCode"  <br/> ||
|Città  <br/> |Città (facoltativo).  <br/> Nome nel file ini: "città"  <br/> ||
|Stato  <br/> |Stato (facoltativo).  <br/> Nome in file ini: "stato"  <br/> ||
|Indirizzo IP di base VM  <br/> |Indirizzo IP della VM di base temporanea che verrà usata per creare il VHDX per tutte le macchine virtuali di Cloud Connector. Questo IP deve essere nella stessa subnet della rete aziendale perimetrale definita nel passaggio successivo e richiede l'accesso a Internet. Assicurati di definire il gateway predefinito aziendale e il DNS instradabile a Internet.  <br/> Nome in file ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Rilascio 1.4.1 e versioni successive  <br/> |Indirizzo di Windows Server Update Services (WSUS), un server Intranet per ospitare gli aggiornamenti da Microsoft Update.  <br/> Se non è necessario, è possibile lasciarlo vuoto.  <br/> ||
|Subnet mask per la rete interna  <br/> |Cloud Connector configura una rete IP per la comunicazione interna tra i componenti di Cloud Connector. Anche Edge deve essere collegato a un'altra subnet che consente la connettività Internet.  <br/> Nome in file ini: "CorpnetIPPrefixLength" in "parametri per un pool di rete VM"  <br/> ||
|Subnet mask per la rete esterna  <br/> |Per la rete esterna del componente Edge.  <br/> Nome in file ini: "InternetIPPrefix" in "parametri per un pool di rete VM"  <br/> ||
|Cambiare nome per la rete interna  <br/> |Nome per l'opzione che verrà usata per la rete di connettori cloud interni.  <br/> Nella maggior parte dei casi può essere usato il valore suggerito predefinito.  <br/> Nome in file ini: "CorpnetSwitchName" in "parametri per un pool di rete VM  <br/> ||
|Cambiare nome per la rete esterna  <br/> |Nome per l'opzione che verrà usata per la rete di connettori cloud esterni.  <br/> Nella maggior parte dei casi può essere usato il valore suggerito predefinito.  <br/> Nome in file ini: "InternetSwitchName" in "parametri per un pool di rete VM  <br/> ||
|Gateway predefinito per la rete interna  <br/> |Questo gateway deve consentire l'accesso a Internet (Internet richiede anche l'impostazione del server DNS) e sarà configurato sulle interfacce interne dei componenti del connettore Cloud.  <br/> Nome in file ini: "CorpnetDefaultGateway" in "parametri per un pool di rete VM  <br/> ||
|Gateway predefinito per l'interfaccia esterna del componente Edge  <br/> |Verranno configurati sull'interfaccia esterna del componente Edge.  <br/> Nome in file ini: "InternetDefaultGateway" in "parametri per un pool di rete VM  <br/> ||
|Server DNS per la rete interna  <br/> |Verrà configurato sull'interfaccia interna della VM temporanea. Deve specificare la risoluzione dei nomi per i nome Internet. Senza fornire un server DNS, la connessione Internet non viene completata e la distribuzione non viene completata.  <br/> Nome in file ini: "CorpnetDNSIPAddress" in "parametri per un pool di rete VM  <br/> ||
|Server DNS per l'interfaccia esterna del componente Edge  <br/> |Verrà configurato sull'interfaccia esterna di Edge.  <br/> Nome in file ini: "InternetDNSIPAddress" in "parametri per un pool di rete VM  <br/> ||
|Nome dell'opzione di gestione  <br/> |L'opzione di gestione è un interruttore temporaneo che verrà creato automaticamente e che verrà usato per la configurazione del connettore cloud durante la distribuzione. Verrà disconnessa automaticamente dopo la distribuzione. Deve essere una subnet diversa da qualsiasi altra rete usata nel connettore Cloud.  <br/> Nella maggior parte dei casi può essere usato il valore suggerito predefinito.  <br/> Nome in file ini: "ManagementSwitchName" in "parametri per un pool di rete VM  <br/> ||
|Indirizzo subnet di gestione/subnet mask  <br/> |La subnet di gestione è una subnet temporanea che verrà creata automaticamente e che verrà usata per la configurazione del connettore cloud durante la distribuzione. Verrà rimosso automaticamente dopo la distribuzione. Deve essere una subnet diversa da qualsiasi altra rete usata nel connettore Cloud.  <br/> Nomi in file ini: "ManagementIPPrefix" e "ManagementIPPrefixLength" in "parametri per un pool di rete VM  <br/> ||
|Computer CMS (Central Management store)  <br/> |FQDN singolo usato per Central Management store (CMS). Il nome di dominio dell'annuncio verrà usato per generare l'FQDN.  <br/> Nome in file ini: "nomeserver" in "parametri per il servizio di gestione centrale principale  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> (Nome pool CMS = nome server)  <br/> |
|Indirizzo IP macchina CMS  <br/> |Indirizzo IP per il server CMS (interno nella rete perimetrale).  <br/> Nome nel file INI: "IP" in "parametri per il servizio di gestione centrale principale  <br/> ||
|Nome condivisione file  <br/> |Nome condivisione file da creare nel server CMS per i dati di replica di Skype for business (ad esempio, CmsFileStore).  <br/> Nella maggior parte dei casi può essere usato il valore suggerito predefinito.  <br/> Nome in file ini: "CmsFileStore" in "parametri per il servizio di gestione centrale principale  <br/> ||
|Nome del pool del componente di mediazione  <br/> |Nome del pool del componente di mediazione. Immettere solo il nome NetBIOS. Il nome di dominio dell'annuncio verrà usato per generare l'FQDN.  <br/> Nome in file ini: "PoolName" in "parametri per un pool di Mediation Server"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> |
|Nome del componente di mediazione  <br/> |Nome componente del componente di mediazione 1. Immettere solo il nome NetBIOS. Il nome di dominio dell'annuncio verrà usato per generare l'FQDN.  <br/> Nome in file ini: "nomeserver" in "parametri per un pool di Mediation Server"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> |
|Indirizzo IP del computer componente di mediazione  <br/> |IP corpnet interno per il componente di mediazione (interno nella rete perimetrale).  <br/> Nome in file ini: "IP" in "parametri per un pool di Mediation Server"  <br/> ||
|Nome interno del pool Edge  <br/> |Nome del pool del componente Edge. Immettere solo il nome NetBIOS. Il nome di dominio dell'annuncio verrà usato per generare l'FQDN.  <br/> Nome in file ini: "InternalPoolName" in "parametri per un pool di Edge Server"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> |
|Nome interno del server perimetrale  <br/> |Nome componente del componente bordo. Immettere solo il nome NetBIOS. Il nome di dominio dell'annuncio verrà usato per generare l'FQDN.  <br/> Nome in file ini: "InternalServerName" in "parametri per un pool di Edge Server"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> |
|IP interno del server perimetrale  <br/> |IP della rete perimetrale interna del componente Edge per comunicare con altri componenti del connettore Cloud.  <br/> Nome in file ini: "InternalServerIPs" in "parametri per un pool di Edge Server"  <br/> ||
|Nome esterno del pool di Access  <br/> |Nome del bordo di Access; ad esempio, AP. Questo nome deve corrispondere al nome specificato per il certificato SSL. Immettere solo il nome NetBIOS. Il nome di dominio SIP verrà usato per generare l'FQDN. Verrà usato un nome per i pool esterni per tutti i componenti del bordo nel pool. È necessario un pool di Access Edge per ogni sito PSTN.  <br/> Nome in file ini: "ExternalSIPPoolName" in "parametri per un pool di Edge Server"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> "SIP" è riservato e quindi non può essere usato come nome.  <br/> Il nome FQDN generato deve corrispondere al nome specificato per il certificato SSL.  <br/> |
|IP esterno di Access Edge  <br/> |IP esterno del componente Edge-IP pubblico se non è disponibile alcun NAT o IP tradotto (specificare entrambi gli indirizzi se mappati).  <br/> Nome in file ini: "ExternalSIPIPs" in "parametri per un pool di Edge Server"  <br/> ||
|Nome dell'inoltro multimediale  <br/> |Nome del bordo dell'inoltro audio video multimediale; ad esempio, MR. Verrà usato un nome per i pool esterni per tutti i componenti perimetrali in un pool. Per ogni sito PSTN è necessario un pool di Relay Media Edge.  <br/> Nome in file ini: "ExternalMRFQDNPoolName" in "parametri per un pool di Edge Server"  <br/> |Devono essere di 15 caratteri o meno. Immettere solo il nome NetBIOS.  <br/> |
|IP esterno del bordo del relè multimediale  <br/> |Attualmente è supportato solo un IP, quindi questo sarà lo stesso IP di Access Edge, IP pubblico o mappato (specificare entrambi gli indirizzi se mappati). Può essere lo stesso indirizzo dell'IP esterno del componente perimetrale di Access Edge. Nota Se Edge è dietro NAT, devi anche specificare il valore per il parametro Next.  <br/> Nome in file ini: "ExternalMRIPs" in "parametri per un pool di Edge Server"  <br/> ||
|IP esterno del bordo del relè multimediale (se Edge è dietro NAT)  <br/> |Se il tuo Edge è dietro NAT, devi anche specificare l'indirizzo pubblico del dispositivo NAT.  <br/> Nome in file ini: "ExternalMRPublicIPs" in "parametri per un pool di Edge Server"  <br/> ||
|Creare e modellare il gateway vocale 1  <br/> |Specifica la creazione e il modello del gateway SBC/Voice. Tieni presente che puoi connettere un dispositivo o un trunk SIP dall'elenco dei dispositivi testati [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Creare e modellare il gateway vocale 2 (copiare questa riga se si hanno più di 2 gateway)  <br/> |Specificare la creazione e il modello del gateway vocale. Tieni presente che puoi connettere un dispositivo dall'elenco dei dispositivi testati [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP).  <br/> ||
|Nome del gateway vocale 1  <br/> |Usato per generare l'FQDN del computer con dominio Active Directory. Obbligatorio se TLS verrà usato tra il componente di mediazione e il gateway vocale. Se non si prevede di usare il nome di dominio completo, ad esempio TLS non è obbligatorio o il gateway vocale non supporta la connessione tramite FQDN (solo IP), specificare.  <br/> ||
|Nome del gateway vocale 2 (copiare questa riga se si hanno più di 2 gateway)  <br/> |Usato per generare l'FQDN del computer con dominio Active Directory. Obbligatorio se TLS verrà usato tra il componente di mediazione e il gateway vocale. Se non si prevede di usare il nome di dominio completo, ad esempio TLS non è obbligatorio o il gateway vocale non supporta la connessione tramite FQDN (solo IP), specificare.  <br/> ||
|Indirizzo IP del gateway vocale 1  <br/> |Indirizzo IP del gateway vocale.  <br/> ||
|Indirizzo IP del gateway vocale 2 (copiare questa riga se si hanno più di 2 gateway)  <br/> |Indirizzo IP del gateway vocale.  <br/> ||
|Gateway vocale 1 porta # (copiare questa riga se si hanno più di 2 gateway)  <br/> |Porta che verrà ascoltata dal trunk SIP del gateway vocale, ad esempio 5060.  <br/> ||
|Porta del gateway vocale 2 #  <br/> |Porta che verrà ascoltata dal trunk SIP del gateway vocale, ad esempio 5060.  <br/> ||
|Protocollo Voice Gateway 1 per il traffico SIP  <br/> |TCP o TLS.  <br/> ||
|Protocollo Voice Gateway 2 per il traffico SIP (copiare questa riga se si hanno più di 2 gateway)  <br/> |TCP o TLS.  <br/> ||
|Intervallo di porte multimediali esterne per il traffico da e verso il componente Edge  <br/> |Intervallo di porte TCP/UDP per il traffico multimediale da e verso l'interfaccia esterna di Edge. Deve sempre iniziare da 50 000. Per altre informazioni, vedere "porte e protocolli".  <br/> |50000-59 999  <br/> |
|Intervallo di porte multimediali per comunicare al/dal componente di mediazione tramite il firewall interno  <br/> |Intervallo di porte UDP che il componente di mediazione userà per comunicare con i client e i gateway (Raccomandazione 4 porte per chiamata).  <br/> ||
|Intervallo di porte multimediali per comunicare a/da client Skype for business tramite firewall interno  <br/> |Per scopi di pianificazione, non può essere modificato. Le porte devono essere aperte nel firewall interno per comunicare tra client Skype for business all'interno della rete interna e con il componente di mediazione.  <br/> |50 000-50 019  <br/> |
|Password di certificato pubblico  <br/> |Devono essere forniti nello script.  <br/> ||
|Password di amministratore in modalità provvisoria  <br/> Solo versione 1.4.2  <br/> |Password di amministratore in modalità provvisoria per il dominio CC interno.  <br/> ||
|Password di amministratore del dominio del connettore Cloud  <br/> Solo versione 1.4.2  <br/> |Password per l'amministratore del dominio del connettore Cloud (diverso dal dominio di produzione). Nome utente è Administrator. Non è possibile modificare il nome utente.  <br/> ||
|Password amministratore macchine virtuali  <br/> Solo versione 1.4.2  <br/> |Usato per configurare la rete di gestione durante la distribuzione.  <br/> Nome utente è Administrator. Non è possibile modificare il nome utente.  <br/> ||
|CABackupFile  <br/> Versione 2,0 e successive  <br/> |Usato per salvare il servizio autorità di certificazione dal server di Active Directory a un file durante la distribuzione di più appliance in un sito di connettori cloud. Assicurarsi di usare la stessa password per tutti gli elettrodomestici all'interno di un sito del connettore Cloud per importare correttamente il file di backup della CA nel nuovo dispositivo aggiunto.  <br/> ||
|CCEService  <br/> Versione 2,0 e successive  <br/> |Usato per il servizio di gestione dei Cloud Connector; richiede l'accesso alla directory del sito del connettore Cloud. Assicurarsi di usare la stessa password per tutti gli elettrodomestici all'interno di un sito del connettore Cloud.  <br/> ||
|Amministratore del tenant di Office 365  <br/> | L'account viene usato da Cloud Connector per aggiornare e gestire le impostazioni del tenant per Cloud Connector: <br/>  Versione 2,0 e successive: credenziali per un account di Office 365 dedicato con i diritti di amministratore di Skype for business. <br/>  Versioni precedenti a 2,0: credenziali per un account di Office 365 dedicato con diritti di amministratore del tenant globale. <br/> ||
|Abilitare il supporto per i riferimenti  <br/> |Questo definirà se il supporto SIP REFER è abilitato o disabilitato nella configurazione trunk per il tuo IP/PBX. Il valore predefinito è True. Se il gateway IP/PBX supporta il supporto per i riferimenti, lasciarlo come vero. In caso contrario, questo valore deve essere impostato su false. Se non si è certi che il gateway supporti il riferimento, vedere [IP-PBX e gateway qualificati](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Versione 2,0 e successive  <br/> |Con il valore predefinito "true", se le chiamate in uscita non rispondono al gateway entro 10 secondi, verranno instradate al gateway disponibile successivo; Se non ci sono trunk aggiuntivi, la chiamata verrà eliminata automaticamente.  <br/> Tuttavia, in un'organizzazione con reti lente e risposte di gateway o quando il processo di creazione di chiamate richiede più di 10 secondi, potrebbe risultare inutilmente necessario che le chiamate vengano eliminate.  <br/> Quando si inseriscono chiamate in alcuni paesi, ad esempio Emirati Arabi Uniti o Afghanistan, il processo di definizione delle chiamate può richiedere più di 10 secondi. Se si verificano problemi simili, sarà necessario modificare il valore in false. Non dimenticare di modificare l'impostazione corrispondente nell'SBC o nel gateway connesso.  <br/> Il valore può essere vero o falso. Il valore predefinito è True.  <br/> ||
|ForwardCallHistory  <br/> Versione 2,0 e successive  <br/> | Questo parametro viene usato per attivare le intestazioni SIP usate per segnalare il chiamante iniziale nello squillo simultaneo, nell'inoltro di chiamata e negli scenari di trasferimento delle chiamate. Se si imposta il parametro su true, verranno attivate due intestazioni SIP: <br/>  Cronologia-informazioni <br/>  Fatto riferimento <br/>  L'intestazione History-info viene usata per la ridestinazione delle richieste SIP e "offre un meccanismo standard per l'acquisizione delle informazioni sulla cronologia delle richieste per consentire un'ampia varietà di servizi per le reti e gli utenti finali" ([RFC 4244-Section 1,1](http://www.ietf.org/rfc/rfc4244.txt)). Per le interfacce trunk del connettore Cloud, questo viene usato negli scenari di inoltro di Simulring e di chiamata.  <br/>  Il valore può essere vero o falso. Il valore predefinito è False. <br/> ||
|Inoltrare PAI  <br/> Versione 2,0 e successive  <br/> |PAI è un'estensione privata da SIP che consente ai server SIP di affermare l'identità degli utenti autenticati. Per il provider trunk SIP, PAI può essere usato per scopi di fatturazione, se non sono presenti le intestazioni History-info e di riferimento. Quando l'inoltro P-Asserted-Identity è abilitato nella configurazione, il Mediation Server inoltra le intestazioni di PAI &amp; con il connettore SIP Tel URI from cloud sul trunk SIP. Il Mediation Server inoltra le intestazioni di PAI con i &amp; numeri E. 164 di Tel URI ricevuti solo nel connettore trunk SIP per il Cloud Connector. Il Mediation Server inoltra anche le intestazioni di privacy ricevute in entrambe le direzioni. Se la richiesta SIP inviata dal Mediation Server include un'intestazione di privacy della maschera "privacy: ID" in combinazione con l'intestazione PAI, l'identità asserita deve essere mantenuta privata all'esterno del dominio di trust di rete.  <br/> Il valore può essere vero o falso. Il valore predefinito è False.  <br/> ||

### <a name="certificate-requirements"></a>Requisiti per i certificati
<a name="BKMK_Certs"> </a>

Ogni componente Edge richiede un certificato di un'autorità di certificazione pubblica. I certificati devono avere una chiave privata esportabile da copiare tra i componenti di Edge. Per soddisfare i requisiti di certificato, è necessario decidere tra le opzioni seguenti e specificare il nome dell'oggetto (SN) e il nome alternativo soggetto (SAN) per il certificato.

 **Se si ha un singolo dominio SIP:**

- **Opzione 1.** Il nome del soggetto deve contenere il nome del pool assegnato ai componenti Edge. Tieni presente che il nome del soggetto non può essere sip.sipdomain.com perché questo nome è riservato per il componente online Skype for Business Edge. La SAN deve contenere sip.sipdomain.com e il nome del pool di Access Edge:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opzione 2.** Se si vuole usare un singolo certificato con caratteri jolly in tutti i server del pool di Edge distribuiti, è possibile usare una voce SAN jolly \*di. SipDomain.com anziché il nome del pool di bordi nel certificato. Il nome dell'oggetto può essere il nome del pool di Access Edge di uno dei pool di bordi distribuiti:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Non è necessario creare una voce DNS esterna per SIP. \<SipDomain\>. com perché questo nome appartiene alla distribuzione di Office 365.

> [!NOTE]
> Se si vuole usare un singolo certificato per tutti i pool di bordi distribuiti nell'organizzazione e non è possibile usare un certificato con caratteri jolly come definito nell'opzione 2, sarà necessario includere l'FQDN per tutti i pool di bordi distribuiti nel nome SAN nel certificato.

 **Se si hanno più domini SIP:**

Sarà necessario aggiungere sip.sipdomain.com per ogni dominio SIP e il nome dei pool di Access Edge per dominio (può essere un pool fisico, ma con nomi diversi). Di seguito è riportato un esempio di voci SN e SAN in uno scenario di dominio SIP multiplo:

- **Opzione 1.** Il nome del soggetto deve contenere il nome del pool assegnato per i componenti Edge. Tieni presente che il nome del soggetto non può essere sip.sipdomain.com perché questo nome è riservato per il componente online Skype for Business Edge. La SAN deve contenere sip.sipdomain.com e il nome del pool di Access Edge:

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opzione 2.</strong> Se si vuole usare un singolo certificato con caratteri jolly in tutti i server del pool di Edge distribuiti, è possibile usare una voce SAN jolly \*di. SipDomain.com anziché il nome del pool di bordi nel certificato. Il nome dell'oggetto può essere il nome del pool di Access Edge di uno dei pool di bordi distribuiti:

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Non è necessario creare una voce DNS esterna per SIP. \<SipDomain\>. com perché questo nome appartiene alla distribuzione di Office 365.

Per scopi di distribuzione, è possibile usare la tabella seguente:

|**Opzione**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Quale opzione si usa per la distribuzione?  <br/> |Opzione 1 o 2  <br/> ||
|SN  <br/> |Specificare lo SN per il certificato  <br/> ||
|SAN  <br/> |Fornisce la SAN per il certificato  <br/> ||

Se si usa TLS tra il gateway e il Mediation Server, sarà necessario ottenere il certificato radice o la catena di certificati completa per il certificato assegnato al gateway.

## <a name="dial-plan-considerations"></a>Considerazioni sul dial plan
<a name="BKMK_DailPlan"> </a>

Cloud Connector richiede l'uso di un dial plan online. Per altre informazioni su come configurare un dial plan online, vedere [cosa sono i dial plan?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considerazioni sulla disponibilità elevata
<a name="BKMK_HA"> </a>

Quando si distribuisce Cloud Connector Edition per l'elevata disponibilità, è possibile distribuire almeno due dispositivi che fungono da backup. Ogni appliance è costituito da quattro componenti: Edge, Mediation, Central Management store (CMS) e Domain controller.

In generale, se un componente all'interno di un dispositivo si abbassa, Cloud Connector Edition può continuare a gestire le chiamate, ma è necessario tenere presente quanto segue:

- **Considerazioni sui componenti di mediazione, CMS e controller di dominio**

    Supponiamo che il componente CMS o controller di dominio in un dispositivo vada in calo. L'appliance può comunque gestire le chiamate in ingresso e in uscita, ma se si riavvia un componente di mediazione quando il controller di dominio o il componente CMS non è raggiungibile, la mediazione non funzionerà. Lo stesso vale per riavviare il componente CMS quando il controller di dominio è in calo.

    **Suggerimento:** Prima di riavviare i componenti, verificare la disponibilità degli altri componenti nell'appliance.

- **Considerazioni sui componenti Edge**

    Se il componente Edge in un dispositivo non è disponibile, il comportamento delle chiamate in ingresso e in uscita sarà diverso dal seguente:

  - **Chiamata in uscita**: chiamata dall'utente in Internet a una rete PSTN.

    Il meccanismo di distribuzione delle chiamate nel cloud identificherà l'abbandono di un componente Edge e instraderà tutte le chiamate a un altro dispositivo, in modo che la chiamata in uscita abbia esito positivo.

  - **Chiamata in ingresso**: chiamata dalla rete PSTN a un utente che si trova in una rete locale o in Internet.

     Se il componente Edge dell'appliance che ha ricevuto la chiamata non funziona, le chiamate in ingresso a questo dispositivo non avranno esito positivo perché il componente di mediazione non può reindirizzare la chiamata al componente Edge nell'altro dispositivo.

    **Suggerimento:** Disporre di un sistema di monitoraggio in posizione. Dopo aver identificato un malfunzionamento del componente Edge, arrestare tutti i componenti dell'appliance in cui il componente bordo non è disponibile.

## <a name="cloud-connector-media-flow"></a>Flusso multimediale Cloud Connector
<a name="BKMK_MediaFlow"> </a>

I diagrammi seguenti illustrano il flusso di una chiamata in uscita e in ingresso tramite Cloud Connector Edition. Si tratta di informazioni utili per capire come viene stabilita la connettività.

Nel primo diagramma un utente interno inserisce una chiamata in uscita come segue:

1. Dave, un utente ospitato online, ma ora nella rete interna, effettua una chiamata a un utente PSTN esterno.

2. Le route di traffico SIP in Skype for business online.

3. Skype for business online esegue una ricerca inversa del numero. La ricerca del numero inverso non riesce perché questo numero non appartiene a nessuno nell'organizzazione Skype for business.

4. La chiamata viene instradata al componente Edge (SIP e flusso multimediale tramite Edge online per primo; I contenuti multimediali andranno al componente mediazione tramite il firewall interno.

5. Se la route esiste, il componente Edge inoltra il traffico al componente di mediazione nella rete perimetrale.

6. Il componente mediazione invia il traffico al gateway PSTN.

![Flusso multimediale in uscita per il connettore Cloud](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Nel diagramma successivo un utente interno riceve una chiamata in ingresso come indicato di seguito:

1. Il gateway PSTN riceve una chiamata per l'utente Dave che è homed online, ma ora è nella rete interna.

2. Il traffico SIP viene instradato al componente di mediazione.

3. Il componente mediazione invia il traffico SIP al componente Edge e quindi passa a Skype for business online.

4. Skype for business online esegue una ricerca inversa del numero e scopre che si tratta di un utente Dave.

5. La segnalazione SIP passa a tutti i punti di presenza di Dave.

6. Il traffico multimediale verrà stabilito tra il gateway e il componente di mediazione e tra il componente di mediazione e il punto finale.

![Flusso multimediale in ingresso per il connettore Cloud](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Monitoraggio e risoluzione dei problemi
<a name="BKMK_Monitor"> </a>

Il meccanismo di monitoraggio e risoluzione dei problemi viene installato automaticamente con ogni accessorio Cloud Connector. Il meccanismo rileva gli eventi seguenti:

- Una o più macchine virtuali di un dispositivo di connessione cloud non sono connesse a un interruttore virtuale interno o Internet.

- Uno o più macchine virtuali di un dispositivo di connessione cloud sono in stato salvato o arrestato.

- Servizi che non sono in uso.

  Se viene rilevato uno degli eventi seguenti, l'intero dispositivo Cloud Connector viene svuotato e contrassegnato come offline per impedire il tentativo di stabilire chiamate a un dispositivo che non funziona correttamente. Le funzionalità di ripristino automatico del Cloud Connector verranno in seguito ripristinate e contrassegnate l'accessorio come online. Se il ripristino automatico non riesce per qualche motivo, vedere [risoluzione dei problemi relativi alla distribuzione di Cloud Connector](troubleshoot-your-cloud-connector-deployment.md).

  - Nella macchina virtuale di Central Management store:

     - Agente di replica master di Skype for business

     - Agente replica di Skype for business

  - Nella macchina virtuale Mediation Server:

     - Agente replica di Skype for business

     - Mediazione di Skype for Business Server

  - Nella macchina virtuale Edge Server

     - Agente replica di Skype for business

     -  Access Edge di Skype for Business Server

     - Edge audio/video di Skype for Business Server

     - Autenticazione audio/video di Skype for Business Server

     - Skype for Business Server Web Conferencing Edge

- Regola in entrata di Windows Firewall per "CS RTCSRV" sul bordo, "CS RTCMEDSRV" sul server Mediation è disabilitato.

Cloud Connector 2,1 e versioni successive supporta il monitoraggio del connettore cloud tramite le Operations Management Suite (OMS). Per altre informazioni, vedere [monitorare il connettore cloud tramite Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Per altre informazioni
<a name="BKMK_MoreInfo"> </a>

Per altre informazioni, vedere quanto segue:

- [Soluzioni di telefonia Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configurare e gestire Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Distribuire il bypass multimediale in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


