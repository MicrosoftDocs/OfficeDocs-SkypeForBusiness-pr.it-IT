---
title: Ottimizzazione della rete
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: I seguenti requisiti sono molto importanti per garantire il corretto funzionamento e il successo a lungo termine di tutte le funzioni di Skype for Business online che stai configurando per l'organizzazione. Se sei tra le persone che hanno molta dimestichezza con gli aspetti tecnici, questo documento è per te. Ma ci sono altri che non sono altrettanto a proprio agio. Se hai bisogno di aiuto per l'impostazione di Skype for Business online, leggi questo documento per prendere coscienza degli aspetti che dovrai considerare. Vi insegnerà anche che linguaggio usare quando interagite con Microsoft FastTrack Center, i vostri team di account e di servizi Microsoft o con i partner Microsoft per capire come è possibile soddisfare questi requisiti.
ms.openlocfilehash: aac6a85b78df7477a6e62ddbf766015182bb7a2b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234529"
---
# <a name="optimizing-your-network-for-skype-for-business-online"></a>Ottimizzare la rete per Skype for Business online

[] I seguenti requisiti sono molto importanti per garantire il corretto funzionamento e il successo a lungo termine di tutte le funzioni di Skype for Business online che stai configurando per l'organizzazione. Se sei tra le persone che hanno molta dimestichezza con gli aspetti tecnici, questo documento è per te. Ma ci sono altri che non sono altrettanto a proprio agio. Se hai bisogno di aiuto per l'impostazione di Skype for Business online, leggi questo documento per prendere coscienza degli aspetti che dovrai considerare. Vi insegnerà anche che linguaggio usare quando interagite con [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), i vostri team di account e di servizi Microsoft o con i [partner Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search) per capire come è possibile soddisfare questi requisiti.
  
## <a name="a-quick-overview"></a>Una rapida panoramica

Skype for Business consente di connettersi con i colleghi o partner commerciali nella tua azienda o in tutto il mondo.
  
Con Skype for Business puoi:
  
- iniziare conversazioni con messaggistica istantanea, chiamate vocali o video;
    
- vedere quando i contatti online sono disponibili, sono in riunione o stanno dando una presentazione;
    
- impostare protezione di livello industriale per le riunioni;
    
- trasmettere in broadcast online a un pubblico ampio;
    
- presentare lo schermo durante le riunioni o lasciare il controllo ad altri;
    
- usare Skype for Business in altri programmi Office per chattare, chiamare o partecipare a una riunione con un clic.
    
## <a name="why-is-this-all-so-important"></a>Perché tutto questo è così importante?

La qualità della connettività di rete end-to-end influisce notevolmente sulla qualità dei supporti multimediali in tempo reale (condivisione di audio, video e applicazioni) su IP. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
Utilizzo di un [partner di Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), è possibile connettere una varietà di applicazioni di Office 365 inclusi Skype Business online nel cloud per la rete e vocali in tempo reale e funzionalità di comunicazione video per Skype per le aziende richiedono rete servizi devono essere configurati in modo specifico per il supporto di questi carichi di lavoro in tempo reale di Office 365. Ciò comprende una rete che abbia una larghezza di banda sufficiente per supportare il volume di traffico richiesto e che sia in grado di supportare la qualità del servizio (QoS, Quality of Service) per offrire agli utenti un'esperienza di livello aziendale.
  
Oltre alle informazioni fornite qui, ci sono altre risorse che possono aiutare a pianificare e implementare i servizi e le funzionalità di Skype for Business online e garantire che i servizi di rete soddisfino tali requisiti:
  
- [Flusso delle chiamate con ExpressRoute](call-flow-using-expressroute.md)
    
- [ExpressRoute e QoS in Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance.md)
    
## <a name="implement-quality-of-service-qos-for-skype-for-business"></a>Implementazione di Quality of Service (QoS) per Skype for Business

Prima di passare a Skype for Business online, verifica la capacità della rete di gestire il traffico della sessione per audio, video e condivisione. Come avviene con altri servizi di Office 365, Microsoft mette a disposizione per il download il [Calcolatore di larghezza di banda di Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=19011) che viene utilizzato per determinare il traffico di rete necessario per ciascuno dei tuoi siti aziendali. Consigliamo di eseguire una modellizzazione dell'utilizzo, compresa la modellizzazione dei flussi multimediali di traffico delle comunicazioni in tempo reale e della quantità di traffico Skype for Business per sede dell'azienda, calcolando il volume di traffico e analizzandone l'impatto sul traffico della rete complessiva. Fatto questo, l'analisi di questi dati dovrebbe fornire raccomandazioni su dove migliorare la rete e raccomandare le dimensioni delle code per poter fornire un'esperienza ottimale all'utente finale.
  
Il traffico in tempo reale di Skype for Business è sensibile a perdita di pacchetti, ritardo e jitter, che si verificano spesso nelle reti congestionate. La Qualità del servizio (QoS) - a volte chiamata Class of Service - deve essere distribuita su reti WAN esterne gestite, LAN interne gestite e reti WiFi aziendali. Ciò contribuirà a prioritizzare correttamente il traffico in tempo reale di Skype for Business, come audio e video, rispetto ad altro traffico non in tempo reale su reti locali e su WAN, per dare così una migliore esperienza agli utenti finali.
  
L'audio di Skype for Business deve essere distribuito in coda EF (Expedited Forwarding - DSCP 46) e il video di Skype for Business deve essere distribuito nella coda AF41 (Assured Forwarding - DSCP 34). Questo vale anche per il traffico peer-to-peer e di conferenza, indipendentemente dal fatto che siano stati distribuiti Cloud PBX o altre funzioni di telefonia.
  
Se da una parte possono essere già implementate politiche di QoS sulla LAN e WAN per altri prodotti di telefonia IP, Skype for Business consente agli utenti di essere mobili e spostarsi da un luogo all'altro durante l'utilizzo del servizio. Per questo motivo, le politiche di QoS devono essere contrassegnate sulle reti LAN, WAN e wireless in modo da essere sicuri che tutto il traffico di Skype for Business sia prioritario sulle reti gestite.
  
Per aiutarti nel dimensionamento della rete, scarica il [Calcolatore di larghezza di banda di Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Per maggiori informazioni su qualità multimediale e QoS, consulta [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance.md)
  
Per maggiori informazioni su come impostare e gestire la QoS, vedi [Gestione della qualità del servizio](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## <a name="bypass-proxies-and-wan-optimization-devices"></a>Bypassare proxy e dispositivi di ottimizzazione WAN

Ogni parte di Office 365, compreso Skype for Business online, è crittografata e generalmente non è ispezionabile dai dispositivi proxy. Per queste ragioni si consiglia di bypassare i dispositivi proxy per tutto il traffico di rete di Office 365, ovvero tutte le connessioni degli utenti agli [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Dato che i dispositivi proxy introducono probabilmente un ritardo nei flussi multimediali in tempo reale di Skype for Business online, si consiglia vivamente di bypassare i dispositivi proxy quanto più possibile per tale traffico.
  
Microsoft consiglia di escludere gli URL di Office 365 utilizzando file PAC per inviare il traffico di Office 365 a un firewall.
  
Ecco alcune altre risorse disponibili che possono essere d'aiuto:
  
- [Ottimizzazione delle prestazioni di Office 365 con la cronologia delle previsioni e delle prestazioni](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Pianificazione della rete e della migrazione per Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Generatore di PAC per proxy di Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Utilizzare i dispositivi di controllo ottimizzazione WAN o di traffico/ispezione con Office 365](https://aka.ms/kb2690045)
    
- [Routing con ExpressRoute per Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## <a name="bypass-double-encryption"></a>Bypassare la doppia crittografia

Per fornire agli utenti la migliore esperienza audio e video possibile, è necessario implementare una soluzione che impedisce ai contenuti multimediali di Skype for Business (audio e video) di attraversare un tunnel VPN. Tutto il traffico di Skype for Business è crittografato con Transport Layer Security (TLS) e i carichi di lavoro multimediali sono crittografati con Secure Real Time Protocol (SRTP). La segnalazione viene crittografata con TLS e i carichi di lavoro multimediali sono crittografati con SRTP. L'invio di questo traffico attraverso un tunnel VPN aggiunge un ulteriore livello di crittografia e altri tratti di rete tra il client e Office 365, entrambi fattori che possono degradare la qualità della sessione perché aumentano jitter, perdita di pacchetti e latenza.
  
Una possibilità per evitare che il traffico di Skype for Business attraversi i tunnel VPN è lo Split Tunneling. Per implementare lo split tunneling, i clienti devono consultare il proprio fornitore di VPN per istruzioni specifiche su come procedere nel loro software.
  
> [!NOTE]
> Questo è necessario solo per i carichi di lavoro multimediali di Skype for Business e non è applicabile ad altri servizi di Office 365. 
  
Risorse aggiuntive:
  
- [Consentire ai contenuti multimediali di Lync di ignorare un tunnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Altre informazioni su accesso diretto, split tunneling e force tunneling](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Abilitare l'accesso diretto](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## <a name="ensure-the-right-ports-and-protocols-are-open"></a>Assicurarsi che le porte e i protocolli corretti siano aperti

I clienti devono garantire la raggiungibilità degli URL e degli indirizzi IP necessari per il servizio O365. Per un elenco completo di tutti gli indirizzi IP e gli URL per Skype for Business online, vedere [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
I client di Skype for Business utilizzano diverse porte e protocolli. La direzione e il flusso del traffico di rete per una sessione di Skype for Business varieranno a seconda del tipo di interazioni (peer-to-peer vs multiparte) e a seconda della condivisione dei contenuti e del traffico vocale/video. È necessario consultare e aprire l'elenco di porte e protocolli, con particolare attenzione alle porte di origine e di destinazione. Ad esempio, il traffico audio utilizza solo 20 porte (50000-50019 TCP/UDP) sul lato client, ma la porta di destinazione potrebbe essere qualsiasi in un intervallo di 10.000 porte (50000-59999 TCP/UDP) sul lato servizio. Questo include anche l'apertura di TCP 443 e UDP 3478 sul firewall.
  
Potrebbe essere necessaria una configurazione di rete aggiuntiva per supportare Skype for Business online.
  
  
## <a name="use-phones-and-devices-optimized-for-skype-for-business"></a>Utilizzare i telefoni e dispositivi ottimizzati per Skype for Business

In una sessione multimediale in tempo reale, i dispositivi multimediali usati da tutti i partecipanti, come ad esempio cuffie auricolari e web cam, hanno un impatto notevole sulla qualità complessiva di audio e video. Dispositivi di qualità inferiore o basati su driver di dispositivo non corretto genererà inferiore qualità audio complessiva per la qualità audio e riduzione dell'immagine per il video. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Telefoni e dispositivi fanno un'enorme differenza nella qualità di audio e video per gli utenti finali. Il programma di certificazione Skype for Business è un'evoluzione del programma "Lync Compatibile" e convalida che il dispositivo sia conforme agli standard di Microsoft per audio e video. Diversi telefoni IP, dispositivi audio e video USB, PC e dispositivi per sala riunioni sono stati testati e qualificati da Microsoft. Consulta l'elenco dei dispositivi ottimizzati per Skype for Business e fai in modo di fornire dispositivi diversi che soddisfino le diverse esigenze e preferenze personali degli utenti finali nell'organizzazione.
  
Consulta quanto segue per ulteriori informazioni sui dispositivi supportati e certificati:  
  
- [Ottenere telefoni per Skype for Business online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Cellulari e dispositivi per Skype for Business](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catalogo di soluzioni per le periferiche personali](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Telefoni e dispositivi qualificati per Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per ottenere una visione dell'utilizzo di audio e video esperienza dell'utente di Skype per app Business **Strumenti** > **Opzioni** > **Dispositivo Audio** o **Video** per apportare modifiche al dispositivo in uso e personalizzare le impostazioni. È inoltre possibile controllare la qualità dell'audio di una chiamata facendo clic su **Controlla qualità chiamata**. Se gli utenti fanno clic su **Controllo qualità chiamata**, possono segnalare li livello di qualità e i problemi riscontrati con una chiamata di prova.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## <a name="related-topics"></a>Argomenti correlati 

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)
  
  
 
