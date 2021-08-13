---
title: Visualizzazione registrazione
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: Nella vista Registration sono archiviate informazioni sulla registrazione degli utenti. Questa visualizzazione è stata introdotta in Lync Server 2013.
ms.openlocfilehash: a28b094fd78f0a5d8b339edc372acf4503ba854d7e59e8cc81fff942e22cdcfc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341701"
---
# <a name="registration-view"></a>Visualizzazione registrazione
 
Nella vista Registration sono archiviate informazioni sulla registrazione degli utenti. Questa visualizzazione è stata introdotta in Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Ora della richiesta di sessione. Valore usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Valore usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Ora in cui è stata eseguita la registrazione.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI dell'utente che ha effettuato la registrazione.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo di URI dell'utente che ha effettuato la registrazione. Per ulteriori informazioni, vedere la tabella [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Tenant dell'utente che ha effettuato la registrazione. Per ulteriori [informazioni, vedere](tenants.md) la tabella Tenants. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'endpoint in cui l'utente ha effettuato la registrazione.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificatore univoco usato per differenziare le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Ora in cui la registrazione è stata annullata.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Motivo dell'annullamento della registrazione.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Versione del client utilizzata dall'utente che ha effettuato la registrazione.  <br/> |
|**ClientType** <br/> |int  <br/> |Client utilizzato dall'utente che ha effettuato la registrazione. Per ulteriori dettagli, vedere la [tabella UserAgentDef.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Categoria del client utilizzato dall'utente che ha effettuato la registrazione.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |Indirizzo IP con cui l'utente ha effettuato la registrazione. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID finestra di dialogo SIP. Formato:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP all'invito alla sessione. Questo campo viene in genere popolato con i dati generati dal messaggio INVITE iniziale nella sessione. Se non sono presenti messaggi INVITE, il campo viene popolato con data e ora del primo messaggio SIP rilevante (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID di diagnostica acquisito dall'intestazione SIP.  <br/> |
|**Registrar** <br/> |nvarchar(256)  <br/> |FQDN del registrar.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |FQDN del pool che ha acquisito i dati per la sessione.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |FQDN del server perimetrale usato dall'utente che ha effettuato la registrazione.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Indica se l'utente ha effettuato l'accesso dalla rete interna.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Indica se UserService era disponibile al momento della registrazione.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Indica se la registrazione è stata effettuata con il registrar principale.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Indirizzo MAC del dispositivo registrato.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Produttore del dispositivo registrato. Per ulteriori informazioni, vedere la tabella Manufacturers [Skype for Business Server 2015.](manufacturers.md) <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Versione hardware del dispositivo registrato. Per ulteriori informazioni, vedere la tabella [HardwareVersions Skype for Business Server 2015.](hardwareversions.md) <br/> |
   

