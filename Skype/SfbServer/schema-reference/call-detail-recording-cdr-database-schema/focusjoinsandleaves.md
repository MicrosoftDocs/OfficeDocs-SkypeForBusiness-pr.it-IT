---
title: Tabella FocusJoinsAndLeaves in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Ogni record in questa tabella contiene le informazioni CDR relative alle informazioni di partecipazione e di uscita di un utente per una conferenza. Ogni conferenza viene rappresentata in questa tabella da un record per ogni volta che un utente si unisce e lascia la conferenza.
ms.openlocfilehash: 4eb9f6300613fb61a7173be547aa83adf61d1026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194800"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Tabella FocusJoinsAndLeaves in Skype for Business Server 2015
 
Ogni record in questa tabella contiene le informazioni CDR relative alle informazioni di partecipazione e di uscita di un utente per una conferenza. Ogni conferenza viene rappresentata in questa tabella da un record per ogni volta che un utente si unisce e lascia la conferenza.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora dell'istanza di conferenza. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare l'istanza di conferenza. Usato in combinazione con **SessionIdTime** per identificare in modo univoco un'istanza di conferenza. Per altre informazioni, vedere la [tabella conferenze in Skype for Business Server 2015](conferences.md) . <br/> |
|**DialogSessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserId** <br/> |int  <br/> |Esterna  <br/> |Numero univoco che identifica l'utente, a cui viene fatto riferimento dalla [tabella utenti](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Se un utente ha eseguito l'accesso a più computer o dispositivi contemporaneamente, **UserInstance** viene usato per identificare in modo univoco la combinazione utente/dispositivo. <br/> |
|**IsUserInternal** <br/> |po'  <br/> | <br/> |Se l'utente ha effettuato l'accesso da Internal o not.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Ruolo di questo utente nella conferenza, ad esempio relatore o partecipante.  <br/> |
|**UserJoinTime** <br/> |DateTime  <br/> | <br/> |L'ora in cui l'utente partecipa alla conferenza.  <br/> |
|**UserLeaveTime** <br/> |DateTime  <br/> | <br/> |L'ora in cui l'utente esce dalla conferenza.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Esterna  <br/> |Versione del software client dell'utente, a cui si fa riferimento alla [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificatore univoco globale (GUID) dell'endpoint usato nella conferenza.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

