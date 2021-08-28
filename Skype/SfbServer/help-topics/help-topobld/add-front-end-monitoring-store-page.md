---
title: Pagina per l'aggiunta dell'archivio di monitoraggio per Front End Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: "È possibile definire l'archivio SQL Server per il monitoraggio configurando le proprietà seguenti:"
ms.openlocfilehash: fca62973e1ad204b0ecc065297fb09a161494353
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628018"
---
# <a name="add-front-end-monitoring-store-page"></a>Pagina per l'aggiunta dell'archivio di monitoraggio di Front End Server
 
È possibile **definire l'archivio SQL Server per il monitoraggio** configurando le proprietà seguenti:
  
- **Monitoraggio SQL Server archivio**: selezionare un SQL Server di dominio completo (e, facoltativamente, un'istanza) dall'elenco.
    
    Fare **clic su** Nuovo per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio Monitoring Server.
    
- Selezionare la **casella SQL Server il mirroring dell'archivio** se si desidera aggiungere il mirroring del database per Monitoring Server.
    
    Selezionare un mirror archivio nell'elenco **Mirror archivio SQL Server monitoraggio**.
    
    Fare **clic su** Nuovo per creare una nuova SQL Server fqdn e facoltativamente un nome di istanza per l'archivio mirror.
    
- Se è stato selezionato **Abilita mirroring** SQL Server archivio , facoltativamente selezionare Usa il controllo del mirroring di SQL Server per abilitare il **failover** automatico per selezionare un archivio di controllo del mirroring SQL Server dall'elenco.
    
    Fare **clic su Nuovo** per creare una nuova SQL Server fqdn e facoltativamente un nome di istanza per l'archivio di controllo del mirroring.
    
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare clic su **Avanti** dopo avere specificato le opzioni per questa finestra di dialogo per continuare con la configurazione.
  
Fare clic su **Annulla** per annullare tutte le modifiche e terminare la procedura guidata.
  
Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Associare un archivio di monitoraggio a un pool Front End Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
