---
title: Qual è lo stato degli ordini di portabilità?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Learn how to get the status of your port orders, and what the different actions you can take on them. '
ms.openlocfilehash: 8290ffba7be56f3ede0e275c801110f8c9d9539e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44205687"
---
# <a name="whats-the-status-of-your-port-orders"></a>Qual è lo stato degli ordini di portabilità?

Per visualizzare lo stato dell'ordine di trasferimento, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare > **Ordini** di trasferimento vocale e quindi fare clic su Cronologia  >   **ordini.** Ogni stato dell'ordine di trasferimento è elencato nella **colonna** Stato. Vedere [quanto tempo è necessario per i numeri di portabilità](../phone-number-calling-plans/port-order-overview.md#how-long-does-it-take-to-port-numbers) per informazioni sul processo di ordine. 

La tabella seguente elenca gli stati degli ordini di trasferimento e le azioni che è possibile eseguire, se necessario.

|**Stato**|**È possibile visualizzare l'ordine?**|**È possibile modificare l'ordine?**|**È possibile annullare l'ordine?**|**È possibile eliminare l'ordine?**|**Descrizione**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Elaborazione in corso** <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |No  <br/> |L'amministratore ha creato l'ordine ed è stato ricevuto da Microsoft.  <br/> |
|**Operatore di contatto** <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |No  <br/> |L'ordine è stato ricevuto e approvato da Microsoft e stiamo lavorando con il gestore perdente per ottenerlo approvato.  <br/> |
|**Trasferimento approvato** <br/> |Sì  <br/> |No  <br/> |Sì  <br/> |No  <br/> |L'ordine è stato accettato dal gestore perdente e la data FOC (Firm Order Commitment) è stata impostata.  <br/> |
|**Trasferimento in sospeso** <br/> |Sì  <br/> |No  <br/> |No  <br/> |No  <br/> |Il trasferimento è di meno di 24 ore, quindi l'ordine non può più essere modificato o annullato.  <br/> |
|**Errore** <br/> |No  <br/> |Sì  <br/> |Sì  <br/> |Sì (al momento non è possibile eliminare l'ordine di trasferimento in caso di errore. L'ordine di trasferimento deve essere ri-creato oppure è necessario contattare l'assistenza [del service desk PSTN.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)  <br/> |Il corriere perdente ha rifiutato l'ordine.  <br/> |
|**Completato** <br/> |Sì  <br/> |No  <br/> |No  <br/> |No  <br/> |I numeri sono stati trasferiti correttamente.  <br/> |
|**Annullato** <br/> |No  <br/> |Sì  <br/> |No  <br/> |No  <br/> |L'amministratore ha annullato l'ordine.  <br/> |

Per istruzioni dettagliate, vedere Trasferire i numeri di telefono Teams [.](transfer-phone-numbers-to-teams.md)

Se serve assistenza o se è necessario ottenere altri numeri di telefono, contattare il [service desk PSTN.](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)

## <a name="related-topics"></a>Argomenti correlati

- [Cos'è un ordine di portabilità?](port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Etichetta di esclusione di responsabilità per chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
