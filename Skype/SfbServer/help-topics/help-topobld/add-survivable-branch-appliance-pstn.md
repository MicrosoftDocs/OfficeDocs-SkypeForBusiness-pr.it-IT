---
title: Aggiungere l'indirizzo PSTN di Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Per definire il gateway PSTN (Public Switched Telephone Network) per un Survivable Branch Appliance in un sito di succursale, specificare quanto segue:'
ms.openlocfilehash: d5ba39a79f7810a64776efcd7b7c47488fe93d2b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697951"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Aggiungere l'indirizzo PSTN di Survivable Branch Appliance
 
Per definire il gateway PSTN (Public Switched Telephone Network) per un Survivable Branch Appliance in un sito di succursale, specificare quanto segue: 
  
- Un nome di dominio completo (FQDN) o un indirizzo IP per il peer del gateway a cui è associato il Survivable Branch Appliance o Survivable Branch Server per il routing delle chiamate PSTN in ingresso e in uscita.
    
    > [!IMPORTANT]
    > Se si definisce un Survivable Branch Appliance, si tratta del gateway a cui il Mediation Server all'interno del Survivable Branch Appliance si connetterà per la connettività PSTN. 
  
- La porta di attesa da utilizzare per i messaggi SIP (Session Initiation Protocol). Per impostazione predefinita, le porte sono la 5066 per TCP (Transmission Control Protocol) e la 5067 per TLS (Transport Layer Security) in un gateway, un centralino (PBX) o un Session Border Controller (SBC). In un Survivable Branch Appliance presso un sito di succursale le porte predefinite sono la 5081 per TCP e la 5082 per TLS.
    
- Per motivi di sicurezza, è consigliabile utilizzare TLS. Se si definisce un Survivable Branch Appliance, vedere la documentazione del fornitore di Survivable Branch Appliance per verificare che il Survivable Branch Appliance supporti il protocollo TLS.
    
    > [!IMPORTANT]
    > Per motivi di sicurezza, è consigliabile distribuire un gateway che supporti TLS. 
  
> [!NOTE]
> Se si vuole aggiungere un gateway PSTN, sarà possibile configurarlo in un secondo momento, ma la funzionalità sarà limitata finché il gateway PSTN non verrà definito e configurato. 
  

