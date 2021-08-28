---
title: Visualizzazione MediaLine
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: Nella visualizzazione MediaLine vengono archiviate informazioni su ogni linea multimediale nel database. Una sessione audio in genere contiene una linea multimediale audio. Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 778e322f737a80c71a046073611c234071e3f24b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582570"
---
# <a name="medialine-view"></a>Visualizzazione MediaLine
 
Nella visualizzazione MediaLine vengono archiviate informazioni su ogni linea multimediale nel database. Una sessione audio in genere contiene una linea multimediale audio. Una sessione audio e video (A/V) in genere contiene una linea multimediale audio e una video; la sessione, tuttavia, contiene due linee multimediali video se si utilizza un dispositivo per conferenze o la visualizzazione Raccolta. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**dettagli**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la Specifica del protocollo Quality of Experience Monitoring Server.  <br/> |
|Sicurezza  <br/> |tinyint  <br/> |Profilo di sicurezza in uso. 0 per NESSUNA, 1 per SRTP, 2 per V1.  <br/> |
|Trasporto  <br/> |tinyint  <br/> |Tipo di trasporto. 0 per UDP, 1 per TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se il chiamante si trova nella rete dell'organizzazione. 1 significa che il chiamante è all'interno della rete dell'organizzazione. 0 significa che il chiamante è all'esterno della rete dell'organizzazione.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Indirizzo MAC dell'interfaccia di rete utilizzata dal chiamante.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori informazioni, vedere la tabella [IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del chiamante riportato dal servizio A/V Edge. Questo indirizzo può essere diverso rispetto al CallerIPAddr se il client si trova dietro un sistema NAT, ad esempio.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256  <br/> |Descrizione del driver Wifi del chiamante.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Versione del driver WiFi del chiamante.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Dettagli della connessione di rete del chiamante. Per ulteriori informazioni, vedere la [tabella NetworkConnectionDetail.](networkconnectiondetail.md) <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |BSSI (Basic Service Set Identifier) utilizzato dalla connessione WiFi del chiamante.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se il chiamante ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del destinatario della chiamata. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal destinatario della chiamata.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se il destinatario della chiamata si trova all'interno della rete aziendale. 1 indica che il destinatario della chiamata è all'interno della rete aziendale, mentre 0 indica che è all'esterno della rete.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Indirizzo MAC dell'interfaccia di rete utilizzata dal destinatario della chiamata.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori informazioni, vedere la tabella [IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del destinatario della chiamata riportato dal servizio A/V Edge. Questo indirizzo può essere diverso rispetto al CalleeIPAddr se il client si trova dietro un sistema NAT, ad esempio.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nome del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di rendering del chiamato.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di rendering del chiamato.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Descrizione del driver Wifi del chiamato.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256  <br/> |Versione del driver WiFi del chiamato.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Dettagli della connessione di rete del chiamato. Per ulteriori informazioni, vedere la [tabella NetworkConnectionDetail.](networkconnectiondetail.md) <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Identificatore del set di servizi di base utilizzato dalla connessione WiFi del chiamato.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se il destinatario della chiamata ha eseguito la connessione su una rete privata virtuale. 1 indica una VPN, 0 indica una rete non VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Questa è la larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Origine del limite della larghezza di banda imposto. Descrive da dove proviene il limite di larghezza di banda (ad esempio, "Policy Server", "TURN Server" o "Modality").  <br/> |
|Chiamante  <br/> |bit  <br/> |Indica se è stata ricevuta la metrica del chiamante. 1 indica sì e 0 indica no.  <br/> |
|Chiamato  <br/> |bit  <br/> |Indica se è stata ricevuta la metrica del destinatario della chiamata. 1 indica sì e 0 indica no.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica se il report riguarda una parte della chiamata o l'intera chiamata.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica se una chiamata è stata classificata come di livello insufficiente (1) o buono (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica se il chiamante ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica se il destinatario della chiamata ha eseguito la connessione alla rete utilizzando il protocollo ICE (Internet Connectivity Establishment).  <br/> |
   

