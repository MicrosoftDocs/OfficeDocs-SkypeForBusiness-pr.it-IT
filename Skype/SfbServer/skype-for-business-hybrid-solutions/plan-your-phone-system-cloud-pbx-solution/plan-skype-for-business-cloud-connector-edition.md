---
title: Pianificare Skype for Business Cloud Connector Edition
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
description: Trovare informazioni su Skype for Business Cloud Connector Edition, un set di macchine virtuali in pacchetti (VM) che implementano la connettività PSTN locale con sistema telefonico (cloud PBX).
ms.openlocfilehash: d2b7f4203da082112b846cc3f12f57dd7758fc82
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220086"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>Pianificare Skype for Business Cloud Connector Edition

Trovare informazioni su Skype for Business Cloud Connector Edition, un set di macchine virtuali in pacchetti (VM) che implementano la connettività PSTN locale con sistema telefonico (cloud PBX).

Cloud Connector Edition potrebbe essere la soluzione ideale per l'organizzazione se non si dispone già di una distribuzione di Lync Server o di Skype for Business Server esistente. Se si sta ancora studiando quale soluzione di sistema telefonico è adatta alla propria azienda, vedere [Microsoft telefonia Solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions).

In questo documento vengono descritti i requisiti di Cloud Connector Edition e le topologie supportate e vengono fornite informazioni utili per pianificare la distribuzione di Cloud Connector Edition. Leggere questo argomento prima di configurare l'ambiente dei connettori cloud. Quando si è pronti per la distribuzione e la configurazione di Cloud Connector Edition, vedere [Configure and Manage Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md).

Cloud Connector Edition 2,1 è ora disponibile. Se non è ancora stato eseguito l'aggiornamento a 2,1, vedere [upgrade to a New Version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md). È possibile trovare il file di installazione in [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .

> [!NOTE]
> Microsoft supporta la versione precedente di Cloud Connector Edition per 60 giorni dopo il rilascio di una nuova versione. Microsoft supporterà la versione 2.0.1 per 60 giorni dopo il rilascio di 2,1 per consentire il tempo necessario per l'aggiornamento. Tutte le versioni precedenti a 2.0.1 non sono più supportate.

Cloud Connector Edition è un'offerta ibrida costituita da un insieme di macchine virtuali in pacchetti (VM) che implementano la connettività PSTN locale con il sistema telefonico. Distribuendo una topologia minima di Skype for Business Server in un ambiente virtualizzato, gli utenti dell'organizzazione che si trovano nel cloud possono ricevere servizi PBX dal cloud Microsoft, ma la connettività PSTN viene fornita tramite l'infrastruttura vocale locale esistente.

![Diagramma della topologia che mostra il gateway cloud PBX che connette cloud PBX a una distribuzione locale di Skype for business.](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

Poiché il connettore Cloud consente di integrare i servizi di sistema telefonico con l'ambiente di telefonia esistente, ad esempio PBX, dispositivi analogici e Call Center, è possibile implementare una migrazione in fasi dalla soluzione di telefonia esistente al sistema telefonico.

Si supponga, ad esempio, che la società disponga di un Call Center sofisticato con funzionalità specifiche che il sistema telefonico non fornisce. È possibile scegliere di lasciare gli utenti di Call Center con la soluzione esistente, ma spostare altri utenti nel sistema telefonico.

Cloud Connector fornirà il routing tra gli utenti ospitati in locale e online ed è possibile scegliere di usare il proprio provider PSTN con sistema telefonico.

Quando si pianifica la distribuzione di Cloud Connector Edition, tenere presente quanto segue:

- Per utilizzare Cloud Connector per sfruttare le soluzioni cloud Voice, è necessario iscriversi a un'organizzazione Microsoft 365 o Office 365 che include il sistema telefonico. [! Nota] se non si dispone ancora di un'organizzazione Microsoft 365 o Office 365, è possibile ottenere informazioni su come iscriversi qui: [microsoft 365 for business](https://products.office.com/business/office). Si noti che è necessario iscriversi a un piano che include Skype for business online.

- Per registrare gli apparecchi dei connettori cloud con il servizio Skype for business online e per eseguire vari cmdlet, Cloud Connector 2,0 e versioni successive richiede un account Microsoft 365 o Office 365 dedicato con i diritti di amministratore del tenant di Skype for business. Le versioni dei connettori cloud precedenti a 2,0 richiedono un account Microsoft 365 o Office 365 dedicato con diritti di amministratore globale del tenant.

- Il connettore Cloud non richiede una distribuzione completa di Skype for Business Server in locale.

    Attualmente, il connettore Cloud non può coesistere con Lync o i server locali di Skype for business. Se si desidera spostare gli utenti di Lync o Skype for business esistenti in Microsoft 365 e mantenere la fornitura di telefonia locale agli utenti, prendere in considerazione il sistema telefonico con connettività locale utilizzando una distribuzione di Skype for Business Server esistente. Per ulteriori informazioni, vedere [Plan Your Phone System (cloud PBX) Solution](plan-your-phone-system-cloud-pbx-solution.md) and [Plan Phone System con connettività PSTN locale in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).

- Se si dispone di una distribuzione precedente di Skype for business o di Lync Server ed è stato esteso lo schema, non è necessario pulire lo schema per la distribuzione del connettore Cloud, purché siano stati rimossi tutti i componenti di Skype for business o di Lync Server dall'ambiente in uso.

- Gli utenti sono ospitati online.

- Se nell'organizzazione è stata configurata la sincronizzazione della directory (DirSync), tutti gli account degli utenti pianificati per la voce ibrida devono essere creati prima nella distribuzione locale e quindi sincronizzati con il cloud.

- Se necessario, è possibile mantenere il vettore PSTN corrente.

- Se si desidera fornire servizi di conferenza telefonica con accesso esterno agli utenti ospitati su cloud Connector, è possibile acquistare una licenza di conferenza PSTN o pay as you go audioconferenza da Microsoft.

- La licenza di audioconferenza (o pay as you go) è necessaria anche per le escalation delle chiamate. Se un utente Skype for business riceve una chiamata da un utente PSTN esterno e desidera aggiungere un altro partecipante alla chiamata (inoltrare la chiamata a una conferenza), l'escalation verrà eseguita tramite Microsoft Audio Conferencing Service.

- Il connettore Cloud 2,0 e versioni successive supporta quindi il bypass multimediale. Il bypass multimediale consente a un client di inviare contenuti multimediali direttamente alla rete PSTN (Public Switched Telephone Network), ovvero a un gateway o a un session border controller (SBC), ed eliminare il componente cloud Connector Edition dal percorso multimediale. Per ulteriori informazioni, vedere [Plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).

- Cloud Connector 2,1 e versioni successive supporta il Monitoring Cloud Connector tramite Operations Management Suite (OMS). Per ulteriori informazioni, vedere [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

- Il connettore Cloud è disponibile in tutti i paesi in cui è disponibile Office 365 Enterprise E5.

In questa sezione sono contenute le seguenti sezioni:

- [Componenti di Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [Topologie di Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [Requisiti per la distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [Informazioni necessarie per la raccolta prima della distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [Considerazioni sul dial plan](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [Considerazioni sulla disponibilità elevata](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [Flusso multimediale del connettore Cloud](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [Monitoraggio e risoluzione dei problemi](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [Ulteriori informazioni](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>Componenti di Cloud Connector Edition
<a name="BKMK_Components"> </a>

Con Cloud Connector Edition, è possibile distribuire un insieme di macchine virtuali con pacchetti che contengono una topologia di Skype for Business Server minima, costituita da un componente perimetrale, da un componente di Mediation e da un ruolo CMS (Central Management store). Verrà installato anche un controller di dominio, necessario per il funzionamento interno del connettore Cloud. Questi servizi sono configurati per l'ambiente ibrido con l'organizzazione Microsoft 365 o Office 365 che include i servizi Skype for business online.

![Componenti di Cloud Connector Edition](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

I componenti dei connettori cloud offrono le seguenti funzionalità:

- **Componente perimetrale** -la comunicazione tra la topologia locale e i servizi online passa attraverso il componente Edge, che include i componenti seguenti:

  - **Access Edge** -fornisce il routing SIP tra la distribuzione locale e Skype for business online.

  - **Inoltro multimediale** : consente di instradare il contenuto multimediale tra il componente Mediation e gli altri endpoint multimediali.

  - **Media Relay Authentication/MRAS** -genera i token per l'accesso all'inoltro multimediale.

- **Routing in uscita** -fornisce il bilanciamento del carico del traffico vocale tra gateway o SBCS connesso a un dispositivo di connessione cloud. Le chiamate verranno divise equamente tra tutti i gateway o SBCs connessi all'accessorio Cloud Connector.

    Fornisce il routing ai gateway in base ai criteri. Sono supportati solo i criteri globali che si basano su numeri PSTN di destinazione (in uscita).

- **Ruolo di archivio di gestione centrale (CMS)** -include l'archivio di configurazione per i componenti della topologia, incluso il trasferimento di file CMS.

- **Replica dell'archivio di gestione centrale (CMS)** : consente di sincronizzare le informazioni di configurazione dal database CMS globale sul server di ruolo CMS.

- **Domain controller** -Cloud Connector Active Directory Domain Services per archiviare tutte le impostazioni globali e i gruppi necessari per la distribuzione dei componenti del connettore Cloud. Verrà creata una foresta per ogni accessorio Cloud Connector. Il controller di dominio non deve disporre di connessioni con Active Directory di produzione. I servizi di Active Directory includono:

  - Active Directory Domain Services

  - Servizi certificati Active Directory per l'emissione di certificati interni

- **Mediation Component** -implementa SIP and media gateway mapping Protocol tra Skype for business e i gateway PSTN. Include una replica CMS che sincronizza la configurazione dal database CMS globale.

## <a name="cloud-connector-edition-topologies"></a>Topologie di Cloud Connector Edition
<a name="BKMK_Topologies"> </a>

Ai fini di questa discussione, verranno riferiti a siti PSTN. Un sito PSTN è una combinazione di dispositivi di connettori cloud, distribuiti nello stesso percorso e con gateway PSTN comuni ad essi connessi. I siti PSTN consentono di:

- Fornire la connettività ai gateway più vicini agli utenti.

- Consentire la scalabilità distribuendo più appliance di connettori cloud all'interno di uno o più siti PSTN.

- Consentire la disponibilità elevata distribuendo più appliance di connettori cloud all'interno di un singolo sito PSTN.

In questo argomento vengono introdotti i siti PSTN. Per ulteriori informazioni sulla pianificazione dei siti PSTN, vedere [Plan for Cloud Connector Edition PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md).

È possibile distribuire le topologie dei connettori cloud seguenti:

- Un singolo accessorio Cloud Connector Edition per sito PSTN. Questa topologia è consigliata solo a scopo di valutazione, perché non garantisce una disponibilità elevata.

- Più appliance di Cloud Connector Edition per sito PSTN per garantire una disponibilità elevata.

- Più siti PSTN con più appliance di Cloud Connector Edition per garantire la scalabilità con disponibilità elevata. È possibile distribuire fino a 200 siti.

Quando si pianifica la topologia, prendere in considerazione quanto segue:

- Con il connettore Cloud 2,0 e versioni successive, un sito PSTN può avere fino a 16 appliance di connettori cloud. Le versioni precedenti supportano fino a 4 dispositivi per sito.

- Sono stati testati due tipi di configurazioni hardware con il connettore Cloud:

  - La versione più grande è in grado di gestire grandi volumi di chiamate simultanee ed è supportata in tutti i tipi di ambiente di produzione.

  - La versione più piccola è destinata all'esecuzione su hardware di fascia più bassa e può essere utilizzata per scopi di valutazione o per siti con volumi di chiamate insufficienti. Se si distribuisce una versione ridotta del connettore Cloud, è comunque necessario essere consapevoli dei requisiti hardware della classe di produzione, ad esempio i due alimentatori.

- Se si dispone del connettore Cloud versione 2,0 o successiva e si distribuisce la configurazione massima di 16 Appliance (con hardware più grande), il sito PSTN può gestire fino a 8.000 chiamate simultanee. Se si distribuisce la versione ridotta, il limite supportato è 800.

    È inoltre necessario dedicare alcuni dispositivi per la disponibilità elevata. La raccomandazione minima è che un dispositivo dovrebbe essere riservato per la disponibilità elevata.

  - Con la versione 2, se si distribuisce una configurazione di 15 + 1, il sito PSTN può gestire fino a 7.500 chiamate simultanee.

  - Se si dispone di una versione precedente e si distribuisce la configurazione massima di 3 + 1 (con hardware più grande), il sito PSTN può gestire fino a 1500 chiamate simultanee. Se si distribuisce la versione ridotta, il limite supportato è 150.

-  Se è necessario disporre di più chiamate per sito PSTN, è possibile eseguire la scalabilità verticale distribuendo ulteriori siti PSTN nello stesso percorso.

> [!NOTE]
> Se non specificato, i diagrammi e gli esempi riportati di seguito presuppongono l'utilizzo della versione più grande del connettore Cloud.

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>Dispositivo single Cloud Connector all'interno di un singolo sito PSTN

Nel diagramma seguente viene illustrato un singolo accessorio Cloud Connector Edition all'interno di un singolo sito PSTN. Si noti che il connettore Cloud è costituito da quattro macchine virtuali installate su un computer host fisico che si trova all'interno di una rete perimetrale per motivi di sicurezza.

![Un connettore Cloud con un solo sito PSTN](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>Più appliance di connettori cloud all'interno di un singolo sito PSTN

 Per la scalabilità e la disponibilità elevata, è possibile scegliere di disporre di più edizioni di connettori cloud all'interno di un singolo sito PSTN, come illustrato nel diagramma seguente. Considerare quanto segue:

- Le chiamate vengono distribuite in ordine casuale tra connettori cloud in un pool.

- Per la pianificazione della capacità, è necessario prendere in considerazione la possibilità di gestire il carico se uno o più connettori cloud non sono in linea, in base ai calcoli seguenti:

  - **N + 1 caselle.** Per la versione più grande del connettore Cloud, le caselle N + 1 supportano le \* chiamate simultanee di 500 n con disponibilità del 99,8%.

    Per la versione ridotta del connettore Cloud, le caselle N + 1 supportano le \* chiamate simultanee 50 n con la disponibilità del 99,8%.

  - **N + 2 caselle.** Per la versione più grande del connettore Cloud, le caselle N + 2 supportano le \* chiamate simultanee di 500 n con la disponibilità del 99,9%.

    Per la versione ridotta del connettore Cloud, le caselle N + 2 supportano le \* chiamate simultanee di 50 n con la disponibilità del 99,9%.

![Due connettori cloud all'interno di 1 sito PSTN](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>Più siti PSTN con uno o più connettori cloud per sito

È inoltre possibile scegliere di disporre di più siti PSTN con una o più edizioni del connettore Cloud in ogni sito. Se il sito PSTN raggiunge il limite di chiamate simultanee, è possibile aggiungere un altro sito PSTN per gestire il carico.

Più siti PSTN consentono anche di fornire la connettività ai gateway più vicini agli utenti. Si supponga, ad esempio, di disporre di gateway PSTN in Seattle e Amsterdam. È possibile distribuire due siti PSTN, uno a Seattle, uno di Amsterdam, e assegnare agli utenti l'utilizzo del sito PSTN più vicino. Gli utenti di Seattle verranno instradati al sito PSTN di Seattle e ai gateway, mentre gli utenti di Amsterdam verranno instradati al sito PSTN di Amsterdam e ai gateway:

![Cloud Connector Edition all'interno di 2 siti PSTN](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>Requisiti per la distribuzione
<a name="BKMK_Requirements"> </a>

Prima di distribuire Cloud Connector Edition, verificare di disporre dei seguenti elementi per l'ambiente in uso:

- **Per il computer host-** Le macchine virtuali dei connettori cloud devono essere distribuite su hardware dedicato che esegue Windows Server 2012 R2 Datacenter Edition (Inglese) con il ruolo Hyper-V abilitato.

    Per la versione 2,0 e versioni successive, la scheda di rete del computer host associata all'opzione Corpnet di Skype for business deve disporre di un indirizzo IP configurato nella stessa subnet del Cloud Connector Corporate Network machines.

- Per le versioni 2,1 e versioni successive, è necessario che nell'accessorio host sia installato .NET Framework 4.6.1 o versione successiva.

- **Per le macchine virtuali-** Un'immagine di Windows Server 2012 R2 ISO (Inglese) (. ISO). La ISO verrà convertita in VHD per le macchine virtuali che eseguirà Skype for Business Cloud Connector Edition.

- L'hardware necessario per supportare l'installazione delle 4 macchine virtuali per ogni versione di Cloud Connector nella distribuzione. Sono consigliate le configurazioni seguenti:

  - processore duale a 64 bit, Six Core (12 core reali), 2,50 gigahertz (GHz) o superiore

  - 64 gigabyte (GB) di RAM ECC

  - 4 600 GB (o superiore) 10K RPM 128M cache SAS 6Gbps disks, configurati in una configurazione RAID 5

  - Tre schede di rete da 1 Gbps RJ45 ad alta velocità

- Se si sceglie di distribuire la versione ridotta di Cloud Connector Edition che supporta fino a 50 chiamate simultanee, sarà necessario l'hardware seguente:

  - Intel i7 4790 quad core con grafica Intel 4600 (non è necessaria alcuna grafica di fascia alta)

  - 32 GB DDR3-1600 non ECC

  - 2:1 TB 7200RPM SATA III (6 Gbps) in RAID 0

  - 2:1 Gbps Ethernet (RJ45)

- Se nel computer host è necessario un server proxy per l'esplorazione di Internet, è necessario apportare le modifiche seguenti alla configurazione:

  - Per ignorare il proxy, specificare le impostazioni del proxy WinHTTP impostate con il server proxy e un bypass-list che include "192.168.213 \* ". rete utilizzata dai servizi di gestione Cloud Connector e dalla subnet Corpnet di Skype for business, come definito nel file CloudConnector. ini. In caso contrario, la connettività di gestione avrà esito negativo e impedirà la distribuzione e il ripristino automatico del connettore Cloud. Di seguito è riportato un comando di configurazione WinHTTP di esempio: netsh winhttp set proxy "10.10.10.175:8080" bypass-list = " \* . local; 1. \* ; 172,20. \* ; 192.168.218. \* ' \< local \> ".

  - Specificare le impostazioni del proxy per ogni computer anziché per utente. In caso contrario, i download del connettore Cloud falliranno. È possibile specificare le impostazioni del proxy per computer con una modifica del registro di sistema o con l'impostazione di criteri di gruppo, come indicato di seguito:

  - **Registro di sistema:** HKEY_LOCAL_MACHINE impostazioni di \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet] ProxySettingsPerUser DWORD: 00000000

  - **Criteri di gruppo:** \>Modelli amministrativi per computer i \> componenti \> di Windows Internet Explorer: rendere le impostazioni del proxy per ogni computer (invece che per utente)

- È consigliabile utilizzare PBX/trunk qualificati o SBC/gateway qualificati (è consigliato un minimo di due gateway).

    Il connettore Cloud supporta gli stessi session border controller (SBCs) certificati per Skype for business. Per ulteriori informazioni, vedere l' [infrastruttura di telefonia per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).

- Un account di amministratore del server locale con le autorizzazioni per installare e configurare Hyper-V nei server host. L'account deve disporre di autorizzazioni di amministratore per il server locale in cui è installato e configurato Hyper-V.

- Durante la distribuzione, verrà richiesto di creare un account di amministratore di dominio con le autorizzazioni per creare e pubblicare la topologia nel dominio del connettore Cloud.

- I record DNS esterni, definiti nel file CloudConnector. ini incluso nel pacchetto di installazione:

  - Record DNS esterno per il servizio Access Edge del componente perimetrale; ad esempio, AP. \< Nome di dominio \> . È necessario un record per ogni sito PSTN. Questo record deve contenere indirizzi IP di tutti i bordi per il sito.

- Un'organizzazione di Microsoft 365 o Office 365 con tutti i record DNS e SRV necessari creati.

    > [!IMPORTANT]
    > Quando si integra il tenant con Cloud Connector Edition, l'utilizzo del suffisso di dominio predefinito,. onmicrosoft.com, come dominio SIP per l'organizzazione non è supportato. > non è possibile utilizzare SIP. \< Nome \> di dominio come nome dell'interfaccia del proxy di accesso Edge del connettore Cloud poiché questo record DNS è utilizzato da Microsoft 365 e Office 365.

- Un certificato per il perimetro esterno ottenuto da un'autorità di certificazione (CA) pubblica.

- Le regole del firewall per consentire il traffico tramite le porte necessarie sono state completate.

- Una connessione Internet per la macchina host e le macchine virtuali. Cloud Connector Scarica alcuni software da Internet; Pertanto, è necessario fornire le informazioni sui server gateway e DNS in modo che il computer host e la macchina virtuale del connettore Cloud siano in grado di connettersi a Internet e scaricare il software necessario.

- Un modulo di PowerShell remoto tenant installato nel computer host.

- Le credenziali di amministratore di Skype for business per eseguire Remote PowerShell.

    > [!IMPORTANT]
    > L'account Administrator non deve avere l'autenticazione a più fattori abilitata.

> [!NOTE]
> La distribuzione dei connettori cloud è supportata solo nella piattaforma Microsoft Hyper-V virtualizzata. Altre piattaforme, ad esempio i servizi Web di VMware e Amazon, non sono supportate.

> [!NOTE]
> Le indicazioni minime sull'hardware per l'esecuzione del connettore Cloud si basano sulla capacità hardware di base (core, MHz, Gigabyte e così via) con alcuni buffer per soddisfare le intangibili alterazioni delle prestazioni interrate nell'architettura di qualsiasi computer. Microsoft ha eseguito i test di carico più sfavorevoli su hardware disponibile commercialmente per soddisfare le indicazioni minime. La qualità multimediale e le prestazioni del sistema vengono verificate. I partner ufficiali del dispositivo Cloud Connector di Microsoft dispongono di implementazioni hardware specifiche del connettore Cloud su cui sono state verificate in modo indipendente le prestazioni e sono adeguate all'idoneità del proprio hardware per soddisfare i requisiti di carico e qualità.

> [!NOTE]
> I dispositivi prodotti da AudioCodes e Sonus dispongono di codice modificato ed eseguiti in Windows Server Standard Edition of servers. Questi dispositivi sono supportati.

## <a name="information-you-need-to-gather-before-deployment"></a>Informazioni necessarie per la raccolta prima della distribuzione
<a name="BKMK_PlanDeployment"> </a>

Prima di iniziare la distribuzione, è necessario determinare le dimensioni della distribuzione, i domini SIP che vengono serviti e le informazioni di configurazione per ogni sito PSTN che si intende distribuire. Per iniziare, è necessario:

- Identificare tutti i domini SIP che verranno serviti dalla distribuzione in base agli URI SIP in uso nella propria azienda.

- Determinare il numero di siti PSTN che è necessario distribuire.

- Assicurarsi di disporre dell'hardware necessario per supportare le quattro macchine virtuali che verranno installate per ogni versione di Cloud Connector.

Per ogni sito PSTN che si intende distribuire, è necessario eseguire le operazioni seguenti:

- Creare nomi per tutti i componenti di ogni accessorio Cloud Connector (vedere [Determine Deployment Parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)).

- Definire gli intervalli di porte (vedere [porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)).

- Creare record DNS esterni per il componente perimetrale (vedere [requisiti per la distribuzione](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)).

- Determinare i requisiti dei certificati per il componente perimetrale (vedere [Certificate Requirements](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)).

### <a name="ports-and-protocols"></a>Porte e protocolli
<a name="BKMB_Ports"> </a>

Quando si definiscono gli intervalli di porte multimediali, tenere presente quanto segue:

- I client utilizzano sempre l'intervallo di porte compreso tra 50000 e 50019 per il traffico multimediale: questo intervallo è predefinito in Skype for business online e non può essere modificato.

- Il componente Mediation, per impostazione predefinita, utilizzerà l'intervallo di porte da 49 152 a 57 500 per il traffico multimediale. Tuttavia, la connessione viene stabilita tramite firewall interno e, per motivi di sicurezza, è possibile limitare l'intervallo di porte nella topologia. Sarà necessario fino a 4 porte per chiamata. Se si desidera limitare il numero di porte tra il componente Mediation e il gateway PSTN, sarà inoltre necessario configurare l'intervallo di porte corrispondente sul gateway.

- È necessario distribuire il connettore Cloud in una rete perimetrale. Questo significa che si avranno due firewall:

  - Il primo firewall è esterno tra Internet e la rete perimetrale.

  - Il secondo firewall è interno tra la rete perimetrale e la rete interna.

    I client possono trovarsi in Internet o nella rete interna:

  - I client su Internet si connettono alla rete PSTN tramite il firewall esterno tramite il componente Edge.

  - I client della rete interna si connetteranno tramite il firewall interno al componente Mediation nella rete perimetrale, che consentirà di connettere il traffico al gateway SBC o PSTN.

    Questo significa che è necessario aprire le porte in entrambi i firewall.

Nelle tabelle seguenti vengono descritti gli intervalli di porte e porta per i firewall esterni e interni.

In questa tabella vengono illustrati gli intervalli di porte e porta per l'abilitazione delle comunicazioni tra i client nella rete interna e il componente Mediation:

**Firewall interno**



|**IP di origine**|**IP destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Componente di mediazione del connettore Cloud  <br/> |SBC/gateway PSTN  <br/> |Qualsiasi  <br/> |TCP 5060\*\*  <br/> |
|SBC/gateway PSTN  <br/> |Componente di mediazione del connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 5068/TLS 5067  <br/> |
|Componente di mediazione del connettore Cloud  <br/> |SBC/gateway PSTN  <br/> |UDP 49 152-57 500  <br/> |Qualsiasi\*\*\*  <br/> |
|SBC/gateway PSTN  <br/> |Componente di mediazione del connettore Cloud  <br/> |Qualsiasi\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|Componente di mediazione del connettore Cloud  <br/> |Client interni  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50019  <br/> Optional  <br/> |
|Componente di mediazione del connettore Cloud  <br/> |Client interni  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50019  <br/> |
|Client interni  <br/> |Componente di mediazione del connettore Cloud  <br/> |TCP 50000-50019  <br/> |TCP 49 152-57 500\*  <br/> |
|Client interni  <br/> |Componente di mediazione del connettore Cloud  <br/> |UDP 50000-50019  <br/> |UDP 49 152-57 500\*  <br/> |

\*Questo è l'intervallo di porte predefinito del componente Mediation. Per un flusso di chiamata ottimale, sono necessarie quattro porte per chiamata.

\*\*Questa porta deve essere configurata nel gateway SBC/PSTN. 5060 è un esempio. È possibile configurare altre porte sul gateway SBC/PSTN.

\*\*\*Tenere presente che è inoltre possibile limitare l'intervallo di porte sul SBC/gateway, se consentito dal produttore di SBC/gateway.

Per motivi di sicurezza, è possibile limitare l'intervallo di porte per il componente Mediation utilizzando il cmdlet [Set-CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) .

Ad esempio, il comando seguente consente di limitare il numero di porte che il componente Mediation utilizzerà per il traffico multimediale su 50 000-51 000 per l'audio (in e out). Il componente Mediation sarà in grado di gestire le chiamate simultanee 250 con questa configurazione. Tenere presente che è inoltre possibile limitare questo intervallo nel gateway SBC/PSTN:

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

Per recuperare il nome del componente Mediation e visualizzare le porte predefinite, è possibile utilizzare il cmdlet [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) come indicato di seguito:

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

Nella tabella seguente sono riportati gli intervalli di porte e porta per l'abilitazione della comunicazione tra il componente Edge del connettore Cloud e il firewall esterno. In questa tabella viene visualizzata una raccomandazione minima.

In questo caso, tutto il traffico multimediale su Internet scorrerà tramite il server Edge online come indicato di seguito: punto finale dell'utente-- \> Edge online-- \> Edge del connettore Cloud:

**Firewall esterno-configurazione minima**



|**IP di origine**|**IP destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |Porta TCP 80  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |UDP 53  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 53  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore Cloud  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore Cloud  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 50000-59.999  <br/> |TCP 443  <br/> |

La tabella successiva indica le porte e gli intervalli di porte per l'abilitazione della comunicazione tra il componente Edge del connettore Cloud e il firewall esterno. In questa tabella viene illustrata la soluzione consigliata.

In questo caso, tutto il traffico multimediale per il punto finale in Internet può fluire direttamente sul componente Edge del connettore Cloud. Il percorso multimediale sarà Edge del connettore Cloud del punto finale dell'utente \> .

> [!NOTE]
> Questa soluzione non funzionerà se il punto finale dell'utente si trova dietro a un NAT simmetrico.

**Firewall esterno-configurazione consigliata**


|**IP di origine**|**IP destinazione**|**Porta di origine**|**Porta di destinazione**|
|:-----|:-----|:-----|:-----|
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP (MTLS) 5061  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |Porta TCP 80  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |UDP 53  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |Qualsiasi  <br/> |TCP 53  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 50000-59.999  <br/> |Qualsiasi  <br/> |
|Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |UDP 3478; UDP 50000-59.999  <br/> |Qualsiasi  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |TCP 443; TCP 50000-59.999  <br/> |
|Qualsiasi  <br/> |Interfaccia esterna perimetrale del connettore Cloud  <br/> |Qualsiasi  <br/> |UDP 3478; UDP 50.000-59.999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>Requisiti di connettività Internet host
<a name="BKMB_Ports"> </a>

Il computer host deve essere in grado di raggiungere risorse esterne per installare, aggiornare e gestire correttamente il connettore Cloud. Nella tabella seguente vengono riportate le destinazioni e le porte necessarie tra il computer host e le risorse esterne.

|Direction  <br/> |IP origine  <br/> |IP destinazione  <br/> |Porta di origine  <br/> |Porta di destinazione  <br/> |Protocollo  <br/> |Scopo  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|In uscita  <br/> |IPs host del connettore Cloud  <br/> |qualsiasi  <br/> |qualsiasi  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|In uscita  <br/> |IPs host del connettore Cloud  <br/> |qualsiasi  <br/> |qualsiasi  <br/> |80, 443  <br/> |TCP  <br/> |Elenco di revoche di certificati (CRL)  <br/> |
|In uscita  <br/> |IPs host del connettore Cloud  <br/> |qualsiasi  <br/> |qualsiasi  <br/> |80, 443  <br/> |TCP  <br/> |Aggiornamento del connettore Cloud  <br/> Skype for Business Online  <br/> PowerShell per amministratori  <br/> Windows Update  <br/> |

Se sono necessarie regole più restrittive, fare riferimento ai seguenti URL di whitelist:

- [URL dell'elenco di revoche di certificati](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) negli [URL e negli intervalli di indirizzi IP di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)

- Windows Update: [come configurare un firewall per gli aggiornamenti software](https://technet.microsoft.com/library/bb693717.aspx)

- PowerShell per amministratori di Skype for business online: \* . online.Lync.com

    Se è necessaria l'esclusione di un proxy per questa destinazione, sarà necessario aggiungerla all'elenco di esclusione di WinHTTP.

- Aggiornamento del connettore Cloud: [Centro download](https://aka.ms/CloudConnectorInstaller) [https://go.microsoft.com](https://go.microsoft.com) e[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Risoluzione dei nomi DNS per il componente perimetrale
<a name="BKMB_Ports"> </a>

Il componente perimetrale deve risolvere i nomi esterni dei servizi Microsoft 365 o Office 365 e i nomi interni di altri componenti del connettore Cloud.

Ogni componente perimetrale è un computer multihomed con interfacce esterne e interne. Il connettore Cloud distribuisce i server DNS sul componente del controller di dominio all'interno della rete perimetrale. È possibile puntare server perimetrale al server DNS all'interno del perimetro per tutte le risoluzioni nome, ma è necessario abilitare il server DNS del connettore Cloud per risolvere i nomi esterni impostando una zona DNS contenente uno o più record A DNS per le query esterne che fanno riferimento alle ricerche dei nomi ad altri server DNS pubblici.

Nel file ini, se si imposta il nome FQDN per i gateway dallo stesso spazio di dominio del dominio SIP, l'area autorevole per questo dominio SIP verrà creata nel server DNS all'interno del perimetro. Se il server perimetrale punta a questo server DNS per risolvere i nomi, Edge non risolverà mai la _sipfederationtls. \< \>record DNS dominio, necessario per il flusso di chiamata. In questo caso, Microsoft consiglia di fornire un server DNS nell'interfaccia esterna perimetrale per risolvere le ricerche dei nomi Internet e ogni componente perimetrale deve utilizzare un file HOST per risolvere altri nomi di componenti del connettore Cloud in indirizzi IP.

> [!NOTE]
> Per motivi di sicurezza, si consiglia di non puntare il server DNS del connettore Cloud ai server interni nel dominio di produzione per la risoluzione dei nomi.

### <a name="determine-deployment-parameters"></a>Determinare i parametri di distribuzione
<a name="BKMK_SiteParams"> </a>

Per prima cosa, è necessario definire i seguenti parametri di distribuzione comuni:


|**Elemento**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Domini SIP  <br/> |URI SIP in uso da parte degli utenti dell'azienda. Fornire tutti i domini SIP che verranno serviti dalla distribuzione. È possibile disporre di più di un dominio SIP.  <br/> ||
|Numero di siti PSTN  <br/> |Il numero di siti PSTN che verranno distribuiti.  <br/> ||

Per ogni sito PSTN che si intende distribuire, è necessario raccogliere le informazioni seguenti prima di iniziare la distribuzione. Sarà necessario fornire queste informazioni quando si aggiorna il file CloudConnector. ini.

Quando si configurano le informazioni sul gateway, tenere presente quanto segue:

- Se si dispone di un solo gateway, rimuovere la sezione nel file. ini per il secondo gateway. Se sono presenti più di due gateway, seguire il formato esistente per aggiungerne uno nuovo.

- Verificare che l'indirizzo IP e la porta del gateway siano corretti.

- Per supportare l'HA a livello di gateway PSTN, mantenere il gateway secondario o aggiungere altri gateway.

Optional Per limitare i numeri delle chiamate in uscita, aggiornare il valore LocalRoute.



|**Parametri del sito**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Nome di dominio della macchina virtuale  <br/> |Nome di dominio per i componenti interni del connettore Cloud. Questo dominio deve essere diverso dal dominio di produzione. Il nome deve essere lo stesso in tutti gli elettrodomestici del connettore Cloud.  <br/> Nome nel file. ini: "VirtualMachineDomain"  <br/> |il dominio. local è preferibile.  <br/> |
|Nome del controller di dominio del connettore Cloud  <br/> |Nome del controller di dominio.  <br/> Nome nel file con estensione ini: "nomeserver"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> |
|IP/subnet mask del controller di dominio cloud Connector  <br/> |Indirizzo IP del controller di dominio.  <br/> Nome nel file. ini: "IP"  <br/> ||
|FQDN del servizio Microsoft 365 o Office 365 online  <br/> |Deve essere l'impostazione predefinita nella maggior parte dei casi per l'istanza di Microsoft 365 o di Office 365 a livello mondiale.  <br/> Nome nel file. ini: "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |Nome del sito di Skype for business; ad esempio, Seattle.  <br/> Nome nel file. ini: "nomesito"  <br/> Per il rilascio 1.4.1 e versioni successive, il nome del sito deve essere diverso per ogni sito e il nome deve corrispondere al sito PSTN, se esiste, definito in Microsoft 365 o Office 365. Si noti che i siti PSTN verranno creati automaticamente durante la registrazione del primo dispositivo in un sito.  <br/> ||
|HardwareType  <br/> Rilascio 1.4.1 e versioni successive  <br/> |Tipo di hardware. Il valore predefinito è Normal. È anche possibile impostare su Minimum.  <br/> ||
|Country Code  <br/> |Codice paese per la composizione.  <br/> Nome nel file. ini: "CountryCode"  <br/> ||
|Città  <br/> |Città (facoltativa).  <br/> Nome nel file. ini: "City"  <br/> ||
|Stato  <br/> |Stato (facoltativo).  <br/> Nome nel file. ini: "stato"  <br/> ||
|Indirizzo IP di base VM  <br/> |L'indirizzo IP della VM di base temporanea che verrà utilizzato per creare la VHDX per tutte le macchine virtuali del connettore Cloud. Questo indirizzo IP deve trovarsi nella stessa subnet della rete aziendale perimetrale definita nel passaggio successivo e richiede l'accesso a Internet. Assicurarsi di definire il gateway predefinito aziendale e il DNS che può essere instradato su Internet.  <br/> Nome nel file. ini: "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> Rilascio 1.4.1 e versioni successive  <br/> |L'indirizzo di Windows Server Update Services (WSUS), ovvero un server Intranet per ospitare gli aggiornamenti da Microsoft Update.  <br/> È possibile lasciare vuoto se WSUS non è necessario.  <br/> ||
|Subnet mask per la rete interna  <br/> |Il connettore cloud configura una rete IP per la comunicazione interna tra i componenti dei connettori cloud. È inoltre necessario che Edge sia connesso a un'altra subnet che consenta la connettività Internet.  <br/> Nome nel file. ini: "CorpnetIPPrefixLength" in "parametri per un pool di rete VM"  <br/> ||
|Subnet mask per la rete esterna  <br/> |Per la rete esterna del componente perimetrale.  <br/> Nome nel file. ini: "InternetIPPrefix" in "parametri per un pool di rete VM"  <br/> ||
|Cambia nome per la rete interna  <br/> |Nome per l'opzione che verrà utilizzata per la rete del connettore cloud interno.  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file. ini: "CorpnetSwitchName" in "parametri per un pool di rete VM  <br/> ||
|Cambia nome per la rete esterna  <br/> |Nome per l'opzione che verrà utilizzata per la rete di connettori cloud esterni.  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file. ini: "InternetSwitchName" in "parametri per un pool di rete VM  <br/> ||
|Gateway predefinito per la rete interna  <br/> |Questo gateway deve fornire l'accesso a Internet (Internet richiede anche l'impostazione del server DNS) e sarà configurato su interfacce interne dei componenti del connettore Cloud.  <br/> Nome nel file. ini: "CorpnetDefaultGateway" in "parametri per un pool di rete VM  <br/> ||
|Gateway predefinito per l'interfaccia esterna del componente perimetrale  <br/> |Verrà configurato nell'interfaccia esterna del componente perimetrale.  <br/> Nome nel file. ini: "InternetDefaultGateway" in "parametri per un pool di rete VM  <br/> ||
|Server DNS per la rete interna  <br/> |Verrà configurato nell'interfaccia interna della macchina virtuale temporanea. Deve fornire la risoluzione del nome per i nomi Internet. Senza fornire un server DNS, la connessione a Internet avrà esito negativo e la distribuzione non verrà completata.  <br/> Nome nel file. ini: "CorpnetDNSIPAddress" in "parametri per un pool di rete VM  <br/> ||
|Server DNS per l'interfaccia esterna del componente perimetrale  <br/> |Verrà configurato sull'interfaccia esterna del server perimetrale.  <br/> Nome nel file. ini: "InternetDNSIPAddress" in "parametri per un pool di rete VM  <br/> ||
|Nome dell'opzione di gestione  <br/> |L'opzione di gestione è un'opzione temporanea che verrà creata automaticamente e che verrà utilizzata per la configurazione del connettore cloud durante la distribuzione. Verrà disconnessa automaticamente dopo la distribuzione. Deve essere una subnet diversa da qualsiasi altra rete utilizzata in Cloud Connector.  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file. ini: "ManagementSwitchName" in "parametri per un pool di rete VM  <br/> ||
|Indirizzo della subnet di gestione/subnet mask  <br/> |La subnet di gestione è una subnet temporanea che verrà creata automaticamente e che verrà utilizzata per la configurazione del connettore cloud durante la distribuzione. Verrà rimossa automaticamente dopo la distribuzione. Deve essere una subnet diversa da qualsiasi altra rete utilizzata in Cloud Connector.  <br/> Nomi nel file. ini: "ManagementIPPrefix" e "ManagementIPPrefixLength" in "parametri per un pool di rete VM  <br/> ||
|Computer dell'archivio di gestione centrale (CMS)  <br/> |FQDN singolo utilizzato per l'archivio di gestione centrale (CMS). Il nome del dominio Active Directory verrà utilizzato per generare l'FQDN.  <br/> Nome nel file. ini: "nomeserver" in "parametri per il servizio di gestione centrale primario  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> (Nome pool CMS = nome server)  <br/> |
|Indirizzo IP del computer CMS  <br/> |Indirizzo IP per il server CMS (interno in rete perimetrale).  <br/> Nome nel file INI: "IP" in "parametri per il servizio di gestione centrale primario  <br/> ||
|Nome condivisione file  <br/> |Nome condivisione file da creare nel server CMS per i dati di replica di Skype for business (ad esempio, CmsFileStore).  <br/> Nella maggior parte dei casi è possibile utilizzare il valore suggerito predefinito.  <br/> Nome nel file. ini: "CmsFileStore" in "parametri per il servizio di gestione centrale primario  <br/> ||
|Nome del pool di Mediation Component  <br/> |Nome del pool del componente Mediation. Immettere solo il nome NetBIOS. Il nome del dominio Active Directory verrà utilizzato per generare l'FQDN.  <br/> Nome nel file. ini: "PoolName" in "parametri per un pool di Mediation Server"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> |
|Nome del componente Mediation  <br/> |Nome componente del componente Mediation 1. Immettere solo il nome NetBIOS. Il nome del dominio Active Directory verrà utilizzato per generare l'FQDN.  <br/> Nome nel file. ini: "nomeserver" in "parametri per un pool di Mediation Server"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> |
|Indirizzo IP del computer componente Mediation  <br/> |IP corpnet interno per il componente Mediation (interno in rete perimetrale).  <br/> Nome nel file. ini: "IP" in "parametri per un pool di Mediation Server"  <br/> ||
|Nome interno del pool di server perimetrali  <br/> |Nome del pool del componente perimetrale. Immettere solo il nome NetBIOS. Il nome del dominio Active Directory verrà utilizzato per generare l'FQDN.  <br/> Nome nel file. ini: "InternalPoolName" in "parametri per un pool di server perimetrali"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> |
|Nome interno del server perimetrale  <br/> |Nome del componente del componente perimetrale. Immettere solo il nome NetBIOS. Il nome del dominio Active Directory verrà utilizzato per generare l'FQDN.  <br/> Nome nel file. ini: "InternalServerName" in "parametri per un pool di server perimetrali"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> |
|IP interno del server perimetrale  <br/> |IP della rete perimetrale interna del componente Edge per comunicare con altri componenti del connettore Cloud.  <br/> Nome nel file. ini: "InternalServerIPs" in "parametri per un pool di server perimetrali"  <br/> ||
|Nome esterno del pool di accesso  <br/> |Nome del server perimetrale di accesso; ad esempio, AP. Questo nome deve corrispondere al nome specificato per il certificato SSL. Immettere solo il nome NetBIOS. Il nome di dominio SIP verrà utilizzato per generare l'FQDN. Un nome di pool esterno verrà utilizzato per tutti i componenti perimetrali nel pool. Un pool di accesso Edge è necessario per ogni sito PSTN.  <br/> Nome nel file. ini: "ExternalSIPPoolName" in "parametri per un pool di server perimetrali"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> "SIP" è riservato e pertanto non può essere utilizzato come nome.  <br/> Il nome FQDN generato deve corrispondere al nome specificato per il certificato SSL.  <br/> |
|IP esterno di Access Edge  <br/> |IP esterno del componente perimetrale-IP pubblico se non è disponibile alcun NAT o IP tradotto (specificare entrambi gli indirizzi se sono mappati).  <br/> Nome nel file. ini: "ExternalSIPIPs" in "parametri per un pool di server perimetrali"  <br/> ||
|Nome del relay multimediale  <br/> |Nome del bordo di inoltro multimediale audio video; ad esempio, MR. Un nome di pool esterno verrà utilizzato per tutti i componenti perimetrali in un pool. Per ogni sito PSTN è necessario un pool di inoltro Media Edge.  <br/> Nome nel file. ini: "ExternalMRFQDNPoolName" in "parametri per un pool di server perimetrali"  <br/> |Il valore deve essere inferiore o pari a 15 caratteri. Immettere solo il nome NetBIOS.  <br/> |
|IP esterno del server perimetrale di inoltro multimediale  <br/> |Attualmente è supportato un solo IP, quindi questo è lo stesso IP di Access Edge, pubblico o IP mappato (specificare entrambi gli indirizzi se sono mappati). Può essere lo stesso indirizzo del componente perimetrale IP esterno del server perimetrale di accesso. Nota Se Edge è dietro NAT, è necessario specificare anche il valore per il parametro Next.  <br/> Nome nel file. ini: "ExternalMRIPs" in "parametri per un pool di server perimetrali"  <br/> ||
|Indirizzo IP esterno del server perimetrale di inoltro multimediale (se Edge è dietro NAT)  <br/> |Se il server perimetrale è dietro NAT, è inoltre necessario specificare l'indirizzo pubblico del dispositivo NAT.  <br/> Nome nel file. ini: "ExternalMRPublicIPs" in "parametri per un pool di server perimetrali"  <br/> ||
|Fare e modellare il gateway vocale 1  <br/> |Specificare la marca e il modello del gateway SBC/VoIP. Si noti che è possibile connettere un dispositivo o un trunk SIP dall'elenco dei dispositivi testati all'indirizzo [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) .  <br/> ||
|Fare e modellare il gateway vocale 2 (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Specificare la marca e il modello del gateway vocale. Si noti che è possibile connettere un dispositivo all'elenco dei dispositivi testati all'indirizzo [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP) .  <br/> ||
|Nome gateway vocale 1  <br/> |Utilizzato per generare l'FQDN del computer con dominio di Active Directory. Obbligatorio se TLS verrà utilizzato tra il componente Mediation e il gateway vocale. Se non si prevede di utilizzare il nome di dominio completo (FQDN), ad esempio, TLS non è necessario o il gateway vocale non supporta la connessione utilizzando FQDN (solo IP), specificare.  <br/> ||
|Nome gateway vocale 2 (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Utilizzato per generare l'FQDN del computer con dominio di Active Directory. Obbligatorio se TLS verrà utilizzato tra il componente Mediation e il gateway vocale. Se non si prevede di utilizzare il nome di dominio completo (FQDN), ad esempio, TLS non è necessario o il gateway vocale non supporta la connessione utilizzando FQDN (solo IP), specificare.  <br/> ||
|Indirizzo IP del gateway vocale 1  <br/> |Indirizzo IP del gateway vocale.  <br/> ||
|Indirizzo IP del gateway vocale 2 (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Indirizzo IP del gateway vocale.  <br/> ||
|Gateway vocale 1 porta # (copiare questa riga se si dispone di più di 2 gateway)  <br/> |Porta che il trunk SIP del gateway vocale ascolterà, ad esempio 5060.  <br/> ||
|Porta Voice Gateway 2 #  <br/> |Porta che il trunk SIP del gateway vocale ascolterà, ad esempio 5060.  <br/> ||
|Protocollo Voice Gateway 1 per il traffico SIP  <br/> |TCP o TLS.  <br/> ||
|Protocollo Voice Gateway 2 per il traffico SIP (copiare questa riga se si dispone di più di 2 gateway)  <br/> |TCP o TLS.  <br/> ||
|Intervallo di porte multimediali esterne per il traffico da e verso il componente perimetrale  <br/> |Intervallo di porte TCP/UDP per il traffico multimediale da e verso l'interfaccia esterna del server perimetrale. Deve iniziare sempre da 50 000. Per ulteriori informazioni, vedere "porte e protocolli".  <br/> |50000-59 999  <br/> |
|Intervallo di porte multimediali per comunicare da/verso il componente Mediation tramite il firewall interno  <br/> |Intervallo di porte UDP che verrà utilizzato dal componente Mediation per comunicare con i client e i gateway (Raccomandazione 4 porte per chiamata).  <br/> ||
|Intervallo di porte multimediali per comunicare con/dal client Skype for business tramite firewall interno  <br/> |A scopo di pianificazione, non è possibile modificarlo. Le porte devono essere aperte nel firewall interno per comunicare tra i client Skype for business all'interno della rete interna e con il componente Mediation.  <br/> |50 000-50 019  <br/> |
|Password del certificato pubblico  <br/> |Deve essere fornito nello script.  <br/> ||
|Password di amministratore della modalità provvisoria  <br/> Solo versione 1.4.2  <br/> |Password di amministratore della modalità provvisoria per il dominio CC interno.  <br/> ||
|Password di amministratore del dominio del connettore Cloud  <br/> Solo versione 1.4.2  <br/> |Password per l'amministratore del dominio del connettore Cloud (diverso dal dominio di produzione). Nome utente è Administrator. Non è possibile modificare il nome utente.  <br/> ||
|Password amministratore macchine virtuali  <br/> Solo versione 1.4.2  <br/> |Utilizzato per configurare la rete di gestione durante la distribuzione.  <br/> Nome utente è Administrator. Non è possibile modificare il nome utente.  <br/> ||
|CABackupFile  <br/> Versione 2,0 e versioni successive  <br/> |Utilizzato per salvare il servizio autorità di certificazione dal server Active Directory a un file durante la distribuzione di più dispositivi in un sito di connettori cloud. Assicurarsi di utilizzare la stessa password per tutti gli elettrodomestici all'interno di un sito del connettore Cloud per importare correttamente il file di backup CA su un nuovo dispositivo aggiunto.  <br/> ||
|CCEService  <br/> Versione 2,0 e versioni successive  <br/> |Utilizzato per il servizio di gestione Cloud Connector; ha bisogno dell'accesso alla directory del sito del connettore Cloud. Assicurarsi di utilizzare la stessa password per tutti gli elettrodomestici all'interno di un sito di connettori cloud.  <br/> ||
|Microsoft 365 o Office 365 tenant admin  <br/> | L'account viene utilizzato da Cloud Connector per l'aggiornamento e la gestione delle impostazioni del tenant per il connettore Cloud: <br/>  Versione 2,0 e versioni successive: credenziali per un account Microsoft 365 o Office 365 dedicato con diritti di amministratore di Skype for business. <br/>  Versioni precedenti a 2,0: credenziali per un account Microsoft 365 o Office 365 dedicato con diritti di amministratore tenant globali. <br/> ||
|Abilitare il supporto per i riferimenti  <br/> |In questo modo, verrà definito se il supporto SIP REFER è abilitato o disabilitato sulla configurazione trunk nell'IP/PBX. Il valore predefinito è True. Se il gateway IP/PBX supporta il supporto di riferimento, lasciarlo come vero. In caso contrario, questo valore deve essere impostato su false. Se non si è sicuri se il gateway supporta il riferimento, vedere [IP-PBX e gateway qualificati](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).   <br/> ||
|EnableFastFailoverTimer  <br/> Versione 2,0 e versioni successive  <br/> |Con il valore predefinito "true", se le chiamate in uscita non rispondono al gateway entro 10 secondi, verranno instradate al successivo gateway disponibile. Se non sono presenti ulteriori trunk, la chiamata verrà rilasciata automaticamente.  <br/> Tuttavia, in un'organizzazione con reti lente e risposte del gateway o quando il processo di creazione di chiamate richiede più di 10 secondi, ciò potrebbe causare la caduta inutilmente delle chiamate.  <br/> Quando si effettuano chiamate ad alcuni paesi, ad esempio Emirati Arabi Uniti o Afghanistan, il processo di definizione delle chiamate può richiedere più di 10 secondi. Se si verificano problemi simili, è necessario modificare il valore su false. Non dimenticare di modificare l'impostazione corrispondente nell'SBC o nel gateway connesso.  <br/> Il valore può essere true o false. Il valore predefinito è True.  <br/> ||
|ForwardCallHistory  <br/> Versione 2,0 e versioni successive  <br/> | Questo parametro viene utilizzato per abilitare le intestazioni SIP utilizzate per segnalare il chiamante iniziale nello squillo simultaneo, nell'inoltro di chiamata e negli scenari di trasferimento delle chiamate. Se si imposta il parametro su true, verranno attivate due intestazioni SIP: <br/>  Cronologia-informazioni <br/>  A cui viene fatto riferimento <br/>  L'intestazione History-info viene utilizzata per il reindirizzamento delle richieste SIP e "fornisce un meccanismo standard per l'acquisizione delle informazioni sulla cronologia delle richieste per consentire una vasta gamma di servizi per le reti e gli utenti finali" ([RFC 4244-Section 1,1](http://www.ietf.org/rfc/rfc4244.txt)). Per le interfacce trunk del connettore Cloud, viene utilizzato in Simulring e negli scenari di inoltro di chiamata.  <br/>  Il valore può essere true o false. Il valore predefinito è False. <br/> ||
|Inoltra PAI  <br/> Versione 2,0 e versioni successive  <br/> |PAI è un'estensione privata da SIP che consente ai server SIP di affermare l'identità degli utenti autenticati. Per il provider trunk SIP, PAI può essere utilizzato per scopi di fatturazione nel caso in cui non siano presenti intestazioni di cronologia e di riferimento. Quando si Abilita l'inoltro P-Asserted-Identity nella configurazione, il Mediation Server invierà le intestazioni PAI con SIP &amp; Tel URI dal connettore Cloud sul trunk SIP. Il Mediation Server invierà le intestazioni PAI con &amp; i numeri E. 164 di Tel URI ricevuti solo sul connettore del trunk SIP su cloud. Il Mediation Server invierà anche eventuali intestazioni di privacy ricevute in entrambe le direzioni. Se la richiesta SIP inviata dal Mediation Server include un'intestazione di privacy del modulo-"privacy: ID" in combinazione con l'intestazione PAI, l'identità asserita deve essere mantenuta privata all'esterno del dominio di attendibilità della rete.  <br/> Il valore può essere true o false. Il valore predefinito è False.  <br/> ||

### <a name="certificate-requirements"></a>Requisiti per i certificati
<a name="BKMK_Certs"> </a>

Ogni componente perimetrale richiede un certificato rilasciato da un'autorità di certificazione pubblica. I certificati devono disporre di una chiave privata esportabile da copiare tra i componenti perimetrali. Per soddisfare i requisiti dei certificati, è necessario decidere tra le opzioni seguenti e fornire il nome soggetto (SN) e il nome alternativo del soggetto (SAN) per il certificato.

 **Se si dispone di un singolo dominio SIP:**

- **Opzione 1.** Il nome del soggetto deve contenere il nome del pool assegnato ai componenti del server perimetrale. Si noti che il nome del soggetto non può essere sip.sipdomain.com perché questo nome è riservato al componente online Skype for Business Edge. SAN deve contenere sip.sipdomain.com e il nome del pool di Access Edge:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **Opzione 2.** Se si desidera utilizzare un singolo certificato con caratteri jolly su tutti i server del pool perimetrale distribuiti, è possibile utilizzare una voce di tipo SAN jolly di \* . SipDomain.com invece del nome del pool di Edge nel certificato. Il nome del soggetto può essere il nome del pool di Access Edge di tutti i pool di server perimetrali distribuiti:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> Non è necessario creare una voce DNS esterna per SIP. \< SipDomain \> . com poiché questo nome appartiene alla distribuzione di Microsoft 365 o di Office 365.

> [!NOTE]
> Se si desidera utilizzare un solo certificato per tutti i pool di server perimetrali distribuiti nell'organizzazione e non è possibile utilizzare un certificato con caratteri jolly come definito nell'opzione 2, sarà necessario includere il nome di dominio completo per tutti i pool di server perimetrali distribuiti nel cognome del certificato.

 **Se si dispone di più domini SIP:**

Sarà necessario aggiungere sip.sipdomain.com per ogni dominio SIP e il nome dei pool di Access Edge per dominio (può essere un pool fisico ma con nomi diversi). Di seguito è riportato un esempio di voci SN e SAN in uno scenario di dominio SIP multipli:

- **Opzione 1.** Il nome del soggetto deve contenere il nome del pool assegnato per i componenti perimetrali. Si noti che il nome del soggetto non può essere sip.sipdomain.com perché questo nome è riservato al componente online Skype for Business Edge. SAN deve contenere sip.sipdomain.com e il nome del pool di Access Edge:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>Opzione 2.</strong> Se si desidera utilizzare un singolo certificato con caratteri jolly su tutti i server del pool perimetrale distribuiti, è possibile utilizzare una voce di tipo SAN jolly di \* . SipDomain.com invece del nome del pool di Edge nel certificato. Il nome del soggetto può essere il nome del pool di Access Edge di tutti i pool di server perimetrali distribuiti:

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> Non è necessario creare una voce DNS esterna per SIP. \< SipDomain \> . com poiché questo nome appartiene alla distribuzione di Microsoft 365 o di Office 365.

Ai fini della distribuzione, è possibile utilizzare la tabella seguente:

|**Opzione**|**Descrizione**|**Note**|
|:-----|:-----|:-----|
|Quale opzione verrà utilizzata per la distribuzione?  <br/> |Opzione 1 o 2  <br/> ||
|SN  <br/> |Fornire lo SN per il certificato  <br/> ||
|SAN  <br/> |Fornisce la SAN per il certificato  <br/> ||

Se si utilizza TLS tra il gateway e il Mediation Server, sarà necessario ottenere il certificato radice o la catena di certificati completi per il certificato assegnato al gateway.

## <a name="dial-plan-considerations"></a>Considerazioni sul dial plan
<a name="BKMK_DailPlan"> </a>

Il connettore Cloud richiede l'utilizzo di un dial plan online. Per ulteriori informazioni su come configurare un dial plan online, vedere [What are dial plans?](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>Considerazioni sulla disponibilità elevata
<a name="BKMK_HA"> </a>

Quando si distribuisce Cloud Connector Edition per la disponibilità elevata, è necessario distribuire almeno due dispositivi che fungono da backup. Ogni accessorio è costituito da quattro componenti: Edge, Mediation, Central Management store (CMS) e controller di dominio.

In generale, se un componente all'interno di un dispositivo viene interrotto, Cloud Connector Edition può continuare a gestire le chiamate, ma è necessario tenere in considerazione quanto segue:

- **Considerazioni sui componenti di Mediation, CMS e controller di dominio**

    Si supponga che il componente CMS o controller di dominio in un dispositivo venga premuto. L'accessorio è ancora in grado di gestire le chiamate in ingresso e in uscita, ma se si riavvia un componente di mediazione quando il componente CMS o il controller di dominio non è raggiungibile, la mediazione non funzionerà. Lo stesso vale per il riavvio del componente CMS quando il controller di dominio non è in esecuzione.

    **Raccomandazione:** Prima di riavviare i componenti, verificare la disponibilità degli altri componenti nell'accessorio.

- **Considerazioni sui componenti perimetrali**

    Se il componente perimetrale in un dispositivo non è disponibile, il comportamento per le chiamate in ingresso e in uscita differirà come indicato di seguito:

  - **Chiamata in uscita**: una chiamata da un utente in Internet a una rete PSTN.

    Il meccanismo di distribuzione delle chiamate nel cloud identificherà che un componente perimetrale è inverso verso il basso e instraderà tutte le chiamate a un altro dispositivo, per cui la chiamata in uscita avrà esito positivo.

  - **Chiamata in ingresso**: una chiamata dalla rete PSTN a un utente che si trova in una rete locale o in Internet.

     Se il componente perimetrale dell'accessorio che ha ricevuto la chiamata non funziona, le chiamate in ingresso a questo dispositivo non avranno esito positivo perché il componente Mediation non è in grado di reindirizzare la chiamata al componente perimetrale nell'altro dispositivo.

    **Raccomandazione:** Disporre di un sistema di monitoraggio sul posto. Dopo aver identificato un malfunzionamento del componente perimetrale, arrestare tutti i componenti dell'accessorio in cui il componente perimetrale non è disponibile.

## <a name="cloud-connector-media-flow"></a>Flusso multimediale del connettore Cloud
<a name="BKMK_MediaFlow"> </a>

I diagrammi seguenti delineano il flusso di una chiamata in uscita e in ingresso tramite Cloud Connector Edition. Si tratta di informazioni utili per comprendere il modo in cui viene stabilita la connettività.

Nel primo diagramma un utente interno inserisce una chiamata in uscita come indicato di seguito:

1. Dave, un utente ospitato online, ma ora nella rete interna, inserisce una chiamata a un utente PSTN esterno.

2. Route del traffico SIP su Skype for business online.

3. Skype for business online esegue una ricerca inversa del numero. La ricerca di numeri inversi ha esito negativo perché questo numero non appartiene a nessuno nell'organizzazione di Skype for business.

4. La chiamata viene instradata al componente perimetrale (SIP e il flusso multimediale tramite Edge online prima; Il supporto passerà al componente Mediation tramite il firewall interno.

5. Se la route esiste, il componente perimetrale inoltra il traffico al componente Mediation nella rete perimetrale.

6. Il componente Mediation invia il traffico al gateway PSTN.

![Flusso multimediale in uscita per il connettore Cloud](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

Nel diagramma successivo un utente interno riceve una chiamata in ingresso come indicato di seguito:

1. Il gateway PSTN riceve una chiamata per l'utente Dave che è ospitato online, ma ora si trova nella rete interna.

2. Il traffico SIP viene instradato al componente Mediation.

3. Il componente Mediation invia il traffico SIP al componente perimetrale e quindi passa a Skype for business online.

4. Skype for business online esegue una ricerca inversa del numero e rileva che si tratta di un utente Dave.

5. La segnalazione SIP passa a tutti i punti di presenza di Dave.

6. Il traffico multimediale verrà stabilito tra il gateway e il componente Mediation e tra il componente Mediation e il punto finale.

![Flusso multimediale in ingresso per il connettore Cloud](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>Monitoraggio e risoluzione dei problemi
<a name="BKMK_Monitor"> </a>

Il meccanismo di monitoraggio e risoluzione dei problemi viene installato automaticamente con ogni accessorio Cloud Connector. Il meccanismo rileva gli eventi seguenti:

- Una o più macchine virtuali di un dispositivo di connessione cloud non sono connesse a un commutatore virtuale interno o Internet.

- Una o più macchine virtuali di un dispositivo di connessione cloud sono in stato salvato o interrotto.

- Servizi che non sono in esecuzione.

  Se viene rilevato uno degli eventi seguenti, l'intero dispositivo Cloud Connector viene svuotato e contrassegnato come non in linea per impedire il tentativo di stabilire le chiamate a un dispositivo malfunzionante. Funzionalità di ripristino automatico del connettore Cloud consente di ripristinare successivamente i servizi e contrassegnare l'accessorio come online. Se il ripristino automatico ha esito negativo per qualche motivo, vedere [risolvere i problemi relativi alla distribuzione dei connettori cloud](troubleshoot-your-cloud-connector-deployment.md).

  - Nella macchina virtuale dell'archivio di gestione centrale:

     - Agente di replica master di Skype for business

     - Agente Replicator di replica di Skype for business

  - Nella macchina virtuale Mediation Server:

     - Agente Replicator di replica di Skype for business

     - Mediation Server Skype for business

  - Nella macchina virtuale server perimetrale

     - Agente Replicator di replica di Skype for business

     -  Access Edge di Skype for Business Server

     - Edge audio/video di Skype for Business Server

     - Autenticazione audio/video di Skype for Business Server

     - Web Conferencing Edge di Skype for Business Server

- Regola in ingresso di Windows Firewall per "CS RTCSRV" sul server perimetrale, "CS RTCMEDSRV" sul Mediation è disabilitato.

Cloud Connector 2,1 e versioni successive supporta il Monitoring Cloud Connector tramite Operations Management Suite (OMS). Per ulteriori informazioni, vedere [Monitor Cloud Connector using Operations Management Suite (OMS)](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_MoreInfo"> </a>

Per altre informazioni, vedere gli argomenti seguenti:

- [Soluzioni di telefonia Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [Configurare e gestire Skype for Business Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [Pianificare il bypass multimediale in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)

- [Distribuire il bypass multimediale in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md)


