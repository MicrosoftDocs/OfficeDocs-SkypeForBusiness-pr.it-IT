---
title: Tabella VoipDetails
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
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Ogni record rappresenta una chiamata di 1 2-Party in cui almeno un utente è un utente VoIP.
ms.openlocfilehash: 65bf3b4d7a815434b21b761030a7ac514d9bd803
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814784"
---
# <a name="voipdetails-table"></a>Tabella VoipDetails
 
Ogni record rappresenta una chiamata di 1 2-Party in cui almeno un utente è un utente VoIP.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Principale  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principale  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**FromNumberId** <br/> |int  <br/> |Esterna  <br/> |**PhoneId** del chiamante. Per altre informazioni, vedere la [tabella telefoni](phones.md) . Se non è NULL e **FromGatewayId** non è null, il chiamante era un utente PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Esterna  <br/> |**PhoneId** del destinatario della chiamata. Per altre informazioni, vedere la [tabella telefoni](phones.md) . Se non è NULL e **ToGatewayId** non è null, il destinatario della chiamata è un utente PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Esterna  <br/> |Server di mediazione da cui proviene la chiamata. Per altre informazioni, vedere la [Tabella MediationServers](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Esterna  <br/> |Il server di mediazione chiamato sta andando. Per altre informazioni, vedere la [Tabella MediationServers](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Esterna  <br/> |Gateway da cui proviene la chiamata. Per altre informazioni, vedere la [tabella gateway in Skype for Business Server 2015](gateways.md) . <br/> |
|**ToGatewayId** <br/> |int  <br/> |Esterna  <br/> |Gateway che la chiamata sta per. Per altre informazioni, vedere la [tabella gateway in Skype for Business Server 2015](gateways.md) . <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Esterna  <br/> |URI dell'utente che ha scollegato la chiamata, se l'utente ha un URI. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Esterna  <br/> |ID del telefono che ha scollegato la chiamata è stata disconnessa da un telefono. Per altre informazioni, vedere la [tabella telefoni](phones.md) . <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

