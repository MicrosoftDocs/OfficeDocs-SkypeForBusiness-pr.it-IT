---
title: Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Quando si passa da un account utente a un server Skype for Business Server 2019, vengono spostate le informazioni seguenti con l'account utente seguente:"
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191147"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti

Quando un account utente viene spostato in un server di Skype for Business Server 2019, le informazioni seguenti vengono spostate con l'account utente seguente:
  
- **Riunioni già programmate dall'utente**. Questo include lo spostamento delle directory di conferenza e dei dati di conferenza.
    
- **Pin (Personal Identification Number) dell'utente**. Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.
    
Le informazioni dell'account utente seguenti non vengono spostati nel nuovo server.
  
- **Contenuto della riunione**. Per trasferire il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati del sondaggio, usa il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** . 
    

