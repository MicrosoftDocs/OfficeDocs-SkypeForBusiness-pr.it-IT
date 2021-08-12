---
title: Modifiche apportate da Grant-CsSetupPermission in Skype for Business Server
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
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Per delegare l'installazione, è possibile concedere autorizzazioni al gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, consentendo ai membri del gruppo RTCUniversalServerAdmins in tale unità organizzativa di installare Skype for Business Server nel dominio specificato senza essere membri del gruppo Domain Admins.
ms.openlocfilehash: 32c0d48c5b6c63a38ff48e7808b8009c3ef265e6f0b6eb739094f797e47ace4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349708"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Modifiche apportate da Grant-CsSetupPermission in Skype for Business Server
 
Per delegare l'installazione, è possibile concedere autorizzazioni al gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, consentendo ai membri del gruppo RTCUniversalServerAdmins in tale unità organizzativa di installare Skype for Business Server nel dominio specificato senza essere membri del gruppo Domain Admins. 
  
Il cmdlet **Grant-CsSetupPermission** concede al gruppo RTCUniversalServerAdmins le autorizzazioni per un'unità organizzativa, come specificato nella tabella seguente:
  
**Autorizzazioni concesse a oggetti nell'unità organizzativa**

|**Le autorizzazioni si applicano a:**|**Autorizzazioni concesse:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Accesso speciale: <br/>  Leggi servicePrincipalName <br/>  Scrivi in servicePrincipalName <br/>  Elimina albero <br/>  Replica modifiche directory <br/> |
|Oggetti serviceConnectionPoint discendenti  <br/> | Accesso speciale: <br/>  Autorizzazioni di lettura <br/>  Autorizzazioni di scrittura <br/>  Crea elemento figlio <br/>  Elimina elemento figlio <br/>  Elenca contenuto <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-Server discendenti  <br/> | Accesso speciale: <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-WebComponents discendenti  <br/> | Accesso speciale: <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-MCU discendenti  <br/> | Accesso speciale: <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-MediationServer discendenti  <br/> | Accesso speciale: <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-ApplicationServer discendenti  <br/> | Accesso speciale: <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-ConnectionPoint discendenti  <br/> | Accesso speciale: <br/>  Proprietà di scrittura <br/>  Proprietà di lettura <br/>  Elimina albero <br/> |
|Oggetti Computer discendenti  <br/> | Accesso speciale per serviceConnectionPoint: <br/>  Crea oggetti figli <br/>  Elimina oggetti figli <br/>  Elimina albero <br/>  Accesso speciale per informazioni pubbliche: <br/>  Proprietà di lettura <br/>  Accesso speciale per il nome host DNS: <br/>  Proprietà di lettura <br/> |
   

