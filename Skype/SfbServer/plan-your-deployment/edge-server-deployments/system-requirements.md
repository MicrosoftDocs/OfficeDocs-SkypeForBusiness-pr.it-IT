---
title: Requisiti di sistema per i server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: 'Riepilogo: informazioni sui requisiti di sistema per Edge Server in Skype for Business Server.'
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221026"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisiti di sistema per i server perimetrali in Skype for Business Server
 
**Riepilogo:** Informazioni sui requisiti di sistema per Edge Server in Skype for Business Server.
  
Per quanto riguarda la distribuzione di Skype for Business Server Edge Server, queste sono le operazioni necessarie per il server o i server che si trovano nell'ambiente stesso, nonché per la pianificazione della struttura dell'ambiente. Per ulteriori informazioni sulla topologia, il DNS, i certificati e altri problemi relativi all'infrastruttura, vedere la documentazione relativa ai requisiti per l'ambiente.
  
## <a name="components"></a>Componenti

Quando si discute sull'ambiente server perimetrale, vengono referenziati componenti che, per la maggior parte, sono distribuiti in una rete perimetrale, ovvero in un gruppo di lavoro o in un dominio esterno alla struttura del dominio di Skype for Business Server.
  
Tenendo presente questo, questi sono i componenti che devono essere tenuti presenti per la distribuzione del server perimetrale con esito positivo:
  
- [server perimetrali](system-requirements.md#EdgeServers)
    
- [Proxy inversi](system-requirements.md#ReverseProxies)
    
- [Firewall](system-requirements.md#Firewalls)
    
- [Direttori](system-requirements.md#Directors) (sono facoltativi e, se sono inclusi, verranno posizionati nella rete interna)
    
- Dispositivi di bilanciamento del [carico](system-requirements.md#LoadBalancers) (è possibile disporre di bilanciamento del carico DNS o di un dispositivo di bilanciamento del carico hardware (HLB), ma per un singolo server perimetrale non è necessario)
    
Sono presenti maggiori dettagli su ognuna di queste operazioni:
  
### <a name="edge-servers"></a>server perimetrali
<a name="EdgeServers"> </a>

Questi sono i server Skype for business distribuiti nell'ambiente perimetrale. Il loro ruolo è l'invio e la ricezione del traffico di rete verso gli utenti esterni per i servizi offerti dalla distribuzione interna di Skype for Business Server. A tale scopo, ogni server perimetrale viene eseguito:
  
- **Access Edge service**: fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.
    
- **Servizio Web Conferencing Edge**: consente agli utenti esterni di partecipare alle riunioni ospitate nell'ambiente interno di Skype for Business Server.
    
- **Servizio a/V Edge**: rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni.
    
- **Servizio proxy XMPP**: consente di accettare e inviare messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federati XMPP configurati.
    
Gli utenti esterni autorizzati possono utilizzare i server perimetrali per connettersi alla distribuzione interna di Skype for Business Server, ma in caso contrario, non forniscono nessun altro accesso alla rete interna per chiunque.
  
> [!NOTE]
> I server perimetrali vengono distribuiti per fornire connessioni per i client Skype for business abilitati e altri server perimetrali (in scenari di federazione). Non è possibile connettersi da altri tipi di client o server end point. Il server gateway XMPP può consentire le connessioni con i partner XMPP configurati. Tuttavia, questi sono gli unici client e i tipi di federazione che funzioneranno. 

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Proxy inversi
<a name="ReverseProxies"> </a>

Un server proxy inverso non ha un ruolo del server Skype for business, ma è un componente essenziale di una distribuzione di server perimetrali. Un proxy inverso consente agli utenti esterni di:
  
- connettersi a riunioni o conferenze telefoniche con accesso esterno utilizzando URL semplici.
    
- scaricare il contenuto delle riunioni.
    
- espandere gruppi di distribuzione.
    
- ottenere certificati basati sull'utente per l'autenticazione basata su certificati client
    
- scaricare i file dal server della rubrica oppure inviare query al servizio query Web della Rubrica.
    
- ottenere gli aggiornamenti del software client e del dispositivo.
    
E per i dispositivi mobili:
  
- consente loro di individuare automaticamente i front end server che offrono servizi per dispositivi mobili.
    
- consente di abilitare le notifiche push da Microsoft 365 o Office 365 ai dispositivi mobili.
    
I suggerimenti per i proxy inversi correnti sono disponibili nella pagina [infrastruttura di telefonia per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Pertanto, il proxy inverso:
  
- dovrebbe essere in grado di utilizzare TLS (Transport Layer Security) introdotto nell'ambiente tramite certificati pubblici per connettersi ai servizi Web esterni pubblicati:
    
  - Director o pool di server Director
    
  - Front End Server o pool Front End
    
- deve essere in grado di pubblicare siti Web interni utilizzando i certificati per la crittografia oppure pubblicarli in modo non crittografato, se necessario.
    
- dovrebbe essere in grado di pubblicare esternamente un sito Web ospitato internamente utilizzando un nome di dominio completo (FQDN).
    
- deve essere in grado di pubblicare tutto il contenuto del sito Web ospitato. Per impostazione predefinita, è possibile utilizzare la **/\\** direttiva *, riconosciuta dalla maggior parte dei server Web per indicare "pubblicare tutto il contenuto sul server Web". È inoltre possibile modificare la direttiva, ad esempio * */Uwca/ \\ * * *, che significa "pubblicare tutto il contenuto nella directory virtuale UCWA".
    
- deve richiedere connessioni TLS con client che richiedono contenuti dal sito Web pubblicato.
    
- deve accettare i certificati con le voci del nome alternativo soggetto (SAN).
    
- deve essere in grado di consentire l'associazione di un certificato a un listener o a un'interfaccia tramite la quale verrà risolto il nome di dominio completo dei servizi Web esterni. Le configurazioni dei listener sono preferibili alle interfacce. Molti listener possono essere configurati in una singola interfaccia.
    
- deve consentire la configurazione della gestione delle intestazioni host. Spesso, l'intestazione host originale inviata dal client richiedente deve essere passata in modo trasparente, anziché essere modificata dal proxy inverso.
    
- dovrebbe consentire il bridging del traffico TLS da una porta definita esternamente (ad esempio, TCP 443) a un'altra porta definita (ad esempio, TCP 4443). Il proxy inverso può decrittografare il pacchetto al ricevimento e quindi rieseguire la crittografia del pacchetto all'invio.
    
- dovrebbe consentire il bridging del traffico TCP non crittografato da una porta (ad esempio, TCP 80) a un altro (ad esempio, TCP 8080).
    
- deve consentire la configurazione di, o accettare, l'autenticazione NTLM, nessuna autenticazione e l'autenticazione pass-through.
    
Se il proxy inverso è in grado di soddisfare tutte le esigenze di questo elenco, è consigliabile andare bene, ma tieni presente i suggerimenti consigliati al collegamento sopra indicato.
  
### <a name="firewalls"></a>Firewall
<a name="Firewalls"> </a>

È necessario inserire la distribuzione perimetrale dietro un firewall esterno, ma è consigliabile disporre di due firewall, uno esterno e uno interno tra l'ambiente perimetrale e l'ambiente interno. Tutta la documentazione nei nostri scenari avrà due firewall. È consigliabile disporre di due firewall perché garantisce un routing rigoroso da un lato della rete all'altro e raddoppia la protezione firewall per la rete interna.
  
### <a name="directors"></a>Amministrazione
<a name="Directors"> </a>

Questo è un ruolo facoltativo. Può trattarsi di un singolo server o di un pool di server che eseguono il ruolo Director. Si tratta di un ruolo trovato nell'ambiente interno di Skype for Business Server.
  
Il Director è un server hop successivo interno che riceve il traffico SIP in ingresso dai server perimetrali destinati ai server interni di Skype for Business Server. La preautenticazione richiede le richieste in ingresso e le reindirizza al server o al pool Home di un utente. Questa preautenticazione consente di eliminare le richieste di account utente non identificate.
  
Perché è importante? Una funzione importante per un amministratore è quella di proteggere i server Standard Edition e front end server o pool Front end da traffico dannoso, ad esempio attacchi DoS (Denial of Service). Se la rete è inondata di traffico esterno non valido, il traffico viene interrotto nel server Director.
  
### <a name="load-balancers"></a>Bilanciamento del carico
<a name="LoadBalancers"> </a>

La topologia perimetrale consolidata di Skype for Business Server è stata ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni e si consiglia di eseguire questa operazione. Se è necessaria un'elevata disponibilità, è consigliabile utilizzare un dispositivo di bilanciamento del carico hardware per una situazione specifica:
  
- Messaggistica unificata di Exchange per gli utenti remoti tramite messaggistica unificata di Exchange **prima** di Exchange 2013.
    
> [!IMPORTANT]
> È importante tenere presente che non è possibile mescolare i bilanciamento del carico. Nell'ambiente Skype for Business Server tutte le interfacce devono utilizzare DNS o HLB. 
  
> [!NOTE]
> La modalità DSR (Direct Server Return) NAT non è supportata per Skype for Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisiti per il bilanciamento del carico hardware per i server perimetrali Edge Server che eseguono il servizio A/V Edge

Per qualsiasi server perimetrale che esegue il servizio A/V Edge, questi sono i requisiti seguenti:
  
- Disattiva TCP nagling per porte interne ed esterne 443 (Nagling è il processo di combinazione di diversi pacchetti di piccole dimensioni in un singolo pacchetto più grande per una trasmissione più efficiente).
    
- Disattivare TCP nagling per l'intervallo di porte esterne 50000-59999.
    
- Non utilizzare NAT nei firewall interni o esterni.
    
- L'interfaccia interna perimetrale deve trovarsi in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di esse deve essere disabilitato.
    
- L'interfaccia esterna di qualsiasi server perimetrale che esegue il servizio A/V Edge deve utilizzare gli indirizzi IP instradabili pubblicamente e non la conversione NAT o la porta su uno degli indirizzi IP esterni perimetrali.
    
#### <a name="hlb-requirements"></a>Requisiti di HLB

Skype for Business Server non dispone di molti requisiti di affinità basati su cookie. Pertanto, non è necessario utilizzare la persistenza basata su cookie, a **meno** che (e questo è Skype for Business Server 2015-specific) si sta per avere Lync Server 2010 Front End Server o pool Front end nell'ambiente di Skype for Business Server. Avrebbero bisogno dell'affinità basata su cookie nel metodo di configurazione consigliato per Lync Server 2010.
  
> [!NOTE]
> Se si decide di trasformare l'affinità basata su cookie per la propria HLB, non si verifica un problema, anche se non è necessario per l'ambiente. 
  
Se nell'ambiente **non** è necessaria l'affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 443, impostare **forward host header** su **true**. In questo modo viene inoltrato l'URL originale.
    
Per le distribuzioni **in cui è** necessaria un'affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 443, impostare **forward host header** su **true**. In questo modo viene inoltrato l'URL originale.
    
- Il cookie del dispositivo di bilanciamento del carico hardware **non deve** essere contrassegnato come HttpOnly.
    
- Il cookie del dispositivo di bilanciamento del carico hardware **non deve** avere una data di scadenza.
    
- Il cookie del dispositivo di bilanciamento del carico hardware **deve** essere denominato **MS-WSMan** (questo è il valore previsto per i servizi Web e non è possibile modificarlo).
    
- Il cookie del dispositivo di bilanciamento del carico hardware **deve** essere impostato in ogni risposta http per cui la richiesta HTTP in arrivo non ha un cookie, indipendentemente dal fatto che una risposta http precedente sulla stessa connessione TCP abbia ottenuto un cookie. Se il dispositivo di bilanciamento del carico hardware ottimizza l'inserimento dei cookie in modo che si verifichi solo una volta per ogni connessione TCP, **non è necessario** utilizzare tale ottimizzazione.
    
> [!NOTE]
> È tipico che le configurazioni di HLB utilizzino l'affinità di origine e la durata delle sessioni TCP di 20 minuti, cosa che va bene per Skype for Business Server e i suoi client, perché lo stato della sessione viene gestito tramite l'utilizzo del client e/o l'interazione dell'applicazione. 
  
Se si distribuiscono dispositivi mobili, è necessario che HLB sia in grado di bilanciare il carico delle singole richieste all'interno di una sessione TCP (in effetti, è necessario essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).
  
> [!IMPORTANT]
> F5 HLBs dispone di una funzionalità denominata OneConnect. Garantisce che ogni richiesta all'interno di una connessione TCP sia bilanciata individualmente. Se si stanno distribuendo dispositivi mobili, assicurarsi che il fornitore di HLB supporti la stessa funzionalità. Le più recenti app per dispositivi mobili iOS richiedono la versione 1,2 di TLS. Se hai bisogno di ulteriori informazioni, F5 fornisce impostazioni specifiche per questo. 
  
Di seguito sono riportati i requisiti di HLB per il Director (facoltativo) e per i servizi Web del pool Front End (obbligatorio):
  
- Per i VIP dei servizi Web interni, impostare Source_addr la persistenza (porta interna 80, 443) su HLB. Per Skype for Business Server, la persistenza Source_addr implica che più connessioni provenienti da un singolo indirizzo IP vengano sempre inviate a un solo server, per mantenere lo stato della sessione.
    
- Utilizzare un timeout di inattività TCP pari a 1800 secondi.
    
- Sul firewall tra il proxy inverso e il HLB del pool di hop successivo, creare una regola per consentire HTTPS: traffico sulla porta 4443, dal proxy inverso a HLB. La tua HLB deve essere configurata per l'ascolto sulle porte 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Riepilogo dei requisiti di affinità di HLB

|**Posizione client/utente**|**Requisiti per l'affinità FQDN dei servizi Web esterni**|**Requisiti per l'affinità dei servizi Web interni FQSN**|
|:-----|:-----|:-----|
|Skype for Business Web App (utenti interni ed esterni)  <br/> Dispositivo mobile (utenti interni ed esterni  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Skype for Business Web App (solo utenti esterni)  <br/> Dispositivo mobile (utenti interni ed esterni  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Skype for Business Web App (solo utenti interni)  <br/> Dispositivo mobile (non distribuito)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoraggio delle porte per HLBs

È possibile definire il monitoraggio delle porte sui dispositivi di bilanciamento del carico hardware per determinare se i servizi specifici non sono più disponibili a causa di un errore hardware o di comunicazione. Ad esempio, se il servizio front end server (RTCSRV) si interrompe perché il front end server o il pool Front End ha esito negativo, il monitoraggio di HLB dovrebbe anche interrompere la ricezione del traffico sui servizi Web. È consigliabile implementare il monitoraggio delle porte su HLB per monitorare le operazioni seguenti per l'interfaccia esterna di HLB:
  
|**IP virtuale/Porta**|**Porta nodo**|**Computer/Monitor nodo**|**Profilo persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs del pool \>  <br/> 443  <br/> |4443  <br/> |Front End  <br/> 5061  <br/> |Nessuno  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs del pool \>  <br/> 80  <br/> |8080  <br/> |Front End  <br/> 5061  <br/> |Nessuno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

Sono stati descritti i requisiti hardware e software del server perimetrale nei requisiti generali del server [per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e i [requisiti di sistema per la documentazione di Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Collocazione dei

Nella documentazione relativa alla [topologia di Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) è stata coperta la collocazione dei server perimetrali.
  

