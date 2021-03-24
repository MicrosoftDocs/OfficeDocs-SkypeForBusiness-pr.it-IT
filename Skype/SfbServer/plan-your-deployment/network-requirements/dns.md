---
title: Requisiti DNS per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: esaminare le considerazioni sul DNS in questo argomento prima di implementare Skype for Business Server.'
ms.openlocfilehash: ee69019df0c137fa4cd64260bd804769747ff2a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096240"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>Requisiti DNS per Skype for Business Server

**Riepilogo:** Leggere le considerazioni sul DNS in questo argomento prima di implementare Skype for Business Server.

In questo articolo viene trattata solo la pianificazione DNS per le distribuzioni di Skype for Business Server nella rete locale di un'organizzazione. Per Skype for Business Online, vedere "URL di Office 365 e intervalli di indirizzi IP" all'indirizzo [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) .

Un server DNS (Domain Name Service) esegue il mapping dei nomi host (ad esempio www. <span></span> contoso .com, presumibilmente un server Web) a indirizzi IP (ad esempio <span></span> 10.10.10.10.10). Consente ai client e ai server interdipendenti di comunicare tra loro in rete. Quando si configura un'implementazione di Skype for Business Server 2015, è necessario verificare che il mapping dei nuovi nomi dei server (in genere riflettendo il ruolo che assumeranno) corrisponda agli indirizzi IP a cui sono assegnati.

Anche se all'inizio questo può sembrare un po' scoraggiante, il lavoro pesante per la pianificazione può essere eseguito utilizzando lo strumento di pianificazione di [Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=50357) Dopo aver seguito le domande della procedura guidata sulle funzionalità che si prevede di utilizzare, per ogni sito definito è possibile visualizzare il rapporto DNS all'interno del rapporto di amministrazione di Edge e utilizzare le informazioni elencate per creare i record DNS. È inoltre possibile apportare modifiche a molti dei nomi e degli indirizzi IP utilizzati, per informazioni dettagliate, [vedere Review the DNS Report](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report). Tenere presente che è possibile esportare il report di amministrazione di Edge in un foglio di calcolo di Excel e il rapporto DNS sarà uno dei fogli di lavoro nel file. Anche se questo strumento include funzionalità deprecate da [Skype for Business Server 2019,](../../../SfBServer2019/deprecated.md)può comunque essere usato per creare un piano iniziale se tali funzionalità non sono selezionate

Quando si installa una nuova implementazione come descritto in Creare record DNS per [Skype for Business Server](../../deploy/install/create-dns-records.md) e creare la topologia per Skype for Business Server, si riconosce che è possibile scegliere di utilizzare le funzionalità DNS integrate in Windows Server 2016 o un pacchetto DNS di terze parti, pertanto le discussioni in questo articolo verranno conservate in generale anziché specifiche. We're detailing what's needed, and how you meet that need is your decision to make.

Gli amministratori esperti di Skype for Business, Lync e Office Communications Suite troveranno probabilmente utili le tabelle seguenti. Se la tabella non è chiara, le sezioni o gli articoli successivi chiariranno i concetti seguenti:

## <a name="summary-tables"></a>Tabelle di riepilogo
<a name="BK_Summary"> </a>

Le tabelle seguenti mostrano i record DNS utilizzati da Skype for Business Server per fornire servizi agli utenti. Alcune sono facoltative in quanto sono necessarie solo per supportare determinate funzionalità e possono essere ignorate se tali funzionalità non sono desiderate. I record DNS necessari solo per l'accesso interno sono nella prima tabella e una distribuzione che consente l'accesso interno ed esterno avrà bisogno di record da entrambe le tabelle.

**Mapping DNS interni**

|Tipo di record|Valore|Viene risolto in|Scopo|Obbligatorio|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |Front End pool FQDN  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |Indirizzi IP del server del pool Front End  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Bilanciamento del carico DNS dei pool Front End. Mappa il nome del pool Front End a un set di indirizzi IP.  <br/> Vedere [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | FQDN di ogni front end server o server Standard Edition di un pool o di un server autonomo <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> contoso <span></span> .com FE03. <span></span> contoso <span></span> .com*   |IP corrispondente di ogni server  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |Esegue il mapping del nome del server al relativo indirizzo IP.   |Y   |
|A/AAAA   |Fqdn override dei servizi Web interni del pool Enterprise  <br/> *Web-int. <span></span> contoso <span></span> .com*   |VIP HLB per i servizi Web interni del Front End Server  <br/> *192.168.21.120*   |Necessario per abilitare il traffico Web da client a server, ad esempio il download di Skype for Business Web App. Obbligatorio anche per i client mobili.   |Y   |
|A/AAAA   |Enterprise Pool External Web Services Override FQDN  <br/> *Web-ext. <span></span> contoso <span></span> .com*   |VIP di bilanciamento del carico di rete per i servizi Web esterni del Front End Server  <br/>*68.123.56.90*   |Necessario per abilitare il traffico Web da client a server, ad esempio il download di Skype for Business Web App. Obbligatorio se i client mobili risolvono il DNS internamente. Può essere risolto in IP proxy inverso DMZ o IP Internet.   ||
|A/AAAA   | Fqdn server back-SQL server back-end <br/> *SQL1. <span></span> contoso <span></span> .com*   |indirizzo IP del server  <br/> *192.168.11.90*   |Mappa il nome del server per un server SQL back-end che lavora con il pool Front End al relativo indirizzo IP   ||
|A/AAAA   |Fqdn del server mirror SQL server back-end  <br/> *SQL2. <span></span> contoso <span></span> .com*   |indirizzo IP del server  <br/> *192.168.11.91*   |Esegue il mapping del nome del server per un server mirror SQL back-end che lavora con il pool Front End al relativo indirizzo IP   ||
|A/AAAA   |Director pool FQDN  <br/>**Nota:** Non applicabile quando si utilizza un server Director autonomo <br/> *DirPool. <span></span> contoso <span></span> .com*   |Indirizzi IP del pool di server Director  <br/> DNS LB a *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Bilanciamento del carico DNS dei server del pool di server Director. Mappare il nome del pool di server Director a un indirizzo IP, vedere [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir) <br/> Un Director può autenticare un utente ed è facoltativo.   ||
|A/AAAA   |Director FQDN   |Indirizzo IP del server di ogni server Director   |Mappa il nome del pool per il Server Director a un indirizzo IP, vedere [Deploying DNS Load Balancing on Front End Pools and Director Pools](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |Mediation Server pool FQDN   |Indirizzi IP del pool   |Il ruolo Mediation Server è facoltativo. È possibile co-individuare i servizi forniti da un mediation server al Front End Server o al pool. Vedere [Utilizzo del bilanciamento del carico DNS nei pool Mediation Server](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |Mediation Server FQDN   |Indirizzo IP del server   |È possibile co-individuare i servizi forniti da un mediation server al Front End Server o al pool. Vedere [Utilizzo del bilanciamento del carico DNS nei pool Mediation Server](load-balancing.md#BK_Mediation)  ||
|A/AAAA   |FQDN del server Chat persistente   |Indirizzo IP del server Chat persistente   |Per la funzionalità Persistent Chat è necessario un server Chat persistente e in caso contrario è facoltativo.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |VIP o IP director del pool Front End HLB  <br/>  192.168.21.121  |Servizio di individuazione automatica interno1, necessario per il supporto per dispositivi mobili. Se il DNS interno viene usato per la risoluzione per i dispositivi mobili, deve puntare all'IP esterno o al VIP DMZ.  <br/> Per i servizi Web è necessario il bilanciamento del carico di rete nel pool Front End perché HTTPS non è in grado di sfruttare DNS. Per il pool Front End o il pool di server Director, questa operazione deve essere risolta in un VIP di bilanciamento del carico di rete o in un indirizzo IP normale per un server Standard Edition o un server Director autonomo.   |Y   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |FQDN pool FE HLB o FQDN director  <br/> Web-int. <span></span> contoso <span></span> .com   |Servizio di individuazione automatica interno1 <br/> Se lo si desidera, è possibile implementare questo metodo come CNAME anziché come record A.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |Indirizzi IP del server del pool Front End (o a ogni indirizzo IP del server Director)  <br/>  DNS LB a *192.168.21.122 192.168.21.123 192.168.21.124*   |Obbligatorio per la configurazione automatica, [vedere Procedura dettagliata dei client Skype for Business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> Record o record che puntano ai server del pool Front End o ai server Director nella rete interna o al servizio Access Edge quando il client è esterno   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |VIP del pool FE HLB o VIP di bilanciamento del carico di rete del pool di server Director o IP del server SE/Director  <br/>  192.168.21.121  |La distribuzione di questo record è facoltativa &#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>Porta 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>Porta 5061  |Front End pool FQDN  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |Abilita l'accesso automatico 1 dell'utente interno al Front End Server/pool o al server/pool SE che autentica e reindirizza le richieste client per l'accesso.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |Front End pool FQDN  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |Accesso utente interno &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Origine NTP necessaria per i dispositivi Lync Phone Edition   |Questa operazione è necessaria per supportare i portatili desktop.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | FQDN del servizio Access Edge <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |Creare un record SRV per ogni dominio SIP con client IOS o Windows Phone Mobile.   |Per il supporto di client per dispositivi mobili   |
|A/AAAA   |URL amministratore  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Pannello di controllo di Skype for Business Server, vedere [URL semplici](dns.md#BK_Simple)  ||
|A/AAAA   |URL di meet  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Riunioni online, vedere [URL semplici](dns.md#BK_Simple)  ||
|A/AAAA   |URL di accesso esterno  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Conferenze telefoniche con accesso esterno, vedere [URL semplici](dns.md#BK_Simple)  ||
|A/AAAA   |FQDN dei servizi Web interni  <br/>*Web-int. <span></span> contoso <span></span> .com*  |HLB FE Pool VIP  <br/> 192.168.21.121   |Servizio Web Skype for Business utilizzato da Skype for Business Web App   ||
|A/AAAA   |Office Web Apps Server pool FQDN  <br/> OWA. <span></span> contoso <span></span> .com   | Indirizzo VIP del pool di server Office Web Apps <br/> 192.168.1.5   |Definisce l'FQDN del pool di server Office Web Apps   ||
|A/AAAA   | FQDN Web interno <br/> Web-int. <span></span> contoso <span></span> .com   | Indirizzo VIP del pool Front End <br/> 192.168.21.121   |Definisce l'FQDN Web interno utilizzato da Skype for Business Web App  <br/> Se si utilizza il bilanciamento del carico DNS in questo pool, il pool Front End e la Web farm interna non possono avere lo stesso FQDN.   ||

&#x2776; utilizzato da un client per individuare il Front End Server o il pool Front End ed essere autenticato e connesso come utente. Ulteriori dettagli su questo argomento sono disponibili in [Procedura dettagliata dei client Skype for Business che individuano i servizi.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; Questa operazione è necessaria solo per supportare i client legacy precedenti a Lync 2013 e i portatili desktop.

&#x2778; Nel caso in cui un dispositivo Unified Communications sia acceso, ma un utente non ha mai eseguito l'accesso al dispositivo, il record A consente al dispositivo di individuare il server che ospita il servizio Web Aggiornamento dispositivi e ottenere gli aggiornamenti. In caso contrario, i dispositivi ottengono le informazioni del server tramite provisioning di tipo in-band al primo accesso di un utente.

Nel diagramma seguente viene illustrato un esempio che include record DNS interni ed esterni e molti dei record visualizzati nelle tabelle circostanti:

**Diagramma della rete perimetrale con indirizzi IPv4 pubblici**

![Esempio di diagramma di rete DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**Mapping DNS della rete perimetrale (interfacce interne ed esterne)**

|Tipo di record|Valore|Viene risolto in|Scopo|Obbligatorio|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |FQDN del pool di server perimetrali interno  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |Indirizzi IP del pool di server perimetrali con connessione interna  <br/> 172.25.33.10, 172.25.33.11   |Indirizzi IP dell'interfaccia interna del pool di server perimetrali consolidato   |Y   |
|A/AAAA   |FQDN server perimetrale  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |IP del server con connessione interna per un server nel pool di server perimetrali  <br/> 172.25.33.10   |Creare un record per ogni server del pool con l'FQDN del server che punta all'IP del nodo del server interno nel pool, vedere [DNS Load Balancing on Edge Server Pools](load-balancing.md#BK_Edge).   |Y   |
|A/AAAA   |FQDN del pool di servizi Access Edge  <br/>*Access1. <span></span> contoso <span></span> .com*  |Indirizzi IP esterni del pool di servizi Access Edge  <br/> 131.107.16.10, 131.107.16.11   |Questo servizio fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) sia in ingresso che in uscita.   |Y   |
|A/AAAA   |FQDN del pool di servizi Web Conferencing Edge  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |Indirizzi IP esterni del servizio Web Conferencing Edge  <br/> 131.107.16.90, 131.107.16.91   |Il servizio Web Conferencing Edge consente agli utenti esterni di partecipare alle riunioni ospitate nell'ambiente interno di Skype for Business Server.   |Y   |
|A/AAAA   |*av.\<sip-domain\>* FQDN pool <br/>*AV1. <span></span> contoso <span></span> .com*  |Indirizzi IP esterni A/V Edge  <br/> 131.107.16.170, 131.107.16.171   |Il servizio A/V Edge rende disponibili agli utenti esterni audio, video, condivisione applicazioni e trasferimento di file.   |Y   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |FQDN del pool di server perimetrali di accesso esterno  <br/>*Access1. <span></span> contoso <span></span> .com*  |Individua il pool di server perimetrali . Vedere [Procedura dettagliata dei client Skype for Business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |FQDN access edge esterno  <br/>_Access1. <span></span> contoso <span></span> .com_  |Utilizzato per l'accesso degli utenti esterni. Vedere [Procedura dettagliata dei client Skype for Business che individuano i servizi](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |FQDN access edge esterno  <br/>*Access1. <span></span> contoso <span></span> .com*  |Usato per la federazione e la connettività di messaggistica istantanea pubblica   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN access edge esterno  <br/>*Access1. <span></span> contoso <span></span> .com*  |Il servizio proxy XMPP accetta e invia messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federati XMPP configurati.   |Y, per distribuire la federazione, altrimenti facoltativo  <br/> Non disponibile in Skype for Business Server 2019.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |FQDN access edge esterno  <br/>*Access1. <span></span> contoso <span></span> .com*  |Per supportare il servizio di notifica Push e il servizio notifica Push Apple, devi creare un record SRV per ogni dominio SIP. &#x2778;  ||
|A/AAAA   |FQDN dei servizi Web del pool Front End esterno  <br/>*Web-ext. <span></span> contoso <span></span> .com*  |Indirizzo IP pubblico proxy inverso, proxy all'indirizzo VIP dei servizi Web esterni per il pool Front End &#x2776; <br/> 131.107.155.1 proxy a 192.168.21.120   |Interfaccia esterna del pool Front End utilizzata da Skype for Business Web App   |Y   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |Indirizzo IP pubblico proxy inverso, viene risolto nell'indirizzo VIP dei servizi Web esterni per il pool di server Director, se disponibile, o per il pool Front End se non si dispone di un server Director &#x2777; <br/> 131.107.155.1 proxy a 192.168.21.120   | Record esterno per l'individuazione automatica del client, utilizzato anche da Mobility, Skype for Business Web App e app Web scheduler, risolto dal server proxy inverso <br/> Per supportare il servizio di notifica Push e il servizio notifica Push Apple, creare un record SRV per ogni dominio SIP con client Microsoft Lync Mobile. 3   |Y   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |Indirizzo IP pubblico proxy inverso, risolto nell'interfaccia Web esterna per il pool Front End  <br/> 131.107.155.1 proxy a 192.168.21.120   |Proxy al servizio Web Skype for Business  <br/> Vedere [URL semplici](dns.md#BK_Simple)  |Y   |
|A/AAAA   |accesso remoto.*\<sipdomain\>* <br/> accesso remoto. *<span></span> contoso <span></span> .com*  |Indirizzo IP pubblico proxy inverso, proxy all'interfaccia Web esterna per il pool Front End  <br/> 131.107.155.1 proxy a 192.168.21.120   |Proxy al servizio Web Skype for Business  <br/> Vedere [URL semplici](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps Server pool FQDN  <br/> OWA. <span></span> contoso <span></span> .com   | Indirizzo IP pubblico proxy inverso, proxy all'interfaccia Web esterna per il server Office Web Apps <br/> 131.107.155.1 proxy a 192.168.1.5   | Indirizzo VIP del pool di server Office Web Apps <br/> 192.168.1.5   |Definisce l'FQDN del pool di server Office Web Apps   |

&#x2776; Necessario per distribuire la federazione, altrimenti facoltativo.

&#x2777; utilizzato da un client per individuare il server front-end o il pool Front End ed essere autenticato e connesso come utente.

&#x2778; Questo requisito si applica solo ai client su dispositivi mobili basati su Apple o Microsoft. I dispositivi Android e Nokia Symbian non usano la notifica push.

 Per ulteriori dettagli sui server perimetrali e sulle reti perimetrali, vedere il contenuto della pianificazione [DNS](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) dei server perimetrali.

> [!IMPORTANT]
> Skype for Business Server supporta l'uso dell'indirizzamento IPv6. Per [altri dettagli, vedi Pianificare IPv6 in Skype for Business.](ipv6.md)

> [!IMPORTANT]
> Per ulteriori dettagli sui nomi FQDN, vedere [Nozioni di base su DNS.](basics.md)

**DNS split brain** 
 <a name="BK_split"></a>

Il DNS split brain è una configurazione DNS in cui sono disponibili due zone DNS con lo stesso spazio dei nomi. La prima zona DNS gestisce le richieste interne, mentre la seconda gestisce le richieste esterne, come indicato in queste tabelle. Per ulteriori informazioni, vedere [Dns split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS).

## <a name="hybrid-considerations"></a>Considerazioni sull'ambiente ibrido
<a name="BK_Hybrid"> </a>

Se si prevede di avere alcuni utenti ospitati online e altri ospitati in locale, fare riferimento all'articolo Pianificazione della connettività ibrida [in Skype for Business server 2019.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) Sarà necessario configurare DNS come di consueto per Skype for Business Server 2015 e aggiungere altri record DNS.

È inoltre consigliabile fare riferimento a "URL di Office 365 e intervalli di indirizzi IP" all'indirizzo per verificare che gli utenti avranno accesso alle risorse [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) online necessarie.

## <a name="simple-urls"></a>URL semplici
<a name="BK_Simple"> </a>

Un URL (Uniform Resource Locator) è un riferimento a una risorsa Web che ne specifica la posizione in una rete di computer e un protocollo utilizzato per recuperarla.

Skype for Business Server supporta l'utilizzo di tre URL "semplici" per accedere ai servizi:

- **Meet** viene utilizzato come URL di base per tutte le conferenze nel sito. Un esempio di URL semplice Meet è https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com. Un URL per una determinata riunione può essere https: <span></span> // <span></span> meet. <span></span> contoso <span></span> .com/_nomeutente_/7322994.

    Con l'URL semplice Riunione, i collegamenti per partecipare alle riunioni sono facili da comprendere e da comunicare.

- **L'accesso esterno** consente l'accesso alla pagina Web Impostazioni conferenza telefonica con accesso esterno. In questa pagina vengono visualizzati i numeri di accesso esterno per conferenze con le lingue disponibili, le informazioni sulla conferenza assegnate (ovvero per le riunioni che non devono essere pianificate) e i controlli DTMF in conferenza e supporta la gestione del PIN (Personal Identification Number) e delle informazioni di conferenza assegnate. L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN. Un esempio di URL semplice per l'accesso esterno è https:// <span></span> dialin. <span></span> contoso <span></span> .com.

- **L'amministratore** consente l'accesso rapido al Pannello di controllo di Skype for Business Server. Da qualsiasi computer all'interno dei firewall dell'organizzazione, un amministratore può aprire il Pannello di controllo di Skype for Business Server digitando l'URL semplice amministratore in un browser. L'URL semplice di amministrazione è interno all'organizzazione. Un esempio dell'URL semplice admin è https:// <span></span> admin. <span></span> contoso <span></span> .com.

Gli URL semplici vengono descritti in dettaglio in [Requisiti DNS per GLI URL semplici in Skype for Business Server.](simple-urls.md)

## <a name="dns-by-server-role"></a>DNS per ruolo del server
<a name="BK_Servers"> </a>

È possibile impostare i nomi di questi pool e server come si desidera, ma renderli memorabili e riflettere la loro funzione nel sistema.

### <a name="dns-records-for-individual-servers-or-pools"></a>Record DNS per singoli server o pool

Questi requisiti di record generici si applicano a qualsiasi ruolo del server utilizzato da Skype for Business. Un pool è un insieme di server che eseguono gli stessi servizi che funzionano insieme per gestire le richieste client indirizzate tramite un servizio di bilanciamento del carico. Per [informazioni dettagliate, vedere Requisiti di bilanciamento del carico](load-balancing.md) per Skype for Business

**Record DNS Requirements for Server/pool roles (presuppone il bilanciamento del carico DNS)**

|Scenario di distribuzione|Requisito DNS|
|:-----|:-----|
|One Server:  <br/> Persistent Chat, Director, Mediation Server, Front end Server   |Un record A interno che risolve il nome di dominio completo (FQDN) del server nel relativo indirizzo IP.  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|Pool:  <br/> Persistent Chat, Director, Edge Server, Mediation Server, Front end   |Un record A interno che risolve il nome di dominio completo (FQDN) di ogni nodo del server nel pool nel relativo indirizzo IP.  <br/>**Esempio** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> Più record A interni che risolvono il nome di dominio completo (FQDN) del pool negli indirizzi IP dei nodi del server nel pool.  <br/>**Esempio** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Argomenti DNS specifici del server perimetrale

 Per pianificare la distribuzione dei server perimetrali, vedere Plan [for Edge Server deployments in Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)e [Advanced Edge Server DNS planning for Skype for Business Server 2015](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) con le sezioni seguenti

- [Ripristino di emergenza DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [Bilanciamento del carico DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [Configurazione automatica senza DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [DNS split brain](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [Procedura dettagliata dell'individuazione dei servizi da parte dei client Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)