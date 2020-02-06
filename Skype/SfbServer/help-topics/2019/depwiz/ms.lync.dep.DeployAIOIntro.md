---
title: Preparare un singolo server Standard Edition (Intro)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione di un server di Skype for Business Server Standard Edition che conterrà l'Central Management store e altri servizi collocati selezionati, è necessario avere effettuato l'accesso come membro del gruppo Administrators locale nel server che diventerà Server Standard Edition. Nella pagina Prepara singolo server Standard sono illustrati i requisiti per l'installazione iniziale. Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.
ms.openlocfilehash: 437f90fa99efa920479e7c0dc966c3c63fd5eed1
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796977"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="03e35-105">Preparare un singolo server Standard Edition (Intro)</span><span class="sxs-lookup"><span data-stu-id="03e35-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="03e35-106">Per iniziare l'installazione di un server di Skype for Business Server Standard Edition che conterrà l'Central Management store e altri servizi collocati selezionati, è necessario avere effettuato l'accesso come membro del gruppo Administrators locale nel server che diventerà Server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="03e35-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="03e35-107">Nella pagina **Prepara singolo server Standard** sono illustrati i requisiti per l'installazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="03e35-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="03e35-108">Il computer deve essere membro del dominio in cui verrà distribuito ed è necessario aver completato per la foresta la preparazione dello schema, della foresta e del dominio.</span><span class="sxs-lookup"><span data-stu-id="03e35-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="03e35-109">Questa specifica attività è progettata per configurare un server Standard Edition come primo server dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="03e35-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="03e35-110">Questa attività consente di installare l'Central Management store, che è SQL Server Express, nel server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="03e35-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="03e35-111">Se è già stato distribuito un altro server standard o un pool Front-End, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="03e35-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03e35-112">Dopo aver completato questa attività, si installerà generatore di topologie (se non è già stato installato) e si configura il documento della topologia.</span><span class="sxs-lookup"><span data-stu-id="03e35-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="03e35-113">Non sarà possibile pubblicare tale documento finché non è disponibile un archivio di gestione centrale, che viene distribuito eseguendo l'attività descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="03e35-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

