---
title: Tabella SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable contiene un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici. Questi codici vengono generati in risposta agli eventi che interessano i dispositivi SIP e le sessioni di comunicazione SIP; ad esempio, il codice di risposta 403 viene generato quando un dispositivo SIP effettua una richiesta, ma il server rifiuta di onorare la richiesta.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194740"
---
# <a name="sipresponsemetadata-table"></a>Tabella SIPResponseMetaData
 
SIPResponseMetaDataTable contiene un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici. Questi codici vengono generati in risposta agli eventi che interessano i dispositivi SIP e le sessioni di comunicazione SIP; ad esempio, il codice di risposta 403 viene generato quando un dispositivo SIP effettua una richiesta, ma il server rifiuta di onorare la richiesta.
  
Questa tabella è stata introdotta in Skype for Business Server 2015.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Principale  <br/> |Valore numerico che rappresenta il codice di risposta SIP.  <br/> |
|**Classe** <br/> |int  <br/> || Classificazione generale per il codice di risposta. Le classificazioni includono: <br/>  1-risposte informative <br/>  2-risposte di successo <br/>  3-risposte di Reindirizzamento <br/>  4-risposte di errore client <br/>  5--risposte di errore del server <br/>  6-risposta di errore globale <br/> |
|**Descrizione** <br/> |nvarchar (256)  <br/> ||Descrizione del codice di risposta SIP. Ad esempio, il codice di risposta 181 ha la seguente descrizione:  <br/> Chiamata inoltrata  <br/> |
   

