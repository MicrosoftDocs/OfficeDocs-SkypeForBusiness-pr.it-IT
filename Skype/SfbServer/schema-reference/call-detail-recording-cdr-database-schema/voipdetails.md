---
title: Visualizzazione VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814774"
---
# <a name="voipdetails-view"></a>Visualizzazione VoIPDetails
 
La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
> [!NOTE]
> La visualizzazione VoIPDetails contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |URI telefono dell'utente che ha avviato la sessione.  <br/> |
|**Telefono** <br/> |nvarchar (450)  <br/> |URI telefono dell'utente che ha partecipato alla sessione.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha scollegato la sessione.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha scollegato la sessione. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente che ha scollegato la sessione.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |URI telefono dell'utente che ha scollegato la sessione.  <br/> |
|**FromMediationServer** <br/> |nvarchar (256)  <br/> |Mediation Server usato dall'utente che ha avviato la sessione.  <br/> |
|**ToMediationServer** <br/> |nvarchar (256)  <br/> |Mediation Server usato dall'utente che ha partecipato alla sessione.  <br/> |
|**FromGateway** <br/> |nvarchar (256)  <br/> |Gateway usato dall'utente che ha avviato la sessione.  <br/> |
|**Togateway** <br/> |nvarchar (256)  <br/> |Gateway usato dall'utente che ha partecipato alla sessione.  <br/> |
   

