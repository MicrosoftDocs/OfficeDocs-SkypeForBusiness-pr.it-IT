---
title: Requisiti di sistema di Edge Server in Skype for Business Server
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
ms.openlocfilehash: 4ef2feeb2b486bc9be9f4eb59136d74ef542dd31
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803316"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisiti di sistema di Edge Server in Skype for Business Server
 
**Riepilogo:** Informazioni sui requisiti di sistema per Edge Server in Skype for Business Server.
  
Per quanto riguarda la distribuzione di Skype for Business Server Edge Server, queste sono le operazioni che è necessario eseguire per il server o i server che si trovano nell'ambiente stesso e per la pianificazione della struttura dell'ambiente. Per altre informazioni su topologia, DNS, certificati e altri problemi relativi all'infrastruttura, vedere la documentazione relativa ai requisiti ambientali.
  
## <a name="components"></a>Componenti

Quando discutiamo dell'ambiente Edge Server, stiamo facendo riferimento a componenti che, per la maggior parte, sono distribuiti in una rete perimetrale (vale a dire che si trova in un gruppo di lavoro o in un dominio esterno alla struttura del dominio di Skype for Business Server).
  
Tenendo presente quanto segue, questi sono i componenti da tenere presenti per la distribuzione del bordo correttamente:
  
- [Edge Server](system-requirements.md#EdgeServers)
    
- [Reverse proxy](system-requirements.md#ReverseProxies)
    
- [Firewall](system-requirements.md#Firewalls)
    
- [Amministratori](system-requirements.md#Directors) (questi sono facoltativi e, se inclusi, verranno posizionati nella rete interna)
    
- [Bilanciamento](system-requirements.md#LoadBalancers) del carico (è possibile avere il bilanciamento del carico DNS o un servizio di bilanciamento del carico hardware (HLB), ma per un singolo Edge Server non è necessario)
    
Abbiamo più dettagli su ognuno di essi:
  
### <a name="edge-servers"></a>Edge Server
<a name="EdgeServers"> </a>

Questi sono i server Skype for business distribuiti nell'ambiente perimetrale. Il loro ruolo consiste nell'inviare e ricevere traffico di rete a utenti esterni per i servizi offerti dalla distribuzione interna di Skype for Business Server. A tale scopo, ogni server perimetrale viene eseguito:
  
- **Access Edge Services**: fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in uscita e in ingresso.
    
- **Web Conferencing Edge Services**: consente agli utenti esterni di partecipare a riunioni ospitate nell'ambiente interno di Skype for Business Server.
    
- **A/V Edge Services**: rende disponibili audio, video, condivisione applicazioni e trasferimento di file per gli utenti esterni.
    
- **Servizio proxy XMPP**: accetta e invia i messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner FEDERAtivi XMPP configurati.
    
Gli utenti esterni autorizzati possono usare gli Edge Server per connettersi alla distribuzione interna di Skype for Business Server, ma in caso contrario, non offre altro accesso alla rete interna per chiunque.
  
> [!NOTE]
> I server perimetrali vengono distribuiti per consentire connessioni per client Skype for business abilitati e altri Edge Server (in scenari federativi). Non è possibile connettersi da altri tipi di client o server di fine Point. Il server gateway XMPP può consentire connessioni con partner XMPP configurati. Ma di nuovo, questi sono gli unici tipi di client e federazioni che funzioneranno. 

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
  
### <a name="reverse-proxies"></a>Reverse proxy
<a name="ReverseProxies"> </a>

Un proxy inverso (RP) Server non ha un ruolo di Skype for Business Server, ma è un componente essenziale di una distribuzione di Edge Server. Un proxy inverso consente agli utenti esterni di:
  
- connettersi a riunioni o conferenze telefoniche con accesso esterno usando semplici URL.
    
- scaricare il contenuto della riunione.
    
- espandere gruppi di distribuzione.
    
- ottenere certificati basati sull'utente per l'autenticazione basata su certificato client
    
- scaricare i file dal server della rubrica oppure inviare query al servizio query Web Rubrica.
    
- ottenere gli aggiornamenti per il software client e dispositivo.
    
E per i dispositivi mobili:
  
- consente loro di individuare automaticamente i server front-end che offrono servizi di mobilità.
    
- consente le notifiche push da Office 365 ai dispositivi mobili.
    
Le nostre raccomandazioni di proxy inversa correnti si trovano nella pagina [infrastrutture telefonia per Skype for business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) . Quindi il proxy inverso:
  
- dovrebbe essere in grado di usare Transport Layer Security (TLS) introdotto nell'ambiente tramite certificati pubblici per connettersi ai servizi Web esterni pubblicati:
    
  - Pool di Director o Director
    
  - Server front-end o pool Front-End
    
- deve essere in grado di pubblicare siti Web interni usando certificati per la crittografia oppure pubblicarli su mezzi non crittografati, se necessario.
    
- dovrebbe essere in grado di pubblicare un sito Web ospitato internamente esternamente usando un nome di dominio completo (FQDN).
    
- deve essere in grado di pubblicare tutti i contenuti del sito Web ospitato. Per impostazione predefinita, puoi usare la ** / **direttiva *, riconosciuta dalla maggior parte dei server Web per indicare "pubblica tutto il contenuto sul server Web". È anche possibile modificare la direttiva, ad esempio * */Uwca/\\* * *, che significa "pubblica tutto il contenuto nella directory virtuale UCWA".
    
- deve richiedere connessioni TLS con client che richiedono contenuto dal sito Web pubblicato.
    
- deve accettare i certificati con le voci di nome alternativo soggetto (SAN).
    
- deve essere in grado di consentire il binding di un certificato a un listener o un'interfaccia tramite cui verrà risolto l'FQDN dei servizi Web esterni. Le configurazioni dei listener sono preferibili alle interfacce. Molti listener possono essere configurati in una singola interfaccia.
    
- deve consentire la configurazione della gestione delle intestazioni host. Spesso l'intestazione host originale inviata dal client richiedente deve essere passata in modo trasparente, invece di essere modificata dal proxy inverso.
    
- dovrebbe consentire il bridging del traffico TLS da una porta definita esternamente, ad esempio TCP 443, a un'altra porta definita, ad esempio TCP 4443. Il proxy inverso può decrittografare il pacchetto alla ricezione e quindi ricrittografare il pacchetto all'invio.
    
- dovrebbe consentire il bridging del traffico TCP non crittografato da una porta, ad esempio TCP 80, a un'altra (ad esempio, TCP 8080).
    
- deve consentire la configurazione di, o accettare, l'autenticazione NTLM, nessuna autenticazione e l'autenticazione pass-through.
    
Se il proxy inverso è in grado di rispondere a tutte le esigenze in questo elenco, è consigliabile procedere, ma tenere presenti le raccomandazioni sul collegamento indicato sopra.
  
### <a name="firewalls"></a>Firewall
<a name="Firewalls"> </a>

È necessario inserire la distribuzione di Edge dietro un firewall esterno, ma è consigliabile avere due firewall, uno esterno e uno interno tra l'ambiente Edge e l'ambiente interno. Tutta la documentazione degli scenari include due firewall. È consigliabile disporre di due firewall perché garantisce un routing rigoroso da un bordo di rete all'altro e raddoppia la protezione firewall per la rete interna.
  
### <a name="directors"></a>Consiglio
<a name="Directors"> </a>

Si tratta di un ruolo facoltativo. Può essere un singolo server o un pool di server che gestiscono il ruolo Director. Si tratta di un ruolo trovato nell'ambiente interno di Skype for Business Server.
  
Il Director è un server hop interno successivo che riceve il traffico SIP in ingresso dagli Edge Server destinati ai server interni di Skype for Business Server. Effettua la preautenticazione delle richieste in ingresso e le reindirizza al server o al pool Home di un utente. Questa preautenticazione consente di eliminare le richieste di account utente non identificate.
  
Perché è importante? Una funzione importante per un amministratore consiste nel proteggere i server standard e i server front-end o i pool Front-end da traffico illecito, ad esempio attacchi DoS (Denial of Service). Se la rete è inondata da traffico esterno non valido, il traffico si arresta presso il direttore.
  
### <a name="load-balancers"></a>Bilanciamento del carico
<a name="LoadBalancers"> </a>

La topologia di Edge consolidato di Skype for Business Server è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni ed è consigliabile. Se è necessaria una disponibilità elevata, è consigliabile usare un bilanciamento del carico hardware per una situazione specifica:
  
- Messaggistica unificata di Exchange per gli utenti remoti con messaggistica unificata di Exchange **prima** di Exchange 2013.
    
> [!IMPORTANT]
> È importante tenere presente che non è possibile combinare i carichi di bilanciamento del carico. Nell'ambiente Skype for Business Server tutte le interfacce devono usare DNS o HLB. 
  
> [!NOTE]
> Direct Server Return (DSR) NAT non è supportato per Skype for Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisiti di bilanciamento del carico hardware per Edge Server Edge Server che utilizzano il servizio A/V Edge

Per qualsiasi server perimetrale che esegue il servizio A/V Edge, questi sono i requisiti seguenti:
  
- Disattivare TCP nagling per le porte interne ed esterne 443 (Nagling è il processo di combinazione di diversi piccoli pacchetti in un singolo pacchetto più grande per una trasmissione più efficiente).
    
- Disattivare TCP nagling per l'intervallo di porte esterne 50000-59999.
    
- Non usare NAT nei firewall interni o esterni.
    
- L'interfaccia interna del bordo deve essere in una rete diversa rispetto all'interfaccia esterna del server perimetrale e il routing tra di essi deve essere disabilitato.
    
- L'interfaccia esterna di qualsiasi Edge Server che usa il servizio A/V Edge deve usare indirizzi IP instradabili pubblicamente e nessuna traduzione NAT o Port in uno degli indirizzi IP esterni di Edge.
    
#### <a name="hlb-requirements"></a>Requisiti di HLB

Skype for Business Server non ha molti requisiti di affinità basati su cookie. Non è quindi necessario usare una persistenza basata su cookie a **meno** che (e questo è Skype for Business Server 2015-specifico) che si vuole avere Lync Server 2010 Front-End Server o pool Front-end nell'ambiente di Skype for Business Server. Avrebbero bisogno di affinità basata su cookie nel metodo di configurazione consigliato per Lync Server 2010.
  
> [!NOTE]
> Se si decide di attivare l'affinità basata su cookie per il proprio HLB, non si verifica un problema, anche se l'ambiente non ne ha bisogno. 
  
Se nell'ambiente **non** è necessaria l'affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 443 impostare **Inoltra intestazione host** su **true**. In questo modo verrà inoltrato l'URL originale.
    
Per le distribuzioni **che richiedono** affinità basate su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 443 impostare **Inoltra intestazione host** su **true**. In questo modo verrà inoltrato l'URL originale.
    
- Il cookie di bilanciamento del carico hardware **non deve** essere contrassegnato come HttpOnly.
    
- Il cookie di bilanciamento del carico hardware **non deve** avere una data di scadenza.
    
- Il cookie del servizio di bilanciamento del carico hardware **deve** essere denominato **MS-WSMan** (questo è il valore previsto per i servizi Web e non può essere modificato).
    
- Il cookie di bilanciamento del carico hardware **deve** essere impostato in tutte le risposte http per cui la richiesta HTTP in arrivo non ha un cookie, indipendentemente dal fatto che una risposta http precedente sulla stessa connessione TCP abbia ottenuto un cookie. Se il dispositivo di bilanciamento del carico hardware ottimizza l'inserimento del cookie per eseguire una sola volta per ogni connessione TCP, **non deve** essere usata l'ottimizzazione.
    
> [!NOTE]
> È tipico delle configurazioni di HLB usare l'affinità di origine e la durata della sessione TCP di 20 minuti, che va bene per Skype for Business Server e i suoi clienti, perché lo stato della sessione viene mantenuto tramite l'utilizzo del client e/o l'interazione tra applicazioni. 
  
Se stai distribuendo dispositivi mobili, il tuo HLB deve essere in grado di caricare il bilanciamento delle singole richieste all'interno di una sessione TCP (in effetti devi essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).
  
> [!IMPORTANT]
> F5 HLBs ha una caratteristica chiamata OneConnect. Garantisce che ogni richiesta all'interno di una connessione TCP venga caricata individualmente in modo equilibrato. Se stai distribuendo dispositivi mobili, assicurati che il fornitore di HLB supporti le stesse funzionalità. Le più recenti app per dispositivi mobili iOS richiedono la versione 1,2 di TLS. Per saperne di più, F5 offre impostazioni specifiche per questo. 
  
Ecco i requisiti di HLB per il Director (facoltativo) e i servizi Web del pool di front end (obbligatorio):
  
- Per i VIP dei servizi Web interni, imposta Source_addr persistenza (porta interna 80, 443) in HLB. Per Skype for Business Server, Source_addr persistenza indica che più connessioni provenienti da un singolo indirizzo IP vengono sempre inviate a un server, per mantenere lo stato della sessione.
    
- Usare un timeout di inattività TCP di 1800 secondi.
    
- Nel firewall tra il proxy inverso e il prossimo HLB del pool di hop, crea una regola per consentire HTTPS: traffico sulla porta 4443, dal proxy inverso a HLB. La tua HLB deve essere configurata per l'ascolto sulle porte 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Riepilogo dei requisiti di affinità di HLB

|**Posizione client/utente**|**Requisiti di affinità FQDN servizi Web esterni**|**Requisiti di affinità dei servizi Web interni FQSN**|
|:-----|:-----|:-----|
|Skype for Business Web App (utenti interni ed esterni)  <br/> Dispositivo mobile (utenti interni ed esterni  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Skype for Business Web App (solo utenti esterni)  <br/> Dispositivo mobile (utenti interni ed esterni  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Skype for Business Web App (solo utenti interni)  <br/> Dispositivo mobile (non distribuito)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoraggio della porta per HLBs

Puoi definire il monitoraggio della porta nei dispositivi di bilanciamento del carico hardware per determinare quando i servizi specifici non sono più disponibili, a causa di problemi hardware o comunicazioni. Ad esempio, se il servizio server front-end (RTCSRV) si arresta perché il server front-end o il pool Front-end non riesce, il monitoraggio di HLB dovrebbe interrompere anche la ricezione del traffico sui servizi Web. Devi implementare il monitoraggio della porta su HLB per monitorare le operazioni seguenti per l'interfaccia esterna di HLB:
  
|**IP virtuale/porta**|**Porta nodi**|**Nodo macchina/monitor**|**Profilo di persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>del pool  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Nessuno  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>del pool  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Nessuno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

Sono stati descritti i requisiti hardware e software di Edge Server nei [requisiti generali del server per Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e i [requisiti di sistema per la documentazione di Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) .
  
## <a name="collocation"></a>Collocazione

Abbiamo coperto la collocazione dei server Edge nella nostra [base di topologia per la documentazione di Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) .
  

