---
title: Tabella MediaLine
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 'Ogni record rappresenta una linea multimediale. Una sessione audio contiene in genere una linea multimediale audio. Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una linea multimediale video, anche se la sessione potrebbe contenere due linee multimediali video se viene utilizzato un dispositivo per conferenze o se viene utilizzata la visualizzazione Raccolta.'
---

# <a name="medialine-table"></a>Tabella MediaLine
 
Ogni record rappresenta una linea multimediale. Una sessione audio contiene in genere una linea multimediale audio. Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una linea multimediale video, anche se la sessione potrebbe contenere due linee multimediali video se viene utilizzato un dispositivo per conferenze o se viene utilizzata la visualizzazione Raccolta.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella Session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [tabella Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |0 è l'audio principale, 1 è il video principale e 2 è il video panoramico, 3 è Condivisione applicazioni/desktop, 16 è Condivisione schermo basata su video (VbSS). Questa etichetta deve essere univoca all'interno di una singola sessione.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Questa colonna è presente ma non utilizzata in Microsoft Lync Server 2013. Le informazioni sulla connettività utilizzata per una linea multimediale vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritte in flag di bit. Per informazioni dettagliate, vedere  *Quality of Experience Monitoring Server Protocol Specification*  , disponibile per il download. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Uguale a CallerIceWarningFlags, ma sul lato del chiamato. Per informazioni dettagliate, vedere  *Quality of Experience Monitoring Server Protocol Specification*  , disponibile per il download. <br/> |
|**Sicurezza** <br/> |tinyint  <br/> | <br/> |Profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.  <br/> |
|**Trasporto** <br/> |tinyint  <br/> | <br/> |0 per UDP, 1 per TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Foreign  <br/> |Indirizzo IP del chiamante. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Porta utilizzata dal chiamante. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Foreign <br/> |Subnet del chiamante. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Foreign  <br/> |Indirizzo Mac del chiamante, a cui viene fatto riferimento [dalla tabella MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Porta utilizzata nel servizio A/V Edge dal chiamante.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Foreign  <br/> |Dispositivo di acquisizione utilizzato dal chiamante. Riferimento dalla [tabella Device](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Foreign  <br/> |Dispositivo di rendering utilizzato dal chiamante. Riferimento dalla [tabella Device](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla [tabella DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Foreign  <br/> |Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla [tabella DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Foreign  <br/> |Indica in che modo il chiamante si è connesso alla rete. I valori vengono ottenuti dalla [tabella NetworkConnectionDetail](networkconnectiondetail.md). I valori tipici sono 0 per una connessione cablata 1 per una connessione WiFi. e 3 per una connessione Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Foreign  <br/> |BSSID del chiamante se viene utilizzato wireless. Riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Collegamento del chiamante. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Foreign  <br/> |Indirizzo IP del destinatario della chiamata. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|**CalleePort** <br/> |bit  <br/> ||Porta utilizzata dal destinatario della chiamata.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Foreign  <br/> |Subnet del chiamato. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 indica che il destinatario della chiamata si trova all'interno della rete aziendale, 0 indica che il destinatario della chiamata si trova all'esterno della rete.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Foreign  <br/> |Indirizzo Mac destinatario chiamata. Riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Porta utilizzata nel servizio A/V Edge dal destinatario della chiamata.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |foreign  <br/> |Dispositivo di acquisizione utilizzato dal destinatario della chiamata. Riferimento dalla [tabella Device](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Foreign  <br/> |Dispositivo di rendering utilizzato dal destinatario della chiamata. Riferimento dalla [tabella Device](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |Driver per il dispositivo di acquisizione del destinatario della chiamata. Riferimento dalla [tabella DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Foreign  <br/> |Driver per il dispositivo di rendering del destinatario della chiamata. Riferimento dalla [tabella DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Foreign  <br/> |Indica il modo in cui il chiamato si è connesso alla rete. I valori vengono ottenuti dalla [tabella NetworkConnectionDetail](networkconnectiondetail.md). I valori tipici sono 0 per una connessione cablata 1 per una connessione WiFi. e 3 per una connessione Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Foreign  <br/> |BSSID del chiamato se viene utilizzato wireless. Riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Collegamento del destinatario della chiamata; 1 è rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Si tratta della larghezza di banda effettiva applicata al flusso sul lato di invio specificato in base a diverse impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Origine del limite della larghezza di banda imposto. Descrive da dove proviene il limite di larghezza di banda ("Policy Server", "TURN Server", "Modality" e così via). Riferimento dalla [tabella AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Chiamante** <br/> |bit  <br/> | <br/> |Indica se le metriche del chiamante sono state ricevute. 1 è sì, un valore null è no.  <br/> |
|**Chiamato** <br/> |bit  <br/> | <br/> |Indica se sono state ricevute metriche del destinatario della chiamata. 1 è sì, un valore null è no.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica se il report è per una parte della sessione o per l'intera sessione.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica se una chiamata è stata classificata come scarsa (valore 1) o come buona chiamata (0).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata. Nelle organizzazioni che utilizzano NAT (network address translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |Descrizione del dispositivo per il driver WiFi utilizzato dall'utente che ha effettuato la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |Numero di versione del driver WiFi utilizzato dall'utente che ha effettuato la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata. Nelle organizzazioni che utilizzano NAT (network address translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |Descrizione del dispositivo per il driver WiFi utilizzato dall'utente che ha ricevuto la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |Numero di versione del driver WiFi utilizzato dall'utente che ha ricevuto la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

