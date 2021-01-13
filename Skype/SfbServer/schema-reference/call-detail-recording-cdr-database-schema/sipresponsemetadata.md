---
title: Tabella SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809926"
---
# <a name="sipresponsemetadata-table"></a>Tabella SIPResponseMetaData
 
Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.
  
Questa tabella è stata introdotta in Skype for Business Server 2015.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Principale  <br/> |Valore numerico che rappresenta il codice di risposta SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classifica generale del codice di risposta. Sono incluse le classifiche seguenti: <br/>  1-risposte informative <br/>  2-risposte con esito positivo <br/>  3-risposte di Reindirizzamento <br/>  4-risposte di errore client <br/>  5-risposte di errore del server <br/>  6-risposta di errore globale <br/> |
|**Descrizione** <br/> |nvarchar (256)  <br/> ||Descrizione del codice di risposta SIP. Il codice di risposta 181 ad esempio è associato alla descrizione seguente:  <br/> Call Is Being Forwarded  <br/> |
   

