---
title: Tabella MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Ogni record rappresenta una linea media. (Una sessione audio in genere contiene una linea media audio. Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video, anche se la sessione può contenere due linee multimediali video se viene usato un dispositivo per conferenze o se viene usata la visualizzazione raccolta.
ms.openlocfilehash: 0c189a79a9d87e76ec48be1acb7b4062876b5b16
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808814"
---
# <a name="medialine-table"></a>Tabella MediaLine
 
Ogni record rappresenta una linea media. (Una sessione audio in genere contiene una linea media audio. Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video, anche se la sessione può contenere due linee multimediali video se viene usato un dispositivo per conferenze o se viene usata la visualizzazione raccolta.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [tabella di sessione](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui si fa riferimento dalla [tabella di sessione](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |0 è l'audio principale, 1 è il video principale e 2 è un video panoramico, 3 è la condivisione di applicazioni/desktop, 16 è la condivisione dello schermo basata su video (VbSS). Questa etichetta deve essere univoca all'interno di una singola sessione.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Questa colonna è presente ma non viene usata in Microsoft Lync Server 2013. Le informazioni sulla connettività usata per una linea media vengono acquisite nelle colonne CallerConnectivityICE e CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in flag di bit. Per informazioni dettagliate, vedere la sezione relativa alla *qualità della specifica di protocollo di monitoraggio delle esperienze* disponibile per il download. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Uguale a CallerIceWarningFlags, ma sul lato chiamato. Per informazioni dettagliate, vedere la sezione relativa alla *qualità della specifica di protocollo di monitoraggio delle esperienze* disponibile per il download. <br/> |
|**Sicurezza** <br/> |tinyint  <br/> | <br/> |Profilo di sicurezza in uso. 0 è NONE, 1 è SRTP, 2 è V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 è UDP, 1 è TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Esterna  <br/> |Indirizzo IP del chiamante. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Porta utilizzata dal chiamante. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Esterna <br/> |Subnet del chiamante. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|**CallerInside** <br/> |po'  <br/> | <br/> |1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Esterna  <br/> |Indirizzo MAC del chiamante, a cui si fa riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Esterna  <br/> |Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Porta usata nel servizio A/V Edge dal chiamante.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Esterna  <br/> |Dispositivo di acquisizione usato dal chiamante. A cui si fa riferimento dalla [tabella Device](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Esterna  <br/> |Dispositivo di rendering usato dal chiamante. A cui si fa riferimento dalla [tabella Device](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Esterna  <br/> |Driver per il dispositivo di acquisizione del chiamante, a cui viene fatto riferimento dalla [tabella QRTDDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Esterna  <br/> |Driver per il dispositivo di rendering del chiamante, a cui viene fatto riferimento dalla [tabella QRTDDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Esterna  <br/> |Indica il modo in cui il chiamante si connette alla rete. I valori vengono ottenuti dalla [tabella NetworkConnectionDetail](networkconnectiondetail.md). I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Esterna  <br/> |BSSID del chiamante se viene usato wireless. A cui si fa riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |po'  <br/> ||Collegamento del chiamante. 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimale (18; 0)  <br/> ||Velocità di collegamento di rete, in bps, per l'endpoint del chiamante.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Esterna  <br/> |Indirizzo IP del destinatario della chiamata. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|**CalleePort** <br/> |po'  <br/> ||Porta usata dal destinatario della chiamata.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Esterna  <br/> |Subnet del chiamato. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|**CalleeInside** <br/> |po'  <br/> | <br/> |1 indica che il destinatario della chiamata si trova all'interno della rete aziendale, 0 indica che il destinatario della chiamata si trova all'esterno della rete.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Esterna  <br/> |Indirizzo MAC del destinatario. A cui si fa riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Esterna  <br/> |Indirizzo IP del servizio A/V Edge usato dal destinatario della chiamata. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Porta usata nel servizio A/V Edge dal destinatario della chiamata.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |esterna  <br/> |Dispositivo di acquisizione usato dal destinatario della chiamata. A cui si fa riferimento dalla [tabella Device](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Esterna  <br/> |Dispositivo di rendering usato dal destinatario della chiamata. A cui si fa riferimento dalla [tabella Device](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Esterna  <br/> |Driver per il dispositivo di acquisizione del destinatario della chiamata. A cui si fa riferimento dalla [tabella QRTDDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Esterna  <br/> |Driver per il dispositivo di rendering del destinatario della chiamata. A cui si fa riferimento dalla [tabella QRTDDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Esterna  <br/> |Indica il modo in cui il chiamato si connette alla rete. I valori vengono ottenuti dalla [tabella NetworkConnectionDetail](networkconnectiondetail.md). I valori tipici sono 0 per una connessione cablata ' 1 per una connessione WiFi; e 3 per una connessione Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Esterna  <br/> |BSSID di chiamata se viene usato wireless. A cui si fa riferimento dalla [tabella MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |po'  <br/> | <br/> |Collegamento del destinatario della chiamata; 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimale (18; 0)  <br/> | <br/> |Velocità di collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.  <br/> |
|**ConversationalMOS** <br/> |decimale (3; 2)  <br/> | <br/> |Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Si tratta della larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Questa è l'origine del limite di larghezza di banda imposto. Descrive la posizione del limite di larghezza di banda ("Policy Server", "TURN server", "modality" e così via). A cui si fa riferimento dalla [tabella AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Chiamante** <br/> |po'  <br/> | <br/> |Indica se sono state ricevute metriche dal chiamante; 1 è sì, un valore null è no.  <br/> |
|**Chiamato** <br/> |po'  <br/> | <br/> |Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, un valore null è no.  <br/> |
|**MidCallReport** <br/> |po'  <br/> ||Indica se il report è per una parte della sessione o per la sessione completa.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |po'  <br/> ||Indica se una chiamata è stata classificata come chiamata scadente (valore 1) o come buona chiamata (0).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Esterna  <br/> |Indirizzo IP riflessivo dell'utente che ha effettuato la chiamata. Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Esterna  <br/> |Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Esterna  <br/> |Numero di versione per il driver WiFi impiegato dall'utente che ha effettuato la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Esterna  <br/> |Indirizzo IP riflessivo dell'utente che ha ricevuto la chiamata. Nelle organizzazioni che usano NAT (Network Address Translation), l'indirizzo IP riflessivo è l'indirizzo IP del server proxy.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Esterna  <br/> |Descrizione del dispositivo per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Esterna  <br/> |Numero di versione per il driver WiFi impiegato dall'utente che ha ricevuto la chiamata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

