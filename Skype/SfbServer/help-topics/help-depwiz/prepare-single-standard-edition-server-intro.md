---
title: Preparare un singolo server Standard Edition (Intro)
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 'Per avviare l''installazione di un server edizione Standard di Skype for Business Server 2015 che contenerà l''archivio di gestione centrale e altri servizi collocati selezionati, è necessario essere connessi come membri del gruppo Administrators locale nel server che diventerà il server edizione Standard. Nella pagina Prepara singolo server Standard sono illustrati i requisiti per l''installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.'
---

# <a name="prepare-single-standard-edition-server-intro"></a>Preparare un singolo server Standard Edition (Intro)
 
Per avviare l'installazione di un server edizione Standard di Skype for Business Server 2015 che contenerà l'archivio di gestione centrale e altri servizi collocati selezionati, è necessario essere connessi come membri del gruppo Administrators locale nel server che diventerà il server edizione Standard. Nella pagina **Prepara singolo server Standard** sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
  
Questa particolare attività è progettata per configurare un server edizione Standard come primo server dell'infrastruttura. Questa attività installa l'archivio di gestione centrale, che SQL Server Express, nel server edizione Standard centrale. Se è già stato distribuito un altro edizione Standard server o pool Front End, fare clic su **Annulla**.
  
> [!NOTE]
> Dopo aver completato questa attività, si installerà Generatore di topologie (se non è già stato installato) e si configurerà il documento della topologia. Non sarà possibile pubblicare tale documento finché non è disponibile un archivio di gestione centrale, che viene distribuito eseguendo l'attività descritta in questo argomento. 
  

