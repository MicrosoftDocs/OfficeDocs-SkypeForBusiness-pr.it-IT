---
title: Tabella McuJoinsAndLeaves in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una combinazione di un utente che partecipa o lascia e Conferencing Server. Ad esempio, se un utente si unisce a una conferenza che include Web Conferencing e elementi audio/video, verrà creato un record per l'aggiunta di Web Conferencing per l'utente e verrà creato un altro record per l'aggiunta di conferenze audio/video dell'utente.
ms.openlocfilehash: 8c9e6cba970e113d119ab3ce894dee8d5b4f6b28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821496"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabella McuJoinsAndLeaves in Skype for Business Server 2015
 
Ogni record di questa tabella contiene i dettagli sulle chiamate relative a una combinazione di un utente che partecipa o lascia e Conferencing Server. Ad esempio, se un utente si unisce a una conferenza che include Web Conferencing e elementi audio/video, verrà creato un record per l'aggiunta di Web Conferencing per l'utente e verrà creato un altro record per l'aggiunta di conferenze audio/video dell'utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora dell'istanza di conferenza. Utilizzato insieme a **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare l'istanza di conferenza. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero univoco che identifica l'utente. Per ulteriori informazioni, vedere la [tabella users](users.md) . <br/> |
|**McuUserInstance** <br/> |int  <br/> |Principale  <br/> |Se un utente ha effettuato l'accesso contemporaneamente a più computer o dispositivi, McuUserInstance identifica in modo univoco la combinazione utente/dispositivo.  <br/> |
|**IsFromPstn** <br/> |po'  <br/> | <br/> |Se l'utente partecipa da una rete PSTN o meno.  <br/> |
|**McuId** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero univoco che identifica il server per conferenze. Per ulteriori informazioni, vedere la [tabella MCU in Skype for Business Server 2015](mcus.md) . <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Stranieri  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la [tabella Dialogs in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Stranieri  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la [tabella Dialogs in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Data e ora in cui l'utente accede a questo server per conferenze.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Data e ora in cui l'utente lascia questo server Conferencing.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Stranieri  <br/> |Identificatore che specifica il numero di versione dell'utilizzo del software client nella conferenza. Per ulteriori informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

