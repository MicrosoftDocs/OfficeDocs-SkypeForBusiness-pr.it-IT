---
title: Modifiche apportate dalla preparazione del dominio in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.
ms.openlocfilehash: 4bf190e0b74e082cf187cde94b3a3062906f0c53
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389918"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Modifiche apportate dalla preparazione del dominio in Skype for Business Server
 
Nella tabella riportata di seguito vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nella radice del dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.
  
**Voci di controllo di accesso aggiunte alla radice del dominio**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authenticated-Users**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Read Container (non ereditata)  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet User-Account-Restrictions  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet Personal-Information  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet General-Information  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet Public-Information  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Read User PropertySet RTCUserSearchProperty-Set  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |
|Read User PropertySet RTCPropertySet  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Write User Property Proxy-Addresses  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Write User PropertySet RTCUserSearchProperty-Set  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Write User PropertySet RTCPropertySet  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Read PropertySet DS-Replication-Get-Changes of all Active Directory objects  <br/> |No  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |
   
Nella tabella seguente vengono elencate le voci di controllo di accesso create durante la preparazione del dominio nei tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio. Se non diversamente specificato, tutte le voci di controllo di accesso vengono ereditate.
**Voci di controllo di accesso aggiunte ai contenitori predefiniti**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Read Container (non ereditata)  <br/> |**Sì** <br/> |**Sì** <br/> |
   

