---
title: Modifiche dello schema in Skype for Business Server
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
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Prima di distribuire e gestire Skype for Business Server, è necessario preparare i servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Skype for Business Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813576"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifiche dello schema in Skype for Business Server
 
Prima di distribuire e gestire Skype for Business Server, è necessario preparare i servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Skype for Business Server.

> [!NOTE]
> Se si esegue l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015, non vengono apportate modifiche allo schema e pertanto questo articolo non viene applicato.
  
Skype for Business Server richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti. Inoltre, molte informazioni di configurazione per Skype for Business Server sono archiviate nell'archivio di gestione centrale invece che in servizi di dominio Active Directory come nelle versioni precedenti. Le informazioni seguenti sono ancora memorizzate in servizi di dominio Active Directory in Skype for Business Server:
  
- **Estensioni dello schema**:
    
  - Estensioni degli oggetti utente
    
  - Estensioni per le classi per mantenere la compatibilità con le versioni precedenti supportate di Lync Server.
    
- **Dati** (archiviati in Skype for Business Server Extended schema e nelle classi dello schema esistenti):
    
  - URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente
    
  - Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza
    
  - Puntatore all'archivio di gestione centrale
    
  - Account di autenticazione Kerberos (un oggetto computer facoltativo)
    
In questo argomento vengono descritte le modifiche allo schema di Active Directory richieste da Skype for Business Server. Non vengono descritte le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server. Per un elenco delle classi e delle relative descrizioni, vedere [classi di schema e descrizioni in Skype for Business Server](schema-classes-and-descriptions.md). Per un elenco degli attributi e delle relative descrizioni, vedere [attributi e descrizioni dello schema in Skype for Business Server](schema-attributes-and-descriptions.md). Per un elenco di classi con gli attributi che possono contenere, vedere [schema Attributes by Class in Skype for Business Server](schema-attributes-by-class.md).
  
Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Skype for Business Server.
  
## <a name="new-active-directory-attributes"></a>Nuovi attributi di Active Directory

Nella tabella seguente vengono descritti gli attributi di Active Directory aggiunti da Skype for Business Server.
  
**Attributi aggiunti da Skype for Business Server**

|**Attributo**|**Descrizione**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente. I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco. Questo attributo è condiviso con Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Questo è l'ID del gruppo di routing SIP. Gli utenti dello stesso gruppo registreranno lo stesso front end server.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classi di Active Directory modificate

Nella tabella seguente vengono descritte le classi di Active Directory modificate da Skype for Business Server.
  
**Classi modificate da Skype for Business Server**

|**Classe**|**Modifica**|**Classe o attributo**|
|:-----|:-----|:-----|
|Utente  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contatto  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

