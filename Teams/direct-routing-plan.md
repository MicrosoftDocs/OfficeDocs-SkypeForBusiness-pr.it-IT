---
title: Pianificare Instradamento diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Scopri come Microsoft Direct Routing consente di connettere un controller SBC (Session Border Controller) supportato dal cliente al sistema telefonico.
ms.openlocfilehash: de829008a45e8f4c1095138ddc1b1dcc32cdb3eb
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680519"
---
# <a name="plan-direct-routing"></a>Pianificare Instradamento diretto

> [!Tip]
> Guarda la sessione seguente per informazioni sui vantaggi di Direct Routing, su come pianificarlo e come distribuirlo: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)

Direct Routing consente di connettere un session border controller (SBC) supportato dal cliente al sistema telefonico. Con questa funzionalità, è possibile configurare la connettività PSTN (Public Switched Telephone Network) locale con il client Microsoft Teams, come illustrato nel diagramma seguente: 

![Diagramma che illustra la configurazione della connettività PSTN locale.](media/PlanDirectRouting1-PSTNwithTeams.png "Configurazione della connettività PSTN locale con il client Microsoft Teams")

  > [!NOTE]
  > Skype for Business Online consente anche di associare una scheda SBC fornita dal cliente, ma ciò richiede una distribuzione Skype for Business Server locale o una speciale edizione di Skype for Business, denominata Cloud Connector, tra SBC e Microsoft Cloud. Questo scenario è noto come voce ibrida. Al contrario, direct routing consente una connessione diretta tra l'SBC supportato e Microsoft Cloud.

> [!Important]
> Cloud Connector Edition verrà ritirato il 31 luglio 2021 insieme a Skype for Business Online. Una volta che l'organizzazione ha eseguito l'aggiornamento a Teams, scopri come connettere la rete di telefonia locale a Teams usando il [routing diretto](direct-routing-landing-page.md). 

Con Direct Routing, puoi connettere il tuo SBC a quasi tutti i trunk di telefonia o interconnetterti con apparecchiature PSTN di terze parti. Direct Routing consente di: 

- Usa praticamente qualsiasi trunk PSTN con Sistema telefonico. 

- Configurare l'interoperabilità tra apparecchiature di telefonia di proprietà dei clienti, ad esempio PBX (Private Branch Exchange) di terze parti, dispositivi analogici e Teams.

Microsoft offre anche soluzioni vocali all-in-the-cloud, come il Piano per chiamate. Tuttavia, una soluzione vocale ibrida potrebbe essere la soluzione migliore per l'organizzazione se: 

- Il piano per chiamate Microsoft non è disponibile nel tuo paese. 

- L'organizzazione richiede la connessione a dispositivi analogici di terze parti, call center e così via. 

- L'organizzazione ha un contratto esistente con un gestore PSTN.

Direct Routing supporta anche gli utenti che dispongono della licenza aggiuntiva per il piano per chiamate Microsoft. Per ulteriori informazioni, vedi [Sistema telefonico e Piani per chiamate](calling-plan-landing-page.md). 

Con Direct Routing, quando gli utenti partecipano a una conferenza pianificata, il numero di accesso esterno viene fornito dal servizio Microsoft Audioconferenza, che richiede una licenza appropriata.  Durante la chiamata in uscita, il servizio Di audioconferenza Microsoft effettua la chiamata con funzionalità di chiamata online, che richiedono licenze appropriate. Se un utente non dispone di una licenza per i servizi di audioconferenza Microsoft, la chiamata viene instradata tramite routing diretto. Per altre informazioni, vedere [Riunioni online con Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
Pianificare la distribuzione del routing diretto è fondamentale per un'implementazione corretta. Questo articolo descrive i requisiti di infrastruttura e licenze e fornisce informazioni sulla connettività SBC: 

- [Requisiti dell'infrastruttura](#infrastructure-requirements)
- [Licenze e altri requisiti](#licensing-and-other-requirements)
- [Nomi di dominio SBC](#sbc-domain-names)
- [Certificato pubblico attendibile per SBC](#public-trusted-certificate-for-the-sbc)
- [Segnalazione SIP: FQDN](#sip-signaling-fqdns)
- [Segnalazione SIP: porte](#sip-signaling-ports)
- [Traffico multimediale: intervalli di porte](#media-traffic-port-ranges)
- [Controller dei confini della sessione supportati](#supported-session-border-controllers-sbcs)

Per informazioni dettagliate sulla configurazione del routing diretto, vedere [Configurare il routing diretto](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura
I requisiti dell'infrastruttura per gli SBC supportati, i domini e altri requisiti di connettività di rete per distribuire il routing diretto sono elencati nella tabella seguente:  

|Requisito dell'infrastruttura|Sono necessari i seguenti|
|:--- |:--- |
|Session Border Controller (SBC)|Un'estensione SBC supportata. Per altre informazioni, vedere [Schede SBC supportate](#supported-session-border-controllers-sbcs).|
|Trunk di telefonia collegati alla SBC|Uno o più trunk di telefonia collegati all'SBC. Da un lato, SBC si connette al sistema telefonico tramite routing diretto. SBC può anche connettersi a entità di telefonia di terze parti, come PBX, Analog Telephony Adapter e così via. Qualsiasi opzione di connettività PSTN connessa a SBC funzionerà. Per la configurazione dei trunk PSTN a SBC, fare riferimento ai fornitori di servizi di protezione avanzata o ai provider di trunk.|
|Organizzazione di Microsoft 365|Un'organizzazione di Microsoft 365 che usi per la casa degli utenti di Microsoft Teams e la configurazione e la connessione alla scheda SBC.|
|Registrar utenti|L'utente deve essere ospitato in Microsoft 365.<br/>Se l'azienda ha un ambiente Skype for Business locale o Lync con connettività ibrida a Microsoft 365, non è possibile abilitare la funzionalità vocale in Teams per un utente ospitato in locale.<br/><br/>Per controllare il registrar di un utente, usare il cmdlet di PowerShell di Skype for Business Online seguente:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>L'output del cmdlet dovrebbe mostrare:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domini|Uno o più domini aggiunti a Microsoft 365 o Office 365 organizzazioni.<br/><br/>Si noti che non è possibile usare il dominio predefinito , \*onmicrosoft.com, creato automaticamente per il tenant.<br/><br/>Per visualizzare i domini, è possibile usare il cmdlet di PowerShell di Skype for Business Online seguente:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Per altre informazioni sui domini e microsoft 365 o Office 365 organizzazioni, vedere [Domande frequenti sui domini](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Indirizzo IP pubblico per SBC|Un indirizzo IP pubblico che può essere usato per connettersi a SBC. In base al tipo di SBC, SBC può usare NAT.|
|Nome di dominio completo (FQDN) per SBC|FQDN per SBC, in cui la parte relativa al dominio dell'FQDN è uno dei domini registrati nell'organizzazione di Microsoft 365 o Office 365. Per altre informazioni, vedere [Nomi di dominio SBC](#sbc-domain-names).|
|Voce DNS pubblica per SBC |Una voce DNS pubblica che associa l'FQDN SBC all'indirizzo IP pubblico. |
|Certificato pubblico attendibile per SBC |Un certificato per SBC da usare per tutte le comunicazioni con direct routing. Per altre informazioni, vedere [Certificato attendibile pubblico per il certificato SBC](#public-trusted-certificate-for-the-sbc).|
|Punti di connessione per l'instradamento diretto |I punti di connessione per il routing diretto sono i seguenti tre FQDN:<br/><br/>`sip.pstnhub.microsoft.com` : è necessario provare prima l'FQDN globale.<br/>`sip2.pstnhub.microsoft.com` – FQDN secondario, mappato geograficamente alla seconda area di priorità.<br/>`sip3.pstnhub.microsoft.com` – FQDN fqdn fqdn, geograficamente mappa alla terza area di priorità.<br/><br/>Per informazioni sui requisiti di configurazione, vedere [Segnalazione SIP: FQDN](#sip-signaling-fqdns).|
|Porte e indirizzi IP firewall per i supporti di routing diretto |SBC comunica ai servizi seguenti nel cloud:<br/><br/>Proxy SIP, che gestisce la segnalazione<br/>Processore multimediale, che gestisce i supporti, tranne quando Media Bypass è attivato<br/><br/>Questi due servizi hanno indirizzi IP separati in Microsoft Cloud, descritti più avanti in questo documento.<br/><br/>Per altre informazioni, vedere la [sezione Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [URL e intervalli di indirizzi IP](/office365/enterprise/urls-and-ip-address-ranges). |
|Media Transport Profile|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Porte e indirizzi IP firewall per i supporti di Microsoft Teams |Per altre informazioni, vedere [URL e intervalli di indirizzi IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenze e altri requisiti 

Gli utenti di Direct Routing devono avere le seguenti licenze assegnate in Microsoft 365: 

- Sistema telefonico Microsoft
- Microsoft Teams + Skype for Business Piano 2, se incluso nelle licenze
- Microsoft Audioconferenza (leggi le note e il paragrafo seguente per esempi specifici su quando è richiesta questa licenza).

> [!NOTE]
> Skype for Business Piano non deve essere rimosso da alcun contratto di licenza in cui è incluso. 
> 
> [!IMPORTANT]
> Gli utenti GCC High e DoD devono disabilitare le licenze di Audioconferenza incluse in G5 e attendere l'abilitazione di tutte le audioconferenze fino a quando il routing diretto non è stato completamente configurato. Gli utenti devono avere configurato numeri di telefono per l'accesso esterno e una tastiera funzionante prima di abilitare le licenze per i servizi di audioconferenza. Per maggiori dettagli, vedi [Audioconferenza con routing diretto per GCC High e DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) .


> [!IMPORTANT]
>  Se vuoi aggiungere partecipanti esterni alle riunioni pianificate, effettuando una chiamata in uscita o fornendo il numero di accesso esterno, la licenza per i servizi di audioconferenza è obbligatoria.
> Per GCC High e DoD, non assegnare una licenza per i servizi di audioconferenza agli utenti G5. Per gli utenti G3, non assegnare una licenza per i servizi di audioconferenza finché l'instradamento diretto non è completamente configurato e l'utente dispone di una tastiera del telefono funzionante.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalation delle chiamate ad hoc e licenza per i servizi di audioconferenza

Un utente di Teams può avviare una chiamata Teams-a-PSTN o Teams-to-Teams uno-a-uno e aggiungervi un partecipante PSTN. Questo scenario è detto conferenza ad hoc. Il percorso della chiamata dipende dal fatto che all'utente che effettua l'escalation della chiamata sia assegnata o meno una licenza per i servizi di audioconferenza Microsoft:

- **Se all'utente di Teams che effettua l'escalation della chiamata è assegnata una licenza per i servizi di audioconferenza Microsoft**, l'escalation avviene tramite il servizio Di audioconferenza Microsoft. Il partecipante PSTN remoto invitato alla chiamata esistente riceve una notifica sulla chiamata in arrivo e vede il numero del bridge Microsoft assegnato all'utente di Teams che ha avviato l'escalation.

- **Se all'utente di Teams che effettua l'escalation della chiamata non è assegnata la licenza per i servizi di audioconferenza Microsoft**, l'escalation avviene tramite un controller dei confini della sessione connesso all'interfaccia routing diretto. Il partecipante PSTN remoto invitato alla chiamata riceve una notifica sulla chiamata in arrivo e vede il numero dell'utente di Teams che ha avviato l'escalation. La SBC specifica utilizzata per l'escalation è definita dal criterio di routing dell'utente. 

È necessario verificare quanto segue:
 
- CsOnlineVoiceRoutingPolicy viene assegnato all'utente. 

- Consenti chiamate private è abilitato a livello di tenant per Microsoft Teams. 

Direct Routing supporta anche gli utenti con licenza per il piano per chiamate Microsoft. Sistema telefonico con piano per chiamate può instradare alcune chiamate utilizzando l'interfaccia Routing diretto. Tuttavia, i numeri di telefono degli utenti devono essere acquisiti online o trasferiti in Microsoft.  

Combinare il piano per chiamate e la connettività di routing diretto per lo stesso utente è facoltativo, ma potrebbe essere utile. Ad esempio, quando all'utente è assegnato un piano per chiamate Microsoft ma vuole instradare alcune chiamate tramite SBC. Uno degli scenari più comuni sono le chiamate a PBX di terze parti.  Con i PBX di terze parti, tutte le chiamate, tranne quelle verso i telefoni connessi a tale PBX, vengono instradate tramite il piano per chiamate Microsoft, ma le chiamate ai telefoni connessi a PBX di terze parti vengono indirizzate all'SBC e quindi rimangono all'interno della rete aziendale e non della rete PSTN. 

Per altre informazioni sulle licenze di Sistema telefonico, vedere [Ottenere il massimo da Opzioni di Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) e [piano](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) e Licenze per i [componenti aggiuntivi di Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Endpoint supportati 

È possibile usare come punto finale:

- Qualsiasi client di Teams. 

- Telefoni ad area comune. Vedere [Configurare telefoni area comune per Microsoft Teams](./set-up-common-area-phones.md). Non è necessaria una licenza per il piano per chiamate durante la configurazione di un common area phone con routing diretto.

- Skype for Business telefoni 3PIP. Vedere [Skype for Business supporto per telefoni (3PIP) con Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nomi di dominio SBC

Il nome di dominio SBC deve provenire da uno dei nomi registrati in Domini del tenant. Non è possibile usare il \*tenant con estensione onmicrosoft.com per il nome FQDN di SBC.

La tabella seguente mostra esempi di nomi DNS registrati per il tenant, se il nome può essere usato come FQDN per SBC ed esempi di nomi FQDN validi:

|Nome DNS|Può essere usato per l'FQDN SBC|Esempi di nomi FQDN|
|:--- |:--- |:--- |
contoso.com|Sì|**Nomi validi:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|L'uso dei domini *.onmicrosoft.com non è supportato per i nomi SBC

Si supponga di voler usare un nuovo nome di dominio. Ad esempio, il tenant ha contoso.com come nome di dominio registrato nel tenant e si vuole usare sbc1.sip.contoso.com. Prima di associare un oggetto SBC al nome sbc1.sip.contoso.com, è necessario registrare il nome di dominio sip.contoso.com in Domini nel tenant. Se si prova ad associare un server SBC a sbc1.sip.contoso.com prima di registrare il nome di dominio, viene visualizzato l'errore seguente: "Impossibile usare il dominio "sbc1.sip.contoso.com" perché non è stato configurato per il tenant.
Dopo aver aggiunto il nome di dominio, è necessario anche creare un utente con UPN user@sip.contoso.com e assegnare una licenza di Teams. Il provisioning completo del nome di dominio dopo l'aggiunta ai domini del tenant, la creazione di un utente con un nuovo nome e l'assegnazione di una licenza all'utente potrebbero richiedere fino a 24 ore. 

È possibile che una società abbia diversi spazi di indirizzi SIP in un tenant. Ad esempio, una società potrebbe avere contoso.com come spazio di indirizzi SIP e fabrikam.com come secondo spazio di indirizzi SIP. Alcuni utenti hanno user@contoso.com di indirizzi e altri user@fabrikam.com di indirizzi. 

SBC richiede un solo FQDN e può richiedere assistenza agli utenti da qualsiasi spazio di indirizzi nel tenant associato. Ad esempio, una SBC con il nome sbc1.contoso.com può ricevere e inviare il traffico PSTN per gli utenti con indirizzi user@contoso.com e user@fabrikam.com a condizione che questi spazi di indirizzi SIP siano registrati nello stesso tenant.  

 > [!NOTE]
 > L'FQDN SBC in Servizi di comunicazione di Azure routing diretto deve essere diverso dall'FQDN SBC nel routing diretto di Teams.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Certificato pubblico attendibile per SBC

Microsoft consiglia di richiedere il certificato per SBC generando una richiesta di firma di certificazione (CSR). Per istruzioni specifiche sulla generazione di una CSR per un'SBC, consulta le istruzioni di interconnessione o la documentazione fornita dai fornitori di SBC. 

> [!NOTE]
> La maggior parte delle autorità di certificazione richiede che la dimensione della chiave privata sia almeno 2048. Tieni presente questo aspetto quando generi la CSR.

Il certificato deve avere l'FQDN SBC come nome comune (CN) o il campo SAN (Subject Alternative Name).

In alternativa, Direct Routing supporta un carattere jolly in CN e/o SAN e il carattere jolly deve essere conforme allo standard [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Un esempio potrebbe essere l'uso \*di .contoso.com che corrisponde al sbc.contoso.com FQDN SBC, ma che non corrisponde a sbc.test.contoso.com.

L'interfaccia SIP per il routing diretto considera attendibili solo i certificati firmati da autorità di certificazione (CA) che fanno parte del programma Microsoft Trusted Root Certificate. Verificare che il certificato SBC sia firmato da una CA che fa parte del programma e che l'estensione Utilizzo chiave estesa (EKU) del certificato includa l'autenticazione server.
Altre informazioni: [Requisiti del programma - Microsoft Trusted Root Program](/security/trusted-root/program-requirements)
  
[Elenco certificati CA incluso](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Per il routing diretto in ambienti Office 365 GCCH e DoD, il certificato deve essere generato da una delle autorità di certificazione radice seguenti:

- Ca radice globale DigiCert
- Ca radice EV High Assurance DigiCert

> [!NOTE]
> Se per la connessione Teams su SBC è abilitato il supporto MTLS (Mutual TLS), è necessario installare i certificati Baltimore CyberTrust Root e DigiCert Global Root G2 nell'archivio radice attendibile SBC del contesto TLS di Teams. Il motivo è che i certificati del servizio Microsoft usano uno di questi due certificati radice. Per scaricare questi certificati radice, vedere [catene di crittografia Office 365](/microsoft-365/compliance/encryption-office-365-certificate-chains). Per altre informazioni, vedere [Modifiche al certificato TLS di Office](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN 

Direct Routing è disponibile nei seguenti ambienti:

- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Altre informazioni sugli [ambienti Office 365 e del governo degli Stati Uniti](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government), ad esempio GCC, GCC High e DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

I punti di connessione per il routing diretto sono i seguenti tre FQDN:

- **sip.pstnhub.microsoft.com** , fqdn globale, deve essere prima provata. Quando SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al data center di Azure primario assegnato all'SBC. L'assegnazione si basa sulle metriche delle prestazioni dei data center e sulla prossimità geografica all'SBC.The assignment is based performance metrics of the datacenters and geographical proximity to the SBC. L'indirizzo IP restituito corrisponde all'FQDN primario.

- **sip2.pstnhub.microsoft.com** , FQDN secondario, mappa geograficamente alla seconda area di priorità.

- **sip3.pstnhub.microsoft.com** – FQDN fqdn fqdn : corrisponde geograficamente alla terza area di priorità.

L'inserimento di questi tre FQDN è necessario per:

- Offrire un'esperienza ottimale (meno carico e più vicino al data center SBC assegnato eseguendo una query sul primo FQDN).

- Fornire il failover quando viene stabilita la connessione da un server SBC a un data center in cui si verifica un problema temporaneo. Per ulteriori informazioni, vedere [Meccanismo di failover](#failover-mechanism-for-sip-signaling) di seguito.  

Gli FQDN, sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com, verranno risolti in indirizzi IP dalle subnet seguenti:

- 52.112.0.0/14
- 52.120.0.0/14

È necessario aprire le porte per tutti questi intervalli di indirizzi IP nel firewall per consentire il traffico in arrivo e in uscita da e verso gli indirizzi per la segnalazione.

### <a name="office-gcc-dod-environment"></a>Ambiente DoD GCC di Office

Il punto di connessione per routing diretto è il seguente FQDN:

**sip.pstnhub.dod.teams.microsoft.us** : FQDN globale. Poiché l'ambiente DoD Office 365 esiste solo nei data center degli Stati Uniti, non esiste alcun FQDN secondario e terziario.

Il sip.pstnhub.dod.teams.microsoft.us FQDN verrà risolto in un indirizzo IP dalla subnet seguente:

- 52.127.64.0/21

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente GCC High

Il punto di connessione per routing diretto è il seguente FQDN:

**sip.pstnhub.gov.teams.microsoft.us** - FQDN globale. Poiché l'ambiente GCC High esiste solo nei data center degli Stati Uniti, non esiste alcun FQDN secondario e terziario.

Il sip.pstnhub.gov.teams.microsoft.us FQDN verrà risolto in un indirizzo IP dalla subnet seguente:

- 52.127.88.0/21

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in ingresso e in uscita da e verso gli indirizzi per la segnalazione.

## <a name="sip-signaling-ports"></a>Segnalazione SIP: porte

È necessario utilizzare le porte seguenti per Microsoft 365 o Office 365 ambienti in cui è disponibile il routing diretto:

- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Traffico|Da|A|Porta di origine|Porta di destinazione|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|Sbc|1024 – 65535|Definito su SBC (per Office 365 deve essere usata solo la porta 5061 GCC High/DoD)|
SIP/TLS|Sbc|SIP Proxy|Definito in SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Meccanismo di failover per il segnalazione SIP

SBC crea una query DNS per risolvere sip.pstnhub.microsoft.com. In base alla posizione SBC e alle metriche relative alle prestazioni del data center, viene selezionato il data center principale. Se il data center principale riscontra un problema, SBC tenterà la sip2.pstnhub.microsoft.com, che risolve il secondo data center assegnato, e, nel raro caso in cui i data center di due aree geografiche non siano disponibili, la SBC ritenta l'ultimo FQDN (sip3.pstnhub.microsoft.com), che fornisce l'IP del data center di prova.

La tabella seguente riepiloga le relazioni tra data center primario, secondario e terziario:

|Se il data center principale è|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|Data center secondario (sip2.pstnhub.microsoft.com)|Noi|Ue|Noi|
|Data center terziario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|Ue|
|||||

## <a name="media-traffic-port-ranges"></a>Traffico multimediale: intervalli di porte
Si noti che i requisiti seguenti si applicano se si vuole distribuire il routing diretto senza bypass multimediale. Per i requisiti del firewall per il bypass multimediale, fai riferimento a [Pianificare il bypass multimediale con routing diretto](./direct-routing-plan-media-bypass.md).

Il traffico multimediale scorre da e verso un servizio separato in Microsoft Cloud. Gli intervalli di indirizzi IP per il traffico multimediale sono i seguenti.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Ambienti Microsoft 365, Office 365 e Office 365 GCC

- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (indirizzi IP da 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 ambiente DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 ambiente GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Gamma di porte (applicabile a tutti gli ambienti)
L'intervallo di porte dei processori multimediali è illustrato nella tabella seguente: 

|Traffico|Da|A|Porta di origine|Porta di destinazione|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Media Processor|Sbc|3478-3481 e 49152 – 53247|Definito in SBC|
|UDP/SRTP|Sbc|Media Processor|Definito in SBC|3478-3481 e 49152 – 53247|

  > [!NOTE]
  > Microsoft consiglia almeno due porte per chiamata simultanea in SBC.


## <a name="media-traffic-media-processors-geography"></a>Traffico multimediale: area geografica dei processori multimediali

Il traffico multimediale passa attraverso componenti denominati processori multimediali. I processori multimediali vengono inseriti negli stessi data center dei proxy SIP:

- NOAM (Us South Central, due in data center us west e US East)
- Europa (paesi del Sud del Regno Unito, Francia centrale, Amsterdam e Dublino)
- Asia (data center Singapore)
- Giappone (data center JP Est e West)
- Australia (data center AU est e sudest)
- America Latina (Brasile Sud)

## <a name="media-traffic-codecs"></a>Traffico multimediale: codec

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Gamba tra SBC e Cloud Media Processor o client Microsoft Teams

Si applica sia al caso di bypass multimediale che al caso di non bypass.

L'interfaccia Direct Routing sulla gamba tra session border controller e Cloud Media Processor (senza bypass multimediale) o tra il client Teams e SBC (se Media Bypass abilitato) può utilizzare i codec seguenti:

- Bypass non multimediale (da SBC a Cloud Media Processor): SILK, G.711, G.722, G.729
- Media Bypass (client da SBC a Teams): SILK, G.711, G.722, G.729

È possibile forzare l'uso del codec specifico nel controller dei confini della sessione escludendo i codec indesiderati dall'offerta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Parte tra client Di Microsoft Teams e Cloud Media Processor

Si applica solo al caso di bypass non multimediale. Con Media Bypass, i flussi multimediali passano direttamente tra il client di Teams e SBC.

Sulla gamba tra cloud media processor e client Di Microsoft Teams, viene utilizzato SILK o G.722. La scelta del codec su questa gamba si basa sugli algoritmi Microsoft, che tengono in considerazione più parametri. 

  > [!NOTE]
  > Il re-targeting dei supporti non è supportato. Durante una chiamata con instradamento diretto, se il SBC invia un nuovo indirizzo IP multimediale all'instradamento diretto di Teams, anche se viene negoziato nel segnale SIP, i supporti non vengono mai inviati al nuovo indirizzo IP dall'instradamento diretto di Teams.

## <a name="supported-session-border-controllers-sbcs"></a>Controller dei confini della sessione supportati

Microsoft supporta solo gli SBC certificati da associare al routing diretto. Poiché VoIP aziendale è fondamentale per le aziende, Microsoft esegue test intensivi con le schede SBC selezionate e collabora con i fornitori di SBC per verificare che i due sistemi siano compatibili. 

I dispositivi che sono stati convalidati sono elencati come Certificati per Teams Direct Routing. I dispositivi certificati sono garantiti per funzionare in tutti gli scenari. 

Per ulteriori informazioni sugli SBC supportati, vedi [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).

## <a name="support-boundaries"></a>Limiti del supporto
Microsoft supporta solo un sistema telefonico con instradamento diretto se usato con dispositivi certificati. In caso di problemi, è necessario contattare prima l'assistenza clienti del fornitore SBC. Se necessario, il fornitore SBC invierà il problema a Microsoft tramite canali interni. Microsoft si riserva il diritto di rifiutare i casi di supporto in cui un dispositivo non certificato è connesso al sistema telefonico tramite instradamento diretto. Se Microsoft determina che il problema di instradamento diretto di un cliente riguarda un dispositivo SBC di un fornitore, il cliente dovrà contattare nuovamente il fornitore SBC per ricevere supporto.
 
## <a name="see-also"></a>Vedere anche

[Configurare Instradamento diretto](direct-routing-configure.md)
