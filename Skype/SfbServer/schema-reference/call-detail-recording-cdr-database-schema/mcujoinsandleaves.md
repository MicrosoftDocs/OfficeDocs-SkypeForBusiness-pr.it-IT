---
title: Tabella McuJoinsAndLeaves Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 'Ogni record in questa tabella contiene i dettagli sulle chiamate relative a una combinazione di un utente che partecipa o lascia e un server per conferenze. Ad esempio, se un utente partecipa a una conferenza che include conferenze Web ed elementi audio/video, verrà creato un record per la partecipazione alle conferenze Web dell''utente e verrà creato un altro record per l''aggiunta alle conferenze audio/video dell''utente.'
---

# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabella McuJoinsAndLeaves Skype for Business Server 2015
 
Ogni record in questa tabella contiene i dettagli sulle chiamate relative a una combinazione di un utente che partecipa o lascia e un server per conferenze. Ad esempio, se un utente partecipa a una conferenza che include conferenze Web ed elementi audio/video, verrà creato un record per la partecipazione alle conferenze Web dell'utente e verrà creato un altro record per l'aggiunta alle conferenze audio/video dell'utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora dell'istanza di conferenza. Utilizzato insieme a **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella Conferenze [Skype for Business Server 2015](conferences.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare l'istanza di conferenza. Utilizzato insieme a **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per ulteriori informazioni, vedere la tabella Conferenze [Skype for Business Server 2015](conferences.md). <br/> |
|**UserId** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero univoco che identifica l'utente. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Principale  <br/> |Se un utente è connesso a più computer o dispositivi contemporaneamente, McuUserInstance identifica in modo univoco la combinazione utente/dispositivo.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Indica se l'utente sta partecipando da una rete PSTN o meno.  <br/> |
|**McuId** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero univoco che identifica il server per conferenze. Per ulteriori [informazioni, vedere la tabella Mcus Skype for Business Server 2015](mcus.md). <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori [informazioni, vedere la tabella Dialogs Skype for Business Server 2015](dialogs.md). <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori [informazioni, vedere la tabella Dialogs Skype for Business Server 2015](dialogs.md). <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Ora in cui l'utente si unisce a questo server per conferenze.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Ora in cui l'utente lascia il server per conferenze.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |Identificatore che specifica il numero di versione dell'utilizzo del software client nella conferenza. Per ulteriori informazioni, vedere [la tabella ClientVersions Skype for Business Server 2015](clientversions.md). <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   

