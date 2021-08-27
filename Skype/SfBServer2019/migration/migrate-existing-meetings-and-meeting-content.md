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
ms.localizationpriority: medium
description: 'Quando un account utente viene spostato da un server Skype for Business Server 2019, con tale account utente vengono spostate le informazioni seguenti:'
ms.openlocfilehash: 826b511250e46e2c87720a5b074b43cd545b15c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589302"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti

Quando un account utente viene spostato in un server Skype for Business Server 2019, con tale account utente vengono spostate le informazioni seguenti:
  
- **Le riunioni già pianificate dall'utente**. Vengono spostate anche le directory e i dati delle conferenze.
    
- **PIN (Personal Identification Number) dell'utente.** Il PIN corrente dell'utente continua a funzionare finché non scade o l'utente richiede un nuovo PIN.
    
Le seguenti informazioni sull'account utente non vengono spostate nel nuovo server.
  
- **Contenuto delle riunioni**. Per spostare il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati di polling, utilizzare il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser.** 
    

