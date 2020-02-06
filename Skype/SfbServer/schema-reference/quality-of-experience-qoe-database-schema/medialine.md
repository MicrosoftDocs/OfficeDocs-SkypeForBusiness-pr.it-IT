---
title: Visualizzazione MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La Visualizzazione MediaLine archivia le informazioni su ogni riga multimediale nel database. Una sessione audio in genere contiene una linea media audio. Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video; Tuttavia, la sessione può contenere due linee multimediali video se viene usato un dispositivo per i servizi di conferenza o se viene usata la visualizzazione raccolta. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: b22408ddc40f1df6452895327e8a67800ef24eb9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808194"
---
# <a name="medialine-view"></a>Visualizzazione MediaLine
 
La Visualizzazione MediaLine archivia le informazioni su ogni riga multimediale nel database. Una sessione audio in genere contiene una linea media audio. Una sessione audio e video (A/V) in genere contiene una linea media audio e una linea media video; Tuttavia, la sessione può contenere due linee multimediali video se viene usato un dispositivo per i servizi di conferenza o se viene usata la visualizzazione raccolta. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateTime  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.  <br/> |
|Sicurezza  <br/> |tinyint  <br/> |Profilo di sicurezza in uso. 0 è NONE, 1 è SRTP, 2 è V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo di trasporto. 0 è UDP, 1 è TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |po'  <br/> |Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 indica che il chiamante si trova all'interno della rete aziendale. 0 indica che il chiamante si trova all'esterno della rete.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |Indirizzo MAC dell'interfaccia di rete usata dal chiamante.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usata nel servizio A/V Edge usato dal chiamante.  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del chiamante segnalato dal servizio A/V Edge. Questo indirizzo può essere diverso da quello di CallerIPAddr se il client si trova dietro a un NAT, ad esempio.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Descrizione del driver WiFi del chiamante.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |Versione del driver WiFi del chiamante.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Dettagli della connessione di rete del chiamante. Per altre informazioni, vedere la [tabella NetworkConnectionDetail](networkconnectiondetail.md) . <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |ID set di servizi di base usato dalla connessione WiFi dei chiamanti.  <br/> |
|CallerVPN  <br/> |po'  <br/> |Indica se il chiamante è connesso tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del destinatario. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal chiamato.  <br/> |
|CalleeInside  <br/> |po'  <br/> |Indica se il chiamato si trova all'interno della rete aziendale. 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il chiamato è all'esterno della rete.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |Indirizzo MAC dell'interfaccia di rete usata dal chiamato.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del servizio A/V Edge usato dal destinatario. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usata nel servizio A/V Edge usato dal chiamato.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del destinatario segnalato dal servizio A/V Edge. Questo indirizzo può essere diverso da quello di CalleeIPAddr se il client si trova dietro a un NAT, ad esempio.  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |Nome del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del destinatario.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del destinatario.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del destinatario.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |Descrizione del driver WiFi del chiamato.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Versione del driver WiFi del chiamato.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Dettagli della connessione di rete del chiamato. Per altre informazioni, vedere la [tabella NetworkConnectionDetail](networkconnectiondetail.md) . <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |Identificatore del set di servizi di base usato dalla connessione Wi-Fi del chiamato.  <br/> |
|CalleeVPN  <br/> |po'  <br/> |Indica se il chiamato è connesso tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|ConversationalMOS  <br/> |decimale (3; 2)  <br/> |Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Questa è la larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base a varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, in quanto la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |Origine del limite di larghezza di banda imposto. Descrive la posizione in cui proviene il limite di larghezza di banda, ad esempio "Policy Server", "TURN server" o "modality".  <br/> |
|Chiamante  <br/> |po'  <br/> |Indica se sono state ricevute metriche dal chiamante; 1 è sì, 0 è no.  <br/> |
|Chiamato  <br/> |po'  <br/> |Indica se le metriche del destinatario della chiamata sono state ricevute; 1 è sì, 0 è no.  <br/> |
|MidCallReport  <br/> |po'  <br/> |Indica se il report è per una parte della chiamata o per la chiamata completa.  <br/> |
|ClassifiedPoorCall  <br/> |po'  <br/> |Indica se una chiamata è stata classificata come chiamata scadente (1) o come buona chiamata (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica se il chiamante è connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica se l'utente ha chiamato connesso alla rete usando il protocollo ICE (Internet Connectivity Establishment).  <br/> |
   

