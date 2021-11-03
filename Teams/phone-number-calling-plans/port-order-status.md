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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Learn how to get the status of your port orders, and what the different actions you can take on them. '
ms.openlocfilehash: 3699a7ccbc2aa7a54c70c9cd99c9277f56ea40fc
ms.sourcegitcommit: bf350ea47032bd926e75a5433eadce3905e731ca
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2021
ms.locfileid: "60733097"
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
|**Errore** <br/> |No  <br/> |Sì  <br/> |Sì  <br/> |Sì (al momento non è possibile eliminare l'ordine di trasferimento in caso di errore. L'ordine di trasferimento deve essere ri-creato oppure è necessario contattare [il service desk TNS.](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)  <br/> |Il corriere perdente ha rifiutato l'ordine.  <br/> |
|**Completato** <br/> |Sì  <br/> |No  <br/> |No  <br/> |No  <br/> |I numeri sono stati trasferiti correttamente.  <br/> |
|**Annullato** <br/> |No  <br/> |Sì  <br/> |No  <br/> |No  <br/> |L'amministratore ha annullato l'ordine.  <br/> |

Per istruzioni dettagliate, vedere Trasferire i numeri di telefono Teams [.](transfer-phone-numbers-to-teams.md)

Se hai bisogno di assistenza o se hai bisogno di ottenere più numeri di telefono, contatta [il TNS Service Desk.](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="related-topics"></a>Argomenti correlati

- [Cos'è un ordine di portabilità?](port-order-overview.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Gestire i numeri di telefono per la propria organizzazione](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Termini e condizioni per le chiamate al numero di emergenza](../emergency-calling-terms-and-conditions.md)
- [Dichiarazione di esonero da responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
