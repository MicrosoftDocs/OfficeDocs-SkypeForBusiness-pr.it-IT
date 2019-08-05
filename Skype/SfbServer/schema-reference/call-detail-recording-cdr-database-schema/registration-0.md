---
title: Visualizzazione registrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: La visualizzazione di registrazione archivia le informazioni sulla registrazione dell'utente. Questa visualizzazione è stata introdotta in Lync Server 2013.
ms.openlocfilehash: 6202e40e6385fd243f55badd25dbe196452c890a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194754"
---
# <a name="registration-view"></a>Visualizzazione registrazione
 
La visualizzazione di registrazione archivia le informazioni sulla registrazione dell'utente. Questa visualizzazione è stata introdotta in Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Ora della richiesta della sessione. Usato in combinazione con SessionIdSeq per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numero ID per identificare la sessione. Usato in combinazione con SessionIdTime per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**RegisterTime** <br/> |DateTime  <br/> |Ora in cui si è verificata la registrazione.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI dell'utente che ha registrato.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Tipo di URI dell'utente che ha registrato. Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar (256)  <br/> |Tenant dell'utente che ha registrato. Per altre informazioni, vedere la [tabella tenant](tenants.md) . <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Identificatore univoco dell'endpoint dell'utente registrato con.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Identificatore univoco usato per distinguere le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.  <br/> |
|**DeRegisterType** <br/> |DateTime  <br/> |Ora in cui si è verificata l'annullamento della registrazione.  <br/> |
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> |Motivo dell'annullamento della registrazione.  <br/> |
|**ClientVersion** <br/> |nvarchar (256)  <br/> |Versione del client usata dall'utente che ha registrato.  <br/> |
|**TipoClient** <br/> |int  <br/> |Client usato dall'utente che ha registrato. Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) . <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Categoria del client usata dall'utente che ha registrato.  <br/> |
|**IpAddress** <br/> |nvarchar (256)  <br/> |Indirizzo IP con cui l'utente ha registrato. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |ID finestra di dialogo SIP. Il formato dell'is:  <br/> finestra di dialogo; da-tag; to-Tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |Codice di risposta SIP per l'invito alla sessione. Questo campo viene in genere popolato da dati generati dal messaggio di invito iniziale nella sessione. Se non è presente alcun messaggio di invito, il campo viene popolato con la data e l'ora del primo messaggio SIP pertinente (BYE, CANCEL, MESSAGE o INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID di diagnostica acquisito dall'intestazione SIP.  <br/> |
|**Registrar** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del registrar.  <br/> |
|**Pool** <br/> |nvarchar (256)  <br/> |Nome di dominio completo del pool che ha acquisito i dati per la sessione.  <br/> |
|**EdgeServer** <br/> |nvarchar (256)  <br/> |FQDN dell'Edge Server usato dall'utente che ha registrato.  <br/> |
|**IsInternal** <br/> |po'  <br/> |Indica se l'utente ha effettuato l'accesso dalla rete interna.  <br/> |
|**IsUserServiceAvailable** <br/> |po'  <br/> |Indica se il UserService è disponibile al momento della registrazione.  <br/> |
|**IsPrimaryRegistrar** <br/> |po'  <br/> |Indica se la registrazione è stata con il registrar principale.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |Indirizzo MAC del dispositivo registrato.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar (256)  <br/> |Produttore del dispositivo registrato. Per altre informazioni, vedere la [tabella produttori in Skype for Business Server 2015](manufacturers.md) . <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar (256)  <br/> |Versione hardware del dispositivo registrato. Per altre informazioni, vedere la [tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) . <br/> |
   

