---
title: Schema del database Chat persistente
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
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Questo documento documenta lo schema del database di Persistent Chat in Skype for Business Server.
ms.openlocfilehash: ba50f4391ce35d8a938318e96e1483bbfe0e3dfa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809876"
---
# <a name="persistent-chat-database-schema"></a>Schema del database Chat persistente
 
Questo documento documenta lo schema del database di Persistent Chat in Skype for Business Server.
  
Il database di Persistent Chat fa riferimento al database corrispondente ai ruoli **PersistentChatStore** (corrispondente al database mgc) e **PersistentChatComplianceStore** (corrispondente al database mgccomp) di Skype for Business Server. L'obiettivo della pubblicazione di questo schema è di consentire la creazione di query per comprendere meglio come generare rapporti efficaci relativi all'uso della chat, alle chat attive, agli autori di post più attivi e così via.
  
> [!IMPORTANT]
> Ci riserviamo il diritto di modificare questo schema. Microsoft non garantisce di poter mantenere la completa compatibilità di questo schema pubblicato con le versioni precedenti. 
  
Tenere presenti queste procedure consigliate:
  
- L'istruzione SELECT \* // non è supportata perché l'elenco di colonne può aumentare.
    
- Non sono supportate modifiche allo schema generate dall'utente.
    
- Non sono supportate operazioni di scrittura
    
- Testare le query create con database di dimensioni rappresentative, per assicurarsi che le prestazioni soddisfino le esigenze.
    
## <a name="in-this-section"></a>Contenuto della sezione

- [Elenco di tabelle del server Chat persistente](list-of-persistent-chat-server-tables.md)
    
- [Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Dettagli delle tabelle di Chat persistente](persistent-chat-server-table-details.md)
    
- [Query del database Chat persistente di esempio](sample-persistent-chat-database-queries.md)
    

