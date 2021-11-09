---
title: Pianificare Video Interop Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: "Riepilogo: leggere questo argomento durante la pianificazione dell'integrazione Skype for Business Server con dispositivi di teleconferenza di terze parti."
ms.openlocfilehash: b928e432b464e6bf1a5ccb8748ebf75ef8cc596b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862063"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Pianificare Video Interop Server in Skype for Business Server
 
**Riepilogo:** Esaminare questo argomento durante la pianificazione dell'integrazione Skype for Business Server con dispositivi di teleconferenza di terze parti.
  
Skype for Business Server ora ti consente di integrarti con determinate soluzioni VTC (Video Teleconferencing System) di terze parti. Il nuovo ruolo del server che abilita l'interoperabilità delle videoconferenze è Video Interop Server (VIS), attualmente implementato come ruolo del server autonomo disponibile solo per le installazioni locali. Un VIS funge da intermediario tra un sistema di teleconferenza di terze parti e una Skype for Business Server distribuzione. Per questa versione, VIS si concentra sull'interoperabilità con i sistemi video Cisco/Tandberg. Leggere questo articolo per determinare se utilizzare questa funzionalità nell'Skype for Business Server installazione.
  
## <a name="device-interoperability"></a>Interoperabilità dei dispositivi

L'interoperabilità viene testata e supportata con i VTC Cisco registrati con Cisco Unified Communications Manager (CallManager, o CUCM) versione 10.5 e i trunk SIP TCP impostati tra CUCM e VIS.
  
I VTC attualmente supportati sono:
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  La versione software Cisco TC7.0.0 o successiva è necessaria in questi sistemi per l'integrazione con Skype for Business Server per funzionare come previsto.
  
## <a name="sip-trunks"></a>Trunk SIP

Video Interop Server funziona in modalità trunk SIP, dove i VTC continuano a registrarsi nell'infrastruttura Cisco esistente, ad esempio Cisco Call Manager (CUCM). Un trunk SIP video viene definito tra CUCM e VIS in modo che le chiamate possano essere instradati tra i due sistemi. Sono supportate solo le chiamate tramite il trunk SIP da VTC a VIS. Di conseguenza, i VTC possono accedere a una conferenza Skype for Business (componendo il numero di telefono associato all'Operatore automatico di chiamata), ma non possono essere trascinati e rilasciati nella conferenza.
  
![Diagramma di VIS in SfB.](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Funzionalità

Questo ruolo del server fornisce:
  
- Conversione tra i formati H.264 utilizzati dai sistemi video di terze parti e la Skype for Business Server distribuzione.
    
- Conversione di un singolo flusso video a una determinata risoluzione da un VTC in più flussi simulcast di risoluzioni diverse da usare nella distribuzione Skype for Business Server video. Questi flussi possono essere inviati all'AVMCU e quindi a Skype for Business Server endpoint e altri sistemi video che hanno richiesto risoluzioni diverse. Questa conversione viene usata anche quando il sistema video di terze parti è coinvolto in una Skype for Business conferenza telefonica audio/video. Una volta raggiunto il limite di transcoding in un server VIS specifico, tutte le richieste seguenti per risoluzioni diverse riceveranno solo un flusso con la risoluzione più bassa. 
    
- Supporto per un trunk SIP video tra il gateway CUCM e un Skype for Business Server Video Interop Server; I VTC continuano a registrarsi con il gateway Cisco e avviano le chiamate alla distribuzione Skype for Business tramite il gateway. Le chiamate vengono instradati dal gateway al Skype for Business Video Interop Server tramite il trunk SIP video.
    
- Supporto per un utente in una sala riunioni con un sistema video supportato per comporre da tale sistema per partecipare a una conferenza aperta o chiusa. Questa chiamata attraverserà il trunk SIP video.
    
- Supporto per un utente in una sala riunioni con un sistema video supportato per chiamare un Skype for Business client. La chiamata attraverserà il trunk SIP.
    
- Supporto per il controllo delle chiamate intermedie dal lato Skype for Business Server o dal sistema VTC supportato sia per le chiamate point-to-point che per le chiamate multipoint, tra cui audio mute/un-mute, pause/resume video, lock video e hold/un-hold call.
    
## <a name="known-limitations"></a>Limitazioni note

Questo ruolo del server presenta le limitazioni seguenti:
  
- Le nuove chiamate Skype for Business distribuzione ai VTC tramite il trunk SIP video non sono supportate. . Ciò significa che solo le nuove chiamate dai VTC nella distribuzione Skype for Business sono supportate nel trunk SIP video. La presenza per il sistema video supportato non sarà disponibile nel trunk SIP video per il VIS. 
    
- Solo un pool VIS autonomo sarà supportato per la modalità trunk SIP video.
    
-  TLS + SRTP o TCP + RTP saranno supportati per le comunicazioni tra VTC e VIS tramite il trunk SIP video.
    
- La condivisione delle applicazioni non è supportata. Un utente Skype for Business nella sala riunioni deve partecipare alla conferenza di Skype for Business (ad esempio tramite un portatile) e visualizzare le schermate di condivisione dell'app su uno dei monitor gratuiti nella sala conferenze non associata al VTC.
    
- La possibilità per un VTC di partecipare a una riunione federata tramite VIS non è supportata.
    
- La possibilità per un VTC di partecipare a una riunione online tramite VIS non è supportata.
    
- Le chiamate da un VTC alla rete PSTN tramite VIS non sono supportate.
    
- Le chiamate dalla rete PSTN a un VTC tramite VIS non sono supportate.
    
## <a name="resiliency-mechanisms"></a>Meccanismi di resilienza
<a name="resiliency"> </a>

ViS supporta le chiamate in arrivo da un cucm che vengono trasportate su un trunk SIP video. È possibile perdere la connettività a monte o a valle, quindi per una resilienza affidabile considerare entrambe le possibilità:It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:
  
1. **Failover del pool VIS** Se il pool VIS principale a cui punta il gateway video non è disponibile, il ripristino è possibile se il gateway video ha definito trunk a due (o più) pool VIS. Se il gateway video determina che non è in grado di effettuare chiamate al pool VIS primario, le instrada semplicemente a un pool VIS secondario.
    
     ![Diagramma del failover del pool VIS.](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un particolare pool VIS può avere trunk per più gateway, ma in genere un determinato gateway non può avere trunk per più pool VIS, quindi è necessario eseguire un trucco per supportare questo failover: definire 2 FQDN in DNS che si risolvono nello stesso indirizzo IP di un gateway video. Rappresentare ogni FQDN come gateway video separato nel documento della topologia in cui ogni gateway video dispone di un trunk per un pool VIS diverso ed è ora possibile eseguire il ripristino. Se si utilizza TLS, i nomi multipli dovranno essere nella san del certificato del gateway video.
    
    > [!NOTE]
    > VIS consente solo le chiamate in arrivo dai gateway configurati nel documento topologia. 
  
2. **Failover front-end** Se un pool VIS riceve una chiamata da CUCM ma non riesce a raggiungere la funzione di registrazione dell'hop successivo principale o il pool Front End principale, le chiamate vengono instradati a un pool Front End di backup.
    
     ![Diagramma del failover front-end.](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    ViS tiene traccia dello stato del pool Front End primario e del relativo pool Front End di backup (l'impostazione si trova nell'impostazione di backup per il servizio di registrazione nel documento topologia). Invia i polling delle opzioni una volta al minuto a entrambi i pool e, in caso di cinque errori consecutivi, VIS presuppone che un determinato pool Front End non sia disponibile. Se il pool Front End primario è contrassegnato come in basso ed è disponibile un backup configurato, VIS invia nuove chiamate dal gateway al pool Front End di backup. Una volta che il pool Front End primario torna, il VIS riprenderà a utilizzare il pool Front End primario per le nuove chiamate.
    
    ViS implementerà anche un timer di 10 secondi per le chiamate dal trunk SIP video. Se il pool Front End dell'hop successivo primario è stato utilizzato per una chiamata dal trunk SIP video e il pool Front End dell'hop successivo primario non ha risposto con un messaggio SIP (incluso 100 Tentativo) all'invito inviato entro questo valore timer, il proxy dell'hop successivo di backup per la chiamata deve essere provato se configurato. 
    
    > [!NOTE]
    > Se l'hop successivo del backup è stato tentato per primo, non verrà eseguito un tentativo successivo. 
  
    L'amministratore può inoltre utilizzare il comando di failover Windows PowerShell per forzare VIS a utilizzare il pool Front End di backup, ad esempio quando è necessario eseguire la manutenzione nel pool Front End primario.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coesistenza di trunk vocali e video allo stesso peer gateway
<a name="resiliency"> </a>

Skype for Business Server supporta che i trunk SIP vocali e video utilizzino lo stesso peer gateway. Pertanto, la stessa distribuzione DIS potrebbe avere trunk SIP vocali nel Mediation Server e trunk SIP video in VIS.
  
- Un gateway PSTN dovrà essere definito con un nome di dominio completo specifico nel Documento di topologia per i trunk SIP vocali.
    
- Il peer per il gateway PSTN sarà il Mediation Server.
    
- È possibile definire più trunk vocali che si estendono da un gateway PSTN a più pool Mediation Server, se necessario.
    
- Un gateway video dovrà essere definito nel Documento di topologia per il trunk SIP video con lo stesso FQDN del gateway PSTN.
    
- Il peer per il gateway video sarà VIS.
    
- Un singolo trunk video può essere definito da un gateway video a un pool VIS specifico.
    
- Cucm dovrà essere configurato per instradare correttamente le chiamate sul trunk vocale e sul trunk video. Ad esempio, è possibile utilizzare un prefisso di composizione speciale durante la composizione dal VTC; Cucm potrebbe associare questo prefisso di chiamata alle chiamate a VIS e le regole di conversione appropriate rimuoverebbero questo prefisso dall'invito SIP a VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coesistenza di VIS nella versione Skype for Business con le versioni precedenti di Lync
<a name="resiliency"> </a>

VIS può essere distribuito solo come parte della Skype for Business distribuzione. Può interagire con conferenze lync 2013 e client che fanno parte di una distribuzione esistente; in questi casi, il pool VIS dovrà far parte di una distribuzione di Skype for Business che include un pool registrar/FE che sia l'hop successivo per il pool VIS.
  
VIS non supporta la transcodtura tra RTV e H.264. Non esiste alcuna interoperabilità video tra client pre-Lync 2013 e partecipanti VTC a una conferenza.
  
La presenza di client pre-Lync 2013 in una conferenza causerà l'invio da parte dei client mobili tramite RTV, in modo che i VTC non ricevano alcun video quando il client mobile diventa l'altoparlante dominante.
  
Per consentire a Lync 2013 di funzionare correttamente con VIS che fa parte di una distribuzione di Skype for Business, Lync 2013 deve essere applicato il cu appropriato che aggiorna il client Lync 2013, l'autorità di certificazione e l'AVMCU per funzionare con VIS.
  
L'interoperabilità di VIS con Lync 2013 e Skype for Business client desktop è stata testata ed è supportata.
  
Interoperabilità di VIS con dispositivi non desktop (Android, Ipad, Iphone, Windows Phone, LMX e così via) Skype for Business client disponibili nell'App Store applicabile al momento del rilascio di VIS è stato testato ed è supportato.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Ripristino dalla perdita di pacchetti tramite FEC
<a name="resiliency"> </a>

FeC può essere attivato per facilitare il recupero dalla perdita di pacchetti. Se attivato, verrà utilizzata una larghezza di banda video superiore del 50% nella direzione da VIS a VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS Sizing and Transcoding Costs
<a name="resiliency"> </a>

La transcodtura dei flussi video singoli dal VTC Cisco a più flussi simulcast utilizza la capacità della CPU. Circa 16 VTC possono avere il video transcodificato (presupponendo che un flusso video di 720p da ogni VTC sia transcodificato in 3 flussi simulcast separati a 720p, 360p e 180p) in un singolo VIS in esecuzione sull'equivalente della piattaforma FE consigliata per Lync 2013. Se la transcodtura è disattivata, questa operazione verrà risparmiata sulla CPU VIS. Tuttavia, l'immagine video richiesta da VIS dal VTC sarà la risoluzione comune più bassa per soddisfare tutti i ricevitori Skype for Business lato. Anche con la transcodtura disattivata, la transcoding può essere attivata quando i client Skype for Business richiedono determinate risoluzioni a bassa risoluzione che non possono essere inviate dai VTC.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribuzione delle chiamate dal gateway video a VIS
<a name="resiliency"> </a>

La distribuzione viene eseguita tramite uno dei meccanismi di distribuzione CUCM:
  
- Utilizzo dinamico di DNS.
    
- Sul lato CUCM, è possibile definire singoli trunk, in cui ogni trunk termina su un server diverso nel pool VIS. CUCM instraderà le chiamate tra i diversi trunk.
    
## <a name="no-hybrid-interoperability"></a>Nessuna interoperabilità ibrida
<a name="resiliency"> </a>

Il supporto per VTC che a partecipare a riunioni online tramite VIS locale non fa parte di Skype for Business.
  
## <a name="no-federation-support"></a>Nessun supporto per la federazione
<a name="resiliency"> </a>

Il supporto per VTC che a partecipare a riunioni federate tramite VIS non fa parte di Skype for Business.
  
## <a name="see-also"></a>Vedere anche
<a name="resiliency"> </a>

[Distribuire Video Interop Server in Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
