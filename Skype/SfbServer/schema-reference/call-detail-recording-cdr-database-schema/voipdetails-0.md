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
ms.openlocfilehash: 2314317f23db8edc4d0c2e0cc203cb74104168c472fa81cdfacc1a6595619278
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336411"
---
# <a name="voipdetails-table"></a>Tabella VoipDetails
 
Ogni record rappresenta una chiamata con due partecipanti di cui almeno uno è un utente VoIP.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Principale  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**FromNumberId** <br/> |int  <br/> |Foreign  <br/> |**PhoneId** del chiamante. Per ulteriori [informazioni, vedere](phones.md) la tabella Telefoni. Se questo valore è diverso da NULL e **FromGatewayId** è diverso da NULL, il chiamante è un utente PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Foreign  <br/> |**PhoneId** del destinatario della chiamata. Per ulteriori [informazioni, vedere](phones.md) la tabella Telefoni. Se questo valore è diverso da NULL e **ToGatewayId** è diverso da NULL, il destinatario della chiamata è un utente PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Foreign  <br/> |Mediation Server da cui proviene la chiamata. Per ulteriori informazioni, vedere la tabella [MediationServers.](mediationservers.md) <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Foreign  <br/> |Mediation Server a cui andrà la chiamata. Per ulteriori informazioni, vedere la tabella [MediationServers.](mediationservers.md) <br/> |
|**FromGatewayId** <br/> |int  <br/> |Foreign  <br/> |Gateway da cui proviene la chiamata. Per ulteriori informazioni, vedere la tabella [Gateways Skype for Business Server 2015.](gateways.md) <br/> |
|**ToGatewayId** <br/> |int  <br/> |Foreign  <br/> |Gateway a cui andrà la chiamata. Per ulteriori informazioni, vedere la tabella [Gateways Skype for Business Server 2015.](gateways.md) <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Foreign  <br/> |URI dell'utente che ha disconnesso la chiamata, se l'utente dispone di un URI. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Foreign  <br/> |ID del telefono che ha disconnesso la chiamata se la chiamata è stata disconnessa da un telefono. Per ulteriori [informazioni, vedere](phones.md) la tabella Telefoni. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   

