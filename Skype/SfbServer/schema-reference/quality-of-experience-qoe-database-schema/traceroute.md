---
title: Tabella TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabella TraceRoute contiene le informazioni di routing dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805114"
---
# <a name="traceroute-table"></a>Tabella TraceRoute
 
La tabella TraceRoute contiene le informazioni di routing dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Data e ora di inizio della chiamata.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Identificatore univoco usato per distinguere tra più chiamate che potrebbero essere iniziate nella stessa data e contemporaneamente.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaria, straniera  <br/> |Rappresenta il tipo di linea video usato nella chiamata. I valori consentiti sono:  <br/> 0-audio  <br/> 1-video  <br/> 2-video panoramico  <br/> 3-condivisione di applicazioni/desktop  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |Endpoint che ha posto la chiamata.  <br/> |
|**Hop** <br/> |int  <br/> ||Hop di rete/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Esterna  <br/> |Identificatore univoco per l'indirizzo IP. Le informazioni sull'indirizzo IP sono archiviate nella [tabella IPAddress](ipaddress.md).  <br/> |
|**RTT** <br/> |int  <br/> ||Ora di andata e ritorno. Il tempo di andata e ritorno misura la quantità di tempo necessaria per il pacchetto vocale per raggiungere la destinazione e quindi inviare di nuovo la notifica che è stata ricevuta.  <br/> |
   

