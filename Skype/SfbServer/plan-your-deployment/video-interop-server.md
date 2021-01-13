---
title: Pianificare video Interop server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: "Riepilogo: esaminare questo argomento durante la pianificazione dell'integrazione di Skype for Business Server con dispositivi di teleconferenza di terze parti."
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831946"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Pianificare video Interop server in Skype for Business Server
 
**Riepilogo:** Esaminare questo argomento durante la pianificazione dell'integrazione di Skype for Business Server con dispositivi di teleconferenza di terze parti.
  
Skype for Business Server ora consente l'integrazione con determinate soluzioni di terze parti di videoconferenza (video Conferencing System). Il nuovo ruolo del server che consente questa interoperabilità video conferenza è il video Interop Server (VIS), attualmente implementato come ruolo server autonomo disponibile solo per le installazioni locali. Un VIS funge da intermediario tra un sistema di teleconferenze di terze parti e una distribuzione di Skype for Business Server. Per questa versione, VIS si concentra sull'interoperabilità con i sistemi video Cisco/Tandberg. Leggere questo articolo per determinare se utilizzare questa funzionalità nell'installazione di Skype for Business Server.
  
## <a name="device-interoperability"></a>Interoperabilità del dispositivo

L'interoperabilità è testata e supportata con Cisco VTCs che si sta registrando con Cisco Unified Communications Manager (CallManager o un CUCM) versione 10,5 e TCP SIP Trunks configurati tra un CUCM e il VIS.
  
Le VTCs attualmente supportate sono:
  
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
>  È necessario utilizzare Cisco Software Release TC 7.0.0 o versioni successive su questi sistemi per l'integrazione con Skype for Business Server per funzionare come previsto.
  
## <a name="sip-trunks"></a>Trunk SIP

Il server di interoperabilità video funziona in modalità trunk SIP, in cui VTCs continua a essere registrato con l'infrastruttura Cisco esistente, ad esempio Cisco Call Manager (un CUCM). Un trunk SIP video è definito tra un CUCM e il VIS in modo che le chiamate possano essere instradate tra i due sistemi. Sono supportate solo le chiamate tramite il trunk SIP dall'videoconferenza al VIS. Pertanto, VTCs può comporre una conferenza di Skype for business (componendo il numero di telefono associato all'operatore automatico di chiamata), ma non può essere trascinata e rilasciata nella conferenza.
  
![Diagramma di VIS in questo](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Funzionalità

Questo ruolo del server fornisce:
  
- Conversione tra i formati H. 264 utilizzati dai sistemi video di terze parti e la distribuzione di Skype for Business Server.
    
- Conversione di un singolo flusso video a una determinata risoluzione da un videoconferenza in più flussi simulcast di diverse risoluzioni per l'utilizzo nella distribuzione di Skype for Business Server. Questi flussi possono essere inviati a AVMCU e quindi a endpoint di Skype for Business Server e ad altri sistemi video che hanno richiesto diverse risoluzioni. Questa conversione viene utilizzata anche quando il sistema video di terze parti è coinvolto in una conferenza telefonica Skype for business a/V. Una volta raggiunto il limite di transcodifica in un determinato server VIS, qualsiasi richiesta di risoluzione diversa riceverà un flusso con la risoluzione più bassa. 
    
- Supporto per un trunk SIP video tra il gateway di un CUCM e un server di interoperabilità video di Skype for Business Server; VTCs continuerà a essere registrato con il gateway Cisco e avvierà le chiamate alla distribuzione di Skype for business tramite il gateway. Le chiamate vengono instradate dal gateway al server di interoperabilità video di Skype for business tramite il trunk SIP video.
    
- Supporto per un utente in una sala riunioni con un sistema video supportato per comporre da tale sistema per partecipare a una conferenza aperta o chiusa. Questa chiamata attraverserà il trunk SIP video.
    
- Supporto per un utente in una sala riunioni con un sistema video supportato per chiamare un client Skype for business. La chiamata attraverserà il trunk SIP.
    
- Supporto per il controllo Mid-Call dal server Skype for business o dal sistema videoconferenza supportato sia per le chiamate punto a punto che per quelle multipunto, tra cui audio muto/disattivazione, pausa/Riprendi video, blocca video e blocco/arresto delle chiamate.
    
## <a name="known-limitations"></a>Limitazioni note

Questo ruolo del server presenta le limitazioni seguenti:
  
- Non sono supportate nuove chiamate dalla distribuzione di Skype for business al VTCs sul trunk SIP video. . Questo significa che sono supportate solo le nuove chiamate da VTCs nella distribuzione di Skype for business tramite il trunk SIP video. La presenza del sistema video supportato non sarà disponibile nel trunk SIP video per il VIS. 
    
- Solo un pool VIS autonomo sarà supportato per la modalità trunk SIP video.
    
-  TLS + SRTP o TCP + RTP saranno supportati per le comunicazioni tra videoconferenza e VIS nel trunk SIP video.
    
- La condivisione delle applicazioni non è supportata. Un utente Skype for business nella sala riunioni deve partecipare alla conferenza di Skype for business (ad esempio tramite un computer portatile) e visualizzare le schermate di condivisione delle app su uno dei monitor gratuiti nella sala riunioni non associata all'videoconferenza.
    
- La possibilità per un videoconferenza di partecipare a una riunione federata tramite VIS non è supportata.
    
- La possibilità per un videoconferenza di partecipare a una riunione online tramite VIS non è supportata.
    
- Le chiamate da un videoconferenza alla rete PSTN tramite VIS non sono supportate.
    
- Le chiamate dalla rete PSTN a un videoconferenza tramite VIS non sono supportate.
    
## <a name="resiliency-mechanisms"></a>Meccanismi di resilienza
<a name="resiliency"> </a>

Il VIS supporta le chiamate in arrivo provenienti da un un CUCM che vengono riportate su un trunk SIP video. È possibile perdere la connettività a Monte o a valle, quindi per una resilienza robusta si considerano entrambe le possibilità:
  
1. **Failover del pool Vis** Se il pool di VIS principale a cui punta il gateway video è inverso, il ripristino è possibile se il gateway video ha definito trunk a due o più pool di VIS. Se il gateway video determina che non è in grado di effettuare chiamate al pool di VIS principale, semplicemente instraderà le chiamate a un pool VIS secondario.
    
     ![Diagramma del failover del pool VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un particolare pool VIS può disporre di trunk per più gateway, ma in genere un determinato gateway non può disporre di trunk a più pool VIS, quindi è necessario eseguire un trick per supportare questo failover: define 2 FDQNs in DNS che si risolvono nello stesso indirizzo IP di un gateway video. Rappresentano ogni FQDN come gateway video separato nel documento della topologia in cui ogni gateway video ha un trunk per un pool VIS diverso e il ripristino è ora possibile. Se si utilizza TLS, i nomi multipli dovranno trovarsi nella SAN del certificato del gateway video.
    
    > [!NOTE]
    > VIS consente solo le chiamate in ingresso provenienti da gateway configurati nel documento della topologia. 
  
2. **Failover front-end** Se un pool VIS riceve una chiamata da un CUCM ma non è in grado di raggiungere il registrar principale o il pool Front End, le chiamate vengono instradate a un pool Front End di backup.
    
     ![Diagramma del failover front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Il VIS tiene conto dello stato del pool Front End principale e del pool Front End di backup (l'impostazione viene trovata nell'impostazione di backup per il servizio di registrazione nel documento della topologia). Invia i polli delle opzioni una volta al minuto per entrambi i pool e, se sono presenti cinque errori consecutivi, il VIS presuppone che un pool Front end specifico sia inverso. Se il pool Front End primario è contrassegnato come giù ed è disponibile un backup configurato, il VIS Invia nuove chiamate dal gateway al pool Front End di backup. Una volta che il pool Front End principale torna, il VIS riprenderà usando il pool Front End primario per le nuove chiamate.
    
    Il VIS implementerà anche un timer di 10 secondi per le chiamate dal trunk SIP video. Se è stato utilizzato il pool Front End principale dell'hop successivo per una chiamata proveniente dal trunk SIP video e il pool Front End principale dell'hop successivo non ha risposto con alcuni messaggi SIP (compresi 100 tentativi) all'invito inviato all'interno di questo valore timer, il proxy di backup dell'hop successivo per la chiamata deve essere provato se configurato. 
    
    > [!NOTE]
    > Se l'hop successivo di backup è stato provato per primo, il principale non verrà provato successivamente. 
  
    L'amministratore può anche utilizzare il comando di failover di Windows PowerShell per forzare l'utilizzo del pool Front End di backup, ad esempio quando è necessario eseguire la manutenzione nel pool Front End principale.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coesistenza di trunk vocali e video nello stesso peer gateway
<a name="resiliency"> </a>

Skype for Business Server supporta l'utilizzo di trunk SIP vocali e video tramite lo stesso peer gateway. Pertanto, la stessa distribuzione di un CUCM potrebbe avere trunk SIP vocali per il Mediation Server e i trunk SIP video in VIS.
  
- Un gateway PSTN dovrà essere definito con un FQDN specifico nel documento della topologia per i trunk SIP vocali.
    
- Il peer to the PSTN Gateway sarà il Mediation Server.
    
- Più trunk vocali può essere definito che si estende da un gateway PSTN a più pool di Mediation Server, se necessario.
    
- Sarà necessario definire un gateway video nel documento della topologia del trunk SIP video con lo stesso FQDN del gateway PSTN.
    
- Il peer per il gateway video sarà VIS.
    
- Un singolo trunk video può essere definito da un gateway video a un particolare pool VIS.
    
- UN CUCM dovrà essere configurato in modo da instradare correttamente le chiamate tramite il trunk vocale e il trunk video. Ad esempio, un prefisso di chiamata speciale può essere utilizzato durante la composizione da videoconferenza; UN CUCM potrebbe associare il prefisso di chiamata a VIS e le regole di conversione appropriate rimuoveranno questo prefisso dall'invito SIP a VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coesistenza di VIS nella versione di Skype for business con le versioni precedenti di Lync
<a name="resiliency"> </a>

VIS può essere distribuito solo come parte della distribuzione di Skype for business. Può interoperare con le conferenze e i client di Lync 2013 che fanno parte di una distribuzione esistente. in questi casi, il pool VIS dovrà far parte di una distribuzione di Skype for business che include un pool di registrazione/FE che rappresenta l'hop successivo per il pool VIS.
  
VIS non supporta la transcodifica tra RTV e H. 264. Non esiste alcuna interoperabilità video tra i client di prima Lync 2013 e i partecipanti di videoconferenza in una conferenza.
  
L'utilizzo di client prelync 2013 in una conferenza consentirà ai client mobili di inviare messaggi utilizzando RTV con conseguente VTCs che non riceve alcun video quando il client mobile diventa l'altoparlante dominante.
  
Affinché Lync 2013 funzioni correttamente con VIS che fa parte di una distribuzione di Skype for business, Lync 2013 ha bisogno del CU appropriato da applicare che consente di aggiornare il client Lync 2013, CAA e AVMCU in modo che funzionino con VIS.
  
L'interoperabilità dei client desktop di VIS con Lync 2013 e Skype for business è stata testata ed è supportata.
  
Interoperabilità di VIS con utenti non desktop (Android, iPad, iPhone, Windows Phone, LMX e così via) I client Skype for business disponibili dall'App Store applicabile al momento del rilascio di VIS sono stati testati ed è supportato.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Ripristino dalla perdita di pacchetti tramite FEC
<a name="resiliency"> </a>

FEC può essere attivato per facilitare il ripristino dalla perdita di pacchetti. Se attivata, la larghezza di banda video del 50% verrà utilizzata nella direzione VIS-videoconferenza.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costi di ridimensionamento e transcodifica VIS
<a name="resiliency"> </a>

La transcodifica dei singoli flussi video dal videoconferenza Cisco a più flussi simulcast utilizza la capacità della CPU. Circa 16 VTCs possono avere il loro video transcoded (supponendo che un flusso video 720p da ogni videoconferenza sia trascodificato in 3 flussi di simulcast separati a 720p, 360p e 180p) in un singolo VIS in esecuzione sull'equivalente della piattaforma FE consigliata di Lync 2013. Se la transcodifica è disattivata, questa verrà salvata sulla CPU VIS. Tuttavia, l'immagine video richiesta da VIS dalla videoconferenza sarà la soluzione comune più bassa per soddisfare tutti i destinatari sul fronte di Skype for business. Si noti che anche con la transcodifica disattivata, la transcodifica può essere attivata quando i client Skype for business richiedono alcune risoluzioni minime che VTCs non può inviare.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribuzione delle chiamate dal gateway video a VIS
<a name="resiliency"> </a>

La distribuzione viene eseguita tramite uno dei meccanismi di distribuzione di un CUCM:
  
- Tramite DNS in modo dinamico.
    
- Sul un CUCM, è possibile definire singoli trunk, in cui ogni trunk termina su un server diverso nel pool VIS. UN CUCM instraderà le chiamate tra i diversi trunk.
    
## <a name="no-hybrid-interoperability"></a>Nessuna interoperabilità ibrida
<a name="resiliency"> </a>

Il supporto per VTCs partecipare a riunioni online tramite VIS locale non è parte di Skype for business.
  
## <a name="no-federation-support"></a>Nessun supporto per la Federazione
<a name="resiliency"> </a>

Il supporto per VTCs che partecipano a riunioni federate tramite VIS non è parte di Skype for business.
  
## <a name="see-also"></a>Vedere anche
<a name="resiliency"> </a>

[Distribuire video Interop server in Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
