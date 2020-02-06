---
title: Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: Per delegare l'amministrazione di Skype for Business Server, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi di RTC universale creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins.
ms.openlocfilehash: 8342d1801d2df91f940f02e8bfc05c3c5b91c4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815524"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Modifiche apportate da Grant-CsOUPermission in Skype for Business Server
 
Per delegare l'amministrazione di Skype for Business Server, è possibile aggiungere le autorizzazioni per le unità organizzative specificate in modo che i membri dei gruppi di RTC universale creati dalla preparazione della foresta possano accedere alle unità organizzative senza essere membri del gruppo Domain Admins. 
  
Il cmdlet **Grant-CsOUPermission** concede le autorizzazioni per gli oggetti nell'UO specificata, come specificato nelle tabelle seguenti.
  
## <a name="granting-permission-for-user-objects"></a>Concessione dell'autorizzazione per gli oggetti utente

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti utente in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti utente**

|**Gruppo**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica delle modifiche della directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere le informazioni pubbliche  <br/> Leggere informazioni generali  <br/> Leggi utente-account-restrizioni  <br/> |Oggetti utente discendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrivere RTCUserSearchPropertySet  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Scrivere RTCUserProvisioningPropertySet  <br/> Scrivere RTCPropertySet  <br/> Scrivere proxyAddresses  <br/> |Oggetti utente discendente  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Concessione dell'autorizzazione per gli oggetti computer

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti computer in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti computer**

|**Gruppo**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica delle modifiche della directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere le informazioni pubbliche  <br/> Lettura convalidata-DNS-host-name  <br/> |Oggetti computer discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Leggere le informazioni pubbliche  <br/> Lettura convalidata-DNS-host-name  <br/> |Oggetti computer discendenti  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Concessione dell'autorizzazione per gli oggetti Contact o AppContact

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti Contact o gli oggetti AppContact in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti Contact o AppContact**

|**Gruppo**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica delle modifiche della directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere le informazioni pubbliche  <br/> Leggere informazioni generali  <br/> Leggere le informazioni personali  <br/> Leggi utente-account-restrizioni  <br/> |Oggetti contatto discendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrivere RTCUserSearchPropertySet  <br/> Scrivere otherIpPhone  <br/> Scrittura di displayName  <br/> Descrizione della scrittura  <br/> Scrivere telephoneNumber  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Scrivere RTCUserProvisioningPropertySet  <br/> Scrivere RTCPropertySet  <br/> Scrivere proxyAddresses  <br/> |Oggetti contatto discendente  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Concessione dell'autorizzazione per gli oggetti dispositivo

Quando si esegue il cmdlet **Grant-CsOUPermission** per oggetti Device in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti dispositivo**

|**Gruppo**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica delle modifiche della directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere le informazioni pubbliche  <br/> Leggere le informazioni personali  <br/> Leggere informazioni generali  <br/> Leggi utente-account-restrizioni  <br/> |Oggetti contatto discendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Creare un bambino  <br/> Eliminare il bambino  <br/> Elimina albero  <br/> |Contatto  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrittura di displayName  <br/> Descrizione della scrittura  <br/> Scrivere telephoneNumber  <br/> |Oggetti utente discendente  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrivere RTCUserSearchPropertySet  <br/> Scrivere otherIpPhone  <br/> Scrittura di displayName  <br/> Descrizione della scrittura  <br/> Scrivere telephoneNumber  <br/> Scrivere msExchUCVoiceMailSettings  <br/> Scrivere RTCUserProvisioningPropertySet  <br/> Scrivere RTCPropertySet  <br/> Scrivere proxyAddresses  <br/> |Oggetti contatto discendente  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>Concessione dell'autorizzazione per gli oggetti InetOrgPerson

Quando si esegue il cmdlet **Grant-CsOUPermission** per gli oggetti InetOrgPerson in un'unità organizzativa, ai gruppi vengono concesse le autorizzazioni, come illustrato nella tabella seguente.
  
**Autorizzazioni concesse per gli oggetti InetOrgPerson**

|**Gruppo**|**Autorizzazione**|**Si applica a**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |Replica delle modifiche della directory  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Contenuto dell'elenco  <br/> Leggere tutte le proprietà  <br/> Autorizzazioni di lettura  <br/> |Solo questo oggetto  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Leggere RTCUserSearchPropertySet  <br/> Leggere RTCUserProvisioningPropertySet  <br/> Leggere RTCPropertySet  <br/> Leggere le informazioni personali  <br/> Leggere le informazioni pubbliche  <br/> Leggere informazioni generali  <br/> Leggi utente-account-restrizioni  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
|RTCUniversalUserAdmins  <br/> |Scrivere RTCUserSearchPropertySet  <br/> Scrivere RTCUserProvisioningPropertySet  <br/> Scrivere RTCPropertySet  <br/> Scrivere proxyAddresses  <br/> |Oggetti inetOrgPerson discendenti  <br/> |
   

