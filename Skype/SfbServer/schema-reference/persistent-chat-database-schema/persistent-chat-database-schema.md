---
title: Schema del database Chat persistente
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
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: In questo modo viene documentato lo schema del database di Persistent Chat in Skype for Business Server.
ms.openlocfilehash: 6f35e947f1cc0c36d6be743d57934453053f4e5c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759348"
---
# <a name="persistent-chat-database-schema"></a>Schema del database Chat persistente
 
In questo modo viene documentato lo schema del database di Persistent Chat in Skype for Business Server.
  
Il database di Persistent Chat fa riferimento al database corrispondente ai ruoli del server back-end Skype for Business Server **PersistentChatStore** (corrispondente al database mgc) e **PersistentChatComplianceStore** (corrispondente al database mgccomp). L'obiettivo della pubblicazione di questo schema è di consentire la creazione di query per comprendere meglio come generare rapporti efficaci relativi all'uso della chat, alle chat attive, agli autori di post più attivi e così via.
  
> [!IMPORTANT]
> Ci riserviamo il diritto di modificare questo schema. Microsoft non garantisce di poter mantenere la completa compatibilità di questo schema pubblicato con le versioni precedenti. 
  
Tenere presenti queste procedure consigliate:
  
- Non è supportata \* l'opzione SELECT // perché l'elenco di colonne può aumentare.
    
- Non sono supportate modifiche allo schema generate dall'utente.
    
- Non sono supportate operazioni di scrittura
    
- Testare le query create con database di dimensioni rappresentative, per assicurarsi che le prestazioni soddisfino le esigenze.
    
## <a name="in-this-section"></a>Contenuto della sezione

- [Elenco di tabelle del server Chat persistente](list-of-persistent-chat-server-tables.md)
    
- [Elenco delle tabelle di conformità del server Chat persistente in Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Dettagli delle tabelle di Chat persistente](persistent-chat-server-table-details.md)
    
- [Query del database Chat persistente di esempio](sample-persistent-chat-database-queries.md)
    

