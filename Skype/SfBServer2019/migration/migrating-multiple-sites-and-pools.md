---
title: Migrazione di più siti e pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server 2019 supporta le distribuzioni multisito e multi-pool. Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752658"
---
# <a name="migrating-multiple-sites-and-pools"></a>Migrazione di più siti e pool

Skype for Business Server 2019 supporta le distribuzioni multisito e multi-pool. Il processo di migrazione di più pool a Skype for Business Server 2019 richiede le considerazioni seguenti: 
  
1. Dopo aver distribuito un pool pilota di Skype for Business Server 2019, è necessario definire un sottoinsieme di utenti pilota che verranno spostati nel pool di Skype for Business Server 2019 e una metodologia per la convalida della funzionalità degli utenti. Ad esempio, dopo lo spostamento di un utente nel pool pilota, verificare che i criteri di conferenza dell'utente siano stati spostati in Skype for Business Server 2019. 
    
2. Dopo aver distribuito un server perimetrale nel pool pilota, è necessario verificare che gli utenti esterni possano comunicare con il pool di Skype for Business Server 2019.

3. La chat persistente, il mirroring SQL e la funzionalità XMPP sono deprecati in Skype for Business Server 2019 e non sono più disponibili come funzionalità di Skype for Business Server 2019, ma possono essere continuati in un ambiente di coesistenza se sono stati precedentemente distribuiti in un ambiente legacy. Se si desidera continuare a utilizzare queste funzionalità, è consigliabile pianificare la prosecuzione di un ambiente di coesistenza in cui alcuni utenti rimarranno nei pool legacy.
    
4. Dopo aver eseguito la transizione dei server perimetrali delle route federate ai server Edge di Skype for Business Server 2019 pilota, è necessario verificare che gli utenti federati possano comunicare con il pool di Skype for Business Server 2019.
    
5. Dopo aver spostato tutti gli utenti e gli oggetti contatto non utente, è necessario verificare che il pool legacy sia vuoto.
    
6. Dopo aver verificato che il pool legacy è vuoto, sarà possibile disattivare il pool. 
    
    Per informazioni dettagliate su come disattivare i server e il pool legacy, vedere [Phase 8: decommission legacy pools](phase-8-decommission-legacy-pools.md).
    

