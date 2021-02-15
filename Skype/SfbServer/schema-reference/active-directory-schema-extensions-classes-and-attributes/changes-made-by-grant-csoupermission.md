---
title: Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Per delegare l'amministrazione di Skype for Business Server, è possibile aggiungere autorizzazioni a unità organizzative specifiche in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.
ms.openlocfilehash: 09a6d6baf554b18db0a388619ffb74c85c6963fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831846"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
 
Per delegare l'amministrazione di Skype for Business Server, è possibile aggiungere autorizzazioni a unità organizzative specifiche in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins. 
  
Il cmdlet **Grant-CsOuPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata come specificato nelle tabelle seguenti.
  
## <a name="granting-permission-for-user-objects"></a>Concessione dell'autorizzazione per gli oggetti utente

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti Utente in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti utente**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Lettura Public-Information  <br/> Lettura General-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti Utente discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti Utente discendenti  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concessione dell'autorizzazione per gli oggetti computer

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti Computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti computer**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Lettura Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Oggetti Computer discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Lettura Public-Information  <br/> Read Validated-DNS-Host-Name  <br/> |Oggetti Computer discendenti  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concessione dell'autorizzazione per oggetti Contact o AppContact

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti Contact o AppContact in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per oggetti Contact o AppContact**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Lettura Public-Information  <br/> Lettura General-Information  <br/> Lettura Personal-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti Contact discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write otherIpPhone  <br/> Write displayName  <br/> Descrizione scrittura  <br/> Write telephoneNumber  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti Contact discendenti  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concessione dell'autorizzazione per gli oggetti dispositivo

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti dispositivo in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti dispositivo**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Lettura Public-Information  <br/> Lettura Personal-Information  <br/> Lettura General-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti Contact discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Crea elemento figlio  <br/> Elimina elemento figlio  <br/> Elimina albero  <br/> |Contatto  <br/> |
|RTCUniversalUserAdmins  <br/> |Write displayName  <br/> Descrizione scrittura  <br/> Write telephoneNumber  <br/> |Oggetti Utente discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write otherIpPhone  <br/> Write displayName  <br/> Descrizione scrittura  <br/> Write telephoneNumber  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti Contact discendenti  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concessione dell'autorizzazione per gli oggetti InetOrgPerson

Quando si esegue il cmdlet **Grant-CsOuPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti InetOrgPerson**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggi tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Read RTCUserSearchPropertySet  <br/> Read RTCUserProvisioningPropertySet  <br/> Read RTCPropertySet  <br/> Lettura Personal-Information  <br/> Lettura Public-Information  <br/> Lettura General-Information  <br/> Leggere User-Account-Restrictions  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Write RTCUserSearchPropertySet  <br/> Write RTCUserProvisioningPropertySet  <br/> Write RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
   

