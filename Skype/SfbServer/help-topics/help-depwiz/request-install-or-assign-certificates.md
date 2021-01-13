---
title: Richiedere, installare o assegnare certificati
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: "In Passaggio 3: richiedere, installare o assegnare certificati è possibile avviare la Configurazione guidata certificati facendo clic su Esegui. I certificati configurati tramite la procedura guidata si basano sulla definizione della topologia di Skype for Business Server 2015 configurata e pubblicata da generatore di topologie all'archivio di gestione centrale. Per eseguire correttamente la Configurazione guidata certificati per un'Autorità di certificazione (CA) online nell'organizzazione, è necessario essere connessi al computer come utenti membri del gruppo Administrators locale del computer stesso. È inoltre necessario essere utenti autenticati nel dominio in cui si trovano il computer e la CA. La procedura guidata certificate fornisce la possibilità di specificare credenziali alternative per accedere all'autorità di certificazione dell'organizzazione."
ms.openlocfilehash: 278aea23430d2fad39c355f03c7512a76ab9cbee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829716"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="b9077-107">Richiedere, installare o assegnare certificati</span><span class="sxs-lookup"><span data-stu-id="b9077-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="b9077-108">In **Passaggio 3: richiedere, installare o assegnare certificati** è possibile avviare la Configurazione guidata certificati facendo clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b9077-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="b9077-109">I certificati configurati tramite la procedura guidata si basano sulla definizione della topologia di Skype for Business Server 2015 configurata e pubblicata da generatore di topologie all'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b9077-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="b9077-110">Per eseguire correttamente la Configurazione guidata certificati per un'Autorità di certificazione (CA) online nell'organizzazione, è necessario essere connessi al computer come utenti membri del gruppo Administrators locale del computer stesso.</span><span class="sxs-lookup"><span data-stu-id="b9077-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="b9077-111">È inoltre necessario essere utenti autenticati nel dominio in cui si trovano il computer e la CA.</span><span class="sxs-lookup"><span data-stu-id="b9077-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="b9077-112">La procedura guidata certificate fornisce la possibilità di specificare credenziali alternative per accedere all'autorità di certificazione dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b9077-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9077-p103">È inoltre possibile utilizzare la Configurazione guidata certificati per richiedere ed elaborare le richieste di certificati offline che vengono inviate a una CA pubblica o a un'altra infrastruttura a chiave pubblica (PKI) offline. Per generare una richiesta offline non è necessario appartenere a gruppi specifici, tranne a quelli previsti per poter eseguire l'accesso al computer. Per elaborare la risposta della CA pubblica e assegnare il certificato al computer e al ruolo, è necessario connettersi come membri del gruppo Administrators locale o di un gruppo equivalente.</span><span class="sxs-lookup"><span data-stu-id="b9077-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

