---
title: "Ottimizzare la rete per Skype for Business online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: b363bdca-b00d-4150-96c3-ec7eab5a8a43
description: "I requisiti seguenti sono realmente importanti per garantire l'integrità a lungo termine e successo per tutti Skype per le caratteristiche di Business Online impostazione per l'organizzazione. È possibile sapere alcuni sono molto tecnici - questo documento è automaticamente, ma sono disponibili alcune che non sono. Se occorre assistenza la configurazione di Skype for Business Online, è consigliabile leggere questo documento per acquisire familiarità con i cambiamenti da tenere in considerazione. Anche dà elementi a cui rivolgersi quando si lavora con Microsoft FastTrack Center, i Microsoft Services e team account o con Microsoft partner per stabilire come si possibile soddisfa questi requisiti."
---

# Ottimizzare la rete per Skype for Business online

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](b363bdca-b00d-4150-96c3-ec7eab5a8a43.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43). 
  
I requisiti seguenti sono realmente importanti per garantire l'integrità a lungo termine e successo per tutti Skype per le caratteristiche di Business Online impostazione per l'organizzazione. È possibile sapere alcuni sono molto tecnici - questo documento è automaticamente, ma sono disponibili alcune che non sono. Se occorre assistenza la configurazione di Skype for Business Online, è consigliabile leggere questo documento per acquisire familiarità con i cambiamenti da tenere in considerazione. Anche dà elementi a cui rivolgersi quando si lavora con [Microsoft FastTrack Center](https://fasttrack.microsoft.com/office), i Microsoft Services e team account o con [Microsoft partner](https://partnercenter.microsoft.com/en-us/pcv/search) per stabilire come si possibile soddisfa questi requisiti.
  
## Una rapida panoramica

Skype for Business consente di connettersi con i colleghi o partner commerciali nella tua azienda o in tutto il mondo.
  
Con Skype for Business puoi:
  
- iniziare conversazioni con messaggistica istantanea, chiamate vocali o video;
    
- vedere quando i contatti online sono disponibili, sono in riunione o stanno dando una presentazione;
    
- impostare protezione di livello industriale per le riunioni;
    
- trasmettere in broadcast online a un pubblico ampio;
    
-  presentare lo schermo durante le riunioni o lasciare il controllo ad altri;
    
- usare Skype for Business in altri programmi Office per chattare, chiamare o partecipare a una riunione con un clic.
    
## Perché tutto questo è così importante?

La qualità della connettività di rete end-to-end influisce notevolmente sulla qualità dei supporti multimediali in tempo reale (condivisione di audio, video e applicazioni) su IP. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
Utilizzo di un [partner Microsoft](https://partnercenter.microsoft.com/en-us/pcv/search), è possibile connettersi svariate inclusi Skype for Business Online nel cloud per la rete e vocali in tempo reale e funzionalità di comunicazione video di Skype per le applicazioni di Office 365 Business richiedono servizi di rete devono essere specificamente configurati per supportare i carichi di lavoro in tempo reale di Office 365. Sono inclusi una rete con larghezza di banda sufficiente per eseguire il volume del traffico necessario ed essere in grado di supportare qualità del servizio (QoS) per fornire un'esperienza di classe business per gli utenti.
  
Oltre alle informazioni fornite qui, ci sono altre risorse che possono aiutare a pianificare e implementare i servizi e le funzionalità di Skype for Business online e garantire che i servizi di rete soddisfino tali requisiti:
  
- [Flusso delle chiamate con ExpressRoute](call-flow-using-expressroute.md)
    
- [ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)
    
- [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)
    
## Implementazione di Quality of Service (QoS) per Skype for Business

Prima di passare a Skype for Business Online, è opportuno osservare la capacità di rete per gestire l'audio, video e il traffico sessione di condivisione. Come con altri servizi di Office 365, Microsoft ha a disposizione per scaricare [Skype per Business della larghezza di banda calcolatrice](https://www.microsoft.com/en-us/download/details.aspx?id=19011) utilizzata per determinare il traffico di rete necessari per ogni sito della società. È consigliabile eseguire modellazione l'uso, tra cui la modellazione in tempo reale il traffico multimediale comunicazione e la quantità di Skype per il traffico di Business per sede aziendale, il calcolo volume di traffico e analisi impatto che il traffico sulla rete complessiva. Dopo aver selezionato, analisi dei dati dovrebbe fornire consigli nel punto in cui la rete deve essere migliorate e consigliabile dimensioni coda per fornire un'esperienza ottimale degli utenti finali.
  
Skype per il traffico in tempo reale Business è riservati per la perdita di pacchetti, ritardo e variazione, si verificano spesso nelle reti traffico ridotto. Qualità del servizio (QoS), a volte chiamato anche classe di servizio - devono essere distribuite anche gestiti WAN esterni, gestita LAN interna e reti WiFi enterprise. In questo modo la priorità correttamente Skype per il traffico in tempo reale di Business, ad esempio audio e video tramite il traffico in tempo reale sulle reti locali e WAN, creare un'esperienza migliore per gli utenti finali.
  
Skype per l'audio di Business deve essere distribuiti in EF (accelerata inoltro-46 DSCP) Skype per le videochiamate Business e coda devono essere distribuiti nel AF41 (sicuri inoltro-DSCP 34) coda. Questo vale anche per il traffico peer-to-peer e conferenze, indipendentemente dal fatto che il sistema telefonico in Office 365 o altre funzionalità di telefonia distribuiti.
  
Mentre si QoS esistente criteri potrebbero essere presenti già sulla LAN e WAN per altri prodotti di telefonia IP, Skype for Business consente agli utenti da dispositivi mobili e per spostarsi in postazioni durante l'utilizzo del servizio. Per questi motivi, criteri QoS devono essere contrassegnati LAN, WAN e reti per assicurarsi che viene assegnata la priorità di Skype tutti per il traffico di Business reti gestito.
  
Per aiutarti nel dimensionamento della rete, scarica il [Calcolatore di larghezza di banda di Skype for Business](https://www.microsoft.com/en-us/download/details.aspx?id=19011).
  
Per maggiori informazioni su qualità multimediale e QoS, consulta [Qualità multimediale e prestazioni della connettività di rete in Skype for Business online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md)
  
Per ulteriori informazioni sull'impostazione e gestione di QoS, vedere [Gestione di qualità del servizio](https://technet.microsoft.com/en-us/library/gg425841.aspx).
  
## Bypassare proxy e dispositivi di ottimizzazione WAN

Tutto Office 365, tra cui Skype for Business Online è crittografato e in genere non può essere controllati da dispositivi proxy. Per questi motivi è consigliabile ignorare dispositivi proxy per tutto il traffico rete Office 365 come definito come connessioni che verificare gli utenti a [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Dal momento che i dispositivi proxy presenterà probabilmente ritardo in tempo reale Skype per Business Online flussi multimediali che si consiglia di ignorare i dispositivi proxy almeno per il traffico.
  
Microsoft consiglia di escludere gli URL di Office 365 utilizzando file PAC per inviare il traffico di Office 365 a un firewall. 
  
Ecco alcune altre risorse disponibili che possono essere d'aiuto:
  
- [Ottimizzazione delle prestazioni di Office 365 con la cronologia delle previsioni e delle prestazioni](https://support.office.com/article/1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
    
- [Pianificazione della rete e della migrazione per Office 365](https://support.office.com/article/f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132)
    
- [Generatore di PAC per proxy di Office 365](https://gallery.technet.microsoft.com/Office-365-Proxy-Pac-60fb28f7)
    
- [Utilizzare i dispositivi di controllo ottimizzazione WAN o di traffico/ispezione con Office 365](https://aka.ms/kb2690045)
    
- [Routing con ExpressRoute per Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)
    
## Bypassare la doppia crittografia

Per offrire agli utenti la migliore possibili esperienza audio e video, è necessario implementare una soluzione che impedisce Skype per i file multimediali Business (audio e video) attraversa un tunnel di rete privata virtuale (VPN). Tutti Skype per il traffico Business verrà crittografate con sicurezza TLS (Transport Layer) e i carichi di lavoro di elementi multimediali vengono crittografati sicura in tempo reale Protocol (SRTP). Segnalazione di crittografia con TLS e i carichi di lavoro di elementi multimediali vengono crittografate con SRTP. Inviare che il traffico attraverso il tunnel VPN aggiunge un livello aggiuntivo di crittografia e hop di rete tra il client e Office 365, che possono causare una sessione di peggiore poiché aumenta variazione, la perdita di pacchetti e la latenza.
  
Per impedire Skype per il traffico Business attraversa tunnel VPN è Tunneling divisa. Per implementare tunneling divisa, clienti consigliabile consultare il proprio fornitore VPN sulle specifiche di come eseguire questa operazione con software.
  
> [!NOTE]
> Questo è necessario solo per i carichi di lavoro multimediali di Skype for Business e non è applicabile ad altri servizi di Office 365. 
  
Risorse aggiuntive:
  
- [Consentire ai contenuti multimediali di Lync di ignorare un tunnel VPN](https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/)
    
- [Altre informazioni su accesso diretto, split tunneling e force tunneling](https://blogs.technet.com/b/tomshinder/archive/2010/03/30/more-on-directaccess-split-tunneling-and-force-tunneling.aspx)
    
- [Abilitare l'accesso diretto](https://technet.microsoft.com/en-us/library/jj574163.aspx)
    
## Assicurarsi che le porte e i protocolli corretti siano aperti

I clienti devono garantire la raggiungibilità degli URL e degli indirizzi IP necessari per il servizio O365. Per un elenco completo di tutti gli indirizzi IP e gli URL per Skype for Business online, vedere [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
  
I client di Skype for Business utilizzano diverse porte e protocolli. La direzione e il flusso del traffico di rete per una sessione di Skype for Business varieranno a seconda del tipo di interazioni (peer-to-peer vs multiparte) e a seconda della condivisione dei contenuti e del traffico vocale/video. È necessario consultare e aprire l'elenco di porte e protocolli, con particolare attenzione alle porte di origine e di destinazione. Ad esempio, il traffico audio utilizza solo 20 porte (50000-50019 TCP/UDP) sul lato client, ma la porta di destinazione potrebbe essere qualsiasi in un intervallo di 10.000 porte (50000-59999 TCP/UDP) sul lato servizio. Questo include anche l'apertura di TCP 443 e UDP 3478 sul firewall.
  
Potrebbe essere necessaria una configurazione di rete aggiuntiva per supportare Skype for Business online.
  
Puoi eseguire il test FastTrack CloudApp dalla macchina client per verificare tutto sia impostato correttamente:
  
- **America del Nord:**
    
  - [Office 365 Fast Track Network Analysis (North America)](http://na1-fasttrack.cloudapp.net/)
    
  - [https://137.117.72.96](https://137.117.72.96)
    
- **EMEA:**
    
  - [Office 365 Fast Track Network Analysis (EMEA)](http://em1-fasttrack.cloudapp.net/)
    
  - [https://137.116.212.202](https://137.116.212.202)
    
- **APAC:**
    
  - [Office 365 Fast Track Network Analysis (Asia Pacific)](http://ap1-fasttrack.cloudapp.net)
    
  - [https://168.63.169.67](https://168.63.169.67)
    
È anche possibile visualizzare, [Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## Utilizzare i telefoni e dispositivi ottimizzati per Skype for Business

In una sessione multimediale in tempo reale, i dispositivi multimediali usati da tutti i partecipanti, come ad esempio cuffie auricolari e web cam, hanno un impatto notevole sulla qualità complessiva di audio e video. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Telefoni e dispositivi apportare una grande differenza nella qualità dell'audio e video per gli utenti finali. Skype per il programma di certificazione Business è un'evoluzione della finestra del programma "Lync compatibile" e verifica che il dispositivo soddisfi standard Microsoft per l'audio e video. Sono disponibili numerosi i telefoni IP, USB dispositivi audio e video, PC e dispositivi di chat room che sono stati testati e qualificati da Microsoft della riunione. È consigliabile esaminare l'elenco dei dispositivi ottimizzate per Skype for Business e lavoro fornire diversi dispositivi per soddisfare diverse esigenze e preferenze degli utenti finali dell'organizzazione.
  
Consulta quanto segue per ulteriori informazioni sui dispositivi supportati e certificati:
  
- [Ottenere telefoni per Skype for Business online](../what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md)
    
- [Cellulari e dispositivi per Skype for Business](https://technet.microsoft.com/en-us/office/dn947482.aspx)
    
- [Catalogo di soluzioni per le periferiche personali](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)
    
- [Telefoni e dispositivi qualificati per Microsoft Lync](https://technet.microsoft.com/en-us/office/dn788944.aspx)
    
L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
Per ottenere un quadro d'uso di audio e video completa di un utente di Skype per Business app **Strumenti** > **Opzioni** > **Dispositivo Audio** o **Video** per apportare modifiche al dispositivo in uso e personalizzare le impostazioni. È anche possibile controllare la qualità audio di una chiamata, fare clic su **Controlla qualità chiamata**. Se si fa clic su **Controlla qualità chiamata**, possono quindi segnalare la qualità e problemi riscontrati con la chiamata di prova.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
## Argomenti correlati

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

