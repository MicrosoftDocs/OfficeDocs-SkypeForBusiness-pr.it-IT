---
title: Pianificare Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Scopri come l'instradamento diretto del Sistema telefonico Microsoft ti consente di connettere un controller SBC (Session Border Controller) fornito dal cliente al Sistema telefonico Microsoft.
ms.openlocfilehash: 77757cf76215dbed0b3ec572b5f1f57120551d86
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923828"
---
# <a name="plan-direct-routing"></a>Pianificare Instradamento diretto

> [!Tip]
> Guardare la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificarlo e su come distribuirlo: Routing [diretto in Microsoft Teams](https://aka.ms/teams-direct-routing)

L'instradamento diretto del Sistema telefonico Microsoft consente di collegare un controller SBC (Session Border Controller) fornito dal cliente al Sistema telefonico Microsoft.  Con questa funzionalità, ad esempio, è possibile configurare la connettività PSTN (Public Switched Telephone Network) locale con il client Microsoft Teams, come illustrato nel diagramma seguente: 

![Diagramma che illustra la configurazione della connettività PSTN locale](media/PlanDirectRouting1-PSTNwithTeams.png "Configurazione della connettività PSTN locale con il client Microsoft Teams")

  > [!NOTE]
  > Skype for Business online ti permette anche di associare un SBC fornito dal cliente, ma questa operazione richiede una distribuzione di Skype for Business Server locale o una versione speciale di Skype for Business, chiamata Cloud Connector, tra SBC e Microsoft Cloud. Questo scenario è noto come voce ibrida. Al contrario, il routing diretto consente una connessione diretta tra il servizio SBC supportato e Microsoft Cloud.

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online. Dopo che l'organizzazione ha eseguito l'aggiornamento a Teams, scopri come connettere la rete telefonica locale a Teams con [il routing diretto.](direct-routing-landing-page.md) 

Con il routing diretto, è possibile connettere il proprio SBC a quasi tutti i trunk di telefonia o interconnessi con apparecchiature PSTN di terze parti. Il routing diretto consente di: 

- Usa praticamente qualsiasi trunk PSTN con il Sistema telefonico Microsoft. 
- Configurare l'interoperabilità tra apparecchiature di telefonia di proprietà del cliente, ad esempio pbx (Private Branch Exchange), dispositivi analogici e Sistema telefonico Microsoft.

Microsoft offre anche soluzioni vocali all-in-the-cloud, come il Piano per chiamate. Tuttavia, una soluzione vocale ibrida potrebbe essere ottimale per l'organizzazione se: 

- Il Piano per chiamate Microsoft non è disponibile nel tuo Paese. 
- L'organizzazione richiede la connessione a dispositivi analogici, call center e così via di terze parti. 
- L'organizzazione ha già stipulato un contratto con un gestore PSTN.

L'instradamento diretto supporta anche gli utenti che dispongono della licenza aggiuntiva per il Piano per chiamate Microsoft. Per ulteriori informazioni, consulta [Sistema telefonico e Piani per chiamate.](calling-plan-landing-page.md) 

Con l'instradamento diretto, quando gli utenti partecipano a una conferenza pianificata, il numero di accesso esterno viene fornito dal servizio di audioconferenza Microsoft, che richiede una corretta licenza.  Quando si effettua una chiamata in uscita, il servizio di audioconferenza Microsoft effettua la chiamata utilizzando funzionalità di chiamata online, che richiedono una licenza appropriata. Se un utente non dispone di una licenza Microsoft Audioconferenza, la chiamata viene instradato attraverso l'instradamento diretto. Per altre informazioni, vedere [Riunioni online con Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
Pianificare la distribuzione del routing diretto è fondamentale per un'implementazione corretta. Questo articolo descrive i requisiti di infrastruttura e licenze e fornisce informazioni sulla connettività SBC: 

- [Requisiti dell'infrastruttura](#infrastructure-requirements)
- [Licenze e altri requisiti](#licensing-and-other-requirements)
- [Nomi di dominio SBC](#sbc-domain-names)
- [Certificato attendibile pubblico per SBC](#public-trusted-certificate-for-the-sbc)
- [Segnalazione SIP: FQDN](#sip-signaling-fqdns)
- [Segnalazione SIP: Porte](#sip-signaling-ports)
- [Traffico multimediale: intervalli di porta](#media-traffic-port-ranges)
- [Controller dei confini della sessione supportati](#supported-session-border-controllers-sbcs)

Per informazioni dettagliate sulla configurazione dell'instradamento diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura
Nella tabella seguente sono elencati i requisiti dell'infrastruttura per gli SBC, i domini e altri requisiti di connettività di rete supportati per la distribuzione del routing diretto:  

|Requisiti dell'infrastruttura|Sono necessarie le operazioni seguenti|
|:--- |:--- |
|Session Border Controller (SBC)|Un SBC supportato. Per altre informazioni, vedere [Gli SBC supportati.](#supported-session-border-controllers-sbcs)|
|Trunk di telefonia connessi a SBC|Uno o più trunk di telefonia connessi a SBC. Da un lato, SBC si connette al Sistema telefonico Microsoft tramite routing diretto. SBC può anche connettersi a entità di telefonia di terze parti, ad esempio PBX, adattatori per telefonia analoga e così via. Qualsiasi opzione di connettività PSTN connessa all'SBC funzionerà. Per la configurazione dei trunk PSTN in SBC, vedere i fornitori o provider di trunk SBC.|
|Organizzazione di Microsoft 365 o Office 365|Un'organizzazione di Microsoft 365 o Office 365 che si usa per ospitare gli utenti di Microsoft Teams e la configurazione e la connessione al servizio SBC.|
|Registrar utente|Gli utenti devono essere ospitati in Microsoft 365 o Office 365.<br/>Se l'azienda dispone di un ambiente Skype for Business o Lync locale con connettività ibrida a Microsoft 365 o Office 365, non è possibile abilitare la voce in Teams per un utente ospitata in locale.<br/><br/>Per controllare il registrar di un utente, utilizza il seguente cmdlet di PowerShell per Skype for Business online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>L'output del cmdlet dovrebbe mostrare:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domini|Uno o più domini aggiunti alle organizzazioni Microsoft 365 o Office 365.<br/><br/>Si noti che non è possibile usare il dominio \* predefinito, onmicrosoft.com, creato automaticamente per il tenant.<br/><br/>Per visualizzare i domini, puoi utilizzare il seguente cmdlet di PowerShell di Skype for Business Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Per altre informazioni sui domini e sulle organizzazioni di Microsoft 365 o Office 365, vedere [Le domande frequenti sui domini.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Indirizzo IP pubblico per SBC|Un indirizzo IP pubblico che può essere usato per connettersi al servizio SBC. In base al tipo di SBC, SBC può usare NAT.|
|Nome di dominio completo per SBC|Un FQDN per SBC, dove la parte relativa al dominio dell'FQDN è uno dei domini registrati nell'organizzazione di Microsoft 365 o Office 365. Per altre informazioni, vedere i [nomi di dominio SBC.](#sbc-domain-names)|
|Voce DNS pubblica per SBC |Una voce DNS pubblica che mappa l'FQDN SBC all'indirizzo IP pubblico. |
|Certificato attendibile pubblico per SBC |Un certificato per il servizio SBC da usare per tutte le comunicazioni con il routing diretto. Per altre informazioni, vedere [Certificato attendibile pubblico per SBC.](#public-trusted-certificate-for-the-sbc)|
|Punti di connessione per il routing diretto |I punti di connessione per il routing diretto sono i tre FQDN seguenti:<br/><br/>`sip.pstnhub.microsoft.com` – L'FQDN globale deve essere provato prima di tutto.<br/>`sip2.pstnhub.microsoft.com` – FQDN secondario, mappato geograficamente alla seconda area geografica di priorità.<br/>`sip3.pstnhub.microsoft.com` - FQDN terziario, geograficamente associato alla terza area geografica di priorità.<br/><br/>Per informazioni sui requisiti di configurazione, consulta [Segnalazione SIP: FQDN.](#sip-signaling-fqdns)|
|Porte e indirizzi IP del firewall per i supporti di routing diretto |Il servizio SBC comunica ai servizi seguenti nel cloud:<br/><br/>Proxy SIP, che gestisce il traffico di segnalazione<br/>Processore multimediale, che gestisce gli elementi multimediali ,tranne quando media bypass è on<br/><br/>Questi due servizi hanno indirizzi IP separati in Microsoft Cloud, descritti più avanti in questo documento.<br/><br/>Per altre informazioni, vedere la [sezione Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in URL e [intervalli di indirizzi IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|Media Transport Profile|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Porte e indirizzi IP del firewall per gli elementi multimediali di Microsoft Teams |Per altre informazioni, vedere [URL e intervalli di indirizzi IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Licenze e altri requisiti 

Gli utenti del routing diretto devono avere le licenze seguenti assegnate in Microsoft 365 o Office 365: 

- Sistema telefonico Microsoft. 
- Microsoft Teams + Skype for Business Piano 2, se incluso nelle licenze.
- Audioconferenza Microsoft (leggere le note e il paragrafo seguente per esempi specifici sui casi in cui è necessaria la licenza).

> [!NOTE]
> Il piano Skype for Business non deve essere rimosso da alcun contratto di licenza in cui è incluso. 


> [!IMPORTANT]
>  Nel caso in cui si desideri aggiungere partecipanti esterni alle riunioni pianificate, tramite chiamata in uscita o fornendo il numero di accesso esterno, è necessaria la licenza per i servizi di audioconferenza.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Riassegnazione delle chiamate ad hoc e audioconferenza

Un utente di Teams può avviare una chiamata uno-a-uno di Teams su PSTN o Teams su Teams e aggiungerne un partecipante PSTN. Questo scenario si chiama conferenza ad hoc. Il percorso della chiamata varia a seconda che all'utente che escalation la chiamata sia assegnata o meno una licenza Microsoft Audioconferenza:

- Se all'utente di Teams che inoltrare la chiamata è assegnata una licenza per i servizi di audioconferenza Microsoft, l'escalation avviene tramite il servizio di audioconferenza Microsoft. Il partecipante PSTN remoto invitato a una chiamata esistente riceve una notifica sulla chiamata in arrivo e vede il numero del bridge Microsoft assegnato all'utente di Teams che ha avviato l'escalation.
- Se all'utente di Teams che esegue l'escalation della chiamata non è assegnata la licenza per i servizi di audioconferenza Microsoft, l'escalation avviene attraverso un Session Border Controller connesso all'interfaccia di routing diretto. Il partecipante PSTN remoto invitato alla chiamata riceve una notifica sulla chiamata in arrivo e vede il numero dell'utente di Teams che ha avviato l'escalation. Il valore SBC specifico usato per l'escalation è definito dai criteri di routing dell'utente. 


È inoltre necessario verificare quanto segue:
 
- CsOnlineVoiceRoutingPolicy viene assegnato all'utente. 
- Consenti chiamate private è abilitato a livello di tenant per Microsoft Teams. 

L'instradamento diretto supporta anche gli utenti con licenza per il Piano per chiamate Microsoft. Il Sistema telefonico Microsoft con Piano per chiamate può instradare alcune chiamate utilizzando l'interfaccia di instradamento diretto. Tuttavia, i numeri di telefono degli utenti devono essere acquisiti online o deve essere esportati in Microsoft.  

La combinazione di connettività Piano per chiamate e Instradamento diretto per lo stesso utente è facoltativa, ma può essere utile (ad esempio, quando all'utente è assegnato un Piano per chiamate Microsoft ma desidera instradare alcune chiamate utilizzando SBC). Uno degli scenari più comuni sono le chiamate a pc di terze parti.  Con i PBX di terze parti, tutte le chiamate, tranne quelle ai telefoni connessi a questi sistemi, vengono instradati utilizzando il Piano per chiamate Microsoft, ma le chiamate ai telefoni connessi a PBC di terze parti passano alla rete SBC, quindi rimangono all'interno della rete aziendale e non della rete PSTN. 

Per altre informazioni sulle licenze sistema telefonico, vedere [Ottenere il massimo da Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) e dalle opzioni di [pianificazione.](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

Per ulteriori informazioni sulle licenze Sistema telefonico, consulta [l'articolo sulle licenze per i componenti aggiuntivi Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>Punti finali supportati 

È possibile usare come punto finale:

- Qualsiasi client di Teams. 
- Telefoni dell'area comune. Vedere [Configurare la licenza Common Area Phone per Microsoft Teams.](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones) Nota: non è necessaria una licenza per un Piano per chiamate quando si imposta un telefono area comune con instradamento diretto.
- Telefoni Skype for Business 3PIP. Vedere [il supporto per i telefoni Skype for Business (3PIP) con Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomi di dominio SBC

Il nome di dominio SBC deve essere di uno dei nomi registrati in Domains del tenant. Non è possibile usare \* il tenant onmicrosoft.com come nome FQDN del database SBC.

La tabella seguente mostra esempi di nomi DNS registrati per il tenant, se il nome può essere usato come FQDN per SBC ed esempi di nomi FQDN validi:

|Nome DNS|Può essere usato per l'FQDN SBC|Esempi di nomi FQDN|
|:--- |:--- |:--- |
contoso.com|Sì|**Nomi validi:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|L'uso di *.onmicrosoft.com domini non è supportato per i nomi SBC

Si supponga di voler usare un nuovo nome di dominio. Ad esempio, il tenant contoso.com come nome di dominio registrato nel tenant e si vuole usare sbc1.sip.contoso.com. Prima di associare un SBC al nome sbc1.sip.contoso.com, è necessario registrare il nome di sip.contoso.com dominio in Domini nel tenant. Se si prova ad associare un dominio SBC a sbc1.sip.contoso.com prima di registrare il nome di dominio, viene visualizzato l'errore seguente: "Impossibile usare il dominio "sbc1.sip.contoso.com" perché non è stato configurato per il tenant."
Dopo aver aggiunto il nome di dominio, devi anche creare un utente con UPN user@sip.contoso.com assegnare una licenza di Teams. Il provisioning completo del nome di dominio dopo l'aggiunta a Domini del tenant, la creazione di un utente con un nuovo nome e l'assegnazione di una licenza all'utente possono richiedere fino a 24 ore. 

È possibile che una società abbia diversi spazi di indirizzi SIP in un tenant. Ad esempio, una società potrebbe avere contoso.com come spazio di indirizzi SIP e fabrikam.com come secondo spazio di indirizzi SIP. Alcuni utenti hanno indirizzi user@contoso.com e altri hanno indirizzi user@fabrikam.com. 

Il servizio SBC deve avere un solo FQDN e può consentire agli utenti di accedere a qualsiasi spazio di indirizzi nel tenant associato. Ad esempio, un SBC con il nome sbc1.contoso.com può ricevere e inviare il traffico PSTN per gli utenti con indirizzi user@contoso.com e user@fabrikam.com purché questi spazi di indirizzi SIP siano registrati nello stesso tenant.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificato attendibile pubblico per SBC

Microsoft consiglia di richiedere il certificato per SBC generando una richiesta di firma della certificazione (CSR). Per istruzioni specifiche sulla generazione di un CSR per un dispositivo SBC, fare riferimento alle istruzioni di interconnessione o alla documentazione fornita dai fornitori di SBC. 

  > [!NOTE]
  > La maggior parte delle autorità di certificazione (CA) richiede che le dimensioni della chiave privata siano almeno di 2048. Tenere presente questo tenere presente quando si genera il CSR.

Il certificato deve avere l'FQDN SBC come campo del nome comune (CN) o del nome alternativo dell'oggetto (SAN). Il certificato deve essere emesso direttamente da un'autorità di certificazione, non da un provider intermedio.

In alternativa, il routing diretto supporta un carattere jolly in CN e/o SAN e il carattere jolly deve essere conforme allo standard [RFC HTTP Su TLS.](https://tools.ietf.org/html/rfc2818#section-3.1) In un esempio sarebbe possibile usare contoso.com che corrisponde al sbc.contoso.com FQDN SBC, ma che non corrisponde al \* sbc.test.contoso.com.

Il certificato deve essere generato da una delle autorità di certificazione radice seguenti:

- AffirmTrust
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- Buypass
- Cybertrust
- Autorità di certificazione principale di classe 3
- Comodo Secure Root CA
- Deutsche Telekom 
- Ca radice globale di DigiCert
- Ca radice DigiCert EV DigiCert
- Affidare
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Radice di Symantec Enterprise Mobile per Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Per il routing diretto negli ambienti Office 365 GCCH e DoD, il certificato deve essere generato da una delle autorità di certificazione radice seguenti:
- Ca radice globale di DigiCert
- Ca radice DigiCert EV DigiCert

> [!NOTE]
> *Se è abilitato il supporto TLS mutuale (MTLS) per la connessione di Teams nell'SBC, è necessario installare il certificato radice di Baltimore CyberTrust nell'archivio radice attendibile di SBC del contesto TLS di Teams. Il problema è dovuto al fatto che i certificati del servizio Microsoft usano il certificato radice di Baltimore. Per scaricare il certificato radice di Baltimore, vedere catene di crittografia di [Office 365.](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft sta lavorando all'aggiunta di altre autorità di certificazione in base alle richieste dei clienti. 

## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN 

Il routing diretto viene offerto negli ambienti seguenti:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Altre informazioni sugli [ambienti di Office 365 e del](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) governo degli Stati Uniti come GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

I punti di connessione per il routing diretto sono i tre FQDN seguenti:

- **sip.pstnhub.microsoft.com,** nome di dominio completo globale, devono essere provati prima. Quando SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato a SBC. L'assegnazione si basa sulle metriche di prestazioni dei data center e sulla prossimità geografica del centro dati per SBC. L'indirizzo IP restituito corrisponde all'FQDN principale.
- **sip2.pstnhub.microsoft.com** - FQDN secondario: corrisponde geograficamente alla seconda area geografica di priorità.
- **sip3.pstnhub.microsoft.com-** FQDN terziario: corrisponde geograficamente alla terza area geografica con priorità.

L'inserimento di questi tre FQDN in ordine è necessario per:

- Offrire un'esperienza ottimale, ovvero meno caricata e più vicina al data center SBC assegnato mediante query sul primo FQDN.
- Fornire il failover quando viene stabilita una connessione da un database SBC a un data center in cui si verifica un problema temporaneo. Per altre informazioni, vedere il meccanismo [di failover seguente.](#failover-mechanism-for-sip-signaling)  

I nomi fqdn, sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com, verranno risolti in uno degli indirizzi IP seguenti:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** risolve in tutti questi indirizzi IP. 

> [!IMPORTANT]
>  Nell'ambito dell'espansione e del miglioramento del servizio di Routing diretto di Teams, abbiamo distribuito nuove istanze dell'infrastruttura di routing diretto in Australia. Questo problema si riflette in altri due indirizzi IP (52.114.16.74 e 52.114.20.29) in cui i seguenti FQDN verranno risolti per i clienti australiani, ovvero sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com. Devi aggiungere questi due indirizzi IP (52.114.16.74 e 52.114.20.29) agli elenchi di controllo di accesso IP (ACL) e aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.

### <a name="office-365-gcch-and-dod-environment"></a>Ambiente MCCH e DoD di Office 365

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.dod.teams.microsoft.us:** FQDN globale. Poiché l'ambiente DoD di Office 365 esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.

L'sip.pstnhub.dod.teams.microsoft.us FQDN verrà risolto in uno degli indirizzi IP seguenti:

- 52.127.64.33
- 52.127.68.34

Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione.

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN globale. Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non sono presenti FQDN secondari e terziari.

L'sip.pstnhub.gov.teams.microsoft.us FQDN verrà risolto in uno degli indirizzi IP seguenti:

- 52.127.88.59
- 52.127.92.64

Devi aprire le porte di tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per il traffico di segnalazione. Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.gov.teams.microsoft.us** risolve in tutti questi indirizzi IP. Questo FQDN può essere usato anche come FQDN federato per la classificazione delle chiamate in ingresso.

## <a name="sip-signaling-ports"></a>Segnalazione SIP: Porte

È necessario usare le porte seguenti per gli ambienti Microsoft 365 o Office 365 in cui è disponibile il routing diretto:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Traffico|Da|A|Porta di origine|Porta di destinazione|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definito su SBC (per la porta High/DoD di Office 365 GCC deve essere usata solo la porta 5061)|
SIP/TLS|SBC|SIP Proxy|Definito nell'SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Meccanismo di failover per il traffico di segnalazione SIP

Il servizio SBC esegue una query DNS per risolvere sip.pstnhub.microsoft.com. In base alla posizione di SBC e alle metriche delle prestazioni del data center, viene selezionato il data center principale. Se si verifica un problema nel data center primario, SBC prova il sip2.pstnhub.microsoft.com, che si risolve nel secondo data center assegnato e, nei rari casi in cui i data center in due aree geografiche non sono disponibili, SBC prova l'ultimo FQDN (sip3.pstnhub.microsoft.com), che fornisce l'IP del data center terziario.

La tabella seguente riepiloga le relazioni tra data center primario, secondario e terziario:

|Se il data center primario è|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|Data center secondario (sip2.pstnhub.microsoft.com)|Stati Uniti|UE|Stati Uniti|
|Data center (sip3.pstnhub.microsoft.com)|ASIA|ASIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Traffico multimediale: intervalli di porta
Tenere presente che i requisiti seguenti sono applicabili se si vuole distribuire il routing diretto senza media bypass. Per i requisiti del firewall per Media Bypass, consulta [Pianificare il bypass multimediale con l'instradamento diretto.](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)



Il traffico multimediale fluisce da e verso un servizio separato in Microsoft Cloud. Gli intervalli di indirizzi IP per il traffico multimediale sono i seguenti.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Ambiente DoD di Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervallo di porte (applicabile a tutti gli ambienti)
L'intervallo di porta dei processori multimediali è illustrato nella tabella seguente: 

|Traffico|Da|A|Porta di origine|Porta di destinazione|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processore multimediale|SBC|3478-3481 e 49152 – 53247|Definito nell'SBC|
|UDP/SRTP|SBC|Processore multimediale|Definito nell'SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > Microsoft consiglia almeno due porte per ogni chiamata simultanea sull'SBC.


## <a name="media-traffic-media-processors-geography"></a>Traffico multimediale: processori multimediali geografici

Il traffico multimediale fluisce attraverso componenti denominati processori multimediali. I processori multimediali sono inseriti negli stessi data center dei proxy SIP. Sono inoltre disponibili altri processori multimediali per ottimizzare il flusso multimediale. Ad esempio, attualmente non è disponibile un componente proxy SIP in Australia (flussi SIP via Singapore o Hong Kong), ma il processore multimediale è disponibile in locale in Australia. L'esigenza dei processori multimediali in locale dipende dalla latenza che si verifica inviando traffico a lunga distanza, ad esempio dall'Australia a Singapore o a Hong Kong. Anche se la latenza nell'esempio di traffico proveniente dall'Australia a Hong Kong o Singapore è accettabile per mantenere una buona qualità delle chiamate per il traffico SIP, per il traffico multimediale in tempo reale non lo è.

Posizione dei processori multimediali:

Posizioni in cui sono distribuiti sia i componenti del proxy SIP che del processore multimediale:
- Stati Uniti (due data center degli Stati Uniti ovest e dell'Est degli Stati Uniti)
- Europa (centri dati Amsterdam e Dublino)
- Asia (data center di Singapore e Hong Kong)

Posizioni in cui sono distribuiti solo processori multimediali (flussi SIP tramite il data center più vicino elencato sopra):
- Giappone (data center Jp East and West)
- Australia (data center au-orientale e sudest)




## <a name="media-traffic-codecs"></a>Traffico multimediale: Codec

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Coda tra SBC e Cloud Media Processor o client Microsoft Teams.
Si applica sia al caso di bypass multimediale che a quello non bypass.

L'interfaccia di routing diretto sulla coda tra il controller dei confini della sessione e il processore cloud media (senza bypass multimediale) o tra il client teams e il client SBC (se è abilitato il bypass multimediale) può usare i codec seguenti:

- Bypass non multimediale (da SBC a Cloud Media Processor): SILK, G.711, G.722, G.729
- Bypass multimediale (client da SBC a Teams): SILK, G.711, G.722, G.729

È possibile forzare l'uso di uno specifico codec nel controller dei confini della sessione escludendo dall'offerta i codec indesiderati.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Coda tra client di Microsoft Teams e processore multimediale cloud
Si applica solo alla distinzione tra maiuscole e minuscole non multimediali. Con Media Bypass, i contenuti multimediali fluire direttamente tra il client di Teams e SBC.

Sul lato tra il processore cloud e il client Microsoft Teams viene usato il metodo SILK o G.722. La scelta del codec su questo campo si basa sugli algoritmi Microsoft, che prendono in considerazione più parametri. 


## <a name="supported-session-border-controllers-sbcs"></a>Controller dei confini della sessione supportati

Microsoft supporta solo gli SBC certificati da associare all'instradamento diretto. Poiché VoIP aziendale è fondamentale per le aziende, Microsoft esegue test intensivi con gli SBC selezionati e collabora con i fornitori di SBC per garantire la compatibilità dei due sistemi. 

I dispositivi convalidati sono elencati come Certificati per l'instradamento diretto di Teams. Il funzionamento dei dispositivi certificati è garantito in tutti gli scenari. 

Per ulteriori informazioni sui controller dei confini della sessione supportati, consulta l'elenco dei controller dei confini [della sessione certificati per l'instradamento diretto.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Vedere anche

[Configurare Instradamento diretto](direct-routing-configure.md)
