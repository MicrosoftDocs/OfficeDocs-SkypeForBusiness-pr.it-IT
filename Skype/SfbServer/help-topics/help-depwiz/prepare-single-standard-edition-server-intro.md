---
title: Preparare un singolo server Standard Edition (Intro)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: Per iniziare l'installazione di un server Skype for Business Server 2015 Standard Edition che contenerà l'archivio di gestione centrale e altri servizi collocati selezionati, è necessario essere connessi come membri del gruppo Administrators locale nel server che diventerà il server Standard Edition. Nella pagina Prepara singolo server Standard sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
ms.openlocfilehash: 0523645350c6d6f2c0e42237b944f29193e06555
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829786"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="c36db-105">Preparare un singolo server Standard Edition (Intro)</span><span class="sxs-lookup"><span data-stu-id="c36db-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="c36db-106">Per iniziare l'installazione di un server Skype for Business Server 2015 Standard Edition che contenerà l'archivio di gestione centrale e altri servizi collocati selezionati, è necessario essere connessi come membri del gruppo Administrators locale nel server che diventerà il server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c36db-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="c36db-107">Nella pagina **Prepara singolo server Standard** sono illustrati i requisiti per l'installazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="c36db-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="c36db-108">Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.</span><span class="sxs-lookup"><span data-stu-id="c36db-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="c36db-109">Questa particolare attività è progettata per configurare un server Standard Edition come primo server dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="c36db-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="c36db-110">Questa attività consente di installare l'archivio di gestione centrale, SQL Server Express, nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c36db-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="c36db-111">Se è già stato distribuito un altro server Standard Edition o pool Front End, fare clic su **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="c36db-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c36db-112">Dopo aver completato questa attività, sarà necessario installare Generatore di topologie (se non è già stato installato) e configurare il documento della topologia.</span><span class="sxs-lookup"><span data-stu-id="c36db-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="c36db-113">Non sarà possibile pubblicare tale documento finché non è disponibile un archivio di gestione centrale, che viene distribuito eseguendo l'attività descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c36db-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

