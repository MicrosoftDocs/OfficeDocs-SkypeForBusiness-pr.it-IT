---
title: Modifiche allo schema in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Prima di distribuire e Skype for Business Server, è necessario preparare Servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi necessari per Skype for Business Server.
ms.openlocfilehash: 000aad35a546556a2a6bceaedc0d0fdb9deb2420
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743282"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifiche allo schema in Skype for Business Server
 
Prima di distribuire e Skype for Business Server, è necessario preparare Servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi necessari per Skype for Business Server.

> [!NOTE]
> Se si esegue l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015, non vengono apportate modifiche allo schema e pertanto questo articolo non è applicabile.
  
Skype for Business Server richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti. Inoltre, molte informazioni di configurazione per Skype for Business Server vengono archiviate nell'archivio di gestione centrale anziché in Servizi di dominio Active Directory come nelle versioni precedenti. Le informazioni seguenti sono ancora archiviate in Servizi di dominio Active Directory in Skype for Business Server:
  
- **Estensioni dello schema**:
    
  - Estensioni degli oggetti utente
    
  - Estensioni per le classi per mantenere la compatibilità con le versioni precedenti supportate di Lync Server.
    
- **Dati** (archiviati in Skype for Business Server schema esteso e in classi di schema esistenti):
    
  - URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente
    
  - Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza
    
  - Puntatore all'archivio di gestione centrale
    
  - Account di autenticazione Kerberos (un oggetto computer facoltativo)
    
In questo argomento vengono descritte le modifiche dello schema di Active Directory richieste da Skype for Business Server. Non vengono descritte le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server. Per un elenco delle classi e delle relative descrizioni, vedere Classi e [descrizioni](schema-classes-and-descriptions.md)dello schema in Skype for Business Server . Per un elenco degli attributi e delle relative descrizioni, vedere Attributi e descrizioni dello [schema in Skype for Business Server](schema-attributes-and-descriptions.md). Per un elenco delle classi con gli attributi che possono contenere, vedere [Attributi dello schema per](schema-attributes-by-class.md)classe in Skype for Business Server .
  
Il prefisso msRTCSIP identifica le classi e gli attributi specifici per Skype for Business Server.
  
## <a name="new-active-directory-attributes"></a>Nuovi attributi di Active Directory

Nella tabella seguente vengono descritti gli attributi di Active Directory aggiunti da Skype for Business Server.
  
**Attributi aggiunti da Skype for Business Server**

|**Attributo**|**Descrizione**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Questo attributo multivalore contiene gli identificatori per i criteri di blocco applicabili all'utente. I criteri di conservazione mantengono gli elementi delle cassette postali per l'utente per tutta la durata del blocco. Questo attributo è condiviso con Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Questo è l'ID del gruppo di routing SIP. Gli utenti dello stesso gruppo verranno registrati nello stesso Front End Server.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Questo attributo viene utilizzato per archiviare il SQL Server back-end con mirroring utilizzato dal pool Front End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classi di Active Directory modificate

Nella tabella seguente vengono descritte le classi di Active Directory modificate da Skype for Business Server.
  
**Classi modificate da Skype for Business Server**

|**Classe**|**Modifica**|**Classe o attributo**|
|:-----|:-----|:-----|
|User  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contatto  <br/> |add: mayContain  <br/> add: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

