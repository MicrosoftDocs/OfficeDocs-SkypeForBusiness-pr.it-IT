---
title: Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Per delegare Skype for Business Server amministrazione, è possibile aggiungere autorizzazioni a unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.
ms.openlocfilehash: b5c507cf91a880c73c7b377deafb672ed25b1125
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745842"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
 
Per delegare Skype for Business Server amministrazione, è possibile aggiungere autorizzazioni a unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins. 
  
Il cmdlet **Grant-CsOuPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata come specificato nelle tabelle seguenti.
  
## <a name="granting-permission-for-user-objects"></a>Concessione dell'autorizzazione per gli oggetti utente

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti User in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti utente**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lettura RTCUserSearchPropertySet  <br/> Lettura di RTCUserProvisioningPropertySet  <br/> Lettura di RTCPropertySet  <br/> Lettura Public-Information  <br/> Lettura General-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti User discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura di RTCUserSearchPropertySet  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Scrittura di RTCUserProvisioningPropertySet  <br/> Scrittura di RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti User discendenti  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concessione dell'autorizzazione per gli oggetti computer

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti Computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti computer**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lettura Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Oggetti Computer discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Lettura Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Oggetti Computer discendenti  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concessione dell'autorizzazione per oggetti Contact o AppContact

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti Contact o AppContact in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per oggetti Contact o AppContact**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lettura RTCUserSearchPropertySet  <br/> Lettura di RTCUserProvisioningPropertySet  <br/> Lettura di RTCPropertySet  <br/> Lettura Public-Information  <br/> Lettura General-Information  <br/> Lettura Personal-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti Contact discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura di RTCUserSearchPropertySet  <br/> Scrivi otherIpPhone  <br/> Write displayName  <br/> Descrizione scrittura  <br/> Write telephoneNumber  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Scrittura di RTCUserProvisioningPropertySet  <br/> Scrittura di RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti Contact discendenti  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concessione dell'autorizzazione per gli oggetti dispositivo

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti dispositivo**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lettura RTCUserSearchPropertySet  <br/> Lettura di RTCUserProvisioningPropertySet  <br/> Lettura di RTCPropertySet  <br/> Lettura Public-Information  <br/> Lettura Personal-Information  <br/> Lettura General-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti Contact discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Crea elemento figlio  <br/> Elimina elemento figlio  <br/> Elimina albero  <br/> |Contatto  <br/> |
|RTCUniversalUserAdmins  <br/> |Write displayName  <br/> Descrizione scrittura  <br/> Write telephoneNumber  <br/> |Oggetti User discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura di RTCUserSearchPropertySet  <br/> Scrivi otherIpPhone  <br/> Write displayName  <br/> Descrizione scrittura  <br/> Write telephoneNumber  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Scrittura di RTCUserProvisioningPropertySet  <br/> Scrittura di RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti Contact discendenti  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concessione dell'autorizzazione per gli oggetti InetOrgPerson

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti InetOrgPerson**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lettura RTCUserSearchPropertySet  <br/> Lettura di RTCUserProvisioningPropertySet  <br/> Lettura di RTCPropertySet  <br/> Lettura Personal-Information  <br/> Lettura Public-Information  <br/> Lettura General-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura di RTCUserSearchPropertySet  <br/> Scrittura di RTCUserProvisioningPropertySet  <br/> Scrittura di RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
   

