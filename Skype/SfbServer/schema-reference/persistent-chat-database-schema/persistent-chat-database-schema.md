---
title: Schema del database di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
description: Questo documenta lo schema del database della chat persistente in Skype for Business Server.
ms.openlocfilehash: 9a3e09a03f764f8866865e08259cbaac12a1c554
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194712"
---
# <a name="persistent-chat-database-schema"></a>Schema del database di Chat persistente
 
Questo documenta lo schema del database della chat persistente in Skype for Business Server.
  
Il database della chat persistente si riferisce al database corrispondente ai ruoli del server back-end di Skype for Business Server **PersistentChatStore** (corrispondente al database mgc) e **PersistentChatComplianceStore** (corrispondente al database di mgccomp). L'obiettivo della pubblicazione di questo schema è quello di consentire la creazione di query e acquisire alcune informazioni utili per la creazione di una segnalazione utile intorno all'utilizzo della chat, alle sale attive, ai poster principali e così via.
  
> [!IMPORTANT]
> Ci riserviamo il diritto di evolvere questo schema. Microsoft non garantisce di mantenere la compatibilità completa con questo schema pubblicato. 
  
Seguire queste procedure consigliate:
  
- Nessun SELECT\* //è supportato perché l'elenco di colonne può aumentare.
    
- Non sono supportate modifiche allo schema generate dall'utente.
    
- Non sono supportate operazioni di scrittura.
    
- Testare le query che si compilano su database di dimensioni rappresentative per verificare che le query possano essere eseguite a un livello per soddisfare le proprie esigenze.
    
## <a name="in-this-section"></a>In questa sezione

- [Elenco delle tabelle del server Chat persistente](list-of-persistent-chat-server-tables.md)
    
- [Elenco delle tabelle di conformità Persistent Chat Server in Skype for Business Server](list-of-persistent-chat-server-compliance-tables.md)
    
- [Dettagli sulle tabelle del server Chat persistente](persistent-chat-server-table-details.md)
    
- [Query del database di Chat persistente di esempio](sample-persistent-chat-database-queries.md)
    

