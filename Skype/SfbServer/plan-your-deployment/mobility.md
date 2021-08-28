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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Pianificare l'implementazione di Mobility per Skype for Business Server.
ms.openlocfilehash: 59523076dc3b59b92af41fc85ef4193a92c87d08
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632720"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Pianificare la mobilità per Skype for Business Server
 
Pianificare l'implementazione di Mobility per Skype for Business Server.
  
Con Skype for Business Server, puoi distribuire la funzionalità per dispositivi mobili per fornire Skype for Business Server funzionalità nei dispositivi mobili. In questo articolo vengono fornite informazioni dettagliate sulla funzionalità per dispositivi mobili e viene illustrata la pianificazione della distribuzione.
  
La funzionalità per dispositivi mobili per Skype for Business Server è in grado di supportare i client mobili per Skype for Business, nonché i client Lync che tornano alla versione 2010. Dopo la distribuzione, gli utenti possono connettersi alla distribuzione di Skype for Business Server usando i dispositivi mobili iOS, Android e Windows Phone supportati per sfruttare diverse funzionalità, tra cui VoIP aziendale. Di seguito è stato incluso un elenco parziale e puoi anche controllare Confronto funzionalità [client desktop](clients-and-devices/desktop-feature-comparison.md) per Skype for Business per altre info:
  
- Inviare e ricevere messaggi
    
- Visualizzare la presenza
    
- Visualizzare i contatti
    
- Fare clic per partecipare a una conferenza
    
- Chiamata tramite lavoro
    
- Raggiungi un singolo numero
    
- Posta vocale
    
- Notifica di chiamata senza chiamata
    
- VoIP (Voice over IP)
    
- Video partecipante (H.264)
    
- Visualizzazione del contenuto delle riunioni (PowerPoint e condivisione desktop/applicazioni)
    
Tutto questo viene ottenuto tramite l'API Web Unified Communications o UCWA. UCWA è stato introdotto per la prima volta in Lync Server 2013 ed è ancora in uso per Skype for Business Server. Esiste una funzionalità aggiuntiva per la comunicazione con i client Lync 2010, ovvero il servizio per dispositivi mobili (MCX). Si tratta di servizi gratuiti, che consentono ai client Lync Server 2010 e 2013, nonché ai client Skype for Business, di accedere correttamente Skype for Business Server distribuzione.
  
> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
È importante notare che, sebbene tutte queste funzionalità siano disponibili dopo l'implementazione di Mobility, potrebbero funzionare in modo leggermente diverso in alcuni dispositivi. Abbiamo un sito Web che illustra le funzionalità che funzionano su quali dispositivi, in Confronto delle funzionalità dei client mobili [per Skype for Business](clients-and-devices/mobile-feature-comparison.md). Abbiamo anche alcune informazioni su dispositivi e sistema operativo importanti in [Plan for clients and devices](clients-and-devices/clients-and-devices.md).
  
I dispositivi mobili usano la funzionalità di individuazione automatica, che consente ai client di individuare automaticamente i servizi Web di Skype for Business Server senza che gli utenti dovranno immettere alcun URL (non dovranno nemmeno conoscerli). Se è necessario eseguire alcune operazioni di risoluzione dei problemi, l'immissione manuale degli URL è ancora supportata.
  
Sono supportate anche le notifiche push, per quando l'app Skype for Business non è in esecuzione in background (o per i dispositivi mobili che non supportano le applicazioni in esecuzione in background). A un dispositivo mobile viene inviata una notifica push relativa a un evento che si verifica quando il dispositivo o l'app non è attiva. Un buon esempio è la mancanza di un messaggio di messaggistica istantanea quando il telefono non è attivo, il che comporta l'invio di una notifica push (viene presentata come avviso popup o notifica, ad esempio quando l'app è in esecuzione in background). Con le notifiche push, gli utenti non mancheranno le chiamate vocali o di messaggistica istantanea.
  
Per ulteriori informazioni, sono disponibili le sezioni seguenti:
  
- [Componenti per dispositivi mobili](mobility.md#MobilityComponents)
    
- [Topologie supportate](mobility.md#SupportedTopos)
    
- [Requisiti tecnici](mobility.md#TechRequirements)
    
- [Definizione delle esigenze di mobilità](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>Componenti per dispositivi mobili
<a name="MobilityComponents"> </a>

Esistono quattro servizi che comprendono Mobility per Skype for Business Server:
  
- **UNIFIED Communications Web API (UCWA)**
    
    Fornisce servizi per le comunicazioni in tempo reale con client mobili e Web per Skype for Business Server. Quando Skype for Business Server viene distribuita, viene creata una directory virtuale UCWA nei servizi Web interni ed esterni. Componente virtuale in questa directory virtuale che accetta chiamate da client abilitati per UCWA. Le app client comunicano tramite un'interfaccia REST (Representational State Transfer) per:
    
  - presence
    
  - contatti
    
  - messaggistica istantanea
    
  - VoIP
    
  - videoconferenza
    
  - collaborazione
    
    UCWA usa un canale basato su P-GET per inviare eventi, ad esempio una chiamata in arrivo, una messaggistica istantanea in arrivo o un messaggio all'app client.
    
- **Servizio per dispositivi mobili (MCX)**
    
    Supporta Skype for Business Server, ad esempio messaggistica istantanea, presenza e contatti, nei dispositivi mobili. Il servizio per dispositivi mobili viene installato in ogni Front End Server di ogni pool destinato a supportare Skype for Business Server funzionalità nei dispositivi mobili. Quando si installa Skype for Business Server 2015 viene creata una nuova directory virtuale (Mcx) sia nei siti Web interni che in siti Web esterni nei Front End Server.
    
    > [!NOTE]
    > Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.
  
- **Servizio di individuazione automatica**
    
    Identifica il percorso dell'utente e consente ai dispositivi mobili e ad altri client Skype for Business di individuare le risorse, ad esempio gli URL interni ed esterni per i servizi Web di Skype for Business Server, l'URL Mcx o l'URL UCWA, indipendentemente dal percorso di rete. L'individuazione automatica utilizza nomi host hardcoded (lyncdiscoverinternal per gli utenti all'interno della rete, lyncdiscover per gli utenti esterni alla rete) e il dominio SIP dell'utente. Supporta le connessioni client che utilizzano HTTP o HTTPS. 
    
    Il servizio di individuazione automatica viene installato in ogni Front End Server e in ogni Server Director di ogni pool destinato a supportare Skype for Business Server funzionalità nei dispositivi mobili. Quando si installa il servizio, viene creata una nuova directory virtuale (individuazione automatica) sia nei siti Web interni che in siti Web esterni nei Front End Server e nei Director.
    
- **Servizio di notifica Push**
    
    Un servizio basato sul cloud che si trova nel data center Skype for Business Online. Nei telefoni che non dispongono di un client Skype for Business in esecuzione in background, quando si verifica un nuovo evento, al dispositivo mobile viene invece inviata la notifica di un evento perso (denominato notifica push). Il servizio per dispositivi mobili invia una notifica al servizio di notifica push (MPNS), che quindi la invia al dispositivo mobile. L'utente può quindi rispondere alla notifica sul dispositivo mobile per attivare l'app. Per questa funzionalità è necessario un server perimetrale.
    
## <a name="supported-topologies"></a>Topologie supportate
<a name="SupportedTopos"> </a>

Sono disponibili le seguenti applicazioni Skype for Business Server per la pianificazione della topologia:
  
- Mobilità edizione Standard
    
- Mobility edizione Enterprise
    
Dovrebbe essere possibile utilizzare questa funzionalità con i Skype for Business Server server perimetrali o i server perimetrali di Lync Server 2013.
  
Il servizio per dispositivi mobili è supportato nei Front End Server se collocato con il ruolo Mediation Server, con due interfacce di rete, ma è necessario eseguire la procedura appropriata per configurare tali interfacce. Sarà necessario assegnare indirizzi IP all'interfaccia specifica che comunicherà come Mediation Server e all'interfaccia IP di rete che comunicherà come Front End Server. È possibile eseguire questa operazione in Generatore di topologie selezionando l'indirizzo IP corretto per ogni servizio, anziché utilizzare la selezione predefinita Usa tutti gli **indirizzi IP** configurati.
  
## <a name="technical-requirements"></a>Requisiti tecnici
<a name="TechRequirements"> </a>

È importante pianificare i vari scenari di applicazioni per dispositivi mobili che possono verificarsi per gli utenti di dispositivi mobili. Ad esempio, un utente potrebbe iniziare a usare un'app per dispositivi mobili all'esterno del lavoro connettendosi tramite una rete 3G e quindi passare alla rete Wi-Fi aziendale quando raggiunge il lavoro. Possono passare al 4G quando lasciano l'edificio. La pianificazione ora consentirà di supportare queste transizioni di rete e garantire un'esperienza utente coerente.
  
### <a name="dns-configuration"></a>Configurazione del sistema DNS

I servizi per dispositivi mobili Mcx e UCWA utilizzano DNS nello stesso modo. Con Individuazione automatica, i dispositivi mobili usano DNS per individuare le risorse. Durante la ricerca DNS, un tentativo di connessione all'FQDN associato al record DNS interno (lyncdiscoverinternal.[ nome di dominio interno]). Se non è possibile utilizzare il record DNS interno per effettuare tale connessione, viene tentata una seconda connessione, questa volta al record DNS esterno (lyncdiscover.[ sipdomain]). Allora perché ne hai due? Un dispositivo mobile interno alla rete sarà in grado di utilizzare l'URL di individuazione automatica interno. I dispositivi mobili esterni utilizzeranno l'URL di individuazione automatica esterno. In entrambi i casi, il servizio di individuazione automatica restituirà tutti gli URL del servizio Web per il pool principale dell'utente, che include il servizio per dispositivi mobili (Mcx e UCWA).
  
Si prevede che le richieste di individuazione automatica esterne passano attraverso il proxy inverso configurato per Skype for Business Server. Tuttavia, sia l'URL del servizio per dispositivi mobili interno che l'URL del servizio per dispositivi mobili esterno sono associati all'FQDN dei servizi Web esterni. Pertanto, indipendentemente dal fatto che un dispositivo mobile sia interno o esterno alla rete, il dispositivo si connette sempre al servizio Skype for Business Server Mobility esternamente, tramite il proxy inverso.
  
> [!NOTE]
> Come abbiamo appena fatto vedere, tutto il traffico del servizio per dispositivi mobili (interno ed esterno) passa attraverso il proxy inverso. Ma a volte si verifica un problema quando il traffico interno esce da un'interfaccia, solo per poi provare a tornare sulla stessa interfaccia. Ciò può violare le regole di sicurezza di spoofing (formalmente denominato spoofing dei pacchetti TCP). Dovrai consentire a **Hair Pinning di** avere la funzione Mobility.
  
> [!NOTE]
> Se si è pronti a eseguire questa operazione, è anche possibile scegliere di utilizzare un proxy inverso separato dal firewall (per motivi di sicurezza, la prevenzione dello spoofing deve sempre essere applicata nel firewall). In questo modo, l'hairpin può avvenire nell'interfaccia esterna del proxy inverso, anziché nell'interfaccia esterna del firewall. Ciò consente di rilevare correttamente lo spoofing nel firewall mentre si rilassa la regola nel proxy inverso e si ottiene la funzionalità per dispositivi mobili. 
  
> [!NOTE]
> Se si passa a questa route, assicurarsi di utilizzare l'host DNS o i record CNAME per definire il proxy inverso per il comportamento di hairpin (non il firewall), se possibile. 
  
È necessario configurare alcuni elementi per supportare gli utenti all'interno e all'esterno della rete aziendale.
  
Queste sono le regole per gli FQDN Web interni ed esterni:
  
- Nuovi record DNS CNAME o A (host, se IPv6, AAAA) per l'individuazione automatica.
    
- Nuova regola del firewall, se si desidera supportare le notifiche push tramite la Wi-Fi rete.
    
- Nomi alternativi del soggetto nei certificati server interni e nei certificati proxy inverso, per l'individuazione automatica.
    
- La configurazione con bilanciamento del carico hardware di Front End Server modifica l'affinità di origine.
    
Questi sono i requisiti della topologia necessari per supportare il servizio per dispositivi mobili e il servizio di individuazione automatica:
  
- L'FQDN Web interno del pool Front End deve essere distinto dall'FQDN Web esterno del pool Front End.
    
- L'FQDN Web interno deve essere risolto solo all'interno della rete aziendale ed essere accessibile da.
    
- L'FQDN Web esterno deve essere risolto solo in Internet ed essere accessibile da Internet.
    
- Per un utente all'interno della rete aziendale, l'URL del servizio per dispositivi mobili deve essere indirizzato all'FQDN Web esterno. Questo requisito è per il servizio per dispositivi mobili e si applica solo a questo URL.
    
- Per un utente esterno alla rete aziendale, la richiesta deve passare all'FQDN Web esterno del pool Front End o del Director.
    
Se si supporta l'individuazione automatica, sarà necessario creare i record DNS seguenti per ogni dominio SIP:
  
- Record DNS interno per supportare gli utenti mobili che si connettono dall'interno della rete dell'organizzazione.
    
- Record DNS esterno o pubblico per supportare gli utenti mobili che si connettono da Internet.
    
L'URL di individuazione automatica interno non deve essere indirizzabile dall'esterno della rete interna. L'URL di individuazione automatica esterno non deve essere indirizzabile dall'interno della rete. Tuttavia, se non è possibile per l'URL esterno, la funzionalità del client per dispositivi mobili probabilmente non verrà influenzata, perché l'URL interno verrà sempre tentato per primo.
  
### <a name="port-and-firewall-requirements"></a>Requisiti di porte e firewall

La maggior parte di queste informazioni è stata trattata nella nostra altra documentazione, ma in particolare per i dispositivi mobili, è necessario aprire le porte seguenti nella rete Wi-Fi aziendale se si dispone di utenti ospitati in un Survivable Branch Appliance (SBA):
  
- UcwaSipExternalListeningPort richiede 5088.
    
- UcwaSipPrimaryListeningPort richiede 5089.
    
### <a name="certificate-requirements"></a>Requisiti per i certificati

Se si utilizza l'individuazione automatica per i client mobili Skype for Business, sarà necessario modificare gli elenchi SAN (nome alternativo soggetto) nei certificati per supportare connessioni protette dai client mobili. Se si dispone già di certificati sul posto, sarà necessario richiedere e assegnare nuovi certificati con le voci SAN descritte qui. Questa operazione dovrà essere eseguita per ogni Front End Server e Director (se presente nell'ambiente) che esegue il servizio di individuazione automatica. È inoltre consigliabile modificare gli elenchi SAN nei certificati proxy inverso, aggiungendo voci SAN per ogni dominio SIP dell'organizzazione.
  
Si tratta di un processo semplice se si richiedono i nuovi certificati da un'autorità di certificazione interna, ma i certificati pubblici sono più complessi e potenzialmente molto più costosi da richiedere di nuovo, per non parlare che potrebbe essere costoso aggiungere molti domini SIP a un nuovo certificato pubblico. In questo caso, esiste un approccio supportato, ma **non consigliato.** È possibile configurare il proxy inverso per effettuare la richiesta iniziale del servizio di individuazione automatica sulla porta 80, che utilizzerà HTTP, anziché la porta 443, ovvero HTTPS (e 443 è la configurazione predefinita). La richiesta in arrivo verrà reindirizzata alla porta 8080 nel pool Front End o nel Director. In questo modo, non sarà necessario apportare modifiche al certificato, perché questo traffico non utilizza HTTPS per le richieste. Ma ancora una volta, non è consigliabile, anche se funzionerà per te.
  
### <a name="windows-and-iis-requirements"></a>Windows e IIS

Dovrebbe essere disponibile una versione Windows Server supportata per l'Skype for Business Server locale. Di conseguenza, è necessario disporre anche di IIS 8 o IIS 8.5 per le esigenze di mobilità. Sarà necessario apportare alcune modifiche alle impostazioni predefinite ASP.NET, ma il programma di installazione del servizio per dispositivi mobili lo farà automaticamente.
  
### <a name="hlb-requirements"></a>Requisiti di bilanciamento del carico di rete

Se si utilizza una topologia per Skype for Business Server che include un bilanciamento del carico di rete per il pool Front End (ovvero qualsiasi topologia che include più Front End Server), è necessario configurare gli IP virtuali (VIP) dei servizi Web esterni per il traffico dei servizi Web per l'origine. L'affinità di origine garantisce che più connessioni da un singolo client siano inviate allo stesso server per mantenere lo stato sessione.
  
Se si prevede di supportare i client mobili Skype for Business solo sulla rete Wi-Fi interna, è consigliabile configurare i VIP dei servizi Web interni per l'origine come descritto per i VIP dei servizi Web esterni. In questo caso, è consigliabile utilizzare source_addr (o TCP) per i VIP dei servizi Web interni nel bilanciamento del carico di rete.
  
Per informazioni dettagliate su tutto questo, consultare i requisiti [di bilanciamento](network-requirements/load-balancing.md) del carico per la Skype for Business documentazione.
  
### <a name="reverse-proxy-requirements"></a>Requisiti del proxy inverso

Per supportare l'individuazione automatica Skype for Business client mobili, è necessario aggiornare la regola di pubblicazione corrente nel modo seguente:
  
- Se si decide di aggiornare gli elenchi san sui certificati proxy inverso e si utilizza HTTPS per la richiesta iniziale del servizio di individuazione automatica, è necessario aggiornare la regola di pubblicazione Web per lyncdiscover. \<sipdomain\> Questa operazione viene in genere combinata con il rul di pubblicazione per l'URL dei servizi Web esterni nel pool Front End.
    
- Se si è deciso di utilizzare HTTP per la richiesta iniziale del servizio di individuazione automatica per evitare di dover aggiornare l'elenco SAN per i certificati proxy inverso (operazione non consigliata), sarà necessario creare una nuova regola di pubblicazione Web per la porta HTTP/TCP 80, se non è già disponibile. Se tale regola esiste, aggiornarla in modo da includere un lyncdiscover.\<sipdomain\> voce.
    
## <a name="defining-your-mobility-needs"></a>Definizione delle esigenze di mobilità
<a name="MobilityNeeds"> </a>

Dopo aver esaminato le topologie, i componenti e i requisiti tecnici, esaminiamo cosa potrebbe essere necessario all'organizzazione in termini di implementazione per dispositivi mobili.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>Si desidera utilizzare l'individuazione automatica per Skype for Business client mobili?

È consigliabile utilizzare l'individuazione automatica. Richiederà la creazione di nuovi record DNS interni ed esterni, come descritto nella sezione Requisiti tecnici sopra riportata. Con l'individuazione automatica, i client Skype for Business possono individuare automaticamente i Skype for Business Server Web da qualsiasi posizione, senza dover immettere manualmente un URL.
  
Se necessario, è possibile utilizzare le impostazioni manuali. Questi URL dovranno essere immessi dagli utenti nei dispositivi mobili:
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root per** l'accesso esterno.
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root per** l'accesso interno.
    
Anche in questo caso, è consigliabile usare l'individuazione automatica. Le impostazioni manuali potrebbero risultare utili per la risoluzione dei problemi.
  
### <a name="are-you-going-to-support-push-notifications"></a>Supporterai le notifiche push?

Le notifiche push vengono usate per le applicazioni per dispositivi mobili che supportano questa funzionalità per notificare a un utente gli eventi mentre l'app non è attiva. Il server perimetrale dovrà avere una relazione di federazione con il servizio di notifica Push Skype for Business Server basato su cloud, disponibile nel datacenter di Skype for Business Online. Sarà necessario eseguire un cmdlet per abilitare le notifiche push.
  
> [!NOTE]
> Se sono ancora in uso client Lync Server 2010, sarà necessaria la porta TCP 5223 aperta in uscita nella rete WiFi aziendale. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>Si desidera che tutti gli utenti accedono a tutte le funzionalità per dispositivi mobili oppure si desideri specificare gli utenti che possono accedere a queste funzionalità?

È disponibile una tabella per aiutare alcune delle funzionalità disponibili per tutti gli utenti e se sono impostate in questo modo o meno per impostazione predefinita. Per un elenco completo, vedere [New-CsMobilityPolicy.](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)
  
> [!NOTE]
> Gli ambiti per tutte queste caratteristiche sono Global/Site/User. 
  
|**Funzionalità**|**Nome parametro**|**Descrizione**|**Impostazione predefinita**|
|:-----|:-----|:-----|:-----|
|Abilitare i dispositivi mobili  <br/> |EnableMobility  <br/> |Controlla gli utenti in un determinato ambito in cui Skype for Business client mobile installato. Se il criterio è impostato su False, gli utenti non potranno accedere con il client.  <br/> |Vero  <br/> |
|Voce esterna  <br/> |EnableOutsideVoice  <br/> |Consente a un utente di utilizzare Chiama tramite lavoro, che consente agli utenti di inviare e ricevere chiamate utilizzando il numero di lavoro anziché il numero di cellulare. Se è impostato su False, gli utenti non saranno in grado di effettuare o ricevere chiamate sul proprio cellulare quando utilizzano il numero di telefono dell'ufficio.  <br/> |Vero  <br/> |
|Abilita audio e video IP  <br/> |EnableIPAudioVideo  <br/> |Impostata sul valore predefinito, consente a un utente di usare VoIP per effettuare o ricevere chiamate telefoniche o videochiamate sul dispositivo mobile. Se impostato su False, gli utenti non potranno usare il dispositivo mobile per eseguire una di queste operazioni.  <br/> |Vero  <br/> |
|Richiedi WiFi per IP Audio  <br/> |RequireWiFiForIPAudio  <br/> |Definisce se un client dovrà effettuare e ricevere chiamate tramite VoIP su WiFi anziché su una rete dati cellulare. Se è impostato su True, gli utenti potranno effettuare e ricevere chiamate VoIP solo quando sono connessi tramite WiFi.  <br/> |Falso  <br/> |
|Richiedi WiFi per IP Video  <br/> |RequireWiFiForIPVideo  <br/> |Definisce se un client dovrà effettuare e ricevere videochiamate su WiFi anziché su una rete dati cellulare. Se è impostato su True, gli utenti potranno effettuare e ricevere chiamate VoIP solo quando sono connessi tramite WiFi.  <br/> |Falso  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>Gli utenti che non sono abilitati per VoIP aziendale possono usare Click to Join per partecipare alle conferenze?

Per consentire agli utenti di accedere alle funzionalità per dispositivi mobili e di chiamare tramite il lavoro, è necessario che siano abilitati per VoIP aziendale. Anche se non sono abilitati, possono comunque partecipare alle conferenze facendo clic su un collegamento nel dispositivo mobile, ma solo se è assegnato un criterio vocale appropriato. È possibile:
  
- assegnare un criterio vocale specifico a questi utenti o,
    
- assicurarsi che esista un criterio globale o un criterio a livello di sito e si applii a questi criteri.
    
In entrambi i casi, il criterio vocale assegnato deve disporre di record di utilizzo PSTN (Public Switched Telephone Network) e route che definiranno dove gli utenti potranno effettuare chiamate in uscita per partecipare alle conferenze.
  
> [!NOTE]
> Gli utenti mobili che desiderano utilizzare Il clic per partecipare richiedono un criterio vocale, insieme ai record di utilizzo PSTN correlati e alle route vocali, perché quando fanno clic su tale collegamento nei dispositivi mobili, ne risulta una chiamata in uscita da Skype for Business Server. 
