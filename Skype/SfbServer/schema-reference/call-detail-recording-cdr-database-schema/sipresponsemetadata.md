---
title: Tabella SIPResponseMetaData
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.
ms.openlocfilehash: acf2c3166628af3a4633e98713ca25a5ae703ff6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863393"
---
# <a name="sipresponsemetadata-table"></a>Tabella SIPResponseMetaData
 
Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.
  
Questa tabella è stata introdotta Skype for Business Server 2015.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Principale  <br/> |Valore numerico che rappresenta il codice di risposta SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classifica generale del codice di risposta. Sono incluse le classifiche seguenti: <br/>  1 - Risposte in informazioni <br/>  2 - Risposte riuscite <br/>  3 - Risposte di reindirizzamento <br/>  4 - Risposte di errore client <br/>  5 - Risposte di errore del server <br/>  6 - Risposta di errore globale <br/> |
|**Descrizione** <br/> |nvarchar(256)  <br/> ||Descrizione del codice di risposta SIP. Il codice di risposta 181 ad esempio è associato alla descrizione seguente:  <br/> Call Is Being Forwarded  <br/> |
   

