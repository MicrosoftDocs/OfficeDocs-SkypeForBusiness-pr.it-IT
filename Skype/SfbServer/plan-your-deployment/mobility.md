---
title: Pianificare la mobilità per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Pianificare l'implementazione della mobilità per Skype for Business Server.
ms.openlocfilehash: 8b0ba8dd4ae07d3330a8ca722a1101c6b41a7cec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194930"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Pianificare la mobilità per Skype for Business Server
 
Pianificare l'implementazione della mobilità per Skype for Business Server.
  
Con Skype for Business Server è possibile distribuire la funzionalità mobilità per ottenere le funzionalità di Skype for Business Server nei dispositivi mobili. Questo articolo fornisce informazioni dettagliate sulla funzionalità mobilità e consente di pianificare la distribuzione.
  
La funzionalità mobilità per Skype for Business Server è in grado di supportare i client mobili per Skype for business e i client Lync risalenti a 2010. Una volta distribuita, gli utenti possono connettersi alla distribuzione di Skype for Business Server con i dispositivi mobili supportati iOS, Android e Windows Phone per sfruttare diverse funzionalità, tra cui le funzionalità VoIP aziendale. È stato incluso un elenco parziale di seguito ed è anche possibile controllare il [confronto delle caratteristiche del client desktop per Skype for business](clients-and-devices/desktop-feature-comparison.md) per altre info:
  
- Inviare e ricevere messaggi
    
- Visualizzare la presenza
    
- Visualizzare i contatti
    
- Fare clic per partecipare a una conferenza
    
- Chiamata tramite lavoro
    
- Portata numero singolo
    
- Segreteria telefonica
    
- Notifica di chiamata senza risposta
    
- Voice over IP (VoIP)
    
- Video partecipanti (H. 264)
    
- Visualizzazione del contenuto della riunione (PowerPoint e condivisione desktop/applicazioni)
    
Tutto questo viene eseguito tramite l'API Web Unified Communications o UCWA. UCWA è stato introdotto per la prima volta in Lync Server 2013 ed è ancora in uso per Skype for Business Server. Sono disponibili altre funzionalità per comunicare con i client di Lync 2010 e il servizio di mobilità (MCX). Si tratta di servizi gratuiti, che consentono ai client Lync Server 2010 e 2013, oltre ai client Skype for business, di accedere correttamente alle distribuzioni di Skype for Business Server.
  
> [!NOTE]
> Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
È importante notare che, mentre tutte queste caratteristiche sono disponibili una volta implementata la mobilità, potrebbero funzionare in modo leggermente diverso in alcuni dispositivi. Abbiamo un sito Web in cui vengono illustrate le caratteristiche che funzionano con i dispositivi, il [confronto tra funzionalità client mobile per Skype for business](clients-and-devices/mobile-feature-comparison.md). In [piano per clienti e dispositivi](clients-and-devices/clients-and-devices.md)sono disponibili anche informazioni su dispositivi e sistemi operativi di grande livello.
  
La mobilità fa uso della funzionalità di individuazione automatica, che consente ai client di individuare automaticamente i servizi Web di Skype for Business Server senza che gli utenti debbano immettersi in qualsiasi URL (non avranno nemmeno bisogno di conoscerli). Se è necessario eseguire alcune operazioni di risoluzione dei problemi, l'immissione manuale degli URL è ancora supportata.
  
Anche le notifiche push sono supportate, perché quando l'app Skype for business non è in background (o per i dispositivi mobili che non supportano le applicazioni in uso in background). Viene inviata una notifica push a un dispositivo mobile relativo a un evento che si verifica quando il dispositivo o l'app non è attiva. Quando il telefono non è attivo, viene visualizzato un messaggio di messaggistica istantanea che causa l'invio di una notifica push (viene presentato come avviso popup o notifica, ad esempio quando l'app viene eseguita in background). Con le notifiche push, gli utenti non potranno perdere la messaggistica istantanea o le chiamate vocali.
  
Per altre informazioni, sono presenti le sezioni seguenti:
  
- [Componenti per la mobilità](mobility.md#MobilityComponents)
    
- [Topologie supportate](mobility.md#SupportedTopos)
    
- [Requisiti tecnici](mobility.md#TechRequirements)
    
- [Definizione delle esigenze di mobilità](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componenti per la mobilità
<a name="MobilityComponents"> </a>

Sono disponibili quattro servizi che includono la mobilità per Skype for Business Server:
  
- **API Web per comunicazioni unificate (UCWA)**
    
    Offre servizi per comunicazioni in tempo reale con i client per dispositivi mobili e Web per Skype for Business Server. Quando si distribuisce Skype for Business Server, viene creata una directory virtuale UCWA nei servizi Web interni ed esterni. Un componente virtuale in questa directory virtuale che accetta chiamate da client abilitati per UCWA. Le app client comunicano tramite un'interfaccia REST (Representational State Transfer) per:
    
  - presenza
    
  - contatti
    
  - messaggistica istantanea (IM)
    
  - VoIP
    
  - video conferenza
    
  - collaborazione
    
    UCWA usa un canale basato su P-GET per inviare eventi, ad esempio una chiamata in arrivo, un messaggio ISTANTANEo in arrivo o un Message all'app client.
    
- **Servizio di mobilità (MCX)**
    
    Supporta le funzionalità di Skype for Business Server, ad esempio messaggistica istantanea, presenza e contatti, nei dispositivi mobili. Il servizio di mobilità viene installato in ogni server front-end in ogni pool progettato per supportare le funzionalità di Skype for Business Server nei dispositivi mobili. Quando si installa Skype for Business Server 2015, viene creata una nuova directory virtuale (MCX) in entrambi i siti Web interni ed esterni nei server front-end.
    
    > [!NOTE]
    > Il supporto di MCX (servizio mobilità) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client di Skype for business mobile correnti usano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
- **Servizio di individuazione automatica**
    
    Identifica la posizione dell'utente e consente ai dispositivi mobili e ad altri client Skype for business di individuare le risorse, ad esempio gli URL interni ed esterni per i servizi Web di Skype for Business Server, l'URL MCX o l'URL UCWA, indipendentemente dal percorso di rete. L'individuazione automatica usa nomi host hardcoded (lyncdiscoverinternal per gli utenti all'interno della rete, lyncdiscover per gli utenti esterni alla rete) e il dominio SIP dell'utente. Supporta le connessioni client che usano HTTP o HTTPS. 
    
    Il servizio di individuazione automatica viene installato in ogni server front-end e in ogni Director in ogni pool destinato a supportare le funzionalità di Skype for Business Server nei dispositivi mobili. Quando si installa il servizio, viene creata una nuova directory virtuale (individuazione automatica) in entrambi i siti Web interni ed esterni nei server e nei direttori front-end.
    
- **Servizio notifica push**
    
    Un servizio basato su cloud che si trova nel centro dati di Skype for business online. Nei telefoni che non hanno client Skype for business in corso in background, quando si verifica un nuovo evento, viene inviata al dispositivo mobile la notifica di un evento mancato (chiamata notifica push). Il servizio di mobilità invia una notifica al servizio di notifica push (MPNS), che lo invia al dispositivo mobile. L'utente può quindi rispondere alla notifica sul dispositivo mobile per attivare l'app. Per questa funzionalità è necessario un server perimetrale.
    
## <a name="supported-topologies"></a>Topologie supportate
<a name="SupportedTopos"> </a>

Per la pianificazione della topologia sono supportate le applicazioni Skype for Business Server seguenti:
  
- Mobilità Standard Edition
    
- Mobility Enterprise Edition
    
Dovresti essere in grado di usare questa funzionalità con Skype for Business Server Edge Servers o Lync Server 2013 Edge Servers.
  
Il servizio di mobilità è supportato nei server front-end quando è collocato con il ruolo di Mediation Server, con due interfacce di rete, ma è necessario eseguire le operazioni appropriate per configurare tali interfacce. Sarà necessario assegnare indirizzi IP all'interfaccia specifica che comunicherà come Mediation Server e l'interfaccia IP di rete che comunicherà come server front-end. Puoi eseguire questa operazione in Generatore di topologia selezionando l'indirizzo IP corretto per ogni servizio, invece di usare la selezione predefinita di **tutti gli indirizzi IP** configurati.
  
## <a name="technical-requirements"></a>Requisiti tecnici
<a name="TechRequirements"> </a>

È importante pianificare i vari scenari di applicazione per dispositivi mobili che possono verificarsi gli utenti di dispositivi mobili. Ad esempio, qualcuno potrebbe iniziare a usare un'app per dispositivi mobili al di fuori del lavoro connettendosi tramite una rete 3G, quindi passare alla rete Wi-Fi aziendale quando raggiungono il lavoro. Possono passare a 4G quando si esce dall'edificio. La pianificazione ora consentirà di supportare queste transizioni di rete e garantire un'esperienza utente coerente.
  
### <a name="dns-configuration"></a>Configurazione DNS

I servizi di mobilità MCX e UCWA usano DNS nello stesso modo. Con l'individuazione automatica, i dispositivi mobili usano DNS per individuare le risorse. Durante la ricerca DNS, una connessione ha tentato l'FQDN associato al record DNS interno (lyncdiscoverinternal. [ nome di dominio interno]). Se il record DNS interno non può essere usato per effettuare la connessione, viene tentata una seconda connessione, questa volta al record DNS esterno (lyncdiscover. [ SipDomain]). Perché sono presenti due? Un dispositivo mobile interno alla rete sarà in grado di usare l'URL di individuazione automatica interno. I dispositivi mobili esterni useranno l'URL di individuazione automatica esterno. In entrambi i casi, il servizio di individuazione automatica restituirà tutti gli URL del servizio Web per il pool di Home dell'utente, che include il servizio di mobilità (MCX e UCWA).
  
È prevedibile che le richieste di individuazione automatica esterna facciano scorrere il proxy inverso configurato per Skype for Business Server. Tuttavia, sia l'URL del servizio di mobilità interno che l'URL del servizio di mobilità esterna sono associati all'FQDN dei servizi Web esterni. Pertanto, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio di mobilità di Skype for Business Server esternamente, tramite il proxy inverso.
  
> [!NOTE]
> Come abbiamo appena notato, tutto il traffico del servizio di mobilità (interno ed esterno) passerà attraverso il proxy inverso. Ma a volte un problema si presenta quando il traffico interno passa attraverso un'interfaccia, solo per provare e tornare alla stessa interfaccia. In questo modo è possibile violare lo spoofing (formalmente si chiama regole di sicurezza dei pacchetti TCP). È necessario consentire il **blocco dei capelli** per avere la funzione mobilità.
  
> [!NOTE]
> Se si è pronti a eseguire questa operazione, è anche possibile scegliere di usare un proxy inverso separato dal firewall (per motivi di sicurezza, la prevenzione dello spoofing deve sempre essere applicata al firewall). In questo modo, il tornante può essere visualizzato all'interfaccia esterna del proxy inverso, invece dell'interfaccia esterna del firewall. In questo modo è possibile rilevare correttamente lo spoofing sul firewall mentre si distende la regola al proxy inverso e si ottengono le funzionalità di mobilità. 
  
> [!NOTE]
> Se si passa a questa route, assicurarsi di usare l'host DNS o i record CNAME per definire il proxy inverso per il comportamento dei tornanti (non il firewall), se possibile. 
  
È necessario configurare alcuni aspetti per supportare gli utenti all'interno e all'esterno della rete aziendale.
  
Queste sono le regole per gli FQDN Web interni ed esterni:
  
- Nuovo record DNS CNAME o A (host, if IPv6, AAAA) per l'individuazione automatica.
    
- Nuova regola del firewall, se si vuole supportare le notifiche push tramite la rete Wi-Fi.
    
- Nomi alternativi oggetto di certificati server interni e certificati di reverse proxy per l'individuazione automatica.
    
- Le modifiche apportate alla configurazione del bilanciamento del carico hardware del server front-end.
    
Questi sono i requisiti di topologia necessari per supportare il servizio di mobilità e il servizio di individuazione automatica:
  
- Il nome FQDN interno del pool di front end deve essere distinto dall'FQDN Web esterno del pool Front-end.
    
- Il nome di dominio completo Web interno deve essere risolto e accessibile dall'interno della rete aziendale.
    
- Il nome FQDN Web esterno deve essere risolto solo per essere accessibile da Internet.
    
- Per un utente all'interno della rete aziendale, l'URL del servizio di mobilità deve essere indirizzato al nome di dominio completo Web esterno. Questo requisito è per il servizio di mobilità e si applica solo a questo URL.
    
- Per un utente esterno alla rete aziendale, la richiesta deve andare al nome FQDN Web esterno del pool o del Director di front-end.
    
Se si supporta l'individuazione automatica, è necessario impostare i record DNS seguenti per ogni dominio SIP:
  
- Record DNS interno che supporta gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione.
    
- Un record DNS esterno o pubblico per supportare gli utenti di dispositivi mobili che si connettono da Internet.
    
L'URL di individuazione automatica interno non deve essere indirizzabile all'esterno della rete interna. L'URL di individuazione automatica esterna non deve essere indirizzabile dall'interno della rete. Ma se non è possibile per l'URL esterno, la funzionalità del client per dispositivi mobili probabilmente non sarà interessata, perché l'URL interno verrà sempre provato per primo.
  
### <a name="port-and-firewall-requirements"></a>Requisiti per la porta e il firewall

La maggior parte di questi documenti è stata trattata in un'altra documentazione, ma in particolare per la mobilità, se si hanno utenti ospitati in un Survivable Branch Appliance (SBA), si vogliono aprire le porte seguenti nella rete Wi-Fi aziendale:
  
- UcwaSipExternalListeningPort richiede 5088.
    
- UcwaSipPrimaryListeningPort richiede 5089.
    
### <a name="certificate-requirements"></a>Requisiti per i certificati

Se si usa l'individuazione automatica per i client di Skype for business per dispositivi mobili, è necessario modificare gli elenchi SAN (nome alternativo oggetto) nei certificati per supportare connessioni sicure dai client mobili. Se sono già presenti certificati sul posto, è necessario richiedere e assegnare nuovi certificati con le voci SAN descritte qui. Questa operazione deve essere eseguita per ogni server front-end e Director (se nell'ambiente) che esegue il servizio di individuazione automatica. Consigliamo anche di modificare gli elenchi SAN nei certificati di proxy inverso, aggiungendo le voci SAN per ogni dominio SIP dell'organizzazione.
  
Questo dovrebbe essere un processo semplice se si richiede che i nuovi CERT vengano disattivati da una CA interna (autorità di certificazione), ma i certificati pubblici sono più complessi e potenzialmente molto più costosi da ripetere, per non parlare che potrebbe essere costoso aggiungere molto SIP domini a un nuovo CERT pubblico. In questa situazione esiste un approccio supportato, ma **non consigliato**. Puoi configurare il proxy inverso per eseguire la richiesta di servizio di individuazione automatica tramite la porta 80, che utilizzerà HTTP, invece della porta 443, che è HTTPS (e 443 è la configurazione predefinita). La richiesta in arrivo verrà reindirizzata alla porta 8080 nel pool o nel Director di front-end. In questo modo, non dovrai apportare modifiche al certificato, perché il traffico non usa HTTPS per le richieste. Ma ancora una volta, non è consigliabile, anche se funzionerà per l'utente.
  
### <a name="windows-and-iis-requirements"></a>Requisiti di Windows e IIS

Dovresti avere una versione di Windows Server supportata per l'ambiente di Skype for Business Server. Di conseguenza, dovresti avere anche IIS 8 o IIS 8,5 per le tue esigenze di mobilità. Sarà necessario apportare alcune modifiche alle impostazioni predefinite di ASP.NET, ma il programma di installazione del servizio di mobilità lo eseguirà automaticamente.
  
### <a name="hlb-requirements"></a>Requisiti di HLB

Se si usa una topologia per Skype for Business Server che include un HLB per il pool Front-End (che sarebbe qualsiasi topologia che include più di un server front-end), è necessario configurare l'IPs virtuale (VIP) dei servizi Web esterni per il traffico di servizi Web per l'origine. L'affinità di origine consente di garantire che più connessioni da un singolo client vengano inviate allo stesso server per mantenere lo stato della sessione.
  
Se si prevede di supportare i client per dispositivi mobili Skype for business solo tramite la rete Wi-Fi interna, è consigliabile configurare i VIP dei servizi Web interni per l'origine, come descritto per i VIP dei servizi Web esterni. In questa situazione dovresti usare l'affinità di Source_addr (o TCP) per i VIP dei servizi Web interni su HLB.
  
Per informazioni dettagliate su tutto questo, vedere i [requisiti di bilanciamento del carico per la documentazione di Skype for business](network-requirements/load-balancing.md) .
  
### <a name="reverse-proxy-requirements"></a>Requisiti del proxy inverso

Per supportare l'individuazione automatica per i client per dispositivi mobili Skype for business, è necessario aggiornare la regola di pubblicazione corrente come indicato di seguito:
  
- Se si decide di aggiornare gli elenchi SAN nei certificati di proxy inverso e si usa HTTPS per la richiesta di servizio di individuazione automatica iniziale, è necessario aggiornare la regola di pubblicazione Web per lyncdiscover. \<SipDomain\>. Questa operazione viene in genere combinata con il RUL di pubblicazione per l'URL dei servizi Web esterni nel pool Front-end.
    
- Se si è deciso di usare HTTP per la richiesta di servizio di individuazione automatica per evitare di dover aggiornare l'elenco SAN per i certificati del proxy inverso (che non è consigliabile), è necessario creare una nuova regola di pubblicazione Web per la porta HTTP/TCP 80, se non è presente uno già. Se tale regola esiste, aggiornarla per includere un lyncdiscover. \<voce\> SipDomain.
    
## <a name="defining-your-mobility-needs"></a>Definizione delle esigenze di mobilità
<a name="MobilityNeeds"> </a>

Ora che abbiamo esaminato le topologie, i componenti e i requisiti tecnici, esaminiamo l'esigenza dell'organizzazione in termini di implementazione della mobilità.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Si vuole usare l'individuazione automatica per i client per dispositivi mobili Skype for business?

Ti consigliamo vivamente di usare l'individuazione automatica. Richiederà la creazione di nuovi record DNS interni ed esterni, come documentato nella sezione requisiti tecnici descritti sopra. Con l'individuazione automatica, i client Skype for business possono individuare automaticamente i servizi web Skype for Business Server da qualsiasi posizione, senza che sia necessario immettere manualmente un URL.
  
Se necessario, è possibile usare le impostazioni manuali. Questi URL dovranno essere immessi dagli utenti nei loro dispositivi mobili:
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root** per l'accesso esterno.
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root** per l'accesso interno.
    
Di nuovo, consigliamo di usare l'individuazione automatica. È possibile trovare le impostazioni manuali utili per la risoluzione dei problemi.
  
### <a name="are-you-going-to-support-push-notifications"></a>Si intende supportare le notifiche push?

Le notifiche push vengono usate per le applicazioni mobili che supportano questa funzionalità per inviare notifiche a un utente di eventi mentre l'app non è attiva. Il server perimetrale dovrà avere una relazione federativa con il servizio di notifica push di Skype for Business Server basato su cloud, disponibile nel Data Center di Skype for business online. È necessario eseguire un cmdlet per abilitare le notifiche push.
  
> [!NOTE]
> Se si hanno ancora utenti che usano client Lync Server 2010, sarà necessario aprire la porta TCP 5223 in uscita nella rete WiFi aziendale. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Si desidera che tutti gli utenti accedano a tutte le caratteristiche di mobilità oppure si desidera specificare gli utenti che possono accedere a queste funzionalità?

È disponibile una tabella che consente di usare alcune delle funzionalità disponibili per tutti gli utenti e se sono impostate in questo modo o meno per impostazione predefinita. Per un elenco completo, rivedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Gli ambiti per tutte queste funzionalità sono globali/sito/utente. 
  
|**Funzionalità**|**Nome parametro**|**Descrizione**|**Impostazione predefinita**|
|:-----|:-----|:-----|:-----|
|Abilitare la mobilità  <br/> |EnableMobility  <br/> |Controlla gli utenti in un ambito specifico in cui è installato il client di Skype for business mobile. Se il criterio è impostato su false, gli utenti non saranno in grado di accedere con il proprio client.  <br/> |True  <br/> |
|Voce esterna  <br/> |EnableOutsideVoice  <br/> |Consente a un utente di usare la chiamata tramite lavoro, che consente agli utenti di inviare e ricevere chiamate usando il loro numero di lavoro invece del numero di cellulare. Se è impostata su falso, gli utenti non potranno effettuare o ricevere chiamate sul proprio telefono cellulare quando usano il proprio numero di telefono dell'ufficio.  <br/> |True  <br/> |
|Abilitare l'audio e il video IP  <br/> |EnableIPAudioVideo  <br/> |Impostato sul valore predefinito, consente a un utente di usare il VoIP per effettuare o ricevere chiamate telefoniche o video nel dispositivo mobile. Quando è impostato su false, gli utenti non potranno usare il loro dispositivo mobile per eseguire una di queste operazioni.  <br/> |True  <br/> |
|Richiedi Wi-Fi per l'audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Definisce se un cliente dovrà effettuare e ricevere chiamate tramite VoIP su WiFi anziché su una rete dati cellulare. Se è impostato su true, gli utenti potranno effettuare e ricevere chiamate VoIP solo quando sono connessi tramite WiFi.  <br/> |False  <br/> |
|Richiedi Wi-Fi per IP video  <br/> |RequireWiFiForIPVideo  <br/> |Definisce se un client dovrà effettuare e ricevere videochiamate su WiFi anziché su una rete dati cellulare. Se è impostato su true, gli utenti potranno effettuare e ricevere chiamate VoIP solo quando sono connessi tramite WiFi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Gli utenti che non sono abilitati per Enterprise Voice possono usare i comandi click to join per partecipare alle conferenze?

Per consentire agli utenti di accedere alle caratteristiche di mobilità e chiamarle tramite lavoro, è necessario abilitarle per VoIP aziendale. Ma anche se non sono abilitate, possono ancora partecipare a conferenze facendo clic su un collegamento nel dispositivo mobile, ma solo se è stato assegnato un criterio vocale appropriato. Puoi:
  
- assegnare un criterio vocale specifico a questi utenti oppure
    
- Verificare che esista un criterio globale o a livello di sito e si applichi a tali criteri.
    
In entrambi i casi, il criterio vocale assegnato deve avere record di utilizzo PSTN (Public Switched Telephone Network) e route che definiranno la posizione in cui gli utenti potranno effettuare la chiamata per partecipare alle conferenze.
  
> [!NOTE]
> Gli utenti di dispositivi mobili che vogliono usare click to join richiedono un criterio vocale, insieme ai relativi record di utilizzo PSTN e alle route vocali, perché quando si fa clic su quel collegamento nei propri dispositivi mobili, sarà il risultato di una chiamata in uscita da Skype for Business Server. 
  

