---
title: Preparare un singolo server Standard Edition (Intro)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Per avviare l'installazione di un server Skype for Business Server edizione Standard che contenerà l'archivio di gestione centrale e altri servizi collocati selezionati, è necessario essere connessi come membri del gruppo Administrators locale nel server che diventerà il server edizione Standard. Nella pagina Prepara singolo server Standard sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
ms.openlocfilehash: e08a902177ba4ca2ccb149436141f16f45eca5b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742842"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparare un singolo server Standard Edition (Intro)
 
Per avviare l'installazione di un server Skype for Business Server edizione Standard che contenerà l'archivio di gestione centrale e altri servizi collocati selezionati, è necessario essere connessi come membri del gruppo Administrators locale nel server che diventerà il server edizione Standard. Nella pagina **Prepara singolo server Standard** sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
  
Questa particolare attività è progettata per configurare un server edizione Standard come primo server dell'infrastruttura. Questa attività installa l'archivio di gestione centrale, che SQL Server Express, nel server edizione Standard server. Se è già stato distribuito un altro edizione Standard server o pool Front End, fare clic su **Annulla.**
  
> [!NOTE]
> Dopo aver completato questa attività, si installerà Generatore di topologie (se non è già stato installato) e si configurerà il documento della topologia. Non sarà possibile pubblicare tale documento finché non è disponibile un archivio di gestione centrale, che viene distribuito eseguendo l'attività descritta in questo argomento. 
  

