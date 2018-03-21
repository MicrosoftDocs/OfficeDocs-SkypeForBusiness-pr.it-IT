---
title: Media Quality and Network Connectivity Performance
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: This topic defines the set of network performance requirements for Skype for Business Online services and how you can choose to use the Internet or ExpressRoute for connectivity between your network and Skype for Business Online based your assessment of the network connectivity. If you have decided to deploy Azure ExpressRoute for dedicated connectivity to Office 365, this document also provides guidance on how to plan your ExpressRoute connections in different Skype for Business Online deployment scenarios.
ms.openlocfilehash: 7b68253fe44850009639de57eadee2edefeb5e0c
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Media Quality and Network Connectivity Performance in Skype for Business Online

This topic defines the set of network performance requirements for Skype for Business Online services and how you can choose to use the Internet or ExpressRoute for connectivity between your network and Skype for Business Online based your assessment of the network connectivity. If you have decided to deploy Azure ExpressRoute for dedicated connectivity to Office 365, this document also provides guidance on how to plan your ExpressRoute connections in different Skype for Business Online deployment scenarios.
  
The quality of Real-Time media (audio, video, and application sharing) over IP is greatly impacted by the quality of end-to-end network connectivity. Per una qualità ottimale dei supporti multimediali di Skype for Business Online, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Il modo migliore per offrire tale qualità è configurare la propria rete interna e la connettività cloud in base alla capacità della rete di contenere picchi di traffico per Skype for Business Online su tutte le connessioni.
  
Azure ExpressRoute isn't a requirement for Office 365 services including Skype for Business Online. However, Azure ExpressRoute is one of the deployment options that are available that will help make sure that connectivity to Office 365 meets the Skype for Business network performance requirements and ensures the most optimal Skype for Business Online media quality experience.
  
> [!TIP]
> Although this topic provides you with overall networking performance guidance, complete guidance for network assessment is outside of the scope of this document. To find a list of Skype for Business Online partners who can help you with the network performance measurements as part of a thorough and complete network assessment, please visit [Skype for Business Partner Solutions](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Network connectivity requirements to Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Factors that impact Skype for Business Online media quality

There are many different factors that contribute to Skype for Business Online Real-Time media (audio, video, and application sharing) quality that include the devices that are used, the environment, and the network connectivity. 
  
#### <a name="devices"></a>Devices

In a Real-Time media session, media capturing and rendering devices that are used by all participants such as headsets and Web cams have a great impact on the overall audio and video quality. I dispositivi di bassa qualità o dotati di driver non adeguati produrranno suoni audio o immagini video di qualità inferiore. Al contrario, i dispositivi certificati o di buona qualità aiutano a eliminare l'eco, filtrare il rumore, migliorare la risoluzione video e ridurre la latenza.
  
Although certified audio and video media devices aren't required, it's highly recommended devices certified for Skype for Business for the most optimal media experience. For a list of all Skype for Business certified devices, see [Phones and Devices for Skype for Business](https://technet.microsoft.com/en-us/office/dn947482). You can use the [Skype for Business Online Call Quality Dashboard](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md), found in the **Skype for Business admin center**, to verify devices in use are working correctly and monitor audio and video media quality.
  
> [!TIP]
> **A certified device is required for the most optimal Skype for Business media quality experience**.
  
It's important to remember that any media devices, Skype for Business clients, and Skype for Business Servers through which Real-Time media flows, introduce some amount of latency. The device and software processing latency, along with network latency, have a great impact on and contribute to the end-to-end overall latency and the end user's experience.
  
#### <a name="environment"></a>Environment

L'ambiente e l'area circostante il punto in cui gli utenti si incontrano e usano dispositivi audio e video rappresentano un altro fattore importante che influisce sulla qualità. Gli utenti che chiamano da ambienti rumorosi dovranno fare i conti con l'eco e suoni soffocati e poco chiari. Gli utenti in ambienti bui o di scarsa illuminazione non potranno produrre immagini chiare e luminose. In una sala riunioni, la posizione del microfono e del dispositivo video hanno un impatto diretto sulla qualità del suono e dell'immagine che riceveranno i partecipanti.
  
To get a clearer picture of a user's audio and video experience use the Skype for Business app **Tools** > **Options** > **Audio Device** or **Video Device** to make changes to the device in use and customize it's settings. You can also check the audio quality of a call by clicking **Check Call Quality**. Se gli utenti fanno clic su **Controllo qualità chiamata**, possono segnalare li livello di qualità e i problemi riscontrati con una chiamata di prova.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>Network

The quality of the Real-Time media over IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:
  
- **Latency** This is the time it takes to get an IP packet from point A to point B on the network. This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between. Latency is measured as one-way or Round-trip Time (RTT).
    
- **Packet Loss** This is often defined as a percentage of packets that are lost in a given window of time. Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.
    
- **Inter-packet arrival jitter or simply jitter** This is the average change in delay between successive packets. Most modern VoIP software including Skype for Business can adapt to some levels of jitter through buffering. It's only when the jitter exceeds the buffering that a participant will notice the effects of jitter.
    
> [!NOTE]
>  Buffering for jitter will increase end-to-end latency.
  
With many concurrent Skype for Business Online Real-Time media sessions, as well as other network traffic generated by other Office 365 services and other business applications, making sure that there is sufficient bandwidth over the entire network path that connects your network to the Skype for Business Online service is critical to avoid network congestion and ensure excellent media Real-Time media (audio, video, and application sharing) quality. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementing Quality of Service (QoS) across congested networks

In addition, traffic congestion across a network will greatly impact media quality. To allow audio and video packets to travel the network quicker and to be prioritized over other network traffic in a congested network, Quality of Service (QoS) can be used to help provide an optimal end-user experience for audio and video communications.
  
QoS provides a way for you to assign higher priorities to network packets that are carrying audio or video data. By assigning a higher priority to these packets, audio and video communications are likely to travel over the network faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because the network packets used for file transfers or database backups by default are assigned "best effort" as a priority and network congestion won't have as large impact. If you don't assign a higher priority to the media (audio, video, and application sharing) packets and leave them also assigned as "best effort", they too will be processed along with all other network traffic. Depending on the amount of network congestion, this will potentially end up in a lower overall audio and video quality experience for your users.
  
It is highly recommended that you implement QoS on your network to make sure that network congestion within your network won't have an impact. However, for this to have the maximum impact, all networking endpoints must support QoS, meaning that all endpoints must honor QoS marking and packet prioritization. Skype for Business Online services honor QoS marking and prioritization within the Microsoft network. However, traffic that is routed across a public connection like the Internet from your company network to the Microsoft network doesn't preserve QoS markings and packet prioritization. Private connections from your network to Office 365 using [Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) offer a deployment solution that preserves QoS markings and packet prioritization that will in turn increase overall audio and video quality for your end users.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Network performance requirements to connect to Skype for Business Online
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time media travels through many different devices, client apps, server software, and across different networks. The end-to-end latency of Real-Time media is the total amount of latency that is introduced across all components and network segments. The quality of the end-to-end network connection is determined by the network segment with the worst quality. This segment acts as a bottleneck for this network traffic.
  
The following diagram illustrates one-way audio flow in a conference from one Skype for Business participant to another.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
In this conferencing scenario, the media path consists across the following network segments:
  
1. **Connection from User 1 to the edge of the Microsoft network** This usually includes a network connection such as WiFi or Ethernet, the WAN connection from User 1 to the Internet egress point (your network Edge device), and the Internet connection from your network Edge to Microsoft network Edge.
    
2. **Connection within Microsoft network** This is between the Microsoft Edge to Skype for Business Online data center, where the A/V Conferencing servers are used.
    
3. **Connection within Microsoft Network** This is between the Skype for Business Online data center and Microsoft network Edge.
    
4. **Connection from Microsoft network edge to User 2** This includes the Internet connection from your network Edge to Microsoft network Edge, the WAN connection from User 2 to the Internet egress point (your network Edge), and the network connection such as a WiFi or an Ethernet.
    
The following diagram shows breakdown of components and network segments of a Skype for Business Online PSTN call:
  
![ExpressRoute PSTN Carrier Call Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
In a PSTN call scenario, the media path crosses the following network segments:
  
1. **Connection from a Skype for Business client caller to the edge of the Microsoft Network** This usually includes a network connection such as WiFi or Ethernet, the WAN connection from the Skype for Business client caller to the Internet egress point (your network Edge device), and the Internet connection from your network Edge to Microsoft network Edge.
    
2. **Connection within Microsoft network** This is between the Microsoft Edge to Skype for Business Online data center, where a Mediation Server is used.
    
3. **Connection within Microsoft Network** This is between the Skype for Business Online data center and Microsoft network Edge.
    
4. **Connection between Microsoft Network and the PSTN service provider partners** This is the connection that exists to place a PSTN call from the Skype for Business client that is outside of the Microsoft network.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Network Performance requirements from a Skype for Business client to Microsoft network Edge
<a name="bkSfBClienttoEdge"></a>

For optimal Skype for Business media quality, the following network performance metrics targets or thresholds are required for a connection from your company's network to the Microsoft network Edge. This segment of the network includes your internal network, this includes all WiFi and Ethernet connections, any company site-to-site traffic over a WAN connection, for example Multiprotocol Label Switching (MPLS), as well as the Internet or ExpressRoute partner connections to the Microsoft network Edge.
  
> [!CAUTION]
> **Connectivity between a Skype for Business client on your company network to Office 365 services must meet these following network performance requirements and thresholds.**
  
|||
|:-----|:-----|
|**Metric** <br/> |**Target** <br/> |
|Latency (one way)  <br/> |< 50ms  <br/> |
|Latency (RTT or Round-trip Time)  <br/> |< 100ms  <br/> |
|Burst packet loss  <br/> |<10% during any 200ms interval  <br/> |
|Packet loss  <br/> |<1% during any 15s interval  <br/> |
|Packet inter-arrival Jitter  <br/> |<30ms during any 15s interval  <br/> |
|Packet reorder  <br/> |<0.05% out-of-order packets  <br/> |
   
 **Other performance target requirements:**
  
- The Microsoft network has over 160 Edge locations worldwide. We work with major Internet Service Providers (ISPs) worldwide through those Edge sites. The latency metric target assumes your company site or sites and the Microsoft Edges are on the same continent.
    
- Your company site or sites to the Microsoft network Edge connection include first hop network access, which can be WiFi or another wireless technology. 
    
- The network performance target assumes proper bandwidth and/or quality of service planning. In other words, This applies directly to Skype for Business Real-Time media traffic when the network connection is under a peak load.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Network performance requirements from your network Edge to Microsoft network Edge
<a name="bkYourNetworkEdge"> </a>

The following are the network performance targets or thresholds that are required for the connection between your network Edge and the Microsoft network Edge. This segment of the network excludes the customer's internal network or WAN, and is intended as guidance when testing your network traffic that is sent over the Internet, or through an ExpressRoute partner network and can also be used when negotiating a performance Service Level Agreement (SLA) with your ExpressRoute provider.
  
> [!CAUTION]
> **Connectivity between your company network Edge to the Microsoft network edge must meet these following network performance requirements and thresholds.**
  
|||
|:-----|:-----|
|**Metric** <br/> |**Target** <br/> |
|Latency (one way)  <br/> |< 30ms  <br/> |
|Latency (RTT)  <br/> |< 60ms  <br/> |
|Burst packet loss  <br/> |<1% during any 200 ms interval  <br/> |
|Packet loss  <br/> |<0.1% during any 15s interval  <br/> |
|Packet inter-arrival Jitter  <br/> |<15ms during any 15s interval  <br/> |
|Packet reorder  <br/> |<0.01% out-of-order packets  <br/> |
   
 **Other performance target requirements:**
  
- The performance target requires connection between any of your company's network Edge and its nearest Microsoft network Edge, to be on the same continent.
    
- The network performance target assumes proper bandwidth and/or quality of service planning. This also applies to Skype for Business Real-Time media traffic when the network connection is under a peak load. For proper bandwidth and QoS planning, please refer to [ExpressRoute and QoS in Skype for Business Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Measuring network performance
<a name="bkNetworkPerf"> </a>

To measure the actual network performance, especially for latency and packet loss, from any company network site to a network Edge, you can use tools such as ping, test against a set of Skype for Business media relay services running from the Microsoft Edge and data center sites. 
  
For testing Internet connections to the Microsoft network, it is recommended that you test against the following VIPs of the Skype for Business media relays. The *Anycast VIP*  will resolve to an IP address of a Media Relay in a Microsoft network Edge site that is closest to the testing location.
  
||||
|:-----|:-----|:-----|
|**IP address** <br/> |**Type** <br/> |**Posizione** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **Here are some high level recommendations to follow for assessing network performance:**
  
- You should assess your internal network as well as the connections to Office 365.
    
- You should assess and gather data for all of your networks over a long period of time. We recommend for you to perform your testing of network performance for a minimum of a week, so that you can see usage patterns for all business days and hours. This will show you peak times.
    
- You should take multiple samples of network performance measurements. We recommend taking a measurement every 10 minutes from a company site during the entire period of time you are gathering data. For comparing the Skype for Business Online network performance requirements, take the 90th percentile measurement value from this sample data set. 
    
- You should continuously assess the network's performance. Network utilization varies over time due to usage pattern changes, new enterprise-based applications that use a large amount of bandwidth, and changes to your organizational or physical company locations. It is important for you to continuously monitor your network performance against these network performance requirements and targets/thresholds and make timely adjustments to ensure the most optimal Real-Time media quality. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Measuring Network Performance using Azure VMs
<a name="bkNetworkPerf"> </a>

Instead of testing against the Microsoft network Edge sites, there are network assessment solutions from Skype for Business customers and partners that leverage testing setup for services in the Microsoft Azure cloud. In those solutions, the network assessment tools test latency, packet loss and jitter against custom endpoints set up as a service in the Azure cloud. As a result, the test network traffic travels through one additional network segment, which is the connection within the Microsoft network between the network edges and Azure data centers that hosts the network assessment service.
  
For those network assessment solutions based on Azure hosted testing services. We recommend performing the network assessment within country and/or region. For example, for customer sites in east U.S., the assessment should be performed against a testing service instance hosted in Azure's east US data center region. 
  
Below are the latency (RTT) targets for the Azure service based network assessment setup. The one-way latency targets will be half of the corresponding RTT targets. The packet loss and jitter goals stays the same as those defined for Skype Media Relay based testing.
  
|||||
|:-----|:-----|:-----|:-----|
|**Customer region** <br/> |**Azure region** <br/> |**Your network Edge - Azure Round-trip Time (RTT)** <br/> |**Your Site - Azure Round-trip Time (RTT)** <br/> |
|Central US  <br/> |Central US  <br/> |99  <br/> |139  <br/> |
|East US  <br/> |East US  <br/> |86  <br/> |126  <br/> |
|North Central US  <br/> |North Central US  <br/> |97  <br/> |137  <br/> |
|South Central US  <br/> |South Central US  <br/> |94  <br/> |134  <br/> |
|West US  <br/> |West US  <br/> |94  <br/> |134  <br/> |
|Hawaii US  <br/> |West US  <br/> |116  <br/> |156  <br/> |
|Canada Central  <br/> |Canada Central  <br/> |138  <br/> |178  <br/> |
|Canada East  <br/> |Canada East  <br/> |131  <br/> |171  <br/> |
|North Europe  <br/> |North Europe  <br/> |99  <br/> |139  <br/> |
|West Europe  <br/> |West Europe  <br/> |95  <br/> |135  <br/> |
|East Asia  <br/> |East Asia  <br/> |118  <br/> |158  <br/> |
|Southeast Asia  <br/> |Southeast Asia  <br/> |97  <br/> |137  <br/> |
|Japan East  <br/> |Japan East  <br/> |111  <br/> |151  <br/> |
|Japan West  <br/> |Japan West  <br/> |118  <br/> |158  <br/> |
|Brazil South  <br/> |Brazil South  <br/> |70  <br/> |110  <br/> |
|Australia East  <br/> |Australia East  <br/> |124  <br/> |164  <br/> |
|Australia Southeast  <br/> |Australia Southeast  <br/> |124  <br/> |164  <br/> |
|India centrale  <br/> |India centrale  <br/> |103  <br/> |143  <br/> |
|South India  <br/> |South India  <br/> |103  <br/> |143  <br/> |
|West India  <br/> |West India  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |120  <br/> |160  <br/> |
|Nord cinese  <br/> |Nord cinese  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualità multimediale ed ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute Azure per Office 365 è una connessione di rete dedicato per la connessione a Office 365. Offre ai clienti la possibilità di controllare il percorso loro il traffico di rete di Office 365. Non è più hanno problemi imprevisti ciclo che si verifica in Internet in cui viene eseguiti dati dai gestori telefonici sconosciuti, provider e provider di servizi Internet. Il traffico di rete che viene inviato tramite ExpressRoute verrà inviato direttamente tramite rete dell'organizzazione partner ExpressRoute alla rete Microsoft. This allows customers to treat Office 365 as if it is located in their own off-site data center with a dedicated connection.
  
Azure ExpressRoute is available for all Office 365 licensing offerings. However, the Azure ExpressRoute Premium Add-on is required for Office 365 to enable global routing. Office 365 customers with at least 500 seats who are implementing ExpressRoute can get the required *ExpressRoute Premium Add-on* at no additional expense.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute necessari per la qualità multimediale ottimale?

ExpressRoute Azure non è un requisito per la visualizzazione Skype ottimale per la qualità multimediale Business Online. È tuttavia, uno della distribuzione di opzioni che consentono di assicurano che la connettività del cloud soddisfi Skype per gli obiettivi di prestazioni rete aziendale o soglie.
  
Office 365 is a high performance and secure service that uses the Internet. È continuano a investire in nuove funzionalità di sicurezza e regionali nodi Edge per continuare a migliorare le prestazioni e protezione. ExpressRoute Azure non è un requisito per servizi di Office 365 inclusi Skype Business online. ExpressRoute Azure è una distribuzione di opzioni disponibili che verranno consentono di assicurarsi che la connettività a Office 365 soddisfi Skype per requisiti di prestazioni di rete aziendali e garantisce Skype ottimale per la qualità multimediale Business Online esperienza.
  
Per Skype per la qualità multimediale in linea aziendale, è importante che la connessione tra i siti della società e i bordi di rete Microsoft soddisfi gli obiettivi di prestazioni in requisiti [le prestazioni della rete da Skype per client Business alla rete di Microsoft Bordo](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) e che la connessione tra i bordi di rete e i bordi di rete Microsoft soddisfi gli obiettivi di prestazioni in [requisiti relativi alle prestazioni di rete dalla rete perimetrale per Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
È inoltre importante che la connettività di rete fisica dell'azienda, tra cui la capacità di connettività di rete e cloud interna supportare il volume del traffico multimediale picco. Azure ExpressRoute is one of many ways that will help customers ensure their Skype for Business Online cloud connectivity meets all of these performance requirements.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>Is ExpressRoute required for voice quality SLA?

No, ExpressRoute non è obbligatorio per Skype per Business Online vocale qualità contratto di servizio. [Skype per SLA di qualità vocale Online Business](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) si applica a qualsiasi chiamata idoneo effettuata da qualsiasi Skype per utente del servizio vocale aziendale Online all'interno della licenza corretta e sottoscrizione che consente all'utente di effettuare qualsiasi tipo di chiamata VoIP o PSTN. Deve includere un contratto di servizio di qualità vocale che si basano tutte le condizioni seguenti:
  
- Le chiamate provenienti da Microsoft certified telefoni IP.
    
- Connessioni Ethernet cablate.
    
- Voice quality issues due to Microsoft Network problems.
    
> [!NOTE]
> The voice quality SLA excludes those calls where the low call quality is caused by problems in non-Microsoft networks including ExpressRoute partner and other networks. 
  
### <a name="internet-or-azure-expressroute"></a>Internet o ExpressRoute Azure?

Prima di prendere una decisione sulla rete opzioni di integrazione applicativa per Skype Business online, è necessario valutare i clienti corrente in base ai requisiti di prestazioni di rete descritti in requisiti relativi alle prestazioni di rete [per la connettività Internet e della rete connettersi a Skype Business online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se le prestazioni della rete con la connessione Internet corrente viene impostata per una capacità sufficiente durante periodi di picco e che soddisfi i requisiti di prestazioni di rete da siti ai bordi di rete di Microsoft e verso i bordi di rete ai bordi di rete di Microsoft, è possibile continuare a utilizzare la connettività Internet esistente a cui connettersi Skype Business online.
  
Società nei siti di cui non sono stati soddisfatti i requisiti di prestazioni rete, è consigliabile innanzitutto collaborare con i provider di servizi di rete esistente per migliorare le prestazioni complessive della rete. Tuttavia, se che non sono ancora vengono soddisfatti, utilizzando Azure ExpressRoute possibile evitare che il Skype per la connettività cloud Business Online consentono di soddisfare i requisiti di prestazioni di rete.
  
ExpressRoute Azure sono disponibili ulteriori vantaggi seguenti:
  
- Un contratto di servizio (SLA) sulla disponibilità della connessione tra la rete e Microsoft network. ExpressRoute dispone di un contratto di servizio garantito disponibilità del 99,9%.
    
- Pianificati e garantito larghezza di banda necessaria per servizi di Office 365. È possibile ottenere questo risultato inviando solo il traffico di Office 365 o Skype per il traffico Business utilizzando il ExpressRoute e quindi dispone tutte le altre Internet passare il traffico tra i punti di ingresso/uscita altri Internet per la rete.
    
- ExpressRoute è progettato per mantenere il contrassegno DSCP QoS contrassegni tra la rete e Microsoft Network.
    
Per ulteriori informazioni sulla pianificazione della capacità ed ExpressRoute QoS, fare riferimento a [ExpressRoute e QoS in Skype Business online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Can I setup Azure ExpressRoute for Skype for Business Online Only?

Yes, you can set up Azure ExpressRoute to ensure excellent network connectivity from your company's network to only Skype for Business Online. This will provide the most optimal Real-Time media quality for your users but you can then continue connecting to other Office 365 services over the Internet.
  
The Border Gateway Protocol (BGP) is a routing protocol on the Internet that is used to route network traffic across the Internet. It is designed to exchange routing information between autonomous systems (AS) found across the Internet. I valori delle community BGP sono tag di attributi che possono essere applicati alle route in ingresso o in uscita. Le community BGP vengono spesso utilizzate per segnalare la ricezione come i collegamenti in uscita da utilizzare per raggiungere una destinazione specificata in base geography, tipo di servizio o altri criteri.
  
Con il supporto per le community BGP, Microsoft verrà contrassegnare con i valori di community BGP appropriati basati sul servizio che a cui appartengono i prefissi e route. Microsoft verrà contrassegnare i prefissi annunciati tramite peering pubblici e Microsoft peering con i valori di community BGP appropriati che indica l'area a cui sono ospitati nei prefissi. È possibile utilizzare i valori di community per prendere le decisioni di routing appropriate per offrire il routing ottimale. È possibile utilizzare il Skype per valore community BGP Online Business per l'installazione di una connessione ExpressRoute solo per Skype Business online. You can find out more at [ExpressRoute routing requirements](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>ExpressRoute connectivity scenarios for Skype for Business Online
<a name="bkNetworkPerf"> </a>

If you have decided that ExpressRoute based on recommendations above is for you, here are the recommendations on where and how many ExpressRoute connections you should get.
  
### <a name="online-only-deployment---single-site"></a>Online only deployment - Single site

If all of your users use the Skype for Business Online service, and if your offices are centered around a single physical location and you decide to deploy Azure ExpressRoute, you should set up single ExpressRoute connection between your company site to the closest [ExpressRoute peering location](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
The following graphic shows an example of this type of deployment. For this example, Contoso is a university located in Orlando, FL. 10.000 docenti e studenti contoso. I test Internet dal relativo percorso ai siti edge Microsoft hanno dimostrato maggiori di 5% la perdita di pacchetti durante le ore di punta classe. Di avere deciso ottenere una connessione dedicata a Office 365 utilizzando ExpressRoute con larghezza di banda si verifichi il provisioning per poter evitare di congestione della rete per Office 365 in particolare per Skype per il traffico in tempo reale in linea aziendale. Si connettono al cloud Microsoft tramite ExpressRoute nel sito di Atlanta, GA MeetMe.
  
![Sito singolo ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Online only deployment - Multiple sites on the same continent

If your company is using Skype for Business Online services from multiple offices in the same region or continent, and you chose to implement Azure ExpressRoute, it is recommended to connect your main site via ExpressRoute, and then optionally add additional ExpressRoute peering for other locations that do not meet the recommended network performance targets.
  
In the following example, Contoso is an US travel services company that is headquartered in New York but has other offices across the United States. Their offices are inter-connected through an WAN that uses MPLS for connecting to Office 365. They initially set up an ExpressRoute connection from their Internet router in Hoboken, New Jersey to the New York MeetMe site. 
  
With this setup, network traffic from most of their sites to the Microsoft Network (New York Edge site) can meet the Skype for Business client connection network performance targets described in [Network Performance requirements from a Skype for Business client to Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). However, latency between Contoso's west coast offices to New York is going over 50ms one-way. In addition, Honolulu is the second largest office for Contoso, latency from Honolulu to New York exceeds 80ms one-way. To ensure good media quality for users in those offices, Contoso decided to add a west coast ExpressRoute connection between their San Jose site and the Silicon Valley ExpressRoute MeetMe site.
  
![Esprimere Router più siti su continente stesso.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Distribuzione sola online - più siti in continenti diversi

Se tutti gli utenti utilizzano Skype per servizio Business Online e delle sedi sono in più posizioni fisiche tra più continenti, se si decide di distribuire ExpressRoute Azure, è consigliabile impostare almeno una connessione ExpressRoute per ogni continente tra siti principale di ogni continente il più vicino [ExpressRoute peering posizione](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). A seconda dei costi e benefici, è possibile distribuire le connessioni ExpressRoute dai siti di cui non sono soddisfatta gli obiettivi di prestazioni di rete.
  
Nell'esempio seguente, Contoso è un'azienda di grandi dimensioni legale aziendale con uffici a città principali in Nord America ed Europa. In base alle loro connessione Internet e la valutazione delle prestazioni di rete interna, Contoso ha deciso di distribuire due connessioni ExpressRoute in Nord America e un singolo ExpressRoute a commutazione di circuito per tutti i suoi uffici European.
  
![ExpressRoute con più siti e continenti.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Distribuzione ibrida

Se si dispone di un Lync in locale o Skype per la distribuzione di Business e sceglie di implementare un ambiente ibrido Skype per l'integrazione di Business in linea, è consigliabile che se si decide di distribuire ExpressRoute Azure, è necessario disporre di almeno una connessione ExpressRoute per ogni locale con Lync o Skype per sito Business Edge e almeno una connessione ExpressRoute per ogni continente con uffici. A seconda dei costi e benefici, per ogni continente è possibile distribuire le connessioni ExpressRoute da uffici dove gli obiettivi di prestazioni di rete non sono soddisfatte.
  
If you have an on-premises Skype for Business deployment, you must follow the [Edge Server Planning and Deployment Guide](https://technet.microsoft.com/en-us/library/mt346417.aspx). Specifically, the Edge servers must be reachable from outside of your network. This is usually achieved either by assigning a routable public IP address to the Edge server, or by using network address translation (NAT).
  
In the following example, Contoso has an existing on-premises Skype for Business Enterprise Voice deployment. They want to migrate on-premises users to Office 365 online services. They also decided to use a hybrid deployment so that they can continue to use their existing PSTN infrastructure for all on-premises and online users. Contoso's on-premises data center and Skype for Business Edge Servers are in Chicago. For their deployment, Contoso decided to set up one ExpressRoute connection between their Chicago data center and the Chicago ExpressRoute. They also added a west coast ExpressRoute connection to better serve their Honolulu office.
  
![ExpressRoute ibrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Distribuzione in linea con Cloud connettore Edition

Skype per Business Online Cloud connettore Edition è che offrono un ambiente ibrido costituita da un insieme di largo macchine () che implementano la connettività PSTN in locale. Distribuendo un Skype minimo per la topologia Server aziendale in un ambiente virtualizzato, sarà in grado di inviare e ricevere chiamate con landlines e telefoni cellulari tramite l'infrastruttura vocale PSTN locale esistente.
  
Se si decide di distribuire ExpressRoute Azure e Cloud connettore Edition, è consigliabile consente di configurare almeno una connessione Express Route per ogni continente tra sito principale di ogni continente collaboratori più stretti [ExpressRoute peering posizione](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Depending on cost vs benefit, for each continent you can choose to deploy additional ExpressRoute connections from sites where network performance targets aren't being met.
  
If you have an on-premises Skype for Business deployment, you must follow the [Planning Guide for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Specifically, the Access Edge and A/V Edge services should be assigned public IP addresses and reachable from Office 365 data centers.
  
In the following example, Contoso is a European accounting firm with presence in a few major European countries and cities. When they sign up for Skype for Business Online for all their collaboration needs, they decided to put a Cloud Connector for each country they have a physical location to continue to use their PSTN infrastructure and carrier contracts that already exist. Based on their testing from all their sites and Microsoft network Edge, they determined that a single ExpressRoute connection in London will help meet the Skype for Business client connection network performance targets described in [Network Performance requirements from a Skype for Business client to Microsoft network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Below is another deployment option for Contoso. In this case, they decided to set up an ExpressRoute connection at each site where a Cloud Connector is deployed. 
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>See also

[ExpressRoute e QoS in Skype for Business online](expressroute-and-qos-in-skype-for-business-online.md)

