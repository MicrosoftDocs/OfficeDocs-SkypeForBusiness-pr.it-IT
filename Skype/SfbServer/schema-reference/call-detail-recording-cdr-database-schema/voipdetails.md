---
title: Visualizzazione VoIPDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Nella visualizzazione VoIPDetails vengono archiviate le informazioni sulle sessioni peer-to-peer, che contengono almeno un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 9e8eeaa0e907496d03a4541792f6f100a9191324497ee7603a65ec5a71fba592
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351955"
---
# <a name="voipdetails-view"></a>Visualizzazione VoIPDetails
 
Nella visualizzazione VoIPDetails vengono archiviate le informazioni sulle sessioni peer-to-peer, che contengono almeno un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione VoIPDetails contiene tutte le colonne nella visualizzazione [SessionDetails,](sessiondetails-0.md) oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI telefono dell'utente che ha avviato la sessione.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI telefono dell'utente che ha partecipato alla sessione.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha interrotto la sessione.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha interrotto la sessione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che ha interrotto la sessione.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI telefono dell'utente che ha interrotto la sessione.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Mediation Server utilizzato dall'utente che ha avviato la sessione.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Mediation Server utilizzato dall'utente che ha partecipato alla sessione.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Gateway utilizzato dall'utente che ha avviato la sessione.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Gateway utilizzato dall'utente che ha partecipato alla sessione.  <br/> |
   

