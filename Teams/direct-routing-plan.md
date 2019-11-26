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
appliesto:
- Microsoft Teams
description: Leggere questo argomento per informazioni su come Microsoft Phone System Direct routing consente di connettere un SBC (Session Border Controller) supportato dal cliente a Microsoft Phone System.
ms.openlocfilehash: 3fb9fcd8ec8dab78b03b408813d32292879cbec2
ms.sourcegitcommit: 4c763a3824e6a2271d98a46d25a03c8f04ee2f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257475"
---
# <a name="plan-direct-routing"></a>Pianificare Instradamento diretto

> [!Tip]
> Vedere la sessione seguente per informazioni sui vantaggi del routing diretto, su come pianificare la procedura e su come distribuirla: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)

Microsoft Phone System Direct routing consente di connettere un SBC (Session Border Controller) supportato e fornito dal cliente al sistema telefonico Microsoft.  Con questa funzionalità, ad esempio, è possibile configurare la connettività PSTN locale con il client Microsoft teams, come illustrato nel diagramma seguente: 

![Diagramma che mostra la configurazione della connettività PSTN locale](media/PlanDirectRouting1-PSTNwithTeams.png "Configurazione della connettività PSTN locale con il client Microsoft Teams")

  > [!NOTE]
  > Skype for business online consente anche di associare un SBC fornito dal cliente, ma richiede una distribuzione locale di Skype for Business Server o un'edizione speciale di Skype for business, denominata Cloud Connector, tra SBC e Microsoft Cloud. Questo scenario è noto come voce ibrida. Al contrario, il routing diretto consente una connessione diretta tra il SBC supportato e il cloud Microsoft. 

Con il routing diretto, è possibile connettere il SBC a quasi tutti i canali di telefonia o di interconnessione con apparecchiature PSTN (Public Switched Telephone Network) di terze parti. Il routing diretto consente di: 

- Usare virtualmente qualsiasi trunk PSTN con il sistema telefonico Microsoft. 
- Configurare l'interoperabilità tra apparecchiature di telefonia di proprietà del cliente, ad esempio un PBX (Private Branch Exchange) di terze parti, dispositivi analogici e sistema telefonico Microsoft.

Microsoft offre anche soluzioni vocali all-in-the-cloud, ad esempio il piano per le chiamate.  Tuttavia, una soluzione vocale ibrida può essere ottimale per l'organizzazione se: 

- Il piano per le chiamate Microsoft non è disponibile nel proprio paese. 
- L'organizzazione richiede la connessione a dispositivi analogici di terze parti, Call Center e così via. 
- L'organizzazione ha un contratto esistente con un vettore PSTN.

Il routing diretto supporta inoltre gli utenti che dispongono della licenza aggiuntiva per il piano di chiamate Microsoft. Per altre informazioni, vedere [sistema telefonico e piani per chiamate](calling-plan-landing-page.md). 

Con il routing diretto, quando gli utenti partecipano a una conferenza pianificata, il numero di accesso esterno viene fornito da Microsoft Audio Conferencing Service, che richiede una licenza appropriata.  Quando si effettua la chiamata in uscita, il servizio di audioconferenza Microsoft inserisce le chiamate usando le funzionalità di chiamata online, che richiedono una licenza appropriata. (Si noti che la chiamata in uscita non viene instradata tramite routing diretto). Per altre informazioni, vedere [riunioni online con teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
La pianificazione della distribuzione di routing diretto è la chiave per un'implementazione corretta. In questo articolo vengono illustrati i requisiti relativi a infrastruttura e licenze e vengono fornite informazioni sulla connettività SBC: 

- [Requisiti per l'infrastruttura](#infrastructure-requirements)
- [Licenze e altri requisiti](#licensing-and-other-requirements)
- [Nomi di dominio SBC](#sbc-domain-names)
- [Certificato attendibile pubblico per SBC](#public-trusted-certificate-for-the-sbc)
- [Segnalazione SIP: FQDN](#sip-signaling-fqdns)
- [Segnalazione SIP: porte](#sip-signaling-ports)
- [Traffico multimediale: intervalli di porte](#media-traffic-port-ranges)
- [Controller di bordo della sessione supportati (SBCs)](#supported-session-border-controllers-sbcs)

Per informazioni dettagliate sulla configurazione del routing diretto, vedere [configurare il routing diretto](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisiti per l'infrastruttura
I requisiti di infrastruttura per i SBCs, i domini e altri requisiti di connettività di rete supportati per distribuire il routing diretto sono elencati nella tabella seguente:  

|**Requisito dell'infrastruttura**|**Sono necessari i seguenti elementi**|
|:--- |:--- |
|SBC (Session Border Controller)|Un SBC supportato. Per altre informazioni, Vedi [SBCS supportate](#supported-session-border-controllers-sbcs).|
|Trunk di telefonia connesso a SBC|Uno o più trunk di telefonia connessi a SBC. Da una parte, il SBC si connette al sistema telefonico Microsoft tramite il routing diretto. SBC può anche connettersi a entità di telefonia di terze parti, come i PBX, gli adattatori per la telefonia analogica e così via. L'opzione di connettività PSTN connessa al SBC funzionerà. Nota: per la configurazione dei trunk PSTN in SBC, vedere i fornitori SBC o i provider trunk.|
|Tenant di Office 365|Un tenant di Office 365 che si usa per gli utenti di Microsoft teams e la configurazione e la connessione a SBC.|
|Registrar utente|L'utente deve essere ospitato in Office 365.<br/>Se l'azienda ha un ambiente di Skype for business o Lync locale con connettività ibrida a Office 365, non è possibile abilitare la funzionalità Voice in teams per un utente ospitato in locale.<br/><br/>Per controllare il registrar di un utente, usare il cmdlet di PowerShell di Skype for business online seguente:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>L'output del cmdlet deve mostrare:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Domini|Uno o più domini aggiunti ai tenant di Office 365.<br/><br/>**Nota:** Non è possibile usare il dominio predefinito, *. onmicrosoft.com, creato automaticamente per il tenant.<br/><br/>Per visualizzare i domini, è possibile usare il cmdlet di PowerShell di Skype for business online seguente:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Per altre informazioni sui domini e i tenant di Office 365, vedere [domande frequenti sui domini](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Indirizzo IP pubblico per SBC|Un indirizzo IP pubblico che può essere usato per la connessione a SBC. In base al tipo di SBC, SBC può usare NAT.|
|Nome di dominio completo (FQDN) per SBC|Un nome di dominio completo per SBC, in cui la parte del dominio del nome FQDN è uno dei domini registrati nel tenant di Office 365. Per altre informazioni, Vedi [nomi di dominio SBC](#sbc-domain-names).|
|Voce DNS pubblica per SBC |Una voce DNS pubblica che mappa il nome di dominio completo SBC all'indirizzo IP pubblico. |
|Certificato attendibile pubblico per SBC |Certificato per l'SBC da usare per tutte le comunicazioni con routing diretto. Per altre informazioni, vedere [certificato attendibile pubblico per SBC](#public-trusted-certificate-for-the-sbc).|
|Punti di connessione per il routing diretto |I punti di connessione per il routing diretto sono i tre FQDN seguenti:<br/><br/>`sip.pstnhub.microsoft.com`-L'FQDN globale deve essere provato per primo.<br/>`sip2.pstnhub.microsoft.com`-FQDN secondario, mappa geograficamente alla seconda area di priorità.<br/>`sip3.pstnhub.microsoft.com`– Il nome di dominio completo terziario viene mappato geograficamente alla terza area prioritaria.<br/><br/>Per informazioni sui requisiti di configurazione, vedere [segnalazione SIP: FQDN](#sip-signaling-fqdns).|
|Indirizzi IP e porte del firewall per il supporto di routing diretto |SBC comunica i servizi seguenti nel cloud:<br/><br/>Proxy SIP, che gestisce la segnalazione<br/>Media processor, che gestisce l'elemento multimediale, eccetto quando è attivato il bypass multimediale<br/><br/>Questi due servizi hanno indirizzi IP distinti in Microsoft Cloud, descritti più avanti in questo documento.<br/><br/>Per altre informazioni, vedere la [sezione Microsoft teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) negli [URL e negli intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Profilo di trasporto multimediale|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Indirizzi IP e porte firewall per Microsoft teams media |Per altre informazioni, vedere [URL e intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licenze e altri requisiti 

Gli utenti del routing diretto devono avere le licenze seguenti assegnate in Office 365: 

- Sistema telefonico Microsoft 
- Microsoft teams + Skype for Business Plan 2 se incluso nella SKU licenze
- Servizi di audioconferenza Microsoft (leggere le note e il paragrafo seguente per esempi specifici su quando è richiesta la licenza)

> [!NOTE]
> Il piano Skype for business non deve essere rimosso da qualsiasi SKU di licenze in cui è incluso. 


> [!IMPORTANT]
>  Nel caso in cui si desideri aggiungere partecipanti esterni alle riunioni pianificate, effettuando la chiamata in uscita o fornendo il numero di accesso esterno, è *necessaria*la licenza per i servizi di audioconferenza.


Escalation delle chiamate ad hoc e licenza per audioconferenza

Un utente di teams può avviare uno su un team per chiamare PSTN o teams to teams e aggiungere un partecipante PSTN. Questo scenario si chiama conferenza ad hoc. Il percorso che la chiamata richiede dipende dal fatto che l'utente che esegue l'escalation della chiamata abbia una licenza di audioconferenza Microsoft assegnata o meno.
1. Se l'utente di teams che escalation la chiamata ha una licenza di audioconferenza Microsoft assegnata, l'escalation avviene tramite il servizio di audioconferenza Microsoft. Il partecipante PSTN remoto invitato alla chiamata esistente riceve una notifica relativa alla chiamata in arrivo e vede il numero di Microsoft Bridge assegnato all'utente del team che ha avviato l'escalation.
2. Se l'utente di teams che escalation la chiamata non ha la licenza di audioconferenza Microsoft assegnata, l'escalation avviene tramite un controller di bordo della sessione collegato all'interfaccia di routing diretto. Il partecipante PSTN remoto invitato alla chiamata riceve una notifica relativa alla chiamata in arrivo e vede il numero dell'utente di teams che ha avviato l'escalation. Lo specifico SBC, usato per l'escalation, viene definito dai criteri di routing dell'utente. 


È inoltre necessario verificare quanto segue:
 
- CsOnlineVoiceRoutingPolicy viene assegnato all'utente. 
- Consenti le chiamate private è abilitato a livello di tenant per Microsoft teams. 

Il routing diretto supporta inoltre gli utenti con licenza per Microsoft Calling Plan. Il sistema telefonico Microsoft con il piano di chiamata può instradare alcune chiamate usando l'interfaccia di routing diretto. Tuttavia, i numeri di telefono degli utenti devono essere acquisiti online o trasferiti a Microsoft.  

La combinazione del piano di chiamata e della connettività di routing diretto per lo stesso utente è facoltativa, ma potrebbe essere utile, ad esempio, quando all'utente viene assegnato un piano di chiamata Microsoft, ma si vuole instradare alcune chiamate tramite SBC. Uno degli scenari più comuni sono le chiamate a sistemi PBX di terze parti.  Con i sistemi PBX di terze parti, tutte le chiamate, eccetto le chiamate ai telefoni collegati ai PBX, vengono instradate tramite il piano di chiamata Microsoft; ma le chiamate ai telefoni collegati ai PBX di terze parti accedono a SBC, quindi restano all'interno della rete aziendale e non della PSTN. 

Per altre informazioni sulle licenze per i sistemi telefonici, vedere [ottenere il massimo da Office con le](https://products.office.com/compare-all-microsoft-office-products?tab=2) opzioni di piano di Office 365 e [Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx). 

Per altre informazioni sulle licenze per i sistemi telefonici, vedere licenze per i [componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="sbc-domain-names"></a>Nomi di dominio SBC

Il nome di dominio SBC deve essere costituito da uno dei nomi registrati in "Domains" del tenant. Non è possibile usare il tenant *. onmicrosoft.com per il nome FQDN di SBC.

Nella tabella seguente sono illustrati alcuni esempi di nomi DNS registrati per il tenant, indipendentemente dal fatto che il nome possa essere usato come FQDN per SBC ed esempi di nomi FQDN validi:

|**Nome DNS**|**Può essere usato per il nome di dominio completo SBC**|**Esempi di nomi FQDN**|
|:--- |:--- |:--- |
contoso.com|Sì|**Nomi validi:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|<br/>L'uso dei domini *. onmicrosoft.com non è supportato per i nomi SBC

Si presuppone che si voglia usare un nuovo nome di dominio. Ad esempio, il tenant ha contoso.com come nome di dominio registrato nel tenant e si vuole usare sbc1.sip.contoso.com. Prima di poter associare un SBC con il nome sbc1.sip.contoso.com, è necessario registrare il nome di dominio sip.contoso.com in "Domains" nel tenant. Se si tenta di associare un SBC a sbc1.sip.contoso.com prima di registrare il nome di dominio, viene visualizzato il messaggio di errore seguente: "non è possibile usare il dominio" sbc1.sip.contoso.com "perché non è stato configurato per il tenant."
Dopo aver aggiunto il nome di dominio, è anche necessario creare un utente con UPN user@sip.contoso.com e assegnare una licenza "Teams". Potrebbe essere necessario fino a 24 ore per eseguire il provisioning completo del nome di dominio dopo l'aggiunta a "domini" del tenant, viene creato un utente con un nuovo nome e viene assegnata una licenza all'utente. 

È possibile che una società abbia diversi spazi di indirizzi SIP in un tenant. Ad esempio, una società può avere contoso.com come spazio di indirizzi SIP e fabrikam.com come secondo spazio di indirizzi SIP. Alcuni utenti hanno l'indirizzo user@contoso.com e alcuni utenti hanno l'indirizzo user@fabrikam.com. 

Il SBC necessita solo di un nome di dominio completo e può servire gli utenti da qualsiasi spazio di indirizzi nel tenant associato. Ad esempio, un SBC con il nome sbc1.contoso.com può ricevere e inviare il traffico PSTN per gli utenti con indirizzi user@contoso.com e user@fabrikam.com, purché questi spazi indirizzo SIP siano registrati nello stesso tenant.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificato attendibile pubblico per SBC

Microsoft consiglia vivamente di richiedere il certificato per SBC generando una richiesta di firma della certificazione (CSR). Per istruzioni specifiche sulla generazione di un CSR per un SBC, vedere le istruzioni di interconnessione o la documentazione fornita dai fornitori di SBC. 

  > [!NOTE]
  > La maggior parte delle autorità di certificazione (CAs) richiede che la dimensione della chiave privata sia almeno 2048. Tienilo presente quando crei la RSI.

Il certificato deve avere il nome di dominio completo SBC nei campi Subject, Common Name o Subject Alternate Name.

In alternativa, il routing diretto supporta un carattere jolly in SAN e il carattere jolly deve essere conforme a [http RFC standard su TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Un esempio dovrebbe essere l'uso di *. contoso.com nella SAN, che corrisponde al nome di dominio completo SBC sbc.contoso.com, ma non corrisponde a sbc.test.contoso.com.

Il certificato deve essere generato da una delle autorità di certificazione radice seguenti:

- AffirmTrust
- Radice CA esterna AddTrust
- Radice CyberTrust Baltimore
- Buypass
- Cybertrust
- Autorità di certificazione primaria pubblica di classe 3
- Comodo Secure root CA
- Deutsche Telekom 
- CA radice globale di DigiCert
- CA radice EV di DigiCert High Assurance
- Affidare
- GlobalSign
- Vai papà
- GeoTrust
- Verisign, Inc. 
- Starfield 
- Symantec Enterprise Mobile root per Microsoft 
- SwissSign
- Thawte timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Microsoft sta lavorando all'aggiunta di altre autorità di certificazione in base alle richieste dei clienti. 

## <a name="sip-signaling-fqdns"></a>Segnalazione SIP: FQDN 

Il routing diretto è disponibile nei seguenti ambienti di Office 365:
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Leggi altre informazioni su [Office 365 e gli ambienti governativi degli Stati Uniti](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , ad esempio GCC, GCC High e DOD.

### <a name="office-365-and-office-365-gcc-environments"></a>Ambienti Office 365 e Office 365 GCC

Il punto di connessione per il routing diretto sono i tre FQDN seguenti:

- **SIP.pstnhub.Microsoft.com** -FQDN globale-deve essere provato per primo. Quando il SBC invia una richiesta di risoluzione di questo nome, i server DNS di Microsoft Azure restituiscono un indirizzo IP che punta al Data Center di Azure principale assegnato a SBC. L'assegnazione si basa sulle metriche delle prestazioni dei datacenter e sulla vicinanza geografica a SBC. L'indirizzo IP restituito corrisponde al nome di dominio completo principale.
- **SIP2.pstnhub.Microsoft.com** -FQDN secondario-Mappa geograficamente alla seconda area di priorità.
- **SIP3.pstnhub.Microsoft.com** -FQDN terziario-Mappa geograficamente alla terza area prioritaria.

L'inserimento di questi tre FQDN in ordine è necessario per:

- Offre un'esperienza ottimale (meno caricato e più vicino al Data Center SBC assegnato eseguendo una query sul primo FQDN).
- Fornisci il failover quando viene stabilita una connessione da un SBC a un centro dati che sta vivendo un problema temporaneo. Per altre informazioni, Vedi [meccanismo di failover](#failover-mechanism-for-sip-signaling) seguente.  

Gli FQDN-sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com e sip3.pstnhub.microsoft.com-verranno risolti in uno degli indirizzi IP seguenti:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in entrata e in uscita da e verso gli indirizzi per la segnalazione.  Se il firewall supporta i nomi DNS, il nome FQDN sip-all.pstnhub.microsoft.com si risolve in tutti questi indirizzi IP. 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD Environment

Il punto di connessione per il routing diretto è il nome di dominio completo seguente:

**SIP.pstnhub.DoD.teams.Microsoft.US** -FQDN globale. Poiché l'ambiente Office 365 DoD esiste solo nei data center degli Stati Uniti, non esistono nomi di dominio completi secondari e terziari.

Gli FQDN-sip.pstnhub.dod.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:

- 52.127.64.33
- 52.127.68.34

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in entrata e in uscita da e verso gli indirizzi per la segnalazione.  Se il firewall supporta i nomi DNS, il nome FQDN sip.pstnhub.dod.teams.microsoft.us si risolve in tutti questi indirizzi IP. 

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High Environment

Il punto di connessione per il routing diretto è il nome di dominio completo seguente:

**SIP.pstnhub.gov.teams.Microsoft.US** -FQDN globale. Dato che l'ambiente GCC High esiste solo nei data center americani, non esistono nomi di dominio completi secondari e terziari.

Gli FQDN-sip.pstnhub.gov.teams.microsoft.us verranno risolti in uno degli indirizzi IP seguenti:

- 52.127.88.59
- 52.127.92.64

È necessario aprire le porte per tutti questi indirizzi IP nel firewall per consentire il traffico in entrata e in uscita da e verso gli indirizzi per la segnalazione.  Se il firewall supporta i nomi DNS, il nome FQDN sip.pstnhub.gov.teams.microsoft.us si risolve in tutti questi indirizzi IP. 

## <a name="sip-signaling-ports"></a>Segnalazione SIP: porte

I requisiti della porta sono gli stessi per tutti gli ambienti di Office 365 in cui viene offerto il routing diretto:
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

È necessario usare le porte seguenti:

|**Traffico**|**Da**|**A**|**Porta di origine**|**Porta di destinazione**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|Proxy SIP|SBC|1024-65535|Definita nell'SBC|
SIP/TLS|SBC|Proxy SIP|Definita nell'SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Meccanismo di failover per la segnalazione SIP

SBC esegue una query DNS per risolvere sip.pstnhub.microsoft.com. In base alla posizione SBC e alle metriche delle prestazioni del centro dati, viene selezionato il centro dati principale. Se il data center principale avverte un problema, il SBC tenterà il sip2.pstnhub.microsoft.com, che viene risolto nel secondo Data Center assegnato, e, nel caso raro che i datacenter in due aree geografiche non sono disponibili, SBC riprova l'ultimo FQDN ( sip3.pstnhub.microsoft.com), che fornisce l'IP del centro dati terziario.

La tabella seguente riepiloga le relazioni tra i centri dati primari, secondari e terziari:

|**Se il data center principale è**|**EMEA**|**NOAM**|**ASIA**|
|:--- |:--- |:--- |:--- |
|Centro dati secondario (sip2.pstnhub.microsoft.com)|NOI|UE|NOI|
|Centro dati terziario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Traffico multimediale: intervalli di porte
Tieni presente che i requisiti seguenti si applicano se vuoi distribuire il routing diretto senza bypass multimediale. Per i requisiti del firewall per il bypass multimediale, fare riferimento a [piano per il bypass multimediale con routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).



Il traffico multimediale passa da e verso un servizio separato nel cloud Microsoft. Intervallo IP per il traffico multimediale:

### <a name="office-365-and-office-365-gcc-environments"></a>Ambienti Office 365 e Office 365 GCC

- 52.112.0.0/14 (indirizzi IP da 52.112.0.1 a 52.115.255.254).

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD Environment

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Ambiente Office 365 GCC High Environment

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervallo di porte (applicabile a tutti gli ambienti)
L'intervallo di porte dei processori multimediali è illustrato nella tabella seguente: 

|**Traffico**|**Da**|**A**|**Porta di origine**|**Porta di destinazione**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Media processor|SBC|49152-53247|Definita nell'SBC|
|UDP/SRTP|SBC|Media processor|Definita nell'SBC|49152-53247|

  > [!NOTE]
  > Microsoft consiglia almeno due porte per chiamata simultanea su SBC.

## <a name="media-traffic-codecs"></a>Traffico multimediale: codec

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Gamba tra SBC e cloud media processor o Microsoft teams client.
Si applica ai casi di bypass multimediale e non di bypass

L'interfaccia di routing diretto sulla gamba tra il controller di bordo della sessione e il processore cloud media (senza bypass multimediale) o tra il client teams e il SBC (se il bypass multimediale abilitato) può usare i codec seguenti:
- Bypass non multimediale (SBC to cloud media processor): SILK, G. 711, G. 722, G. 729
- Bypass multimediale (SBC per il client Teams): SILK, G. 711, G. 722, G. 729, OPUS

Puoi forzare l'uso del codec specifico nel controller di bordo della sessione escludendo i codec indesiderati dall'offerta.

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a>Segmento tra client Microsoft teams e cloud media processor
Si applica solo al caso di bypass non multimediale. Con i flussi multimediali di bypass multimediale direttamente tra team client e SBC

Sulla gamba tra il processore cloud media e il client Microsoft teams sia SILK che G. 722 used. La scelta del codec su questa gamba in base agli algoritmi Microsoft, che prendono in considerazione più parametri. 


## <a name="supported-session-border-controllers-sbcs"></a>Controller di bordo della sessione supportati (SBCs)

Microsoft supporta solo i certificati SBCs per la coppia con il routing diretto. Poiché Enterprise Voice è fondamentale per le aziende, Microsoft esegue test intensivi con il SBCs selezionato e collabora con i fornitori SBC per garantire la compatibilità dei due sistemi. 

I dispositivi convalidati sono elencati come certificati per il routing diretto di teams. I dispositivi certificati sono garantiti per funzionare in tutti gli scenari. 

Per altre informazioni sulle SBCs supportate, vedere l' [elenco dei controller di bordo della sessione certificati per il routing diretto](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Vedere anche

[Configurare Instradamento diretto](direct-routing-configure.md)



