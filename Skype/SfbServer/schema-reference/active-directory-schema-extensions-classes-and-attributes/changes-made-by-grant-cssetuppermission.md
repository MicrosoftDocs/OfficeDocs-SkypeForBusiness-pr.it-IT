---
title: Modifiche apportate da Grant-CsSetupPermission in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: Per delegare la configurazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, che consente ai membri del gruppo RTCUniversalServerAdmins in tale OU di installare Skype for Business Server nella dominio specificato senza essere membri del gruppo Domain Admins.
ms.openlocfilehash: a7cbf49fa7d34b8a81668c4ec598e3a547c098e9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194865"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Modifiche apportate da Grant-CsSetupPermission in Skype for Business Server
 
Per delegare la configurazione, è possibile concedere le autorizzazioni per il gruppo universale RTCUniversalServerAdmins per una specifica unità organizzativa di Active Directory, che consente ai membri del gruppo RTCUniversalServerAdmins in tale OU di installare Skype for Business Server nella dominio specificato senza essere membri del gruppo Domain Admins. 
  
Il cmdlet **Grant-CsSetupPermission** concede le autorizzazioni di gruppo RTCUniversalServerAdmins per un'unità organizzativa, come specificato nella tabella seguente:
  
**Autorizzazioni concesse agli oggetti nell'unità organizzativa**

|**Le autorizzazioni si applicano a:**|**Le autorizzazioni concesse sono:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | Accesso speciale: <br/>  Leggere servicePrincipalName <br/>  Scrivere servicePrincipalName <br/>  Elimina albero <br/>  Replica delle modifiche della directory <br/> |
|Oggetti serviceConnectionPoint discendenti  <br/> | Accesso speciale: <br/>  Autorizzazioni di lettura <br/>  Autorizzazioni di scrittura <br/>  Creare un bambino <br/>  Eliminare il bambino <br/>  Contenuto dell'elenco <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-Server discendenti  <br/> | Accesso speciale: <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-WebComponents discendenti  <br/> | Accesso speciale: <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-MCU discendenti  <br/> | Accesso speciale: <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-MediationServer discendenti  <br/> | Accesso speciale: <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-ApplicationServer discendenti  <br/> | Accesso speciale: <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti msRTCSIP-ConnectionPoint discendenti  <br/> | Accesso speciale: <br/>  Proprietà Write <br/>  Proprietà Read <br/>  Elimina albero <br/> |
|Oggetti computer discendenti  <br/> | Accesso speciale per serviceConnectionPoint: <br/>  Creare oggetti figlio <br/>  Eliminare oggetti figlio <br/>  Elimina albero <br/>  Accesso speciale per informazioni pubbliche: <br/>  Proprietà Read <br/>  Accesso speciale per il nome host DNS: <br/>  Proprietà Read <br/> |
   

