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
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabella TraceRoute contiene le informazioni di routing dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194575"
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
   

