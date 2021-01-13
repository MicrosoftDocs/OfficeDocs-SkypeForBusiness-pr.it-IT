---
title: Patch o aggiornare un server back-end o un server Standard Edition in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Riepilogo: informazioni su come installare un aggiornamento o una patch su un server back-end in Skype for Business Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826306"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="fc569-103">Patch o aggiornare un server back-end o un server Standard Edition in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fc569-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="fc569-104">**Riepilogo:** Informazioni su come installare un aggiornamento o una patch su un server back-end in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc569-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="fc569-105">In questo argomento viene descritto come installare un aggiornamento in un server di back-end Enterprise Edition o in un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="fc569-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="fc569-106">Se un server back-end è inverso verso il basso per almeno 30 minuti mentre lo si sta aggiornando, gli utenti possono accedere alla modalità di resilienza.</span><span class="sxs-lookup"><span data-stu-id="fc569-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="fc569-107">Al termine dell'aggiornamento e i server back-end sono di nuovo connessi con i Front End Server nel pool, gli utenti vengono restituiti alla funzionalità completa.</span><span class="sxs-lookup"><span data-stu-id="fc569-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="fc569-108">Se l'aggiornamento richiede meno di 30 minuti, gli utenti non saranno coinvolti.</span><span class="sxs-lookup"><span data-stu-id="fc569-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="fc569-109">Per aggiornare un server back-end o un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fc569-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="fc569-110">Eseguire l'accesso al server da aggiornare come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="fc569-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="fc569-111">Scaricare l'aggiornamento ed estrarlo nel disco rigido locale.</span><span class="sxs-lookup"><span data-stu-id="fc569-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="fc569-112">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fc569-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="fc569-113">Interrompere i servizi di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc569-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="fc569-114">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fc569-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="fc569-115">Arrestare il servizio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="fc569-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="fc569-116">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="fc569-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="fc569-117">Chiudere tutte le finestre di Windows Management Shell di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fc569-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="fc569-118">Installare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fc569-118">Install the update.</span></span>
    
8. <span data-ttu-id="fc569-119">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business** e quindi su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="fc569-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="fc569-120">Arrestare di nuovo i servizi di Skype for Business Server per individuare gli assembly Global Assembly Cache (GAC)-d.</span><span class="sxs-lookup"><span data-stu-id="fc569-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="fc569-121">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="fc569-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="fc569-122">Riavviare il servizio World Wide Web.</span><span class="sxs-lookup"><span data-stu-id="fc569-122">Restart the World Wide Web service.</span></span> <span data-ttu-id="fc569-123">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="fc569-123">At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="fc569-124">Applicare le modifiche apportate ai database di SQL Server eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc569-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="fc569-125">Se si tratta di un server back-end Enterprise Edition e non sono presenti database collocati nel server, ad esempio i database di archiviazione o di monitoraggio, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="fc569-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="fc569-126">Se si tratta di un server back-end Enterprise Edition e sono presenti database collocati nel server, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="fc569-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="fc569-127">Se si tratta di un server Standard Edition, digitare quanto segue nella riga di comando:</span><span class="sxs-lookup"><span data-stu-id="fc569-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
