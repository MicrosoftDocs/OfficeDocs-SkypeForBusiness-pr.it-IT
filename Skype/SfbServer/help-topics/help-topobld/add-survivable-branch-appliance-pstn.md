---
title: Aggiungere l'indirizzo PSTN di Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Per definire il gateway PSTN (Public Switched Telephone Network) per un Survivable Branch Appliance in un sito di succursale, specificare quanto segue:'
ms.openlocfilehash: 65731fe7227f0aaba485ecf27c1493df120379e2ae8224eaf471c2f557e61479
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307217"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Aggiungere indirizzo PSTN di Survivable Branch Appliance
 
Per definire il gateway PSTN (Public Switched Telephone Network) per un Survivable Branch Appliance in un sito di succursale, specificare quanto segue: 
  
- Un nome di dominio completo (FQDN) o un indirizzo IP per il peer gateway a cui il Survivable Branch Appliance o il Survivable Branch Server è associato per il routing delle chiamate PSTN in ingresso e in uscita.
    
    > [!IMPORTANT]
    > Se si sta definendo un Survivable Branch Appliance, questo è il gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN. 
  
- La porta di attesa da utilizzare per i messaggi SIP (Session Initiation Protocol). Per impostazione predefinita, le porte sono la 5066 per TCP (Transmission Control Protocol) e la 5067 per TLS (Transport Layer Security) in un gateway, un centralino (PBX) o un Session Border Controller (SBC). In un Survivable Branch Appliance presso un sito di succursale le porte predefinite sono la 5081 per TCP e la 5082 per TLS.
    
- Per motivi di sicurezza, è consigliabile usare TLS. Se si sta definendo un Survivable Branch Appliance, consultare la documentazione del relativo fornitore per verificare che supporti il protocollo TLS.
    
    > [!IMPORTANT]
    > Per motivi di sicurezza, è consigliabile distribuire un gateway che supporti TLS. 
  
> [!NOTE]
> Se si vuole aggiungere un gateway PSTN, sarà possibile configurarlo in un secondo momento, ma la funzionalità sarà limitata finché il gateway PSTN non verrà definito e configurato. 
  

