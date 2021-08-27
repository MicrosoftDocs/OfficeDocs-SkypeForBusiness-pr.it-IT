---
title: Pianificare Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Scopri come Telefono Microsoft System Direct Routing consente di connettere un session border controller (SBC) supportato dal cliente a Telefono Microsoft System.
ms.openlocfilehash: 8c699b8893a35383b106271eacea2503f77495dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582340"
---
# <a name="plan-direct-routing"></a>Pianificare Instradamento diretto

> [!Tip]
> Guardare la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificarlo e su come distribuirlo: [Routing diretto in Microsoft Teams](https://aka.ms/teams-direct-routing)

Telefono Microsoft System Direct Routing consente di connettere un session border controller (SBC) supportato e fornito dal cliente a Telefono Microsoft Sistema.  Con questa funzionalità, ad esempio, è possibile configurare la connettività PSTN (Public Switched Telephone Network) locale con un client Microsoft Teams, come illustrato nel diagramma seguente: 

![Diagramma che mostra la configurazione della connettività PSTN locale](media/PlanDirectRouting1-PSTNwithTeams.png "Configurazione della connettività PSTN locale con Microsoft Teams client")

  > [!NOTE]
  > Skype for Business Online consente anche di associare un SBC fornito dal cliente, ma questa operazione richiede una distribuzione di Skype for Business Server locale o una edizione speciale di Skype for Business, denominata Cloud Connector, tra SBC e Microsoft Cloud. Questo scenario è noto come voce ibrida. Al contrario, Direct Routing consente una connessione diretta tra SBC supportato e Microsoft Cloud.

> [!Important]
> Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business Online. Dopo che l'organizzazione ha eseguito l'aggiornamento a Teams, vedere come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](direct-routing-landing-page.md) 

Con Il routing diretto è possibile connettere il proprio SBC a quasi tutti i trunk di telefonia o interconnessi con apparecchiature PSTN di terze parti. Il routing diretto consente di: 

- Usare praticamente qualsiasi trunk PSTN con Telefono Microsoft Sistema. 
- Configurare l'interoperabilità tra apparecchiature di telefonia di proprietà del cliente, ad esempio un PBX (Private Branch Exchange) di terze parti, dispositivi analogici e Telefono Microsoft System.

Microsoft offre anche soluzioni vocali all-in-the-cloud, come piano chiamate. Tuttavia, una soluzione vocale ibrida potrebbe essere ideale per l'organizzazione se: 

- Il Piano per chiamate Microsoft non è disponibile nel tuo Paese. 
- L'organizzazione richiede la connessione a dispositivi analogici di terze parti, call center e così via. 
- L'organizzazione ha un contratto esistente con un gestore PSTN.

Direct Routing supporta anche gli utenti che hanno la licenza aggiuntiva per il piano per chiamate Microsoft. Per altre informazioni, vedere Sistema telefonico [e Piani per chiamate.](calling-plan-landing-page.md) 

Con Il routing diretto, quando gli utenti partecipano a una conferenza pianificata, il numero di accesso esterno viene fornito dal servizio di audioconferenza Microsoft, che richiede una licenza appropriata.  Durante la chiamata in uscita, il servizio di audioconferenza Microsoft effettua la chiamata usando funzionalità di chiamata online, che richiedono licenze appropriate. Nota se un utente non ha una licenza di audioconferenza Microsoft, le chiamate vengono instradate tramite Routing diretto. Per altre informazioni, vedere [Riunioni online con Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
La pianificazione della distribuzione del routing diretto è fondamentale per una corretta implementazione. Questo articolo descrive i requisiti di infrastruttura e licenze e fornisce informazioni sulla connettività SBC: 

- [Requisiti dell'infrastruttura](#infrastructure-requirements)
- [Licenze e altri requisiti](#licensing-and-other-requirements)
- [Nomi di dominio SBC](#sbc-domain-names)
- [Certificato pubblico attendibile per SBC](#public-trusted-certificate-for-the-sbc)
- [Segnalazione SIP: FQDN](#sip-signaling-fqdns)
- [Segnalazione SIP: Porte](#sip-signaling-ports)
- [Traffico multimediale: intervalli di porte](#media-traffic-port-ranges)
- [SBC (Session Border Controller) supportati](#supported-session-border-controllers-sbcs)

Per informazioni dettagliate sulla configurazione del routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura
I requisiti dell'infrastruttura per gli SBC, i domini e altri requisiti di connettività di rete supportati per distribuire il routing diretto sono elencati nella tabella seguente:  

|Requisiti dell'infrastruttura|È necessario quanto segue|
|:--- |:--- |
|Session Border Controller (SBC)|SBC supportato. Per altre informazioni, vedere [SBC supportati.](#supported-session-border-controllers-sbcs)|
|Trunk di telefonia connessi all'SBC|Uno o più trunk di telefonia connessi all'SBC. Da un lato, il sistema SBC si connette al sistema Telefono Microsoft tramite routing diretto. SBC può anche connettersi a entità di telefonia di terze parti, ad esempio PBX, adattatori di telefonia analogica e così via. Qualsiasi opzione di connettività PSTN connessa a SBC funzionerà. Per la configurazione dei trunk PSTN in SBC, vedere i fornitori O provider di trunk SBC.|
|Microsoft 365 o Office 365 organizzazione|Un'Microsoft 365 o Office 365 che si usa per ospitare gli utenti Microsoft Teams utenti e la configurazione e la connessione al database SBC.|
|Registrar utente|L'utente deve essere ospitata in Microsoft 365 o Office 365.<br/>Se l'azienda ha un ambiente Skype for Business o Lync locale con connettività ibrida a Microsoft 365 o Office 365, non è possibile abilitare la voce in Teams per un utente ospitato in locale.<br/><br/>Per controllare il registrar di un utente, usare il cmdlet di PowerShell Skype for Business online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>L'output del cmdlet dovrebbe essere:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domini|Uno o più domini aggiunti alle Microsoft 365 o Office 365 organizzazioni.<br/><br/>Si noti che non è possibile usare il dominio predefinito, con estensione onmicrosoft.com, creato \* automaticamente per il tenant.<br/><br/>Per visualizzare i domini, è possibile usare il cmdlet di PowerShell seguente Skype for Business Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Per altre informazioni sui domini e le Microsoft 365 o Office 365, vedere Domande [frequenti sui domini.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Indirizzo IP pubblico per SBC|Indirizzo IP pubblico che può essere usato per connettersi all'SBC. In base al tipo di SBC, SBC può usare NAT.|
|Nome di dominio completo (FQDN) per SBC|Fqdn per il dominio SBC, dove la parte relativa al dominio dell'FQDN è uno dei domini registrati nell'organizzazione Microsoft 365 o Office 365. Per altre informazioni, vedere [Nomi di dominio SBC.](#sbc-domain-names)|
|Voce DNS pubblica per SBC |Una voce DNS pubblica che mappa l'FQDN SBC all'indirizzo IP pubblico. |
|Certificato pubblico attendibile per SBC |Certificato per SBC da usare per tutte le comunicazioni con il routing diretto. Per altre informazioni, vedere [Certificato pubblico attendibile per SBC.](#public-trusted-certificate-for-the-sbc)|
|Punti di connessione per il routing diretto |I punti di connessione per il routing diretto sono i tre FQDN seguenti:<br/><br/>`sip.pstnhub.microsoft.com` – Il nome FQDN globale deve essere provato per primo.<br/>`sip2.pstnhub.microsoft.com` – FQDN secondario, mappato geograficamente alla seconda area prioritaria.<br/>`sip3.pstnhub.microsoft.com` – FQDN terziario, mappato geograficamente alla terza area prioritaria.<br/><br/>Per informazioni sui requisiti di configurazione, vedere [Segnalazione SIP: FQDN.](#sip-signaling-fqdns)|
|Porte e indirizzi IP del firewall per supporti di routing diretto |SBC comunica con i servizi seguenti nel cloud:<br/><br/>Proxy SIP, che gestisce la segnalazione<br/>Processore multimediale, che gestisce gli elementi multimediali, tranne quando Media Bypass è on<br/><br/>Questi due servizi hanno indirizzi IP separati in Microsoft Cloud, descritti più avanti in questo documento.<br/><br/>Per altre informazioni, vedere la Microsoft Teams [in](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [URL e intervalli di indirizzi IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|Profilo di trasporto multimediale|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Porte e indirizzi IP del firewall per Microsoft Teams multimediali |Per altre informazioni, vedere [URL e intervalli di indirizzi IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Licenze e altri requisiti 

Agli utenti di Direct Routing devono essere assegnate le licenze seguenti in Microsoft 365 o Office 365: 

- Telefono Microsoft Sistema. 
- Microsoft Teams + Skype for Business piano 2, se incluso nelle licenze.
- Audioconferenza Microsoft (leggere le note e il paragrafo seguente per esempi specifici su quando è necessaria la licenza).

> [!NOTE]
> Skype for Business Il piano non deve essere rimosso da alcun contratto di licenza in cui è incluso. 
> 
> [!IMPORTANT]
> GCC Gli utenti High e DoD devono disabilitare le licenze di audioconferenza incluse in G5 e attendere di abilitare le audioconferenze fino a quando il routing diretto non è stato completamente configurato. Prima di abilitare le licenze di audioconferenza, gli utenti devono avere configurato i numeri di telefono per l'accesso esterno e una tastiera del telefono funzionante. Per altre informazioni, vedere Audioconferenza con [routing diretto GCC High e DoD.](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md)


> [!IMPORTANT]
>  Nel caso in cui si desideri aggiungere partecipanti esterni alle riunioni pianificate, tramite chiamata in uscita o fornendo il numero di accesso esterno, è necessaria la licenza per i servizi di audioconferenza.
> Per GCC High e DoD, non assegnare una licenza di audioconferenza per gli utenti G5.  Per gli utenti G3, non assegnare una licenza di audioconferenza finché il routing diretto non è completamente configurato e l'utente non dispone di una tastiera del telefono funzionante.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalation delle chiamate ad hoc e licenza per audioconferenze

Un Teams utente può avviare un Teams uno-a-uno su PSTN o Teams per Teams chiamata e aggiungerne un partecipante PSTN. Questo scenario è detto conferenza ad hoc. Il percorso della chiamata dipende dal fatto che all'utente che la riassegna la chiamata sia assegnata o meno una licenza di audioconferenza Microsoft:

- Se all Teams utente che riassalta la chiamata è assegnata una licenza per i servizi di audioconferenza Microsoft, l'escalation avviene tramite il servizio di audioconferenza Microsoft. Il partecipante PSTN remoto invitato alla chiamata esistente riceve una notifica sulla chiamata in arrivo e visualizza il numero del bridge Microsoft assegnato all'utente Teams che ha avviato l'escalation.
- Se all Teams utente che esegue l'escalation della chiamata non è assegnata la licenza di audioconferenza Microsoft, l'escalation avviene tramite un Session Border Controller connesso all'interfaccia direct routing. Il partecipante PSTN remoto invitato alla chiamata riceve una notifica sulla chiamata in arrivo e visualizza il numero dell'utente Teams che ha avviato l'escalation. Lo specifico SBC usato per l'escalation è definito dai criteri di routing dell'utente. 


Inoltre, è necessario verificare quanto segue:
 
- CsOnlineVoiceRoutingPolicy viene assegnato all'utente. 
- Consenti chiamate private è abilitato a livello di tenant per Microsoft Teams. 

Il routing diretto supporta anche gli utenti con licenza per il piano per chiamate Microsoft. Telefono Microsoft Il sistema con piano di chiamata può instradare alcune chiamate usando l'interfaccia Di routing diretto. Tuttavia, i numeri di telefono degli utenti devono essere acquisiti online o portati in Microsoft.  

La combinazione di connettività Piano chiamate e Routing diretto per lo stesso utente è facoltativa, ma può essere utile, ad esempio quando all'utente è assegnato un piano per chiamate Microsoft, ma si vuole instradare alcune chiamate tramite SBC. Uno degli scenari più comuni sono le chiamate a PBX di terze parti.  Con i sistemi PBX di terze parti, tutte le chiamate, ad eccezione delle chiamate ai telefoni connessi a questi sistemi, vengono instradati usando il Piano per le chiamate Microsoft, ma le chiamate ai telefoni connessi a sistemi PBC di terze parti vengono indirizzate alla rete SBC e quindi rimangono all'interno della rete aziendale e non della RETE PSTN. 

Per altre informazioni sulle licenze Sistema telefonico, [vedere](https://products.office.com/compare-all-microsoft-office-products?tab=2) Ottenere il massimo da Office [opzioni di pianificazione.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

Per altre informazioni sulle licenze Sistema telefonico, vedere Microsoft Teams [licenze per i componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Punti finali supportati 

È possibile usare come punto finale:

- Qualsiasi Teams client. 
- Telefoni dell'area comune. Vedere [Configurare la licenza dell'area Telefono per Microsoft Teams](./set-up-common-area-phones.md). Nota non è necessaria una licenza per il piano di chiamata quando si configura un'area comune Telefono routing diretto.
- Skype for Business telefoni 3PIP. Vedere [Skype for Business telefoni (3PIP)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351) con Microsoft Teams


## <a name="sbc-domain-names"></a>Nomi di dominio SBC

Il nome di dominio SBC deve essere di uno dei nomi registrati in Domini del tenant. Non è possibile usare \* il tenant onmicrosoft.com per il nome FQDN del database SBC.

La tabella seguente mostra esempi di nomi DNS registrati per il tenant, se il nome può essere usato come FQDN per SBC ed esempi di nomi FQDN validi:

|Nome DNS|Può essere usato per fqdn SBC|Esempi di nomi FQDN|
|:--- |:--- |:--- |
contoso.com|Sì|**Nomi validi:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|L'uso di domini *.onmicrosoft.com non è supportato per i nomi SBC

Si supponga di voler usare un nuovo nome di dominio. Ad esempio, il tenant contoso.com come nome di dominio registrato nel tenant e si vuole usare sbc1.sip.contoso.com. Prima di associare un SBC al nome sbc1.sip.contoso.com, è necessario registrare il nome sip.contoso.com dominio in Domini nel tenant. Se si prova ad associare un SBC a un sbc1.sip.contoso.com prima di registrare il nome di dominio, verrà visualizzato l'errore seguente: "Non è possibile usare il dominio "sbc1.sip.contoso.com" perché non è stato configurato per questo tenant.
Dopo aver aggiunto il nome di dominio, è anche necessario creare un utente con upn user@sip.contoso.com e assegnare una Teams licenza. Il provisioning completo del nome di dominio può richiedere fino a 24 ore dopo l'aggiunta a Domini del tenant, la creazione di un utente con un nuovo nome e l'assegnazione di una licenza all'utente. 

È possibile che una società abbia diversi spazi di indirizzi SIP in un tenant. Ad esempio, una società potrebbe avere contoso.com come spazio di indirizzi SIP e fabrikam.com come secondo spazio di indirizzi SIP. Alcuni utenti hanno indirizzi user@contoso.com e altri hanno indirizzi user@fabrikam.com. 

Il servizio SBC ha bisogno di un solo FQDN e può soddisfare gli utenti da qualsiasi spazio di indirizzi nel tenant associato. Ad esempio, un SBC con il nome sbc1.contoso.com può ricevere e inviare il traffico PSTN per gli utenti con indirizzi user@contoso.com e user@fabrikam.com, purché questi spazi di indirizzi SIP siano registrati nello stesso tenant.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificato pubblico attendibile per SBC

Microsoft consiglia di richiedere il certificato per SBC generando una richiesta di firma di certificazione (CSR). Per istruzioni specifiche sulla generazione di una csr per un SBC, vedere le istruzioni di interconnessione o la documentazione fornita dai fornitori di SBC. 

  > [!NOTE]
  > La maggior parte delle autorità di certificazione (CA) richiede che le dimensioni della chiave privata siano almeno 2048. Tenere presente questo problema durante la generazione della RSI.

Il certificato deve avere l'FQDN SBC come nome comune (CN) o come campo del nome alternativo del soggetto (SAN). Il certificato deve essere emesso direttamente da un'autorità di certificazione, non da un provider intermedio.

In alternativa, Il routing diretto supporta un carattere jolly in CN e/o SAN e il carattere jolly deve essere conforme allo standard [RFC HTTP Over TLS.](https://tools.ietf.org/html/rfc2818#section-3.1) Un esempio potrebbe essere l'uso di contoso.com che corrispondono al nome fqdn SBC sbc.contoso.com, ma che non corrispondono a \* sbc.test.contoso.com.

Il certificato deve essere generato da una delle autorità di certificazione radice seguenti:

- AffirmTrust
- Radice ca esterna AddTrust
- Baltimore CyberTrust Root*
- Buypass
- Cybertrust
- Autorità di certificazione principale pubblica di classe 3
- Comodo Secure Root CA
- Deutsche Telekom 
- Ca radice globale di DigiCert
- Ca radice di DigiCert High Assurance EV
- Affidare
- GlobalSign
- Vai a papà
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Campo stellare
- Symantec Enterprise Mobile Root per Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis
- Autorità di certificazione RSA USERTrust
- Hongkong Post Root CA 1,2,3
- Ca radice sectigo

Per il routing diretto negli Office 365 GCCH e DoD, il certificato deve essere generato da una delle autorità di certificazione radice seguenti:
- Ca radice globale di DigiCert
- Ca radice di DigiCert High Assurance EV

> [!NOTE]
> *Se il supporto MTLS (Mutual TLS) è abilitato per la connessione Teams nel SBC, è necessario installare il certificato radice Baltimore CyberTrust nell'archivio radice attendibile SBC del contesto tls di Teams. Questo perché i certificati del servizio Microsoft usano il certificato radice di Baltimora. Per scaricare il certificato radice di Baltimora, vedere [Office 365 catene di crittografia.](/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft sta lavorando all'aggiunta di altre autorità di certificazione in base alle richieste dei clienti. 

## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN 

Il routing diretto è disponibile negli ambienti seguenti:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC alta
- Office 365 DoD

Altre informazioni sugli [ambienti Office 365 enti](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) pubblici degli Stati Uniti, ad esempio GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 e Office 365 GCC ambienti

I punti di connessione per il routing diretto sono i tre FQDN seguenti:

- **sip.pstnhub.microsoft.com,** fqdn globale, deve essere provato prima di tutto. Quando il servizio SBC invia una richiesta di risoluzione del nome, i server DNS Microsoft Azure restituiscono un indirizzo IP che punta al data center primario di Azure assegnato al database SBC. L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla vicinanza geografica al SBC. L'indirizzo IP restituito corrisponde all'FQDN primario.
- **sip2.pstnhub.microsoft.com** , FQDN secondario, mappato geograficamente alla seconda area di priorità.
- **sip3.pstnhub.microsoft.com,** fqdn terziario, viene mappato geograficamente alla terza area prioritaria.

L'inserimento di questi tre FQDN nell'ordine è necessario per:

- Offrire un'esperienza ottimale ,meno caricata e più vicina al data center SBC assegnato tramite query sul primo FQDN.
- Fornire il failover quando viene stabilita una connessione da un SBC a un data center in cui si verifica un problema temporaneo. Per altre informazioni, vedere Meccanismo [di failover più](#failover-mechanism-for-sip-signaling) avanti.  

I nomi FQDN, sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com, verranno risolti in indirizzi IP dalle subnet seguenti:

- 52.112.0.0/14
- 52.120.0.0/14

È necessario aprire le porte per tutti questi intervalli di indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.  Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.microsoft.com** viene risolto in tutte queste subnet IP. 

> [!IMPORTANT]
> Nell'ambito dell Teams di espansione del routing diretto e del miglioramento del servizio, a novembre 2020 sono state distribuite nuove istanze dell'infrastruttura di routing diretto in Australia. Ciò si riflette in due indirizzi IP aggiuntivi (52.114.16.74 e 52.114.20.29) in cui verranno risolti i nomi FQDN seguenti per i clienti australiani: sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com. È necessario assicurarsi che questi due indirizzi IP (52.114.16.74 e 52.114.20.29) siano consentiti negli elenchi di controllo di accesso IP e che le porte siano aperte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.

> [!IMPORTANT]
> Nell'Teams dell'espansione del routing diretto e del miglioramento del servizio, sono state distribuite nuove istanze dell'infrastruttura di routing diretto in Giappone a maggio 2021. Ciò si riflette in due indirizzi IP aggiuntivi (52.114.36.156 e 52.114.32.169) in cui verranno risolti i nomi FQDN seguenti per i clienti giapponesi: sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com. È necessario assicurarsi che questi due indirizzi IP (52.114.36.156 e 52.114.32.169) siano consentiti negli elenchi di controllo di accesso IP e che le porte siano aperte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.

### <a name="office-gcc-dod-environment"></a>Office GCC DoD

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale. Poiché l'Office 365 DoD esiste solo nei data center degli Stati Uniti, non sono disponibili FQDN secondari e terziari.

Il nome fqdn sip.pstnhub.dod.teams.microsoft.us verrà risolto in un indirizzo IP della subnet seguente:

- 52.127.64.0/21

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente High

Il punto di connessione per il routing diretto è il seguente FQDN:

**sip.pstnhub.gov.teams.microsoft.us** : FQDN globale. Poiché l'GCC High è presente solo nei data center degli Stati Uniti, non sono disponibili fqdn secondari e terziari.

Il nome sip.pstnhub.gov.teams.microsoft.us FQDN verrà risolto in un indirizzo IP della subnet seguente:

- 52.127.88.0/21

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione. Se il firewall supporta i nomi DNS, l'FQDN **sip-all.pstnhub.gov.teams.microsoft.us** si risolve in tutti questi indirizzi IP. Questo FQDN può essere usato anche come FQDN federato per la classificazione delle chiamate in ingresso.

## <a name="sip-signaling-ports"></a>Segnalazione SIP: Porte

È necessario usare le porte seguenti per Microsoft 365 o Office 365 in cui è disponibile il routing diretto:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC alta
- Office 365 DoD

|Traffico|Da|A|Porta di origine|Porta di destinazione|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definito nel SBC (per Office 365 GCC deve essere usata solo la porta High/DoD 5061)|
SIP/TLS|SBC|SIP Proxy|Definito nell'SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Meccanismo di failover per la segnalazione SIP

Il servizio SBC esegue una query DNS per risolvere sip.pstnhub.microsoft.com. In base alla posizione SBC e alle metriche delle prestazioni del data center, viene selezionato il data center principale. Se si verifica un problema nel data center principale, SBC proverà il sip2.pstnhub.microsoft.com, che si risolve nel secondo data center assegnato e, nel raro caso in cui i data center in due aree non sono disponibili, il servizio SBC proverà a eseguire un nuovo tentativo con l'ultimo FQDN (sip3.pstnhub.microsoft.com), che fornisce l'IP terziario del data center.

La tabella seguente riepiloga le relazioni tra data center primari, secondari e terziari:

|Se il data center principale è|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|Data center secondario (sip2.pstnhub.microsoft.com)|Stati Uniti|UE|Stati Uniti|
|Data center terziario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Traffico multimediale: intervalli di porte
Tenere presente che i requisiti seguenti sono applicabili se si vuole distribuire il routing diretto senza bypass multimediale. Per i requisiti del firewall per Media Bypass, vedere Pianificare [il bypass multimediale con Il routing diretto.](./direct-routing-plan-media-bypass.md)



Il traffico multimediale fluisce da e verso un servizio separato in Microsoft Cloud. Gli intervalli di indirizzi IP per il traffico multimediale sono i seguenti.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 e Office 365 GCC ambienti

- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 Ambiente DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC ambiente High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervallo di porte (applicabile a tutti gli ambienti)
L'intervallo di porte dei processori multimediali è illustrato nella tabella seguente: 

|Traffico|Da|A|Porta di origine|Porta di destinazione|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Processore multimediale|SBC|3478-3481 e 49152 – 53247|Definito nell'SBC|
|UDP/SRTP|SBC|Processore multimediale|Definito nell'SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > Microsoft consiglia almeno due porte per ogni chiamata simultanea su SBC.


## <a name="media-traffic-media-processors-geography"></a>Traffico multimediale: Geografia dei processori multimediali

Il traffico multimediale fluisce tramite componenti chiamati processori multimediali. I processori multimediali vengono inseriti negli stessi data center dei proxy SIP. Sono inoltre disponibili altri processori multimediali per ottimizzare il flusso multimediale. Ad esempio, non abbiamo un componente proxy SIP ora in Australia (sip fluisce tramite Singapore o Hong Kong), ma abbiamo il processore multimediale locale in Australia. La necessità dei processori multimediali in locale è dettata dalla latenza che si verifica inviando traffico a lunga distanza, ad esempio dall'Australia a Singapore o a Hong Kong. Anche se la latenza nell'esempio di traffico che scorre dall'Australia a Hong Kong o Singapore è accettabile per mantenere una buona qualità delle chiamate per il traffico SIP, per il traffico multimediale in tempo reale non lo è.

Posizione dei processori multimediali:

Posizioni in cui sono distribuiti sia i componenti proxy SIP che i componenti del processore multimediale:
- Stati Uniti (due nei data center degli Stati Uniti occidentali e degli Stati Uniti orientali)
- Europa (data center di Amsterdam e Dublino)
- Asia (data center Singapore)
- Giappone (data center JP East e West)
- Australia (data center Au East e Southeast)

## <a name="media-traffic-codecs"></a>Traffico multimediale: Codec

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Tra SBC e Cloud Media Processor o Microsoft Teams client.
Si applica sia ai casi di bypass multimediale che a casi non di bypass.

L'interfaccia Direct Routing sulla zampa tra Session Border Controller e Cloud Media Processor (senza bypass multimediale) o tra il client Teams e il SBC (se Media Bypass abilitato) può usare i codec seguenti:

- Bypass non multimediale (da SBC a Cloud Media Processor): SILK, G.711, G.722, G.729
- Media Bypass (da SBC Teams client): SILK, G.711, G.722, G.729

È possibile forzare l'uso del codec specifico nel Session Border Controller escludendo i codec indesiderati dall'offerta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Tra il Microsoft Teams client e il processore multimediale cloud
Si applica solo alle maiuscole/minuscole non multimediali. Con Media Bypass, i supporti multimediali fluire direttamente tra Teams client e SBC.

Sulla strada tra il Processore cloud media e Microsoft Teams viene usato il client SILK o G.722. La scelta del codec in questa parte si basa sugli algoritmi Microsoft, che prendono in considerazione più parametri. 


## <a name="supported-session-border-controllers-sbcs"></a>SBC (Session Border Controller) supportati

Microsoft supporta solo SBC certificati da associare a Direct Routing. Poiché VoIP aziendale è fondamentale per le aziende, Microsoft esegue test intensivi con gli SBC selezionati e collabora con i fornitori SBC per assicurarsi che i due sistemi siano compatibili. 

I dispositivi convalidati sono elencati come certificati per Teams routing diretto. I dispositivi certificati sono garantiti per il funzionamento in tutti gli scenari. 

Per altre informazioni sugli SBC supportati, vedere Elenco dei controller di [bordo delle sessioni certificati per il routing diretto.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Vedere anche

[Configurare Instradamento diretto](direct-routing-configure.md)
