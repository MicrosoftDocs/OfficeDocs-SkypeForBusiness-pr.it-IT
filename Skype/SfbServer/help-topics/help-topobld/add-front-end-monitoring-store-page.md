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
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: "È possibile definire l'archivio SQL Server per il monitoraggio configurando le proprietà seguenti:"
ms.openlocfilehash: 5f8a3ccb22aea1efde0b214b9afa61c140e63014
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803546"
---
# <a name="add-front-end-monitoring-store-page"></a>Pagina per l'aggiunta dell'archivio di monitoraggio di Front End Server
 
È possibile **definire l'archivio SQL Server per il monitoraggio** configurando le proprietà seguenti:
  
- **Monitoraggio dell'archivio SQL Server**: selezionare un nome di dominio completo di SQL Server (e, facoltativamente, un'istanza) dall'elenco.
    
    Fare clic su **nuovo** per creare una nuova definizione FQDN di SQL Server e facoltativamente un nome di istanza per l'archivio di Monitoring Server.
    
- Selezionare la casella di controllo **Abilita mirroring dell'archivio SQL Server** se si desidera aggiungere il mirroring del database per il Monitoring Server.
    
    Selezionare un mirror archivio nell'elenco **Mirror archivio SQL Server monitoraggio**.
    
    Fare clic su **nuovo** per creare una nuova definizione FQDN di SQL Server e facoltativamente un nome di istanza per l'archivio mirror.
    
- Se è stata selezionata l'opzione **Abilita mirroring dell'archivio SQL Server**, facoltativamente, selezionare Usa controllo del **mirroring di SQL Server per abilitare il failover automatico** per selezionare un archivio di controllo del mirroring di SQL Server nell'elenco.
    
    Fare clic su **nuovo** per creare una nuova definizione FQDN di SQL Server e facoltativamente un nome di istanza per l'archivio dei testimoni del mirroring.
    
Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.
  
Fare clic su **Avanti** dopo avere specificato le opzioni per questa finestra di dialogo per continuare con la configurazione.
  
Fare clic su **Annulla** per annullare tutte le modifiche e terminare la procedura guidata.
  
Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.
  
## <a name="see-also"></a>Vedere anche

[Associare un archivio di monitoraggio a un pool Front end in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
