---
title: Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti
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
description: 'Quando un account utente viene spostato da un server Skype for Business Server 2019, le seguenti informazioni vengono spostate con tale account utente:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752688"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti

Quando un account utente viene spostato in un server Skype for Business Server 2019, le seguenti informazioni vengono spostate con tale account utente:
  
- **Le riunioni già pianificate dall'utente**. Vengono spostate anche le directory e i dati delle conferenze.
    
- **PIN (Personal Identification Number) dell'utente.** Il PIN corrente dell'utente continua a funzionare fino alla scadenza o fino alla richiesta di un nuovo PIN.
    
Le seguenti informazioni sull'account utente non vengono spostate nel nuovo server.
  
- **Contenuto delle riunioni**. Per spostare il contenuto condiviso durante una riunione, ad esempio PowerPoint, Lavagna, allegati o dati di polling, utilizzare il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser.** 
    

