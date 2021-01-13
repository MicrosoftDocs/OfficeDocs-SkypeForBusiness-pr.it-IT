---
title: Tabella TraceRoute
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Nella tabella TraceRoute sono incluse le informazioni di routing provenienti dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831326"
---
# <a name="traceroute-table"></a>Tabella TraceRoute
 
Nella tabella TraceRoute sono incluse le informazioni di routing provenienti dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Identificatore univoco utilizzato per distinguere le diverse chiamate che possono essere iniziate nella stessa data e alla stessa ora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaria, esterna  <br/> |Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:  <br/> 0-audio  <br/> 1-video  <br/> 2-Panoramica video  <br/> 3-condivisione di applicazioni/desktop  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |Endpoint che ha effettuato la chiamata.  <br/> |
|**Hop** <br/> |int  <br/> ||Hop di rete.  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Stranieri  <br/> |Identificatore univoco dell'indirizzo IP. Le informazioni sull'indirizzo IP sono archiviate nella [tabella IPAddress](ipaddress.md).  <br/> |
|**RTT** <br/> |int  <br/> ||Tempo di roundtrip, ovvero la quantità di tempo necessaria a un pacchetto voce per raggiungere la relativa destinazione e quindi inviare di nuovo la notifica ricevuta.  <br/> |
   

