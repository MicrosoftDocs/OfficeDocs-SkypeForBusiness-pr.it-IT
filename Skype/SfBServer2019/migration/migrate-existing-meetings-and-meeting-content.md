---
title: Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Quando si passa da un account utente a un server Skype for Business Server 2019, vengono spostate le informazioni seguenti con l'account utente seguente:"
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238512"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti

Quando un account utente viene spostato in un server di Skype for Business Server 2019, le informazioni seguenti vengono spostate con l'account utente seguente:
  
- **Riunioni già programmate dall'utente**. Questo include lo spostamento delle directory di conferenza e dei dati di conferenza.
    
- **Pin (Personal Identification Number) dell'utente**. Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.
    
Le informazioni dell'account utente seguenti non vengono spostati nel nuovo server.
  
- **Contenuto della riunione**. Per trasferire il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati del sondaggio, usa il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** . 
    

