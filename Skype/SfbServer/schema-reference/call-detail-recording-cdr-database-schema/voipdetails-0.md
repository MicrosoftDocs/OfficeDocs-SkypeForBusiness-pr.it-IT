---
title: Tabella VoipDetails
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
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.
ms.openlocfilehash: 900598c99965292e7d349520cc2dfa55443bb5a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813096"
---
# <a name="voipdetails-table"></a>Tabella VoipDetails
 
Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principale  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la [tabella Dialogs in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la [tabella Dialogs in Skype for Business Server 2015](dialogs.md) . <br/> |
|**FromNumberId** <br/> |int  <br/> |Stranieri  <br/> |**PhoneId** del chiamante. Per ulteriori informazioni, vedere la [tabella Phones](phones.md) . Se questo valore è diverso da NULL e **FromGatewayId** è diverso da NULL, il chiamante è un utente PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Stranieri  <br/> |**PhoneId** del destinatario della chiamata. Per ulteriori informazioni, vedere la [tabella Phones](phones.md) . Se questo valore è diverso da NULL e **ToGatewayId** è diverso da NULL, il destinatario della chiamata è un utente PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Stranieri  <br/> |Mediation Server da cui proviene la chiamata. Per ulteriori informazioni, vedere la [Tabella MediationServers](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Stranieri  <br/> |Mediation Server a cui andrà la chiamata. Per ulteriori informazioni, vedere la [Tabella MediationServers](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Stranieri  <br/> |Gateway da cui proviene la chiamata. Per ulteriori informazioni, vedere la [tabella gateway in Skype for Business Server 2015](gateways.md) . <br/> |
|**ToGatewayId** <br/> |int  <br/> |Stranieri  <br/> |Gateway a cui andrà la chiamata. Per ulteriori informazioni, vedere la [tabella gateway in Skype for Business Server 2015](gateways.md) . <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Stranieri  <br/> |URI dell'utente che ha disconnesso la chiamata, se l'utente dispone di un URI. Per ulteriori informazioni, vedere la [tabella users](users.md) . <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Stranieri  <br/> |ID del telefono che ha disconnesso la chiamata se la chiamata è stata disconnessa da un telefono. Per ulteriori informazioni, vedere la [tabella Phones](phones.md) . <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

