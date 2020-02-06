---
title: Tabella Registration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Ogni record rappresenta un evento di registrazione utente.
ms.openlocfilehash: bca31b85a0b88854760c2a79528792ee82bd272e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814944"
---
# <a name="registration-table"></a>Tabella Registration
 
Ogni record rappresenta un evento di registrazione utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaria, straniera  <br/> |Ora della richiesta della sessione. Usato in combinazione con **SessionIdSeq** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, straniera  <br/> |Numero ID per identificare la sessione. Usato in combinazione con **SessionIdTime** per identificare in modo univoco una sessione. Per altre informazioni, vedere la [tabella delle finestre di dialogo in Skype for Business Server 2015](dialogs.md) . <br/> |
|**UserId** <br/> |int  <br/> |Esterna  <br/> |ID utente. Per altre informazioni, vedere la [tabella utenti](users.md) . <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID per identificare un endpoint di registrazione. In genere, l'evento Register dello stesso computer dello stesso utente avrà lo stesso ID endpoint. I computer diversi hanno un ID endpoint diverso.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID usato per distinguere le registrazioni che coinvolgono lo stesso utente e lo stesso endpoint.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Esterna  <br/> |Versione client dell'utente corrente. Per altre informazioni, vedere la [Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) . <br/> |
|**RegistrarId** <br/> |int  <br/> |Esterna  <br/> |ID del server registrar usato per la registrazione. Per altre informazioni, vedere la [tabella server](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Esterna  <br/> |ID del pool in cui è stata acquisita la sessione. Per altre informazioni, vedere la [tabella pool](pools.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Esterna  <br/> |Edge Server che la registrazione sta attraversando. Per altre informazioni, vedere la [tabella EdgeServers in Skype for Business Server 2015](edgeservers.md) . <br/> |
|**IsInternal** <br/> |Po'  <br/> ||Se l'utente ha eseguito l'accesso da Internal o not.  <br/> |
|**IsUserServiceAvailable** <br/> |po'  <br/> ||Se il UserService è disponibile o meno.  <br/> |
|**IsPrimaryRegistrar** <br/> |po'  <br/> ||Se eseguire la registrazione al registrar principale o meno.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |po'  <br/> ||Indica se l'utente è registrato o meno con un Survivable Branch Appliance.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |DateTime  <br/> ||Ora di registrazione.  <br/> |
|**DeRegisterTime** <br/> |DateTime  <br/> ||Tempo di annullamento della registrazione.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Codice di risposta della richiesta di registrazione.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID di diagnostica della richiesta di registrazione. Indica il tipo di informazioni di diagnostica.  <br/> |
|**DeviceId** <br/> |int  <br/> |Esterna  <br/> |Il dispositivo da cui proviene la richiesta di registro. Per altre informazioni, vedere la [tabella dispositivi in Skype for Business Server 2015](devices.md) . <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Esterna  <br/> |Il motivo dell'annullamento della registrazione, ad esempio "utente avviato", "Registrazione scaduta", "errore client" e altro ancora. Per altre informazioni, vedere la [Tabella DeRegisterType in Skype for Business Server 2015](deregistertype.md) . <br/> |
|**IPAddress** <br/> |nvarchar (256)  <br/> ||Indirizzo IP dell'endpoint con cui è stato registrato l'utente. Può trattarsi di un indirizzo IPv4 o di un indirizzo IPv6.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |DateTime  <br/> ||Per l'uso interno da parte del servizio di monitoraggio.  <br/> Questo campo è stato introdotto in Skype for Business Server 2015.  <br/> |
   

