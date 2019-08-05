---
title: Modifiche allo schema in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Prima di distribuire e gestire Skype for Business Server, è necessario preparare i servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Skype for Business Server.
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194859"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifiche allo schema in Skype for Business Server
 
Prima di distribuire e gestire Skype for Business Server, è necessario preparare i servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Skype for Business Server.

> [!NOTE]
> Se si esegue l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015, non vengono apportate modifiche allo schema e pertanto questo articolo non si applica.
  
Skype for Business Server richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti. Inoltre, molte informazioni di configurazione per Skype for Business Server sono archiviate nell'archivio di gestione centrale anziché in servizi di dominio Active Directory come nelle versioni precedenti. Le informazioni seguenti sono ancora archiviate in servizi di dominio Active Directory in Skype for Business Server:
  
- **Estensioni dello schema**:
    
  - Estensioni degli oggetti utente
    
  - Estensioni per le classi per mantenere la compatibilità con le versioni precedenti supportate di Lync Server.
    
- **Dati** (archiviato in Skype for Business Server Extended schema e nelle classi dello schema esistenti):
    
  - URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente
    
  - Oggetti contatto per applicazioni come Response Group e operatore di conferenza
    
  - Un puntatore all'archivio di gestione centrale
    
  - Account di autenticazione Kerberos (un oggetto computer facoltativo)
    
Questo argomento descrive le modifiche allo schema di Active Directory richieste da Skype for Business Server. Non descrive le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server. Per un elenco delle classi e delle relative descrizioni, vedere [classi di schema e descrizioni in Skype for Business Server](schema-classes-and-descriptions.md). Per un elenco degli attributi e delle relative descrizioni, vedere [attributi e descrizioni dello schema in Skype for Business Server](schema-attributes-and-descriptions.md). Per un elenco di classi con gli attributi che possono contenere, Vedi [attributi dello schema per classe in Skype for Business Server](schema-attributes-by-class.md).
  
Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Skype for Business Server.
  
## <a name="new-active-directory-attributes"></a>Nuovi attributi di Active Directory

La tabella seguente descrive gli attributi di Active Directory aggiunti da Skype for Business Server.
  
**Attributi aggiunti da Skype for Business Server**

|**Attributo**|**Descrizione**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente. I criteri di blocco mantengono gli elementi della cassetta postale per l'utente per la durata del blocco. Questo attributo è condiviso con Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Questo è l'ID del gruppo di routing SIP. Gli utenti nello stesso gruppo registreranno lo stesso server front-end.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Questo attributo viene usato per archiviare il backend di SQL Server con mirroring usato dal pool Front-end.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classi di Active Directory modificate

La tabella seguente descrive le classi Active Directory modificate da Skype for Business Server.
  
**Classi modificate da Skype for Business Server**

|**Classe**|**Modificare**|**Classe o attributo**|
|:-----|:-----|:-----|
|Utente  <br/> |Aggiungi: mayContain  <br/> Aggiungi: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contatto  <br/> |Aggiungi: mayContain  <br/> Aggiungi: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinatario della posta elettronica  <br/> |Aggiungi: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Aggiungi: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

