---
title: Requisiti di sistema dei server perimetrali in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Riepilogo: informazioni sui requisiti di sistema per il server perimetrale in Skype for Business Server.'
ms.openlocfilehash: d5003a265a53c3603892133077a961f54c974401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112742"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a>Requisiti di sistema dei server perimetrali in Skype for Business Server
 
**Riepilogo:** Informazioni sui requisiti di sistema per il server perimetrale in Skype for Business Server.
  
Per quanto riguarda la distribuzione di Server perimetrali di Skype for Business Server, queste sono le operazioni necessarie per il server o i server presenti nell'ambiente stesso, oltre alla pianificazione della struttura dell'ambiente. Per ulteriori informazioni su topologia, DNS, certificati e altri problemi relativi all'infrastruttura, vedere la documentazione relativa ai requisiti ambientali.
  
## <a name="components"></a>Componenti

Quando si parla dell'ambiente perimetrali, si fa riferimento a componenti che sono, per la maggior parte, distribuiti in una rete perimetrale (ovvero si tratta di un gruppo di lavoro o di un dominio esterno alla struttura di dominio di Skype for Business Server).
  
Tenendo presente questo, questi sono i componenti che dovrai tenere a mente per distribuire correttamente Edge:
  
- [server perimetrali](system-requirements.md#EdgeServers)
    
- [Proxy inversi](system-requirements.md#ReverseProxies)
    
- [Firewall](system-requirements.md#Firewalls)
    
- [Director](system-requirements.md#Directors) (facoltativi e, se inclusi, si trovano nella rete interna)
    
- [Servizi di bilanciamento](system-requirements.md#LoadBalancers) del carico (è possibile disporre del bilanciamento del carico DNS o di un bilanciamento del carico hardware, ma per un singolo server perimetrale non è necessario)
    
Di seguito sono riportati ulteriori dettagli su ognuno di questi elementi:
  
### <a name="edge-servers"></a>server perimetrali
<a name="EdgeServers"> </a>

Questi sono i server Skype for Business distribuiti nell'ambiente perimetrale. Il loro ruolo è quello di inviare e ricevere il traffico di rete agli utenti esterni per i servizi offerti dalla distribuzione interna di Skype for Business Server. A tale scopo, viene eseguito ogni server perimetrale:
  
- **Servizio Access Edge:** fornisce un singolo punto di connessione attendibile per il traffico SIP (Session Initiation Protocol) in ingresso e in uscita.
    
- **Servizio Web Conferencing Edge:** consente agli utenti esterni di partecipare alle riunioni ospitate nell'ambiente interno di Skype for Business Server.
    
- **Servizio A/V Edge:** rende disponibile agli utenti esterni audio, video, condivisione applicazioni e trasferimento di file.
    
- **Servizio proxy XMPP**: accetta e invia messaggi XMPP (Extensible Messaging and Presence Protocol) a e da partner federati XMPP configurati.
    
Gli utenti esterni autorizzati possono usare i server perimetrali per connettersi alla distribuzione interna di Skype for Business Server, ma in caso contrario, non forniscono nessun altro accesso alla rete interna per nessuno.
  
> [!NOTE]
> I server perimetrali vengono distribuiti per fornire connessioni per i client Skype for Business abilitati e altri server perimetrali (in scenari di federazione). Non è possibile connettersi da altri tipi di client o server dell'end point. Il server gateway XMPP può consentire le connessioni con i partner XMPP configurati. Ma anche in questo caso, questi sono gli unici tipi di client e federazione che funzionano. 

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)
  
### <a name="reverse-proxies"></a>Proxy inversi
<a name="ReverseProxies"> </a>

Un server proxy inverso (RP) non dispone di un ruolo di Skype for Business Server, ma è un componente essenziale di una distribuzione di server perimetrali. Un proxy inverso consente agli utenti esterni di:
  
- connettersi a riunioni o conferenze telefoniche con accesso remoto utilizzando URL semplici.
    
- scaricare il contenuto della riunione.
    
- espandere i gruppi di distribuzione.
    
- ottenere certificati basati sull'utente per l'autenticazione basata su certificati client
    
- scaricare i file dal server della Rubrica o per inviare query al servizio Query Web Rubrica.
    
- ottenere gli aggiornamenti del software client e del dispositivo.
    
E per i dispositivi mobili:
  
- consente di individuare automaticamente i Front End Server che offrono servizi per dispositivi mobili.
    
- abilita le notifiche push da Microsoft 365 o Office 365 ai dispositivi mobili.
    
I nostri consigli correnti sul proxy inverso sono disponibili nella pagina [Infrastruttura di telefonia per Skype for Business.](../../../SfbPartnerCertification/certification/infra-gateways.md) Quindi il proxy inverso:
  
- dovrebbe essere in grado di utilizzare TLS (Transport Layer Security) introdotto nell'ambiente tramite certificati pubblici per connettersi ai servizi Web esterni pubblicati di:
    
  - Director o pool di server Director
    
  - Front End Server o pool Front End
    
- deve essere in grado di pubblicare siti Web interni utilizzando certificati per la crittografia o pubblicarli con mezzi non crittografati, se necessario.
    
- dovrebbe essere in grado di pubblicare esternamente un sito Web ospitato internamente utilizzando un nome di dominio completo (FQDN).
    
- deve essere in grado di pubblicare tutto il contenuto del sito Web ospitato. Per impostazione predefinita, è possibile utilizzare la direttiva _, riconosciuta dalla maggior parte dei server Web per indicare "Pubblica tutto il contenuto **/\\** nel server Web". È inoltre possibile modificare la direttiva, ad esempio _*/Uwca/ ***, ovvero "Pubblicare tutto il contenuto nella \\ directory virtuale Ucwa".
    
- deve richiedere connessioni TLS con client che richiedono contenuto dal sito Web pubblicato.
    
- deve accettare certificati con voci di nome alternativo soggetto (SAN).
    
- deve essere in grado di consentire il binding di un certificato a un listener o a un'interfaccia tramite cui verrà risolto il nome di dominio completo dei servizi Web esterni. Le configurazioni listener sono preferibili alle interfacce. Molti listener possono essere configurati su una singola interfaccia.
    
- deve consentire la configurazione della gestione delle intestazioni host. Spesso, l'intestazione host originale inviata dal client richiedente deve essere passata in modo trasparente, anziché essere modificata dal proxy inverso.
    
- deve consentire il bridging del traffico TLS da una porta definita esternamente (ad esempio, TCP 443) a un'altra porta definita (ad esempio, TCP 4443). Il proxy inverso può decrittografare il pacchetto al ricevimento e quindi ricrittografare il pacchetto all'invio.
    
- deve consentire il bridging del traffico TCP non crittografato da una porta (ad esempio, TCP 80) a un'altra (ad esempio, TCP 8080).
    
- deve consentire la configurazione o l'accettazione dell'autenticazione NTLM, nessuna autenticazione e autenticazione pass-through.
    
Se il proxy inverso è in grado di soddisfare tutte le esigenze di questo elenco, è consigliabile continuare, ma tenere presente i suggerimenti forniti al collegamento fornito in precedenza.
  
### <a name="firewalls"></a>Firewall
<a name="Firewalls"> </a>

È necessario mettere la distribuzione edge dietro un firewall esterno, ma è consigliabile avere due firewall, uno esterno e uno interno tra l'ambiente perimetrale e l'ambiente interno. Tutta la documentazione negli scenari avrà due firewall. È consigliabile utilizzare due firewall perché garantisce un routing rigoroso da un perimetro di rete all'altro e raddoppia la protezione del firewall per la rete interna.
  
### <a name="directors"></a>Director
<a name="Directors"> </a>

Questo è un ruolo facoltativo. Può essere un singolo server o un pool di server che eseguono il ruolo Director. Si tratta di un ruolo trovato nell'ambiente interno di Skype for Business Server.
  
Il Director è un server hop successivo interno che riceve il traffico SIP in ingresso dai server perimetrali destinati ai server interni di Skype for Business Server. Preautenta le richieste in ingresso e le reindirizza al pool principale o al server di un utente. Questa preautenticazione consente di eliminare le richieste di account utente non identificate.
  
Perché è importante? Una funzione importante per un Director è proteggere i server Standard Edition e i Front End Server o i pool Front End da traffico dannoso, ad esempio attacchi Denial of Service (DoS). Se la rete è piena di traffico esterno non valido, il traffico si arresta nel Director.
  
### <a name="load-balancers"></a>Servizi di bilanciamento del carico
<a name="LoadBalancers"> </a>

La topologia perimetrale consolidata con scalabilità orizzontale di Skype for Business Server è ottimizzata per il bilanciamento del carico DNS per le nuove distribuzioni e si consiglia di eseguire questa operazione. Se è necessaria la disponibilità elevata, è consigliabile usare un servizio di bilanciamento del carico hardware per una situazione specifica:
  
- Messaggistica unificata di Exchange per gli utenti remoti che utilizzano la messaggistica unificata di Exchange **prima** di Exchange 2013.
    
> [!IMPORTANT]
> È fondamentale notare che non è possibile combinare i servizi di bilanciamento del carico. Nell'ambiente Skype for Business Server tutte le interfacce devono utilizzare DNS o HLB. 
  
> [!NOTE]
> Direct Server Return (DSR) NAT non è supportato per Skype for Business Server. 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a>requisiti di bilanciamento del carico hardware per i server perimetrali dei server perimetrali che eseguono il servizio A/V Edge

Per tutti i server perimetrali che eseguono il servizio A/V Edge, questi sono i requisiti:
  
- Disattivare il nagling TCP sia per le porte interne che per le porte esterne 443 (il nagling è il processo di combinazione di diversi pacchetti di piccole dimensioni in un singolo pacchetto più grande per una trasmissione più efficiente).
    
- Disattivare il nagling TCP per l'intervallo di porte esterne 50000 - 59999.
    
- Non usare NAT nei firewall interni o esterni.
    
- L'interfaccia interna di Edge deve essere in una rete diversa dall'interfaccia esterna del server perimetrale e il routing tra di essi deve essere disabilitato.
    
- L'interfaccia esterna di qualsiasi server perimetrale che esegue il servizio A/V Edge deve utilizzare indirizzi IP instradabili pubblicamente e nessuna conversione NAT o porta su uno qualsiasi degli indirizzi IP esterni di Edge.
    
#### <a name="hlb-requirements"></a>Requisiti di bilanciamento del carico di rete

Skype for Business Server non ha molti requisiti di affinità basati su cookie. Pertanto, non è necessario utilizzare una persistenza basata su cookie a meno che **(e** questo è Skype for Business Server 2015 specifico) si abbia Lync Server 2010 Front End Server o pool Front End nell'ambiente Skype for Business Server. Avrebbero bisogno di affinità basata su cookie nel metodo di configurazione consigliato per Lync Server 2010.
  
> [!NOTE]
> Se decidi di attivare l'affinità basata su cookie per il bilanciamento del carico di rete, non ci saranno problemi a farlo, anche se l'ambiente non ne ha bisogno. 
  
Se **l'ambiente non richiede** affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 443 impostare Inoltra intestazione **host** su **True.** In questo modo l'URL originale verrà inoltrato.
    
Per le distribuzioni **che necessitano** di affinità basata su cookie:
  
- Nella regola di pubblicazione del proxy inverso per la porta 443 impostare Inoltra intestazione **host** su **True.** In questo modo l'URL originale verrà inoltrato.
    
- Il cookie del servizio di **bilanciamento del carico** hardware non deve essere contrassegnato come httpOnly.
    
- Il cookie del servizio di **bilanciamento del carico** hardware non deve avere una scadenza.
    
- Il cookie del servizio di bilanciamento del carico **hardware** deve essere denominato **MS-WSMAN** (questo è il valore previsto per i servizi Web e non può essere modificato).
    
- Il **cookie** del servizio di bilanciamento del carico hardware deve essere impostato in ogni risposta HTTP per la quale la richiesta HTTP in ingresso non dispone di un cookie, indipendentemente dal fatto che una precedente risposta HTTP sulla stessa connessione TCP abbia ricevuto un cookie. Se il servizio di bilanciamento del carico hardware ottimizza l'inserimento dei cookie in modo che si verifichi una sola volta per ogni connessione TCP, tale ottimizzazione **non deve** essere utilizzata.
    
> [!NOTE]
> Le configurazioni HLB usano in genere l'affinità di origine e la durata della sessione TCP di 20 minuti, cosa che va bene per Skype for Business Server e i relativi client, perché lo stato della sessione viene mantenuto tramite l'utilizzo del client e/o l'interazione dell'applicazione. 
  
Se stai distribuendo dispositivi mobili, il bilanciamento del carico deve essere in grado di bilanciare il carico delle singole richieste all'interno di una sessione TCP (in effetti, devi essere in grado di bilanciare il carico di una singola richiesta in base all'indirizzo IP di destinazione).
  
> [!IMPORTANT]
> Gli F5 HLB hanno una funzionalità denominata OneConnect. Garantisce che ogni richiesta all'interno di una connessione TCP sia bilanciata singolarmente. Se stai distribuendo dispositivi mobili, assicurati che il fornitore del bilanciamento del carico di rete supporti le stesse funzionalità. Le app per dispositivi mobili iOS più recenti richiedono TLS versione 1.2. Per saperne di più, F5 fornisce impostazioni specifiche per questo scopo. 
  
Ecco i requisiti di bilanciamento del carico di rete per i servizi Web del pool Front End (facoltativo) e (obbligatorio):
  
- Per i VIP dei servizi Web interni, impostare Source_addr persistenza (porta interna 80, 443) nel bilanciamento del carico di rete. Per Skype for Business Server, Source_addr persistenza significa che più connessioni provenienti da un singolo indirizzo IP vengono sempre inviate a un server per mantenere lo stato sessione.
    
- Utilizzare un timeout di inattività TCP di 1800 secondi.
    
- Nel firewall tra il proxy inverso e il bilanciamento del carico di rete del pool di hop successivo, creare una regola per consentire il traffico https: sulla porta 4443, dal proxy inverso al bilanciamento del carico di rete. Il bilanciamento del carico di rete deve essere configurato per l'ascolto sulle porte 80, 443 e 4443.
    
#### <a name="summary-of-hlb-affinity-requirements"></a>Riepilogo dei requisiti di affinità HLB

|**Posizione client/utente**|**Requisiti per l'affinità FQDN dei servizi Web esterni**|**Requisiti di affinità FQSN dei servizi Web interni**|
|:-----|:-----|:-----|
|Skype for Business Web App (utenti interni ed esterni)  <br/> Dispositivo mobile (utenti interni ed esterni  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Skype for Business Web App (solo utenti esterni)  <br/> Dispositivo mobile (utenti interni ed esterni  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
|Skype for Business Web App (solo utenti interni)  <br/> Dispositivo mobile (non distribuito)  <br/> |Nessuna affinità  <br/> |Affinità indirizzo di origine  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a>Monitoraggio delle porte per gli SHLB

È possibile definire il monitoraggio delle porte nei servizi di bilanciamento del carico hardware per determinare quando servizi specifici non sono più disponibili a causa di un errore hardware o di comunicazione. Ad esempio, se il servizio Front End Server (RTCSRV) si interrompe a causa di un errore del Front End Server o del pool Front End, anche il monitoraggio del bilanciamento del carico di rete dovrebbe interrompere la ricezione del traffico sui servizi Web. È consigliabile implementare il monitoraggio delle porte nel bilanciamento del carico di rete per monitorare quanto segue per l'interfaccia esterna HLB:
  
|**IP virtuale/Porta**|**Porta nodo**|**Computer/Monitor nodo**|**Profilo persistenza**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front End  <br/> 5061  <br/> |Nessuno  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front End  <br/> 5061  <br/> |Nessuno  <br/> |HTTP  <br/> |
   
## <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

Sono stati trattati i requisiti hardware e software dei server perimetrali nella documentazione generale dei server per [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e Requisiti di sistema per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="collocation"></a>Collocazione

La collocazione dei server perimetrali è stata trattata nella documentazione relativa alle nozioni di base sulla topologia [per Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md)
