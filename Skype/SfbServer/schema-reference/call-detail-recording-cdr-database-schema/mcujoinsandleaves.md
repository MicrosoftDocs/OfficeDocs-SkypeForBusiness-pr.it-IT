---
title: Tabella McuJoinsAndLeaves in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Ogni record in questa tabella contiene i dettagli delle chiamate su una combinazione di un utente che partecipa o abbandona e Conferencing Server. Ad esempio, se un utente partecipa a una conferenza che include Web Conferencing e audio/video Elements, verrà creato un record per il Web Conferencing di tale utente e verrà creato un altro record per la partecipazione a conferenze audio/video dell'utente.
ms.openlocfilehash: 7eb2e8bccafcbd585c66cb77f2ba18a96c842d60
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815084"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabella McuJoinsAndLeaves in Skype for Business Server 2015
 
Ogni record in questa tabella contiene i dettagli delle chiamate su una combinazione di un utente che partecipa o abbandona e Conferencing Server. Ad esempio, se un utente partecipa a una conferenza che include Web Conferencing e audio/video Elements, verrà creato un record per il Web Conferencing di tale utente e verrà creato un altro record per la partecipazione a conferenze audio/video dell'utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora dell'istanza di conferenza. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare l'istanza di conferenza. Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero univoco che identifica questo utente. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**McuUserInstance** <br/> |int  <br/> |Principale  <br/> |Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, McuUserInstance identifica in modo univoco la combinazione utente/dispositivo.  <br/> |
|**IsFromPstn** <br/> |po'  <br/> | <br/> |Se l'utente partecipa da una rete PSTN o meno.  <br/> |
|**McuId** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero univoco che identifica questo server di conferenza. Per altre informazioni, vedere la [tabella MCU in Skype for Business Server 2015](mcus.md) . <br/> |
|**DialogSessionIdTime** <br/> |DateTime  <br/> |Esterna  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Esterna  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserJoinTime** <br/> |DateTime  <br/> | <br/> |L'ora in cui l'utente partecipa a questo server di conferenza.  <br/> |
|**UserLeaveTime** <br/> |DateTime  <br/> | <br/> |L'ora in cui l'utente lascia questo server di conferenza.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Esterna  <br/> |Identificatore che specifica il numero di versione dell'uso del software client nella conferenza. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

