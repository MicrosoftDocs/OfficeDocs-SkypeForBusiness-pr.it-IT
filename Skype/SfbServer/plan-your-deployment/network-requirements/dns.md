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
description: 'Riepilogo: esaminare le considerazioni relative a DNS in questo argomento prima di implementare Skype for Business Server.'
ms.openlocfilehash: 33c5e18c6bc8d5a29b0e4a6fa447fbde02028556
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982811"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisiti DNS per Skype for Business Server

**Riepilogo:** Leggere le considerazioni sul DNS in questo argomento prima di implementare Skype for Business Server.

In questo articolo viene indirizzata solo la pianificazione DNS per le distribuzioni di Skype for Business Server in una rete locale dell'organizzazione. Per Skype for business online, vedere "URL di Office 365 e intervalli di indirizzi IP [https://aka.ms/o365ips](https://aka.ms/o365ips)" all'indirizzo.

Un server DNS (Domain Name Service) esegue il mapping dei nomi host (<span> </span> come www. Contoso<span></span>. com, presumibilmente un server Web, a indirizzi IP (ad esempio, 10.10.10.10). Consente ai client e ai server interdipendenti di comunicare tra loro sulla rete. Quando si configura un'implementazione di Skype for Business Server 2015, è necessario verificare che il mapping dei nuovi nomi di server (che in genere riflettono il ruolo da intraprendere) corrisponda agli indirizzi IP a cui sono assegnati.

Anche se questo può sembrare un po' scoraggiante all'inizio, il sollevamento di carichi pesanti per la pianificazione può essere effettuato utilizzando lo [strumento di pianificazione di Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=50357). Dopo aver completato le domande della procedura guidata sulle caratteristiche che si intende utilizzare, per ogni sito definito è possibile visualizzare il report DNS all'interno del rapporto di amministrazione del server perimetrale e utilizzare le informazioni riportate di seguito per creare i record DNS. Per ulteriori informazioni, vedere [rivedere il report DNS](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)....... Tenere presente che è possibile esportare il report amministratore Edge in un foglio di calcolo di Excel e il report DNS sarà uno dei fogli di lavoro nel file. Anche se questo strumento include funzionalità [deprecate da Skype for Business Server 2019](../../../SfBServer2019/deprecated.md), è comunque possibile utilizzarlo per creare un piano iniziale se tali caratteristiche non sono selezionate

Quando si installa una nuova implementazione come descritto in [create DNS Records for Skype for Business Server](../../deploy/install/create-dns-records.md) e si crea la topologia per Skype for Business Server, si riconosce che è possibile scegliere di utilizzare le funzionalità DNS incorporate in Windows Server 2016 o un pacchetto DNS di terze parti, in modo da mantenere le discussioni in questo articolo generale piuttosto che specifiche. Il dettaglio è necessario e il modo in cui si soddisfano le esigenze è la decisione da prendere.

Gli amministratori di Skype for business, Lync e Office Communications Suite con esperienza troveranno probabilmente utili le tabelle seguenti. Se la tabella è confusa con l'utente, le sezioni o gli articoli successivi forniranno luce sui concetti seguenti:

## <a name="summary-tables"></a>Tabelle di riepilogo
<a name="BK_Summary"> </a>

Nelle tabelle seguenti vengono illustrati i record DNS utilizzati da Skype for Business Server per fornire servizi agli utenti. Alcuni sono facoltativi in quanto sono necessari solo per supportare determinate funzionalità e possono essere ignorati se tali caratteristiche non sono desiderate. I record DNS necessari per l'accesso interno sono disponibili solo nella prima tabella e una distribuzione che consente l'accesso interno ed esterno avrà bisogno di record da entrambe le tabelle.

**Mapping DNS interni**

|Tipo di record|Valore|Viene risolto in|Scopo|Obbligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |FQDN del pool Front End  <br/> *FE-pool. <span> </span>Contoso<span></span>. com*   |Indirizzi IP del server del pool Front End  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |Bilanciamento del carico DNS dei pool Front end. Esegue il mapping del nome del pool Front end a un set di indirizzi IP.  <br/> Vedere [distribuzione del bilanciamento del carico DNS in pool Front end e pool](load-balancing.md#BK_FE_Dir) di server Director  |Y   |
|A/AAAA   | FQDN di ogni server front end server o Standard Edition in un pool o in un server autonomo <br/>  *FE01. <span> </span>contoso. <span> </span>FE02 com. <span> </span>Contoso<span></span>. com fe03. <span> </span>Contoso<span></span>. com*   |Indirizzo IP corrispondente di ogni server  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Esegue il mapping del nome del server al relativo indirizzo IP.   |Y   |
|A/AAAA   |FQDN dell'override dei servizi Web interni del pool Enterprise  <br/> *Web-int.<span></span>Contoso<span></span>. com*   |HLB VIP per i servizi Web interni di front end server  <br/> *192.168.21.120*   |Necessario per abilitare il traffico Web client-server, ad esempio il download di Skype for Business Web App. Necessario anche per i client mobili.   |Y   |
|A/AAAA   |NOME FQDN dei servizi Web esterni del pool Enterprise  <br/> *Web-ext.<span></span>Contoso<span></span>. com*   |HLB VIP per i servizi Web esterni di front end server  <br/>*68.123.56.90*   |Necessario per abilitare il traffico Web client-server, ad esempio il download di Skype for Business Web App. Obbligatorio se i client mobili risolvono internamente il DNS. È in grado di risolvere la DMZ IP o Internet IP proxy inverso.   ||
|A/AAAA   | FQDN SQL Server back-end server <br/> *SQL1. <span> </span>Contoso<span></span>. com*   |Indirizzo IP del server  <br/> *192.168.11.90*   |Esegue il mapping del nome del server per un SQL Server back-end che utilizza il pool Front end con il relativo indirizzo IP   ||
|A/AAAA   |FQDN SQL Server mirror server back-end  <br/> *SQL2. <span> </span>Contoso<span></span>. com*   |Indirizzo IP del server  <br/> *192.168.11.91*   |Esegue il mapping del nome del server per un server mirror SQL back-end che utilizza il pool Front end con il relativo indirizzo IP   ||
|A/AAAA   |FQDN del pool di server Director  <br/>**Nota:** Non applicabile quando si utilizza un server Director autonomo <br/> *DirPool. <span> </span>Contoso<span></span>. com*   |Indirizzi IP del pool di server Director  <br/> DNS LB to *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Bilanciamento del carico DNS dei server del pool di Director. Esegue il mapping del nome del pool per il pool di server Director a un indirizzo IP, vedere [Deployment del bilanciamento del carico DNS in pool Front end e pool](load-balancing.md#BK_FE_Dir) di server Director <br/> Un amministratore può eseguire l'autenticazione di un utente ed è facoltativo.   ||
|A/AAAA   |FQDN del server Director   |Indirizzo IP del server di ogni server Director   |Esegue il mapping del nome del pool per il server Director a un indirizzo IP, vedere [Deploying DNS Load Balancing in pool Front end e pool](load-balancing.md#BK_FE_Dir) di server Director  ||
|A/AAAA   |FQDN del pool di Mediation Server   |Indirizzi IP del pool   |Il ruolo Mediation Server è facoltativo. È possibile co-individuare i servizi forniti da un Mediation Server al server front-end o al pool. Vedere [utilizzo del bilanciamento del carico DNS nei pool di Mediation Server](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN Mediation Server   |Indirizzo IP del server   |È possibile co-individuare i servizi forniti da un Mediation Server al server front-end o al pool. Vedere [utilizzo del bilanciamento del carico DNS nei pool di Mediation Server](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del server Chat persistente   |Indirizzo IP del server Chat persistente   |Un server Chat persistente è necessario per la funzionalità chat persistente ed è altrimenti facoltativo.   ||
|A/AAAA   |LyncdiscoverInternal. * \<SipDomain\>* <br/> LyncdiscoverInternal. * <span> </span>Contoso<span></span>. com*   |VIP del pool Front End di HLB o IP del server Director  <br/>  192.168.21.121  |Service1 interno di individuazione automatica, necessario per il supporto per dispositivi mobili. Se il DNS interno viene utilizzato per la risoluzione dei dispositivi mobili, deve puntare all'IP esterno o al VIP DMZ.  <br/> Per i servizi Web è necessario che HLB nel pool Front end come HTTPS non può sfruttare DNS. Per il pool Front end o il pool di server Director, questo dovrebbe essere risolto in un VIP di HLB o un IP normale per un server Standard Edition o per un amministratore autonomo.   |Y   |
|CNAME   |LyncdiscoverInternal. * \<SipDomain\>* <br/> LyncdiscoverInternal. *<span></span>Contoso<span></span>. com*   |FQDN del pool del FE di HLB o FQDN del Director  <br/> Web-int.<span></span>Contoso<span></span>. com   |Service1 interno di individuazione automatica <br/> Se lo si desidera, è possibile implementarlo come CNAME anziché come record A.   ||
|A/AAAA   |SIP. * \<SipDomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |Indirizzi IP del server del pool Front End (o a un indirizzo IP di ogni Director)  <br/>  DNS LB to *192.168.21.122 192.168.21.123 192.168.21.124*   |Necessario per la configurazione automatica, vedere [Walkthrough de clients Skype for business che individua i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Record o record che puntano ai server del pool Front end o ai server Director sulla rete interna o al servizio Access Edge quando il client è esterno   |&#x2777;  |
|A/AAAA   |ucupdates-R2. * \<SipDomain\>* <br/> ucupdates-R2. * <span> </span>Contoso<span></span>. com*  |Il VIP del pool di HLB FE o il VIP del pool di HLB o il SE/server Director IP  <br/>  192.168.21.121  |La distribuzione di questo record è facoltativa &#x2778;  ||
|SRV   |\_sipinternaltls. \_TCP. * \<SipDomain\> * <br/>Porta 5061 <br/>\_sipinternaltls. \_TCP. * <span> </span>Contoso<span></span>. com* <br/>Porta 5061  |FQDN del pool Front End  <br/>*FE-pool. <span> </span>Contoso<span></span>. com*  |Abilita l'accesso automatico dell'utente interno 1 al server/pool Front end o al server/pool che autentica e reindirizza le richieste client per l'accesso.  |&#x2777; |
|A/AAAA |sipinternal. * \<SipDomain\>* <br/>sipinternal. <span> </span> *Contoso<span></span>. com*  |FQDN del pool Front End  <br/>_FE-pool. <span> </span>Contoso<span></span>. com_  |&#x2776; di accesso degli utenti interni  |&#x2777;  |
|SRV   | \_NTP. \_UDP. * \<SipDomain\> * <br/> \_NTP. \_UDP. <span> </span> *Contoso<span></span>. com*  |FQDN TimeServer  <br/> north-america.pool.ntp.org   |Origine NTP necessaria per i dispositivi Lync Phone Edition   |Questo è necessario per supportare i telefoni desktop.   |
|SRV   |\_sipfederationtls. \_TCP. * \<SipDomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  | FQDN del servizio Access Edge <br/> EdgePool-int.<span></span>*Contoso<span></span>. com*  |Creare un record SRV per ogni dominio SIP con client mobili IOS o Windows Phone.   |Per il supporto dei client per dispositivi mobili   |
|A/AAAA   |URL di amministrazione  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP del pool di HLB FE  <br/> 192.168.21.121   |Pannello di controllo di Skype for Business Server, vedere [Simple URLs](dns.md#BK_Simple)  ||
|A/AAAA   |URL di riunione  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP del pool di HLB FE  <br/> 192.168.21.121   |Riunioni online, vedere [Simple URLs](dns.md#BK_Simple)  ||
|A/AAAA   |URL di accesso esterno  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP del pool di HLB FE  <br/> 192.168.21.121   |Conferenze telefoniche con accesso esterno, vedere [Simple URLs](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN dei servizi Web interni  <br/>*Web-int.<span></span>Contoso<span></span>. com*  |VIP del pool di HLB FE  <br/> 192.168.21.121   |Servizio Web Skype for business utilizzato da Skype for Business Web App   ||
|A/AAAA   |FQDN del pool di server Office Web Apps  <br/> OWA. <span> </span>Contoso<span></span>. com   | Indirizzo VIP del pool di server Office Web Apps <br/> 192.168.1.5   |Definisce il nome di dominio completo del pool di server Office Web Apps   ||
|A/AAAA   | FQDN Web interno <br/> Web-int.<span></span>Contoso<span></span>. com   | Indirizzo VIP del pool Front End <br/> 192.168.21.121   |Definisce il nome di dominio completo Web interno utilizzato da Skype for Business Web App  <br/> Se si utilizza il bilanciamento del carico DNS in questo pool, il pool Front end e la Web farm interna non possono avere lo stesso nome di dominio completo.   ||

&#x2776; utilizzata da un client per individuare il front end server o il pool Front end ed essere autenticato e firmato come utente. Maggiori dettagli su questo argomento sono in [procedura dettagliata dei client Skype for business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype).

&#x2777; questo è necessario solo per supportare i client legacy precedenti a Lync 2013 e i telefoni desktop.

&#x2778; nella situazione in cui è attivato un dispositivo di comunicazione unificata, ma un utente non ha mai effettuato l'accesso al dispositivo, il record A consente al dispositivo di individuare il servizio Web di aggiornamento dei dispositivi che ospita il server e di ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono le informazioni del server tramite provisioning di tipo in-band al primo accesso di un utente.

Nel diagramma seguente viene illustrato un esempio in cui sono inclusi record DNS interni ed esterni e molti dei record riportati nelle tabelle circostanti:

**Diagramma di rete perimetrale con indirizzi IPv4 pubblici**

![esempio di diagramma di rete DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapping DNS di rete perimetrale (interfacce sia interne che esterne)**

|Tipo di record|Valore|Viene risolto in|Scopo|Obbligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del pool di server perimetrali interni  <br/>*EdgePool-int.<span></span>Contoso<span></span>. com*  |Indirizzi IP del pool di server perimetrali rivolti all'interno  <br/> 172.25.33.10, 172.25.33.11   |Indirizzi IP dell'interfaccia interna del pool di server perimetrale consolidato   |Y   |
|A/AAAA   |FQDN del server perimetrale  <br/>*Cons-1. <span> </span>Contoso<span></span>. com*  |IP del server con rivolto interno per un server nel pool perimetrale  <br/> 172.25.33.10   |Creare un record per ogni server del pool con il nome di dominio completo del server che punta al relativo IP del nodo del server interno nel pool, vedere [DNS Load Balancing nei pool di server perimetrali](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |FQDN del pool di servizi Access Edge  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Indirizzi IP esterni del pool di servizi di Access Edge  <br/> 131.107.16.10, 131.107.16.11   |Questo servizio fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) sia in ingresso che in uscita.   |Y   |
|A/AAAA   |FQDN del pool di servizi Web Conferencing Edge  <br/>*Webcon1. <span> </span>Contoso<span></span>. com*  |Indirizzi IP esterni del servizio Web Conferencing Edge  <br/> 131.107.16.90, 131.107.16.91   |Il servizio Web Conferencing Edge consente agli utenti esterni di partecipare alle riunioni ospitate nell'ambiente interno di Skype for Business Server.   |Y   |
|A/AAAA   |*AV.\<SIP-Domain\> * FQDN del pool <br/>*AV1. <span> </span>Contoso<span></span>. com*  |Indirizzi IP esterni A/V Edge  <br/> 131.107.16.170, 131.107.16.171   |Il servizio A/V Edge rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni.   |Y   |
|CNAME   |SIP. * \<SipDomain\>* <br/> SIP. * <span> </span>Contoso<span></span>. com*  |FQDN del pool di Access Edge esterni  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Individuare il pool di server perimetrali. Vedere [la procedura dettagliata dei client Skype for business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_SIP. \_TLS. * \<SipDomain\> * <br/>\_SIP. \_TLS. <span> </span> *Contoso<span></span>. com*  |FQDN del perimetro di accesso esterno  <br/>_Access1. <span> </span>Contoso<span></span>. com_  |Utilizzato per l'accesso degli utenti esterni. Vedere [la procedura dettagliata dei client Skype for business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_TCP. * \<SipDomain\> * <br/>\_sipfederationtls. \_TCP. <span> </span> *Contoso<span></span>. com*  |FQDN del perimetro di accesso esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Utilizzato per la Federazione e la connettività per la messaggistica istantanea pubblica   |&#x2776;  |
|SRV   |\_XMPP-server. \_TCP. *<SipDomain\> * <br/>\_XMPP-server. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN del perimetro di accesso esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Il servizio proxy XMPP accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federati XMPP configurati.   |Y, per distribuire la Federazione, altrimenti facoltativa  <br/> Non disponibile in Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_TCP. * \<SipDomain\> * <br/>\_sipfederationtls. \_TCP. * <span> </span>Contoso<span></span>. com*  |FQDN del perimetro di accesso esterno  <br/>*Access1. <span> </span>Contoso<span></span>. com*  |Per supportare il servizio di notifica push e il servizio di notifica push di Apple, è necessario creare un record SRV per ogni dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN dei servizi Web del pool Front End esterno  <br/>*Web-ext.<span></span>Contoso<span></span>. com*  |Indirizzo IP pubblico proxy inverso, proxy per i servizi Web esterni VIP per il pool Front End &#x2776; <br/> proxy di 131.107.155.1 a 192.168.21.120   |Interfaccia esterna del pool Front end utilizzata da Skype for Business Web App   |Y   |
|A/AAAA/CNAME   |Lyncdiscover. * \<SipDomain\>* <br/> Lyncdiscover. * <span> </span>Contoso<span></span>. com*  |Indirizzo IP pubblico del proxy inverso, viene risolto nel VIP dei servizi Web esterni per il pool di server Director, se presente, o per il pool Front end se non si dispone di un Director &#x2777; <br/> proxy di 131.107.155.1 a 192.168.21.120   | Record esterno per l'individuazione automatica del client, utilizzato anche da Mobility, Skype for Business Web App e Scheduler Web App, risolto dal server proxy inverso <br/> Per supportare il servizio di notifica push e il servizio di notifica push di Apple, è necessario creare un record SRV per ogni dominio SIP con client Microsoft Lync mobile. 3   |Y   |
|A/AAAA   |soddisfare. * \<SipDomain\>* <br/> soddisfare. * <span> </span>Contoso<span></span>. com*  |Indirizzo IP pubblico del proxy inverso, viene risolto nell'interfaccia Web esterna per il pool Front End  <br/> proxy di 131.107.155.1 a 192.168.21.120   |Proxy per il servizio Web di Skype for business  <br/> Visualizzare gli [URL semplici](dns.md#BK_Simple)  |Y   |
|A/AAAA   |accesso esterno.*\<SipDomain\>* <br/> accesso esterno.*<span></span><span></span>contoso. com*  |Indirizzo IP pubblico proxy inverso, proxy all'interfaccia Web esterna per il pool Front End  <br/> proxy di 131.107.155.1 a 192.168.21.120   |Proxy per il servizio Web di Skype for business  <br/> Visualizzare gli [URL semplici](dns.md#BK_Simple)  |Y   |
|A/AAAA   |FQDN del pool di server Office Web Apps  <br/> OWA. <span> </span>Contoso<span></span>. com   | Indirizzo IP pubblico proxy inverso, proxy all'interfaccia Web esterna per il server Office Web Apps <br/> proxy di 131.107.155.1 a 192.168.1.5   | Indirizzo VIP del pool di server Office Web Apps <br/> 192.168.1.5   |Definisce il nome di dominio completo del pool di server Office Web Apps   |

&#x2776; necessario per distribuire la Federazione, altrimenti facoltativa.

&#x2777; utilizzata da un client per individuare il front end server o il pool Front end ed essere autenticato e firmato come utente.

&#x2778; questo requisito si applica solo ai client su dispositivi mobili basati su Apple o Microsoft. I dispositivi Android e Nokia Symbian non utilizzano la notifica push.

 Per ulteriori informazioni sui server perimetrali e sulle reti di bordo, vedere The Edge Server [DNS Planning](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) content.

> [!IMPORTANT]
> Skype for Business Server supporta l'utilizzo dell'indirizzamento IPv6. Per ulteriori informazioni, vedere [Plan for IPv6 in Skype for business](ipv6.md) .

> [!IMPORTANT]
> Per ulteriori informazioni sugli FQDN, vedere [DNS nozioni di base](basics.md).

****
 DNS<a name="BK_split"> </a> Split Brain

Il DNS split brain è una configurazione DNS in cui si dispone di due aree DNS con lo stesso spazio dei nomi. La prima area DNS gestisce le richieste interne, mentre la seconda zona DNS gestisce le richieste esterne, come indicato in queste tabelle. Per ulteriori informazioni, vedere [DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerazioni ibride
<a name="BK_Hybrid"> </a>

Se si prevede di avere alcuni utenti ospitati online e alcuni ospitati in locale, fare riferimento all'articolo sulla pianificazione della connettività ibrida di [Skype for Business server 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json). Sarà necessario configurare DNS come normale per Skype for Business Server 2015 e aggiungere anche altri record DNS.

È inoltre consigliabile fare riferimento a "URL e intervalli di indirizzi IP di Office [https://aka.ms/o365ips](https://aka.ms/o365ips) 365" per confermare che gli utenti avranno accesso alle risorse online di cui avranno bisogno.

## <a name="simple-urls"></a>URL semplici
<a name="BK_Simple"> </a>

Un URL (Uniform Resource Locator) è un riferimento a una risorsa Web che specifica la posizione in una rete di computer e un protocollo utilizzato per recuperarla.

Skype for Business Server supporta l'utilizzo di tre URL "semplici" per accedere ai servizi:

- La **riunione** viene utilizzata come URL di base per tutte le conferenze del sito. Un esempio di URL semplice Meet è https:<span></span>//<span></span>meet. <span> </span>Contoso<span></span>. com. Un URL per una riunione specifica potrebbe essere https:<span></span>//<span></span>meet. <span> </span>Contoso<span></span>. com/_username_/7322994.

    Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facilmente comunicabili.

- Accesso esterno consente di accedere alla pagina Web delle impostazioni per le conferenze telefoniche **con chiamata in** ingresso. In questa pagina vengono visualizzati i numeri di accesso esterno alle conferenze con le lingue disponibili, le informazioni sulle conferenze assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in-Conference e che supportano la gestione del numero di identificazione personale ( PIN) e informazioni per le conferenze assegnate. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN. Un esempio di URL semplice con accesso esterno è https://<span></span>dialin. <span> </span>Contoso<span></span>. com.

- L' **amministratore** consente di accedere rapidamente al pannello di controllo di Skype for Business Server. Da qualsiasi computer all'interno dei firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Skype for Business Server digitando l'URL semplice di amministrazione in un browser. L'URL semplice di amministrazione è interno all'organizzazione. Un esempio di URL semplice di amministrazione è https://<span></span>admin. <span> </span>Contoso<span></span>. com.

Gli URL semplici vengono descritti in modo più dettagliato nei [requisiti DNS per gli URL semplici in Skype for Business Server](simple-urls.md).

## <a name="dns-by-server-role"></a>DNS per ruolo del server
<a name="BK_Servers"> </a>

È possibile impostare i nomi di questi pool e server come si desidera, ma renderli memorabili e rifletterne la funzione nel sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Record DNS per singoli server o pool

Questi requisiti dei record generici si applicano a qualsiasi ruolo del server utilizzato da Skype for business. Un pool è un insieme di server che eseguono gli stessi servizi che interagiscono per gestire le richieste dei client indirizzate tramite un servizio di bilanciamento del carico. Per informazioni dettagliate, vedere [requisiti per il bilanciamento del carico per Skype for business](load-balancing.md)

**Requisiti dei record DNS per i ruoli server/pool (presume il bilanciamento del carico DNS)**

|Scenario di distribuzione|Requisito DNS|
|:-----|:-----|
|Un server:  <br/> Chat persistente, Director, Mediation Server, Front End Server   |Un record A interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.  <br/> ServerRole. <span> </span>Contoso<span></span>. com 10.10.10.0   |
|Pool  <br/> Chat persistente, Director, server perimetrale, Mediation Server, front-end   |Un record interno che risolve il nome di dominio completo (FQDN) di ogni nodo del server nel pool al relativo indirizzo IP.  <br/>**Esempio** <br/> ServerRole01. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerRole02. <span> </span>Contoso<span></span>. com 10.10.10.2  <br/> Più record interni A che consente di risolvere il nome di dominio completo (FQDN) del pool negli indirizzi IP dei nodi server nel pool.  <br/>**Esempio** <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.1  <br/> ServerPool. <span> </span>Contoso<span></span>. com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Argomenti DNS specifici del server perimetrale

 Per pianificare la distribuzione di server perimetrali, esaminare il [piano per le distribuzioni di server perimetrali in Skype for Business server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e la [pianificazione DNS avanzata del server perimetrale per Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) , che include le sezioni seguenti

- [Ripristino di emergenza DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configurazione automatica senza DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS split-brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Procedura dettagliata dei client Skype for business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


