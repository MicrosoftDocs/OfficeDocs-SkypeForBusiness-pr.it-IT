---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for Business Server 2019 supporta distribuzioni multisito e multi-pool. Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti:'
ms.openlocfilehash: 05a94cb47568b9dfc3834f65f960353ad2933b03
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195009"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

Skype for Business Server 2019 supporta distribuzioni multisito e multi-pool. Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti: 
  
1. Dopo aver distribuito un pool pilota di Skype for Business Server 2019, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Skype for Business Server 2019 e una metodologia per la convalida della funzionalità degli utenti. Ad esempio, dopo lo spostamento di un utente nel pool pilota, verificare che il criterio di conferenza dell'utente sia stato spostato in Skype for Business Server 2019. 
    
2. Dopo la distribuzione di un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Skype for Business Server 2019.

3. La chat persistente, il mirroring SQL e la funzionalità XMPP sono deprecati in Skype for Business Server 2019 e non sono più disponibili come funzionalità di Skype for Business Server 2019, ma possono essere proseguiti in un ambiente di coesistenza se in precedenza sono stati distribuiti in un ambiente legacy. Se si vuole continuare a usare queste funzionalità, è consigliabile continuare con un ambiente di coesistenza in cui alcuni utenti rimarranno in pool legacy.
    
4. Dopo la transizione dei server Edge delle route federate ai server Edge pilota di Skype for Business Server 2019, è necessario verificare che gli utenti federati possano comunicare con il pool di Skype for Business Server 2019.
    
5. Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool legacy sia vuoto.
    
6. Dopo aver verificato che il pool legacy sia vuoto, è possibile disattivare il pool. 
    
    Per informazioni dettagliate su come disattivare il pool e i server legacy, vedere la [fase 8: rimuovere i pool legacy](phase-8-decommission-legacy-pools.md).
    

