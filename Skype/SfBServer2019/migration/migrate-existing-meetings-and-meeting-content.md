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
description: 'Quando un account utente viene spostato da un server Skype for Business Server 2019, con tale account utente vengono spostate le informazioni seguenti:'
ms.openlocfilehash: e28cbce30608672d27578cfaa5ab92dbe1ed3c4cd6b234da7389b1f9a6978350
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312294"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti

Quando un account utente viene spostato in un server Skype for Business Server 2019, con tale account utente vengono spostate le informazioni seguenti:
  
- **Le riunioni già pianificate dall'utente**. Vengono spostate anche le directory e i dati delle conferenze.
    
- **PIN (Personal Identification Number) dell'utente.** Il PIN corrente dell'utente continua a funzionare finché non scade o l'utente richiede un nuovo PIN.
    
Le seguenti informazioni sull'account utente non vengono spostate nel nuovo server.
  
- **Contenuto delle riunioni**. Per spostare il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati di polling, utilizzare il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser.** 
    

