---
title: Pagina per l'aggiunta dell'archivio di monitoraggio per Front End Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
ROBOTS: NOINDEX, NOFOLLOW
description: "È possibile definire l'archivio SQL Server per il monitoraggio configurando le proprietà seguenti:"
ms.openlocfilehash: 074d7aefa6e5b724d7266fbfb9d2b05dd558e4fc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766924"
---
# <a name="add-front-end-monitoring-store-page"></a>Pagina per l'aggiunta dell'archivio di monitoraggio di Front End Server
 
È possibile **definire l'archivio SQL Server per il monitoraggio** configurando le proprietà seguenti:
  
- **Monitoraggio SQL Server archivio**: selezionare un SQL Server di dominio completo (e, facoltativamente, un'istanza) dall'elenco.
    
    Fare **clic su** Nuovo per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio Monitoring Server.
    
- Selezionare la **casella SQL Server il mirroring dell'archivio** se si desidera aggiungere il mirroring del database per il Monitoring Server.
    
    Selezionare un mirror archivio nell'elenco **Mirror archivio SQL Server monitoraggio**.
    
    Fare **clic su** Nuovo per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio mirror.
    
- Se è stato selezionato Abilita **mirroring** SQL Server archivio , facoltativamente selezionare Usa controllo **del mirroring** di SQL Server per abilitare il failover automatico per selezionare un archivio di controllo del mirroring SQL Server dall'elenco.
    
    Fare **clic su Nuovo** per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio di controllo del mirroring.
    
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare clic su **Avanti** dopo avere specificato le opzioni per questa finestra di dialogo per continuare con la configurazione.
  
Fare clic su **Annulla** per annullare tutte le modifiche e terminare la procedura guidata.
  
Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Associare un archivio di monitoraggio a un pool Front End in Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
