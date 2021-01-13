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
description: Per delegare l'amministrazione di Skype for Business Server, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.
ms.openlocfilehash: 09a6d6baf554b18db0a388619ffb74c85c6963fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831846"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
 
Per delegare l'amministrazione di Skype for Business Server, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi universali RTC creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins. 
  
Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni agli oggetti nell'unità organizzativa specificata, come indicato nelle tabelle seguenti.
  
## <a name="granting-permission-for-user-objects"></a>Concessione di autorizzazioni per gli oggetti utente

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente di un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti utente**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere Public-Information  <br/> Leggere General-Information  <br/> Leggere le restrizioni degli account utente  <br/> |Oggetti utente discendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura RTCUserSearchPropertySet  <br/> Scrittura msExchUCVoiceMailSettings  <br/> Scrittura RTCUserProvisioningPropertySet  <br/> Scrittura RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti utente discendente  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concessione di autorizzazioni per gli oggetti computer

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti computer**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere Public-Information  <br/> Lettura convalidata-DNS-host-name  <br/> |Oggetti Computer discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Leggere Public-Information  <br/> Lettura convalidata-DNS-host-name  <br/> |Oggetti Computer discendenti  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concessione di autorizzazioni per gli oggetti Contact o AppContact

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti contatto o gli oggetti AppContact su un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti Contact o AppContact**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere Public-Information  <br/> Leggere General-Information  <br/> Leggere Personal-Information  <br/> Leggere le restrizioni degli account utente  <br/> |Oggetti contatto discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura RTCUserSearchPropertySet  <br/> Scrittura otherIpPhone  <br/> Scrittura di displayName  <br/> Descrizione di scrittura  <br/> Scrittura telephoneNumber  <br/> Scrittura msExchUCVoiceMailSettings  <br/> Scrittura RTCUserProvisioningPropertySet  <br/> Scrittura RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti contatto discendenti  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concessione di autorizzazioni per gli oggetti Device

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti Device**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere Public-Information  <br/> Leggere Personal-Information  <br/> Leggere General-Information  <br/> Leggere le restrizioni degli account utente  <br/> |Oggetti contatto discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Crea elemento figlio  <br/> Elimina elemento figlio  <br/> Elimina albero  <br/> |Contatto  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura di displayName  <br/> Descrizione di scrittura  <br/> Scrittura telephoneNumber  <br/> |Oggetti utente discendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura RTCUserSearchPropertySet  <br/> Scrittura otherIpPhone  <br/> Scrittura di displayName  <br/> Descrizione di scrittura  <br/> Scrittura telephoneNumber  <br/> Scrittura msExchUCVoiceMailSettings  <br/> Scrittura RTCUserProvisioningPropertySet  <br/> Scrittura RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti contatto discendenti  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concessione di autorizzazioni per gli oggetti InetOrgPerson

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti InetOrgPerson**

|**Group**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica modifiche directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Elenca contenuto  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere Personal-Information  <br/> Leggere Public-Information  <br/> Leggere General-Information  <br/> Leggere le restrizioni degli account utente  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura RTCUserSearchPropertySet  <br/> Scrittura RTCUserProvisioningPropertySet  <br/> Scrittura RTCPropertySet  <br/> Scrittura proxyAddresses  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
   

