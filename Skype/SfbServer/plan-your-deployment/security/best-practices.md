---
title: Procedure consigliate per l'infrastruttura principale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Probabilmente hai già adottato misure per progettare la tolleranza di errore nel sistema, usando procedure come la garanzia di ridondanza hardware, la protezione contro la perdita di corrente, l'installazione di routine degli aggiornamenti della sicurezza e delle misure antivirus e il monitoraggio delle attività del server. Queste procedure non sono utili solo per l'infrastruttura di Skype for Business Server, ma anche per l'intera rete. Se non sono state implementate queste procedure, è consigliabile eseguire questa operazione prima di distribuire Skype for Business Server.
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815684"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Procedure consigliate per l'infrastruttura principale in Skype for Business Server
 
Probabilmente hai già adottato misure per progettare la tolleranza di errore nel sistema, usando procedure come la garanzia di ridondanza hardware, la protezione contro la perdita di corrente, l'installazione di routine degli aggiornamenti della sicurezza e delle misure antivirus e il monitoraggio delle attività del server. Queste procedure non sono utili solo per l'infrastruttura di Skype for Business Server, ma anche per l'intera rete. Se non sono state implementate queste procedure, è consigliabile eseguire questa operazione prima di distribuire Skype for Business Server.
  
Per proteggere i server della distribuzione di Skype for Business Server da danni accidentali o mirati che potrebbero causare tempi di inattività, seguire le seguenti precauzioni:
  
- Aggiornare i server con gli aggiornamenti della sicurezza. La sottoscrizione al servizio di notifica della sicurezza Microsoft consente di ricevere una notifica immediata dei rilasci del Bollettino della sicurezza per qualsiasi prodotto Microsoft. Per eseguire la sottoscrizione, visitare il [sito Web Microsoft Technical Security Notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Verificare che i diritti di accesso siano configurati correttamente.
    
- Conservare i server in un ambiente fisico che impedisce l'accesso non autorizzato. Verificare che in tutti i server sia installato un software antivirus adeguato. Tieni aggiornato il software con i file di firma del virus più recenti. Usa la funzionalità di aggiornamento automatico dell'applicazione antivirus per conservare le firme del virus aggiornate.
    
- È consigliabile disabilitare i servizi di sistema operativo Windows Server che non sono necessari nei computer in cui si installa Skype for Business Server.
    
- Crittografare sistemi operativi e unità disco in cui i dati vengono archiviati con un sistema di crittografia completo, a meno che non sia possibile garantire il controllo costante e completo dei server, il totale isolamento fisico e la disattivazione corretta e sicura del disco sostituito o non riuscito unità.
    
- Disabilitare tutte le porte di accesso diretto alla memoria esterna (DMA) del server, a meno che non sia possibile garantire un controllo molto limitato sull'accesso fisico ai server. Gli attacchi basati su DMA, che possono essere avviati abbastanza facilmente, potrebbero esporre informazioni molto riservate, come le chiavi di crittografia private.
    

