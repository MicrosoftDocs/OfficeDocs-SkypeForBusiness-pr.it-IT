---
title: Pianificare la mobilità per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Pianificare la propria implementazione della mobilità per Skype for Business Server.
ms.openlocfilehash: 6452154db1047cfe91a7c8ceaf6ee6c63b94ee6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810076"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Pianificare la mobilità per Skype for Business Server
 
Pianificare la propria implementazione della mobilità per Skype for Business Server.
  
Con Skype for Business Server, è possibile distribuire la funzionalità di mobilità per fornire le funzionalità di Skype for Business Server nei dispositivi mobili. In questo articolo vengono fornite informazioni dettagliate sulla funzionalità per dispositivi mobili e viene illustrato come pianificare la distribuzione.
  
La funzionalità di mobilità per Skype for Business Server è in grado di supportare i client mobili per Skype for business, nonché i client Lync risalenti a 2010. Una volta distribuito, gli utenti possono connettersi alla distribuzione di Skype for Business Server utilizzando i dispositivi mobili supportati per iOS, Android e Windows Phone per usufruire di diverse funzionalità, tra cui le funzionalità di VoIP aziendale. È stato incluso un elenco parziale in basso ed è inoltre possibile controllare il [confronto delle funzionalità dei client desktop per Skype for business](clients-and-devices/desktop-feature-comparison.md) per altre info:
  
- Inviare e ricevere messaggi
    
- Visualizzazione della presenza
    
- Visualizza contatti
    
- Fare clic per partecipare a una conferenza
    
- Chiamata tramite lavoro
    
- Raggiungimento numero singolo
    
- Posta vocale
    
- Notifica di chiamata senza risposta
    
- VoIP (Voice over IP)
    
- Video partecipante (H. 264)
    
- Visualizzazione del contenuto delle riunioni (PowerPoint e condivisione applicazioni e desktop)
    
Tutto ciò viene ottenuto tramite l'API Web Unified Communications o UCWA. UCWA è stato introdotto per la prima volta in Lync Server 2013 ed è ancora in uso per Skype for Business Server. Sono disponibili altre funzionalità per la comunicazione con i client di Lync 2010 e il servizio per dispositivi mobili (MCX). Si tratta di servizi gratuiti che consentono ai client Lync Server 2010 e 2013, nonché ai client Skype for business, di accedere correttamente alle distribuzioni di Skype for Business Server.
  
> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
È importante tenere presente che, quando tutte queste caratteristiche sono disponibili dopo l'implementazione della funzionalità, potrebbero funzionare un po' diversamente in alcuni dispositivi. È presente un sito Web in cui vengono illustrate le caratteristiche che interagiscono con i dispositivi, al [confronto tra le funzionalità dei client mobili di Skype for business](clients-and-devices/mobile-feature-comparison.md). In [Plan for clients and Devices](clients-and-devices/clients-and-devices.md)sono inoltre disponibili informazioni su dispositivi e sistemi operativi ottimali.
  
La funzionalità mobilità utilizza la caratteristica di individuazione automatica, che consente ai client di individuare automaticamente i servizi Web di Skype for Business Server senza che gli utenti debbano immettere gli URL (non avranno nemmeno bisogno di conoscerli). Se è necessario eseguire alcune procedure di risoluzione dei problemi, la voce manuale degli URL è ancora supportata.
  
Anche le notifiche push sono supportate, perché quando l'app Skype for business non è in esecuzione in background (o per i dispositivi mobili che non supportano le applicazioni in esecuzione in background). Una notifica push viene inviata a un dispositivo mobile relativo a un evento che si verifica quando il dispositivo o l'app non è attiva. Un buon esempio manca un messaggio di messaggistica istantanea quando il telefono non è attivo, che comporterà l'invio di una notifica push (viene presentato come un brindisi o una notifica, come quando l'app è in esecuzione in background). Con le notifiche push, gli utenti non mancherà la messaggistica istantanea o le chiamate vocali.
  
Per ulteriori informazioni, sono presenti le sezioni seguenti:
  
- [Componenti per dispositivi mobili](mobility.md#MobilityComponents)
    
- [Topologie supportate](mobility.md#SupportedTopos)
    
- [Requisiti tecnici](mobility.md#TechRequirements)
    
- [Definizione delle esigenze di mobilità](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componenti per dispositivi mobili
<a name="MobilityComponents"> </a>

Sono disponibili quattro servizi che compongono la mobilità per Skype for Business Server:
  
- **API Web per le comunicazioni unificate (UCWA)**
    
    Fornisce servizi per le comunicazioni in tempo reale con i client mobili e Web per Skype for Business Server. Quando si distribuisce Skype for Business Server, viene creata una directory virtuale di UCWA nei servizi Web interni ed esterni. Componente virtuale in questa directory virtuale che accetta le chiamate provenienti da client abilitati per UCWA. Le app client comunicano su un'interfaccia REST (Representational State Transfer) per:
    
  - presenza
    
  - contatti
    
  - messaggistica istantanea (IM)
    
  - VoIP
    
  - video Conferencing
    
  - collaborazione
    
    UCWA utilizza un canale basato su P-GET per inviare eventi, ad esempio una chiamata in arrivo, una messaggistica istantanea in arrivo o un messaggio all'app client.
    
- **Servizio per dispositivi mobili (MCX)**
    
    Supporta le funzionalità di Skype for Business Server, quali messaggistica istantanea, presenza e contatti, su dispositivi mobili. Il servizio per dispositivi mobili è installato su tutti i front end server in ogni pool che ha lo scopo di supportare le funzionalità di Skype for Business Server nei telefoni cellulari. Quando si installa Skype for Business Server 2015, viene creata una nuova directory virtuale (MCX) in entrambi i siti Web interni ed esterni nei server front end.
    
    > [!NOTE]
    > Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
- **Servizio di individuazione automatica**
    
    Identifica la posizione dell'utente e consente ai dispositivi mobili e ad altri client Skype for business di individuare risorse (ad esempio, gli URL interni ed esterni per i servizi Web di Skype for Business Server, l'URL di MCX o l'URL di UCWA) indipendentemente dal percorso di rete. Individuazione automatica utilizza nomi host hardcoded (lyncdiscoverinternal per gli utenti all'interno della rete, lyncdiscover per gli utenti all'esterno della rete) e il dominio SIP dell'utente. Supporta le connessioni client che utilizzano HTTP o HTTPS. 
    
    Il servizio di individuazione automatica è installato su tutti i Front End Server e su tutti i Director di ogni pool che ha lo scopo di supportare le funzionalità di Skype for Business Server nei dispositivi mobili. Quando si installa il servizio, viene creata una nuova directory virtuale (individuazione automatica) in entrambi i siti Web interni ed esterni nei server front-end e nei direttori.
    
- **Servizio di notifica push**
    
    Un servizio basato sul cloud che si trova nel Data Center di Skype for business online. Nei telefoni che non dispongono di client Skype for business in esecuzione in background, quando si verifica un nuovo evento, la notifica di un evento mancante (denominato notifica push) viene invece inviata al dispositivo mobile. Il servizio per dispositivi mobili invia una notifica al servizio di notifica push (MPNS), che lo invia al dispositivo mobile. L'utente può quindi rispondere alla notifica sul proprio dispositivo mobile per attivare l'app. Per questa funzionalità è necessario un server perimetrale.
    
## <a name="supported-topologies"></a>Topologie supportate
<a name="SupportedTopos"> </a>

Per la pianificazione della topologia sono disponibili le seguenti applicazioni di Skype for Business Server supportate:
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
È possibile utilizzare questa funzionalità con Skype for Business Server Edge Server o Lync Server 2013 Edge Server.
  
Il servizio per dispositivi mobili è supportato nei front end server quando è collocato con il ruolo Mediation Server, con due interfacce di rete, ma è necessario eseguire le procedure appropriate per configurare tali interfacce. Sarà necessario assegnare gli indirizzi IP all'interfaccia specifica che comunicherà come Mediation Server e l'interfaccia IP di rete che comunicherà come front end server. È possibile eseguire questa operazione in Generatore di topologie selezionando l'indirizzo IP corretto per ogni servizio, anziché utilizzare l'impostazione predefinita **Usa tutti gli indirizzi IP configurati** .
  
## <a name="technical-requirements"></a>Requisiti tecnici
<a name="TechRequirements"> </a>

È importante pianificare i diversi scenari di applicazioni per dispositivi mobili che possono verificarsi gli utenti di dispositivi mobili. Ad esempio, un utente può iniziare a utilizzare un'app per dispositivi mobili al di fuori del lavoro collegandosi tramite una rete 3G, quindi passare alla rete Wi-Fi aziendale quando raggiunge il lavoro. Possono passare a 4G quando lasciano la propria struttura. La pianificazione ora consentirà di supportare queste transizioni di rete e garantire un'esperienza utente coerente.
  
### <a name="dns-configuration"></a>Configurazione del sistema DNS

I servizi per dispositivi mobili MCX e UCWA utilizzano DNS nello stesso modo. Con l'individuazione automatica, i dispositivi mobili utilizzano DNS per individuare le risorse. Durante la ricerca DNS, il tentativo di una connessione al nome di dominio completo associato al record DNS interno (lyncdiscoverinternal. [ nome di dominio interno]). Se il record DNS interno non può essere utilizzato per effettuare la connessione, viene tentata una seconda connessione, questa volta al record DNS esterno (lyncdiscover. [ SipDomain]). Quindi, perché sono due? Un dispositivo mobile interno alla rete sarà in grado di utilizzare l'URL di individuazione automatica interno. I dispositivi mobili esterni utilizzeranno l'URL di individuazione automatica esterno. In entrambi i casi, il servizio di individuazione automatica restituirà tutti gli URL dei servizi Web per il pool principale dell'utente, che include il servizio per dispositivi mobili (MCX e UCWA).
  
Le richieste di individuazione automatica esterne passano attraverso il proxy inverso configurato per Skype for Business Server. Tuttavia, sia l'URL del servizio per dispositivi mobili interno che l'URL del servizio per dispositivi mobili esterni sono associati all'FQDN dei servizi Web esterni. Pertanto, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio per dispositivi mobili di Skype for Business Server esternamente, tramite il proxy inverso.
  
> [!NOTE]
> Come abbiamo appena rilevato, tutto il traffico del servizio per dispositivi mobili (interno ed esterno) passerà attraverso il proxy inverso. Tuttavia, a volte un problema si presenta quando il traffico interno passa attraverso un'interfaccia, solo per poi provare a tornare sulla stessa interfaccia. Questo può violare lo spoofing (formalmente si chiama protocollo di protezione dei pacchetti TCP). Sarà necessario consentire al **pinning dei capelli** di avere una funzione di mobilità.
  
> [!NOTE]
> Se si è pronti a eseguire questa operazione, è anche possibile scegliere di usare un proxy inverso separato dal firewall (per motivi di sicurezza, la prevenzione dello spoofing dovrebbe essere sempre applicata al firewall). In questo modo, la tornante può verificarsi nell'interfaccia esterna del proxy inverso, anziché nell'interfaccia esterna del firewall. In questo modo è possibile rilevare correttamente lo spoofing sul firewall mentre si rilassa la regola al proxy inverso e si ottiene la funzionalità di mobilità. 
  
> [!NOTE]
> Se si passa questa route, assicurarsi di utilizzare l'host DNS o i record CNAME per definire il proxy inverso per il comportamento dei tornanti (non il firewall), se possibile. 
  
È necessario configurare alcuni elementi per supportare gli utenti all'interno e all'esterno della rete aziendale.
  
Queste sono le regole per gli FQDN Web interni ed esterni:
  
- Nuovi record DNS CNAME o A (host, if IPv6, AAAA) per l'individuazione automatica.
    
- Nuova regola del firewall, se si desidera supportare le notifiche push tramite la rete Wi-Fi.
    
- Nomi alternativi del soggetto sui certificati del server interno e sui certificati del proxy inverso, per l'individuazione automatica.
    
- L'affinità di origine del bilanciamento del carico hardware del server front-end viene modificata.
    
Questi sono i requisiti di topologia necessari per supportare il servizio per dispositivi mobili e il servizio di individuazione automatica:
  
- Il nome FQDN Web interno del pool Front end deve essere diverso dal nome FQDN Web esterno del pool Front end.
    
- Il nome di dominio completo Web interno deve essere risolto e accessibile dall'interno della rete aziendale.
    
- Il nome FQDN Web esterno deve essere risolto solo in Internet.
    
- Per un utente all'interno della rete aziendale, è necessario che l'URL del servizio per dispositivi mobili sia indirizzato all'FQDN Web esterno. Questo requisito è per il servizio per dispositivi mobili e si applica solo a questo URL.
    
- Per un utente esterno alla rete aziendale, la richiesta deve passare all'FQDN Web esterno del pool Front end o del server Director.
    
Se si supporta l'individuazione automatica, è necessario creare i record DNS seguenti per ogni dominio SIP:
  
- Un record DNS interno per supportare gli utenti di dispositivi mobili che si connettono dall'interno della rete dell'organizzazione.
    
- Un record DNS esterno, o pubblico, per supportare gli utenti di dispositivi mobili che si connettono da Internet.
    
L'URL di individuazione automatica interno non deve essere indirizzabile dall'esterno della rete interna. L'URL di individuazione automatica esterno non deve essere indirizzato all'interno della rete. Tuttavia, se l'URL esterno non è possibile, è probabile che la funzionalità dei client per dispositivi mobili non venga danneggiata, in quanto l'URL interno verrà sempre provato per primo.
  
### <a name="port-and-firewall-requirements"></a>Requisiti relativi a porte e firewall

La maggior parte di questo è stata trattata nell'altra documentazione, ma in particolare per la mobilità, si desidera che le porte seguenti siano aperte sulla rete aziendale Wi-Fi se sono presenti utenti che si trovano in un Survivable Branch Appliance (SBA):
  
- UcwaSipExternalListeningPort richiede 5088.
    
- UcwaSipPrimaryListeningPort richiede 5089.
    
### <a name="certificate-requirements"></a>Requisiti per i certificati

Se si utilizza il servizio di individuazione automatica per i client mobili Skype for business, è necessario modificare gli elenchi SAN (Subject Alternative Name) sui certificati per supportare connessioni sicure dai client mobili. Se si dispone già di certificati sul posto, è necessario richiedere e assegnare nuovi certificati con le voci di SAN descritte di seguito. Sarà necessario eseguire questa operazione per ogni Front End Server e Director (se nell'ambiente in uso) che esegue il servizio di individuazione automatica. È inoltre consigliabile modificare gli elenchi SAN nei certificati del proxy inverso, aggiungendo le voci di SAN per ogni dominio SIP nell'organizzazione.
  
Si tratta di un processo semplice se si richiedono i nuovi certificati da un'autorità di certificazione interna (Certificate Authority), ma è più complesso e potenzialmente molto più costoso rieseguire la richiesta, per non parlare del fatto che potrebbe essere costoso aggiungere un numero elevato di domini SIP a un nuovo CERT pubblico. In tale situazione, è disponibile un approccio che è supportato, ma **non consigliato**. È possibile configurare il proxy inverso per eseguire la richiesta iniziale del servizio di individuazione automatica sulla porta 80, che utilizzerà HTTP anziché la porta 443, ovvero HTTPS (e 443 è la configurazione predefinita). La richiesta in arrivo verrà reindirizzata alla porta 8080 del pool o del Director front end. In questo modo, non è necessario apportare modifiche al certificato, perché questo traffico non utilizza HTTPS per le richieste. Tuttavia, non è consigliabile, anche se funzionerà per l'utente.
  
### <a name="windows-and-iis-requirements"></a>Requisiti di Windows e IIS

È consigliabile disporre di una versione supportata di Windows Server per l'ambiente di Skype for Business Server. Di conseguenza, è necessario disporre anche di IIS 8 o IIS 8,5 per le proprie esigenze di mobilità. Sarà necessario apportare alcune modifiche alle impostazioni predefinite di ASP.NET, ma il programma di installazione del servizio per dispositivi mobili lo farà automaticamente.
  
### <a name="hlb-requirements"></a>Requisiti di HLB

Se si usa una topologia per Skype for Business Server che include un HLB per il pool Front End (che potrebbe essere una topologia che include più di un front end Server), è necessario configurare i servizi IP virtuali (VIP) per il traffico dei servizi Web per l'origine. L'affinità di origine consente di garantire che più connessioni da un singolo client vengano inviate allo stesso server per mantenere lo stato della sessione.
  
Se si prevede di supportare i client mobili Skype for business solo tramite la rete di Wi-Fi interna, è necessario configurare i VIP dei servizi Web interni per l'origine come descritto per i VIP dei servizi Web esterni. In questo caso, è consigliabile utilizzare l'affinità source_addr (o TCP) per i VIP dei servizi Web interni su HLB.
  
Per informazioni dettagliate su tutto questo, consultare i [requisiti di bilanciamento del carico per la documentazione di Skype for business](network-requirements/load-balancing.md) .
  
### <a name="reverse-proxy-requirements"></a>Requisiti per il proxy inverso

Al fine di supportare l'individuazione automatica per i client mobili Skype for business, è necessario aggiornare la regola di pubblicazione corrente come indicato di seguito:
  
- Se si decide di aggiornare gli elenchi SAN nei certificati del proxy inverso e si sta utilizzando HTTPS per la richiesta di servizio di individuazione automatica iniziale, è necessario aggiornare la regola di pubblicazione Web per \<sipdomain\> lyncdiscover. Questo è in genere combinato con l'RUL di pubblicazione per l'URL dei servizi Web esterni nel pool Front end.
    
- Se si è deciso di utilizzare HTTP per la richiesta iniziale del servizio di individuazione automatica per evitare di dover aggiornare l'elenco SAN per i certificati del proxy inverso (che non è consigliabile), è necessario creare una nuova regola di pubblicazione Web per la porta HTTP/TCP 80, se non ne esiste già una. Se tale regola esiste, aggiornarla in modo da includere un lyncdiscover.\<sipdomain\> voce.
    
## <a name="defining-your-mobility-needs"></a>Definizione delle esigenze di mobilità
<a name="MobilityNeeds"> </a>

Ora che sono state esaminate le topologie, i componenti e i requisiti tecnici, è possibile esaminare le esigenze dell'organizzazione in termini di implementazione di dispositivi mobili.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Si desidera utilizzare l'individuazione automatica per i client mobili Skype for business?

Si consiglia vivamente di utilizzare l'individuazione automatica. Richiederà la creazione di nuovi record DNS interni ed esterni, come documentato nella sezione requisiti tecnici sopra riportati. Con l'individuazione automatica, i client Skype for business possono individuare automaticamente i servizi web Skype for Business Server da qualsiasi posizione, senza che sia necessario immettere manualmente un URL.
  
Se necessario, è possibile utilizzare le impostazioni manuali. Questi URL dovranno essere immessi dagli utenti nei propri dispositivi mobili:
  
- **\<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/root https://** per l'accesso esterno.
    
- **\<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/root https://** per l'accesso interno.
    
Anche in questo caso, è consigliabile utilizzare l'individuazione automatica. È possibile trovare le impostazioni manuali utili per la risoluzione dei problemi.
  
### <a name="are-you-going-to-support-push-notifications"></a>Si intende supportare le notifiche push?

Le notifiche push vengono utilizzate per le applicazioni mobili che supportano questa funzionalità per notificare a un utente degli eventi quando l'app non è attiva. Il server perimetrale dovrà avere una relazione di federazione con il servizio di notifica push di Skype for Business Server basato sul cloud, che si trova nel datacenter di Skype for business online. È necessario eseguire un cmdlet per abilitare le notifiche push.
  
> [!NOTE]
> Se si hanno ancora utenti che utilizzano i client Lync Server 2010, è necessario che la porta TCP 5223 venga aperta in uscita sulla rete Wi-Fi aziendale. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Si desidera che tutti gli utenti accedano a tutte le funzionalità per dispositivi mobili oppure si desidera specificare gli utenti che possono accedere a queste funzionalità?

È disponibile una tabella che consente di eseguire alcune delle funzionalità disponibili per tutti gli utenti e se sono impostate in questo modo o meno per impostazione predefinita. Per un elenco completo, vedere [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
  
> [!NOTE]
> Gli ambiti di tutte queste funzionalità sono Global/site/user. 
  
|**Caratteristica**|**Nome del parametro**|**Descrizione**|**Impostazione predefinita**|
|:-----|:-----|:-----|:-----|
|Abilitare la mobilità  <br/> |EnableMobility  <br/> |Controlla gli utenti in un determinato ambito che hanno installato il client per dispositivi mobili Skype for business. Se il criterio è impostato su false, gli utenti non saranno in grado di eseguire l'accesso con il proprio client.  <br/> |Vero  <br/> |
|Voce esterna  <br/> |EnableOutsideVoice  <br/> |Consente all'utente di utilizzare la chiamata tramite il lavoro, in modo da consentire agli utenti di inviare e ricevere chiamate utilizzando il numero di lavoro invece del numero di cellulare. Se è impostato su false, gli utenti non saranno in grado di effettuare o ricevere chiamate sul proprio telefono cellulare quando utilizzano il numero di telefono dell'ufficio.  <br/> |Vero  <br/> |
|Abilitare l'audio e il video IP  <br/> |EnableIPAudioVideo  <br/> |Impostato sul valore predefinito, consente a un utente di utilizzare il VoIP per effettuare o ricevere chiamate telefoniche o video sul dispositivo mobile. Quando è impostato su false, gli utenti non saranno in grado di usare il proprio dispositivo mobile per eseguire una delle operazioni riportate di seguito.  <br/> |Vero  <br/> |
|Richiedi WiFi per l'audio IP  <br/> |RequireWiFiForIPAudio  <br/> |Definisce se un client deve effettuare e ricevere chiamate tramite VoIP su WiFi anziché su una rete di dati cellulare. Se è impostato su true, gli utenti saranno in grado di effettuare e ricevere chiamate VoIP solo quando sono connessi tramite Wi-Fi.  <br/> |False  <br/> |
|Richiedi il WiFi per IP video  <br/> |RequireWiFiForIPVideo  <br/> |Definisce se un client deve effettuare e ricevere chiamate video su WiFi anziché su una rete di dati cellulare. Se è impostato su true, gli utenti saranno in grado di effettuare e ricevere chiamate VoIP solo quando sono connessi tramite Wi-Fi.  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Gli utenti che non sono abilitati per VoIP aziendale potranno utilizzare fare clic per partecipare a conferenze?

Affinché gli utenti possano accedere alle funzionalità per dispositivi mobili e chiamare tramite lavoro, devono essere abilitati per VoIP aziendale. Tuttavia, anche se non sono abilitati, possono ancora partecipare a conferenze facendo clic su un collegamento sul dispositivo mobile, ma solo se dispongono di un criterio vocale appropriato assegnato. È possibile eseguire le operazioni seguenti:
  
- assegnare un criterio vocale specifico a questi utenti oppure
    
- Verificare che esistano criteri globali o a livello di sito per applicarli.
    
In entrambi i casi, il criterio vocale assegnato deve disporre di record di utilizzo PSTN (Public Switched Telephone Network) e rotte che definiranno la posizione in cui gli utenti saranno in grado di effettuare la chiamata per partecipare a conferenze.
  
> [!NOTE]
> Gli utenti mobili che desiderano utilizzare fare clic per partecipare richiedono un criterio vocale, insieme ai record di utilizzo PSTN correlati e alle route vocali, perché quando fanno clic su quel collegamento nei propri dispositivi mobili, la chiamata in uscita da Skype for Business Server sarà il risultato. 
  

