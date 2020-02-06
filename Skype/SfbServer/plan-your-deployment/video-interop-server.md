---
title: Pianificare il video Interop server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Riepilogo: rivedere questo argomento mentre si prevede di integrare Skype for Business Server con dispositivi di teleconferenza di terze parti.'
ms.openlocfilehash: af7618efa0b5f13419be216b37a4f1e7d4065e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815564"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Pianificare il video Interop server in Skype for Business Server
 
**Riepilogo:** Esaminare questo argomento mentre si prevede di integrare Skype for Business Server con dispositivi di teleconferenza di terze parti.
  
Skype for Business Server consente ora di integrarsi con alcune soluzioni di terze parti di VTC (video teleconferenza System). Il nuovo ruolo del server che consente l'interoperabilità di videoconferenza è il video Interop Server (VIS), attualmente implementato come ruolo di server autonomo disponibile solo per le installazioni locali. Un VIS funge da intermediario tra un sistema di teleconferenza di terze parti e una distribuzione di Skype for Business Server. Per questa versione, VIS è focalizzata sull'interoperabilità con i sistemi video Cisco/Tandberg. Esaminare questo articolo per determinare se usare questa funzionalità nell'installazione di Skype for Business Server.
  
## <a name="device-interoperability"></a>Interoperabilità del dispositivo

L'interoperabilità è testata e supportata con Cisco VTCs che si sta registrando con Cisco Unified Communications Manager (CallManager o CUCM) la versione 10,5 e i trunk SIP TCP configurati tra CUCM e il VIS.
  
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
>  Il software Cisco Release TC 7.0.0 o superiore è necessario in questi sistemi per l'integrazione con Skype for Business Server per funzionare come previsto.
  
## <a name="sip-trunks"></a>Trunk SIP

Il server di interoperabilità video funziona in modalità trunk SIP, dove VTCs continua a registrare con l'infrastruttura Cisco esistente, ad esempio Cisco Call Manager (CUCM). Viene definito un trunk SIP video tra CUCM e il VIS in modo che le chiamate possano essere instradate tra i due sistemi. Sono supportate solo le chiamate tramite il trunk SIP da VTC a VIS. In questo modo, VTCs può accedere a una conferenza Skype for business (componendo il numero di telefono associato all'operatore automatico delle chiamate), ma non può essere trascinato e rilasciato alla conferenza.
  
![Diagramma di VIS in SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Caratteristiche

Questo ruolo del server offre:
  
- Conversione tra i formati H. 264 usati dai sistemi video di terze parti e la distribuzione di Skype for Business Server.
    
- Conversione di un singolo flusso video in una determinata risoluzione da un VTC in più flussi simulcast di diverse risoluzioni per l'uso nella distribuzione di Skype for Business Server. Questi flussi possono essere inviati al AVMCU e quindi agli endpoint di Skype for Business Server e ad altri sistemi video che hanno richiesto risoluzioni diverse. Questa conversione viene usata anche quando il sistema video di terze parti è coinvolto in una conferenza telefonica Skype for Business A/V. Una volta raggiunto il limite di transcodifica in un determinato server VIS, le eventuali richieste seguenti per risoluzioni diverse riceveranno solo un flusso con la risoluzione più bassa. 
    
- Supporto di un trunk SIP video tra il gateway CUCM e un server di interoperabilità video di Skype for Business Server; VTCs continuerà a essere registrato con il gateway Cisco e avvierà le chiamate alla distribuzione di Skype for business tramite il gateway. Le chiamate vengono instradate dal gateway al server di interoperabilità video Skype for business tramite il trunk SIP video.
    
- Supporto per un utente in una sala riunioni con un sistema video supportato per effettuare la chiamata da tale sistema per partecipare a una conferenza aperta o chiusa. Questa chiamata attraverserà il trunk SIP del video.
    
- Supporto per un utente in una sala riunioni con un sistema video supportato per chiamare un client Skype for business. La chiamata attraverserà il trunk SIP.
    
- Supporto per il controllo Mid-Call dal lato Skype for Business Server o dal sistema VTC supportato per le chiamate Point to Point e multipunto, tra cui audio muto/disattivato, pausa/ripresa video, blocco video e chiamata in attesa/disattivazione.
    
## <a name="known-limitations"></a>Limitazioni note

Questo ruolo del server ha le seguenti limitazioni:
  
- Le nuove chiamate dalla distribuzione di Skype for business al VTCs sul trunk SIP video non sono supportate. . Questo significa che solo le nuove chiamate di VTCs nella distribuzione di Skype for business sono supportate tramite il trunk SIP video. La presenza per il sistema video supportato non sarà disponibile sul trunk video SIP per il VIS. 
    
- Solo un pool VIS autonomo sarà supportato per la modalità trunk video SIP.
    
-  TLS + SRTP o TCP + RTP saranno supportati per le comunicazioni tra VTC e VIS nel trunk SIP video.
    
- La condivisione delle applicazioni non è supportata. Un utente di Skype for business nella sala riunioni deve partecipare alla conferenza di Skype for business (ad esempio tramite un portatile) e visualizzare le schermate di condivisione delle app in uno dei monitor gratuiti nella sala riunioni non associate al VTC.
    
- La possibilità per un VTC di partecipare a una riunione federata tramite VIS non è supportata.
    
- La possibilità per un VTC di partecipare a una riunione online tramite VIS non è supportata.
    
- Le chiamate da un VTC alla rete PSTN tramite VIS non sono supportate.
    
- Le chiamate dalla rete PSTN a VTC tramite VIS non sono supportate.
    
## <a name="resiliency-mechanisms"></a>Meccanismi di resilienza
<a name="resiliency"> </a>

Il VIS supporta le chiamate in arrivo da un CUCM che vengono riportate su un trunk SIP video. È possibile perdere la connettività a Monte o a valle, quindi per una robusta resilienza si considereranno entrambe le possibilità:
  
1. **Failover del pool Vis** Se il pool di VIS principale a cui punta il gateway video è in calo, il ripristino è possibile se il gateway video ha definito Trunks in due (o più) pool di VIS. Se il gateway video determina che non può effettuare chiamate al pool principale VIS, semplicemente instrada le chiamate a un pool di VIS secondario.
    
     ![Diagramma del failover del pool VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Un particolare pool VIS può avere Trunks per più gateway, ma in genere un determinato gateway non può avere Trunks per più piscine VIS, quindi è necessario eseguire un trucco per supportare questo failover: definire 2 FDQNs in DNS che si risolvono nello stesso indirizzo IP di un gateway video. Rappresenta ogni nome di dominio completo come gateway video separato nel documento della topologia in cui ogni gateway video ha un trunk in un altro pool VIS e il ripristino è ora possibile. Se si usa TLS, è necessario che i nomi multipli siano nella SAN del certificato del gateway video.
    
    > [!NOTE]
    > VIS consente solo le chiamate in arrivo dai gateway configurati nel documento della topologia. 
  
2. **Failover front-end** Se un pool VIS riceve una chiamata da CUCM ma non riesce a raggiungere il proprio registrar principale o il pool di front end, le chiamate vengono instradate a un pool Front-End di backup.
    
     ![Diagramma del failover front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    Il VIS tiene traccia dello stato del pool Front-End principale e del pool Front-End di backup (l'impostazione si trova nell'impostazione di backup per il servizio Registrar nel documento di topologia). Invia i sondaggi delle opzioni una volta al minuto a entrambi i pool e, se sono presenti cinque errori consecutivi, il VIS presuppone che un determinato pool Front-end sia in calo. Se il pool Front-End principale è contrassegnato come giù ed è presente un backup configurato disponibile, il VIS Invia nuove chiamate dal gateway al pool Front-End di backup. Una volta che il pool Front-End principale ritorna, il VIS riprenderà l'uso del pool Front End principale per le nuove chiamate.
    
    Il VIS implementa anche un timer di 10 secondi per le chiamate dal trunk SIP video. Se per una chiamata dal trunk SIP del video è stato usato il pool di front-end di primo hop principale, e il pool di front end del primo hop principale non ha risposto con un messaggio SIP (incluso 100 provando) all'invito inviato all'interno di questo valore del timer, il proxy del successivo hop di backup per la chiamata s hould essere provato se configurato. 
    
    > [!NOTE]
    > Se l'hop successivo di backup è stato provato per primo, il principale non verrà provato avanti. 
  
    L'amministratore può anche usare il comando failover di Windows PowerShell per imporre a VIS di usare il pool Front-End di backup, ad esempio quando la manutenzione deve essere eseguita nel pool Front-End principale.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coesistenza di trunk vocali e video nello stesso peer gateway
<a name="resiliency"> </a>

Skype for Business Server supporta l'uso di trunk SIP vocali e video con lo stesso peer gateway. Quindi la stessa distribuzione CUCM potrebbe avere trunk SIP vocali per il server Mediation e i trunk SIP video in VIS.
  
- Sarà necessario definire un gateway PSTN con un nome FQDN specifico nel documento della topologia per i trunk SIP vocali.
    
- Il peer al gateway PSTN sarà il Mediation Server.
    
- Più trunk vocali può essere definito che si estende da un gateway PSTN a più pool di Mediation Server, se necessario.
    
- Sarà necessario definire un gateway video nel documento di topologia per il trunk SIP video con lo stesso nome di dominio completo del gateway PSTN.
    
- Il peer per il gateway video sarà VIS.
    
- Un singolo trunk video può essere definito da un gateway video a un pool di VIS specifico.
    
- CUCM deve essere configurato per instradare correttamente le chiamate sul tronco vocale e il trunk video. Ad esempio, è possibile usare un prefisso di chiamata speciale durante la chiamata da VTC; CUCM potrebbe associare il prefisso di chiamata con le chiamate a VIS e le regole di traduzione appropriate strisceranno questo prefisso dall'invito SIP a VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coesistenza di VIS nel rilascio di Skype for business con le versioni precedenti di Lync
<a name="resiliency"> </a>

VIS può essere distribuito solo nell'ambito della distribuzione di Skype for business. Può interagire con le conferenze e i client di Lync 2013 che fanno parte di una distribuzione esistente. in questi casi, il pool VIS dovrà far parte di una distribuzione di Skype for business che include un pool di registrar/FE che rappresenta l'hop successivo per il pool VIS.
  
VIS non supporta la transcodifica tra RTV e H. 264. Non c'è interoperabilità video tra client di pre-Lync 2013 e partecipanti VTC in una conferenza.
  
I client di pre-Lync 2013 in una conferenza faranno in modo che i client mobili vengano inviati tramite RTV con il risultato che VTCs non riceve alcun video quando il client mobile diventa l'altoparlante dominante.
  
Per consentire l'utilizzo corretto di Lync 2013 con VIS che fa parte di una distribuzione Skype for business, Lync 2013 richiede l'applicazione di CU appropriata che aggiorni il client Lync 2013, CAA e AVMCU per l'utilizzo con VIS.
  
L'interoperabilità dei client desktop di VIS con Lync 2013 e Skype for business è stata testata ed è supportata.
  
Interoperabilità di VIS con il non-desktop (Android, iPad, iPhone, Windows Phone, LMX e così via) I client Skype for business disponibili nell'App Store applicabile al momento del rilascio di VIS sono stati testati ed è supportato.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recupero dalla perdita di pacchetti tramite FEC
<a name="resiliency"> </a>

FEC può essere attivato per facilitare il ripristino dalla perdita di pacchetti. Se attivata, la larghezza di banda video di 50% verrà usata nella direzione VIS-VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Costi di ridimensionamento e transcodifica VIS
<a name="resiliency"> </a>

La transcodifica dei singoli flussi video dal VTC Cisco a più flussi simulcast usa la capacità della CPU. Circa 16 VTCs possono avere il loro video trascodificato (supponendo che un flusso video 720p da ogni VTC sia transcodificato in 3 flussi separati in simulcast a 720p, 360p e 180p) in un singolo VIS in funzione dell'equivalente della piattaforma FE consigliata di Lync 2013. Se la transcodifica è disattivata, verrà salvata sulla CPU VIS. Tuttavia, l'immagine video richiesta da VIS da VTC sarà la risoluzione comune più bassa per soddisfare tutti i destinatari del lato Skype for business. Tieni presente che anche con la transcodifica disattivata, la transcodifica può essere attivata quando i client Skype for business richiedono alcune risoluzioni minime che VTCs non può inviare.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribuzione delle chiamate dal gateway video a VIS
<a name="resiliency"> </a>

La distribuzione viene eseguita tramite uno dei meccanismi di distribuzione di CUCM:
  
- Uso dinamico di DNS.
    
- Sul lato CUCM è possibile definire singoli trunk, in cui ogni trunk termina in un server diverso nel pool VIS. CUCM instraderà le chiamate tra i diversi trunk.
    
## <a name="no-hybrid-interoperability"></a>Nessuna interoperabilità ibrida
<a name="resiliency"> </a>

Il supporto per VTCs partecipare a riunioni online tramite VIS locale non fa parte di Skype for business.
  
## <a name="no-federation-support"></a>Nessun supporto federativo
<a name="resiliency"> </a>

Il supporto per VTCs partecipare a riunioni federate tramite VIS non fa parte di Skype for business.
  
## <a name="see-also"></a>Vedere anche
<a name="resiliency"> </a>

[Distribuire video Interop server in Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
