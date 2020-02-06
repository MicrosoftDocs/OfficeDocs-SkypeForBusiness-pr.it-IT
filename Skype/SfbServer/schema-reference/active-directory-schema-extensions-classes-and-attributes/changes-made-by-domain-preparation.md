---
title: Modifiche apportate dalla preparazione del dominio in Skype for Business Server
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
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Nella tabella seguente sono elencate le voci di controllo di accesso (ACE) create dalla preparazione del dominio nella radice del dominio. Tutte le voci ACE vengono ereditate se non diversamente specificato.
ms.openlocfilehash: 8a087dfbbd8b670467727803f996694a816cc065
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815544"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Modifiche apportate dalla preparazione del dominio in Skype for Business Server
 
Nella tabella seguente sono elencate le voci di controllo di accesso (ACE) create dalla preparazione del dominio nella radice del dominio. Tutte le voci ACE vengono ereditate se non diversamente specificato.
  
**Voci ACE aggiunte alla radice del dominio**

|**ACE**|**RTCUniversal-UserReadOnly-gruppo**|**RTCUniversal-ServerReadOnly-gruppo**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-servizi**|**Utenti autenticati**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Contenitore di lettura (non ereditato)  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leggere l'utente di PropertySet user-account-Restrictions  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leggere l'utente PropertySet Personal-Information  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leggere l'utente PropertySet generale-informazioni  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leggere l'utente PropertySet Public-Information  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Leggi utente PropertySet RTCUserSearchProperty-set  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |
|Leggere l'utente PropertySet RTCPropertySet  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |No  <br/> |No  <br/> |
|Scrivere gli indirizzi proxy della proprietà utente  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Scrivere l'utente PropertySet RTCUserSearchProperty-set  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Scrivere l'utente PropertySet RTCPropertySet  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Leggere PropertySet DS-replica-Get-modifiche di tutti gli oggetti di Active Directory  <br/> |No  <br/> |No  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |
   
Nella tabella seguente sono elencate le voci ACE create dalla preparazione del dominio nei tre contenitori predefiniti: utenti, computer e controller di dominio. Tutte le voci ACE vengono ereditate se non diversamente specificato.
**Voci ACE aggiunte ai contenitori predefiniti**

|**ACE**|**RTCUniversal-UserReadOnly-gruppo**|**RTCUniversal-ServerReadOnly-gruppo**|
|:-----|:-----|:-----|
|Contenitore di lettura (non ereditato)  <br/> |**Sì** <br/> |**Sì** <br/> |
   

