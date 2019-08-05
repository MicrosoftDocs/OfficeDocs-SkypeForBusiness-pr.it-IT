---
title: Preparare un singolo server Standard Edition (Intro)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione di un server di Skype for Business Server Standard Edition che conterrà l'Central Management store e altri servizi collocati selezionati, è necessario avere effettuato l'accesso come membro del gruppo Administrators locale nel server che diventerà Server Standard Edition. Nella pagina Prepara singolo server Standard sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
ms.openlocfilehash: 93f10f486a7d7541fe28cf5ce03a4e642afa2d0b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187316"
---
# <a name="prepare-single-standard-edition-server-intro"></a>Preparare un singolo server Standard Edition (Intro)
 
Per iniziare l'installazione di un server di Skype for Business Server Standard Edition che conterrà l'Central Management store e altri servizi collocati selezionati, è necessario avere effettuato l'accesso come membro del gruppo Administrators locale nel server che diventerà Server Standard Edition. Nella pagina **Prepara singolo server Standard** sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
  
Questa specifica attività è progettata per configurare un server Standard Edition come primo server dell'infrastruttura. Questa attività consente di installare l'Central Management store, che è SQL Server Express, nel server Standard Edition. Se è già stato distribuito un altro server standard o un pool Front-End, fare clic su **Annulla**.
  
> [!NOTE]
> Dopo aver completato questa attività, si installerà generatore di topologie (se non è già stato installato) e si configura il documento della topologia. Non sarà possibile pubblicare tale documento finché non è disponibile un archivio di gestione centrale, che viene distribuito eseguendo l'attività descritta in questo argomento. 
  

