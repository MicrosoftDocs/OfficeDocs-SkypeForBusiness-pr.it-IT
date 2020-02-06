---
title: Requisiti DNS per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: 'Riepilogo: rivedere le considerazioni DNS in questo argomento prima di implementare Skype for Business Server.'
ms.openlocfilehash: 52984c0813fb96c78ff5a1581c0722a691501ccb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802126"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisiti DNS per Skype for Business Server

**Riepilogo:** Esaminare le considerazioni DNS in questo argomento prima di implementare Skype for Business Server.

Questo articolo riguarda solo la pianificazione DNS per le distribuzioni di Skype for Business Server nella rete locale di un'organizzazione. Per Skype for business online, vedere "URL di Office 365 e intervalli di indirizzi IP [https://aka.ms/o365ips](https://aka.ms/o365ips)".

Un server DNS (Domain Name Service) mappa i nomi host (come www<span> </span> . Contoso<span></span>. com, presumibilmente un server Web, agli indirizzi IP (ad esempio 10.10.10.10). Aiuta i client e i server interdipendenti a comunicare tra loro in rete. Quando si configura un'implementazione di Skype for Business Server 2015, è necessario verificare che il mapping dei nuovi nomi di server (in genere che riflettono il ruolo che assumeranno) corrisponda agli indirizzi IP a cui sono assegnati.

Anche se all'inizio può sembrare un po' scoraggiante, il sollevamento di carichi pesanti per la pianificazione può essere eseguito usando lo [strumento di pianificazione di Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Dopo aver eseguito le domande della procedura guidata sulle caratteristiche che si prevede di usare, per ogni sito che si definisce è possibile visualizzare il report DNS nel report amministratore Edge e usare le informazioni elencate per creare i record DNS. È anche possibile apportare modifiche a molti dei nomi e degli indirizzi IP usati, per informazioni dettagliate vedere [rivedere il report DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tieni presente che puoi esportare il report amministratore Edge in un foglio di calcolo di Excel e il report DNS sarà uno dei fogli di lavoro nel file. Anche se questo strumento include funzionalità [deprecate da Skype for Business Server 2019](../../../SfBServer2019/deprecated.md), può comunque essere usato per creare un piano iniziale se queste caratteristiche non sono selezionate

Quando si installa una nuova implementazione come descritto in [creare record DNS per Skype for Business Server](../../deploy/install/create-dns-records.md) e si crea la topologia per Skype for Business Server, è possibile scegliere di usare le funzionalità DNS predefinite in Windows Server 2016 o in un pacchetto DNS di terze parti, in modo da rendere più specifiche le discussioni in questo articolo. Stiamo specificando le informazioni necessarie e il modo in cui è necessario prendere una decisione.

Gli amministratori di Skype for business, Lync e Office Communications Suite esperti potranno probabilmente trovare le tabelle seguenti utili. Se la tabella è confusa con l'utente, le sezioni o gli articoli successivi consentiranno di chiarire i concetti seguenti:

## <a name="summary-tables"></a>Tabelle di riepilogo
<a name="BK_Summary"> </a>

Le tabelle seguenti mostrano i record DNS usati da Skype for Business Server per prestare servizi agli utenti. Alcune opzioni sono facoltative perché sono necessarie solo per supportare determinate funzionalità e possono essere ignorate se non si desidera che queste funzioni siano disponibili. I record DNS necessari per l'accesso interno si trovano solo nella prima tabella e una distribuzione che consente l'accesso interno ed esterno richiederà record da entrambe le tabelle.

**Mapping DNS interni**

|Tipo di record|Valore|Risolve in|Scopo|Obbligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN del pool Front-End  <br/> *FE-pool. <span> </span>Contoso<span></span>. com*   |Indirizzi IP del server del pool Front-End  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |Bilanciamento del carico DNS dei pool Front-end. Associa il nome del pool Front-end a un set di indirizzi IP.  <br/> Vedere [distribuzione del bilanciamento del carico DNS nei pool di front-end e di Director](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | FQDN di ogni server front-end o Standard Edition in un pool o in un server autonomo <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>Contoso<span></span>. com fe03. <span> </span>Contoso<span></span>. com*   |IP corrispondente di ogni server  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Associa il nome del server al relativo indirizzo IP.   |Y   |
|A/AAAA   |Override del nome FQDN dei servizi Web interni di Enterprise pool  <br/> *Web-int.<span></span>Contoso<span></span>. com*   |HLB VIP per servizi Web interni di front end server  <br/> *192.168.21.120*   |Necessario per abilitare il traffico Web client-server, ad esempio per scaricare l'app web Skype for business. Obbligatorio anche per i client mobili.   |Y   |
|A/AAAA   |Override dei servizi Web esterni di Enterprise pool  <br/> *Web-ext.<span></span>Contoso<span></span>. com*   |HLB VIP per servizi Web esterni di front end server  <br/>*68.123.56.90*   |Necessario per abilitare il traffico Web client-server, ad esempio per scaricare l'app web Skype for business. Obbligatorio se i client mobili risolvano DNS internamente. Può essere risolto in IP o Internet IP di proxy inverso DMZ.   ||
|A/AAAA   | Nome di dominio completo di SQL Server back-end <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |Indirizzo IP del server  <br/> *192.168.11.90*   |Mappa il nome del server per un server SQL di back-end che lavora con il pool Front-end al relativo indirizzo IP   ||
|A/AAAA   |FQDN di SQL Server mirror back end server  <br/> *SQL2. <span> </span>Contoso<span></span>. com*   |Indirizzo IP del server  <br/> *192.168.11.91*   |Mappa il nome del server per un server mirror SQL back-end che lavora con il pool Front-end al relativo indirizzo IP   ||
|A/AAAA   |FQDN del pool di Director  <br/>**Nota:** Non applicabile quando si usa un server Director autonomo <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |Indirizzi IP del pool di Director  <br/> DNS LB in *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Bilanciamento del carico DNS dei server del pool di Director. Esegue il mapping del nome del pool per il pool di Director a un indirizzo IP, vedere [distribuzione del bilanciamento del carico DNS nei pool di front end e direttori](load-balancing.md#BK_FE_Dir) <br/> Un amministratore può eseguire l'autenticazione di un utente ed è facoltativo.   ||
|A/AAAA   |FQDN Director   |Indirizzo IP del server di ogni server Director   |Esegue il mapping del nome del pool per il Director a un indirizzo IP, vedere [distribuzione del bilanciamento del carico DNS nei pool di front end e direttori](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |FQDN del pool di Mediation Server   |Indirizzi IP del pool   |Il ruolo di Mediation Server è facoltativo. È possibile co-individuare i servizi forniti da un Mediation Server al server front-end o al pool. Vedere [utilizzo del bilanciamento del carico DNS nei pool di Mediation Server](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN Mediation Server   |Indirizzo IP del server   |È possibile co-individuare i servizi forniti da un Mediation Server al server front-end o al pool. Vedere [utilizzo del bilanciamento del carico DNS nei pool di Mediation Server](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del server di chat persistente   |Indirizzo IP del server di chat persistente   |È necessario un server di chat persistente per la funzionalità chat persistente ed è in caso contrario facoltativo.   ||
|A/AAAA   |lyncdiscoverinternal. * \<SipDomain\>* <br/> lyncdiscoverinternal. * <span> </span>Contoso<span></span>. com*   |Gruppo VIP o Director IP di HLB front end  <br/>  192.168.21.121  |L'individuazione automatica interna di Service1, necessaria per il supporto della mobilità. Se il DNS interno viene usato per la risoluzione per i dispositivi mobili, deve puntare all'IP esterno o alla DMZ VIP.  <br/> Per i servizi Web è necessario che HLB sia nel pool Front-end che HTTPS non possa sfruttare DNS. Per il pool di front-end o per la piscina di Director, questo dovrebbe essere risolto in un VIP di HLB o in un IP normale per un server standard o un server Director autonomo.   |Y   |
|CNAME   |lyncdiscoverinternal. * \<SipDomain\>* <br/> lyncdiscoverinternal. *<span></span>Contoso<span></span>. com*   |Nome FQDN del pool di HLB FE o FQDN Director  <br/> Web-int.<span></span>Contoso<span></span>. com   |Individuazione automatica interna di Service1 <br/> Se lo si desidera, è possibile implementarlo come CNAME invece che come record A.   ||
|A/AAAA   |SIP. * \<SipDomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Indirizzi IP del server del pool Front-End (o a ogni indirizzo IP di Director)  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |Obbligatorio per la configurazione automatica, vedere [procedura dettagliata di servizi di individuazione dei client Skype for business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Record o record che puntano ai server del pool Front-end o ai server Director nella rete interna o al servizio Access Edge quando il client è esterno   |&#x2777;  |
|A/AAAA   |ucupdates-R2. * \<SipDomain\>* <br/> ucupdates-R2. * <span> </span>Contoso<span></span>. com*  |Il pool VIP di HLB FE o il pool Director di HLB VIP o SE/Director Server IP  <br/>  192.168.21.121  |La distribuzione di questo record è facoltativa &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<SipDomain\> * <br/>Porta 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Porta 5061  |FQDN del pool Front-End  <br/>*FE-pool. <span> </span>Contoso<span></span>. com*  |Consente l'accesso automatico degli utenti interni 1 al server o al pool Front-end o al server/pool di SE che autentica e reindirizza le richieste client per l'accesso.  |&#x2777; |
|A/AAAA |sipinternal. * \<SipDomain\>* <br/>sipinternal. <span> </span> *Contoso<span></span>. com*  |FQDN del pool Front-End  <br/>_FE-pool. <span> </span>Contoso<span></span>. com_  |&#x2776; di accesso degli utenti interni  |&#x2777;  |
|SRV   | \_NTP. \_UDP. * \<SipDomain\> * <br/> \_NTP. \_UDP. <span> </span> *Contoso<span></span>. com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Origine NTP necessaria per i dispositivi Lync Phone Edition   |Questa operazione è necessaria per supportare i telefoni desktop.   |
|SRV   |\_sipfederationtls. \_TCP. * \<SipDomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  | FQDN del servizio Edge di Access <br/> EdgePool-int.<span></span>*Contoso<span></span>. com*  |Creare un record SRV per ogni dominio SIP che include client per dispositivi mobili IOS o Windows Phone.   |Supporto per i client per dispositivi mobili   |
|A/AAAA   |URL di amministratore  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Gruppo VIP di HLB FE  <br/> 192.168.21.121   |Pannello di controllo di Skype for Business Server, vedere [URL semplici](dns.md#BK_Simple)  ||
|A/AAAA   |URL di riunione  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Gruppo VIP di HLB FE  <br/> 192.168.21.121   |Riunioni online, vedere [URL semplici](dns.md#BK_Simple)  ||
|A/AAAA   |URL di accesso esterno  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Gruppo VIP di HLB FE  <br/> 192.168.21.121   |Conferenze telefoniche con accesso esterno, Vedi [URL semplici](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN dei servizi Web interni  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |Gruppo VIP di HLB FE  <br/> 192.168.21.121   |Servizio Web Skype for business usato da Skype for Business Web App   ||
|A/AAAA   |FQDN del pool di server Office Web Apps  <br/> OWA. <span> </span>Contoso<span></span>. com   | Indirizzo VIP del pool di server Office Web Apps <br/> 192.168.1.5   |Definisce il nome di dominio completo del pool di server Office Web Apps   ||
|A/AAAA   | FQDN Web interno <br/> Web-int.<span></span>Contoso<span></span>. com   | Indirizzo VIP del pool Front-End <br/> 192.168.21.121   |Definisce il nome di dominio completo Web interno usato da Skype for Business Web App  <br/> Se si usa il bilanciamento del carico DNS in questo pool, il pool di front end e la Web farm interna non possono avere lo stesso nome FQDN.   ||

&#x2776; usato da un client per individuare il front-end server o il pool Front End, quindi essere autenticato e firmato come utente. Ulteriori dettagli su questo argomento sono illustrati in [procedura dettagliata dei servizi di accesso ai client Skype for business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; questa operazione è necessaria solo per supportare i client legacy prima di Lync 2013 e dei telefoni desktop.

&#x2778; nella situazione in cui è attivato un dispositivo Unified Communications, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il servizio Web di aggiornamento del dispositivo che ospita il server e di ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono le informazioni sul server anche se il provisioning in banda è la prima volta che si accede a un utente.

Il diagramma seguente mostra un esempio che include sia i record DNS interni che esterni e molti dei record visualizzati nelle tabelle circostanti:

**Diagramma reticolare Edge con indirizzi IPv4 pubblici**

![esempio di diagramma reticolare DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapping DNS di rete perimetrale (interfacce interne ed esterne)**

|Tipo di record|Valore|Risolve in|Scopo|Obbligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del pool di Edge interno  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |Indirizzi IP del pool di bordi con rivestimento interno  <br/> 172.25.33.10, 172.25.33.11   |Indirizzi IP dell'interfaccia interna del pool di Edge consolidato   |Y   |
|A/AAAA   |FQDN del server perimetrale  <br/>*Cons-1. <span> </span>Contoso<span></span>. com*  |IP del server con rivestimento interno per un server nel pool di Edge  <br/> 172.25.33.10   |Creare un record per ogni server nel pool con il nome di dominio completo del server che punta al relativo IP del nodo del server interno nel pool, vedere [bilanciamento del carico DNS nei pool di Edge Server](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |FQDN del pool di servizi Edge di Access  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Indirizzi IP esterni del pool di servizi di Access Edge  <br/> 131.107.16.10, 131.107.16.11   |Il servizio Access Edge offre un unico punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.   |Y   |
|A/AAAA   |FQDN del pool di servizi Web Conferencing Edge  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Indirizzi IP esterni per servizi Web Conferencing Edge  <br/> 131.107.16.90, 131.107.16.91   |Il servizio Web Conferencing Edge consente agli utenti esterni di partecipare a riunioni ospitate nell'ambiente interno di Skype for Business Server.   |Y   |
|A/AAAA   |*AV.\<SIP-Domain\> * FQDN del pool <br/>*AV1. <span> </span>Contoso<span></span>. com*  |Indirizzi IP esterni A/V Edge  <br/> 131.107.16.170, 131.107.16.171   |L'A/V Edge Services rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni.   |Y   |
|CNAME   |SIP. * \<SipDomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |FQDN del pool di Access Edge esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Individua il pool di Edge Server. Vedere [la procedura dettagliata di servizi di individuazione dei client Skype for business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_TLS. * \<SipDomain\> * <br/>\_SIP. \_TLS. <span> </span> *Contoso<span></span>. com*  |FQDN di Access Edge esterno  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Usato per l'accesso degli utenti esterni. Vedere [la procedura dettagliata di servizi di individuazione dei client Skype for business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_TCP. * \<SipDomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  |FQDN di Access Edge esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Usato per la connettività di messaggistica istantanea pubblica e della Federazione   |&#x2776;  |
|SRV   |\_server XMPP. \_TCP. *<SipDomain\> * <br/>\_server XMPP. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN di Access Edge esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Il servizio proxy XMPP accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federativi XMPP configurati.   |Y, per distribuire la Federazione, altrimenti facoltativa  <br/> Non disponibile in Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<SipDomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN di Access Edge esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Per supportare il servizio di notifica push e il servizio notifica push Apple, è possibile creare un record SRV per ogni dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN dei servizi Web del pool Front-End esterno  <br/>*Web-ext.<span></span>Contoso<span></span>. com*  |Indirizzo IP pubblico proxy inverso, proxy per i servizi Web esterni VIP per il pool di front-end &#x2776; <br/> proxy 131.107.155.1 a 192.168.21.120   |Interfaccia esterna del pool Front End usato da Skype for Business Web App   |Y   |
|A/AAAA/CNAME   |Lyncdiscover. * \<SipDomain\>* <br/> Lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Invertire l'indirizzo IP pubblico del proxy, si risolve in VIP Servizi Web esterni per il pool di Director, se è presente o per il pool Front-end se non si dispone di un Director &#x2777; <br/> proxy 131.107.155.1 a 192.168.21.120   | Record esterno per l'individuazione automatica dei client, usato anche da mobilità, Skype for Business Web App e Scheduler Web App, risolto dal server proxy inverso <br/> Per supportare il servizio di notifica push e il servizio notifica push Apple, è possibile creare un record SRV per ogni dominio SIP che include i client Microsoft Lync mobile. 3  |Y   |
|A/AAAA   |soddisfano. * \<SipDomain\>* <br/> soddisfano. * <span> </span>Contoso<span></span>. com*  |Indirizzo IP pubblico reverse proxy, risolto nell'interfaccia Web esterna per il pool Front-End  <br/> proxy 131.107.155.1 a 192.168.21.120   |Proxy per il servizio Web Skype for business  <br/> Vedere [URL semplici](dns.md#BK_Simple)  |Y   |
|A/AAAA   |accesso esterno.*\<SipDomain\>* <br/> accesso esterno.*<span></span><span></span>contoso. com*  |Indirizzo IP pubblico proxy inverso, proxy per l'interfaccia Web esterna per il pool Front-End  <br/> proxy 131.107.155.1 a 192.168.21.120   |Proxy per il servizio Web Skype for business  <br/> Vedere [URL semplici](dns.md#BK_Simple)  |Y   |
|A/AAAA   |FQDN del pool di server Office Web Apps  <br/> OWA. <span> </span>Contoso<span></span>. com   | Indirizzo IP pubblico proxy inverso, proxy per l'interfaccia Web esterna per il server Office Web Apps <br/> proxy 131.107.155.1 a 192.168.1.5   | Indirizzo VIP del pool di server Office Web Apps <br/> 192.168.1.5   |Definisce il nome di dominio completo del pool di server Office Web Apps   |

&#x2776; necessario per distribuire la Federazione, altrimenti facoltativa.

&#x2777; usato da un client per individuare il front-end server o il pool Front End, quindi essere autenticato e firmato come utente.

&#x2778; questo requisito si applica solo ai client su dispositivi mobili Apple o Microsoft based. I dispositivi Android e Nokia Symbian non usano la notifica push.

 Per altre informazioni su Edge Server e reti perimetrali, vedere il contenuto della [pianificazione DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) perimetrale.

> [!IMPORTANT]
> Skype for Business Server supporta l'uso di indirizzi IPv6. Per altre informazioni, Vedi [piano per IPv6 in Skype for business](ipv6.md) .

> [!IMPORTANT]
> Per altre informazioni sui nomi di dominio completi, vedere [nozioni di base su DNS](basics.md).

**Split Brain DNS** 
 <a name="BK_split"> </a>

Split Brain DNS è una configurazione DNS in cui sono presenti due aree DNS con lo stesso spazio dei nomi. La prima zona DNS gestisce le richieste interne, mentre la seconda zona DNS gestisce le richieste esterne, come indicato in queste tabelle. Per ulteriori informazioni, vedere [DNS con suddivisione in cervello](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerazioni ibride
<a name="BK_Hybrid"> </a>

Se si prevede di avere alcuni utenti ospitati online e alcuni residenti in locale, vedere l'articolo sulla pianificazione della connettività ibrida [Skype for Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). È necessario configurare DNS come normale per Skype for Business Server 2015 e aggiungere anche altri record DNS.

Dovresti anche fare riferimento a "URL di Office 365 e intervalli [https://aka.ms/o365ips](https://aka.ms/o365ips) di indirizzi IP" per verificare che gli utenti avranno accesso alle risorse online di cui avranno bisogno.

## <a name="simple-urls"></a>URL semplici
<a name="BK_Simple"> </a>

Un URL (Uniform Resource Locator) è un riferimento a una risorsa Web che specifica la posizione in una rete di computer e un protocollo usato per recuperarlo.

Skype for Business Server supporta l'uso di tre URL "semplici" per i servizi di Access:

- L' **incontro** viene usato come URL di base per tutte le conferenze nel sito. Un esempio di URL semplice Meet è https:<span></span>//<span></span>meet. <span> </span>Contoso<span></span>. com. Un URL per una riunione specifica potrebbe essere https:<span></span>//<span></span>meet. <span> </span>Contoso<span></span>. com/_nomeutente_/7322994.

    Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e semplici da comunicare.

- L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con **chiamata in ingresso** . In questa pagina vengono visualizzati i numeri di accesso esterno per conferenze con le lingue disponibili, le informazioni sulla conferenza assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in conferenza e supportano la gestione del numero di identificazione personale ( PIN) e informazioni di conferenza assegnate. L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie. Un esempio dell'URL semplice con accesso esterno è https://<span></span>dialin. <span> </span>Contoso<span></span>. com.

- L' **amministratore** consente l'accesso rapido al pannello di controllo di Skype for Business Server. Da qualsiasi computer all'interno del firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Skype for Business Server digitando l'URL semplice amministratore in un browser. L'URL semplice amministratore è interno dell'organizzazione. Un esempio dell'URL semplice di amministrazione è https://<span></span>admin. <span> </span>Contoso<span></span>. com.

Gli URL semplici vengono discussi in modo più dettagliato ai [requisiti DNS per gli URL semplici in Skype for Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS per ruolo del server
<a name="BK_Servers"> </a>

È possibile impostare i nomi di questi pool e server come si vuole, ma renderli memorabili e rispecchiarne la funzione nel sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Record DNS per singoli server o pool

Questi requisiti di record generici si applicano a qualsiasi ruolo del server usato da Skype for business. Un pool è un set di server che gestiscono gli stessi servizi che collaborano per gestire le richieste client indirizzate tramite un servizio di bilanciamento del carico. Per informazioni dettagliate, vedere [requisiti di bilanciamento del carico per Skype for business](load-balancing.md)

**Requisiti per i record DNS per i ruoli server/pool (presume il bilanciamento del carico DNS)**

|Scenario di distribuzione|Requisito DNS|
|:-----|:-----|
|Un server:  <br/> Chat persistente, Director, Mediation Server, Front End Server   |Un record interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.  <br/> ServerRole. <span> </span>Contoso<span></span>. com 10.10.10.0   |
|Pool  <br/> Chat persistente, Director, Edge Server, Mediation Server, front-end   |Un record interno che risolve il nome di dominio completo (FQDN) di ogni nodo del server nel pool con l'indirizzo IP.  <br/>**Esempio** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>. com 10.10.10.2  <br/> Più record interni che risolvono il nome di dominio completo (FQDN) del pool agli indirizzi IP dei nodi del server nel pool.  <br/>**Esempio** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Argomenti DNS specifici per Edge Server

 Per pianificare la distribuzione di Edge Server, rivedere il [piano per le distribuzioni di Edge Server in Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e la [pianificazione DNS avanzata di Edge Server per Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , che include le sezioni seguenti

- [Ripristino di emergenza DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configurazione automatica senza DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Procedura dettagliata di individuazione dei servizi per i client Skype for business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


