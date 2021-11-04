---
title: Tabella di registrazione
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Ogni record rappresenta un evento di registrazione utente.
ms.openlocfilehash: c4c9ca266ac366526df1723bebc7ef58e9470187
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746542"
---
# <a name="registration-table"></a>Tabella di registrazione
 
Ogni record rappresenta un evento di registrazione utente.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primaria, esterna  <br/> |Data e ora della richiesta di sessione. Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaria, esterna  <br/> |Numero ID per identificare la sessione. Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione. Per ulteriori informazioni, vedere la tabella [Dialogs Skype for Business Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |ID utente. Per ulteriori [informazioni, vedere](users.md) la tabella Utenti. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID per identificare un endpoint di registrazione. L'evento di registrazione dallo stesso computer dello stesso utente in genere avrà lo stesso ID endpoint. Computer diversi hanno un ID endpoint diverso.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||ID utilizzato per distinguere le registrazioni che interessano lo stesso utente e lo stesso endpoint.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Versione client dell'utente corrente. Per ulteriori informazioni, vedere la tabella [ClientVersions Skype for Business Server 2015.](clientversions.md) <br/> |
|**RegistrarId** <br/> |int  <br/> |Foreign  <br/> |ID del server di registrazione utilizzato per la registrazione. Per ulteriori [informazioni, vedere](servers.md) la tabella Servers. <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |ID del pool in cui è stata acquisita la sessione. Per ulteriori [informazioni, vedere](pools.md) la tabella Pools. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |Server perimetrale attraverso il quale passa la registrazione. Per ulteriori informazioni, vedere la tabella [EdgeServers Skype for Business Server 2015.](edgeservers.md) <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Se l'utente è connesso o meno dall'interno.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Se il servizio utente è disponibile o meno.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Se registrare o meno nella funzione di registrazione principale.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Indica se l'utente è registrato o meno con un Survivable Branch Appliance.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Data/ora di registrazione.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Data/ora di annullamento della registrazione.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Codice di risposta della richiesta di registrazione.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID diagnostica della richiesta di registrazione. Indica il tipo di informazioni diagnostiche.  <br/> |
|**DeviceId** <br/> |int  <br/> |Foreign  <br/> |Dispositivo da cui proviene la richiesta di registrazione. Per ulteriori informazioni, vedere la tabella Dispositivi Skype for Business Server [2015.](devices.md) <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |Motivo della deregistrazione, ad esempio "utente avviato", "registrazione scaduta", "client non riuscito" e altro ancora. Per ulteriori informazioni, vedere [la tabella DeRegisterType Skype for Business Server 2015.](deregistertype.md) <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||Indirizzo IP dell'endpoint con cui l'utente è registrato. Può essere un indirizzo IPv4 o IPv6.  <br/> Questo campo è stato introdotto in Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Per uso interno del servizio di monitoraggio.  <br/> Questo campo è stato introdotto Skype for Business Server 2015.  <br/> |
   

