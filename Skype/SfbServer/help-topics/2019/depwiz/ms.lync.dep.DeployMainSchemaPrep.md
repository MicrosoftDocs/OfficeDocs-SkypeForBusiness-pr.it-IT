---
title: Preparare lo schema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparazione schema nella Distribuzione guidata di Skype for Business Server. Fare clic su Esegui per avviare la preparazione dello schema.
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833776"
---
# <a name="prepare-schema"></a><span data-ttu-id="49e36-104">Preparare lo schema</span><span class="sxs-lookup"><span data-stu-id="49e36-104">Prepare Schema</span></span>
 
<span data-ttu-id="49e36-105">Per preparare lo schema per Servizi di dominio Active Directory, eseguire il passaggio Preparazione schema nella Distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49e36-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="49e36-106">Fare clic su **Esegui** per avviare la preparazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="49e36-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="49e36-107">Il passaggio Preparazione schema legge i file di definizione dello schema forniti nella directory \Programmi\Skype for Business Server 2019\Deployment\Setup nel sistema in cui viene eseguita la Distribuzione guidata.</span><span class="sxs-lookup"><span data-stu-id="49e36-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="49e36-108">Tali file sono inoltre disponibili nella directory \Support\Schema dei supporti di installazione.</span><span class="sxs-lookup"><span data-stu-id="49e36-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="49e36-109">Nel corso del passaggio di preparazione dello schema, quest'ultimo verrà esteso e verrà segnalato lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="49e36-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="49e36-110">Verrà inoltre notificato il completamento del processo.</span><span class="sxs-lookup"><span data-stu-id="49e36-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="49e36-111">La schermata di riepilogo consentirà di visualizzare i registri del processo.</span><span class="sxs-lookup"><span data-stu-id="49e36-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="49e36-112">Esaminare tali registri per accertarsi che la preparazione sia stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="49e36-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="49e36-113">Per estendere lo schema, è necessario essere connessi al dominio come membri del gruppo Schema Admins e del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="49e36-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="49e36-114">Vengono aggiunti classi e attributi per estendere lo schema di Servizi di dominio Active Directory per supportare gli oggetti server, servizio e utente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="49e36-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="49e36-115">Prima di estendere lo schema, è consigliabile effettuare un backup dello stato del sistema per il controller di dominio con il ruolo master schema.</span><span class="sxs-lookup"><span data-stu-id="49e36-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="49e36-116">L'estensione dello schema non è un'operazione reversibile.</span><span class="sxs-lookup"><span data-stu-id="49e36-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="49e36-117">È consigliabile fare tutto il possibile per limitare il potenziale impatto di un'estensione dello schema non riuscita e per garantire che l'estensione dello schema avrà esito positivo.</span><span class="sxs-lookup"><span data-stu-id="49e36-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="49e36-118">Ciò è particolarmente importante in caso di perdita di comunicazione o di qualsiasi altro errore nel server.</span><span class="sxs-lookup"><span data-stu-id="49e36-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="49e36-119">È consigliabile eseguire un backup del controller di dominio master schema e un backup completo di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="49e36-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="49e36-120">Per eseguire un backup del controller di dominio master schema e un backup completo di Active Directory:</span><span class="sxs-lookup"><span data-stu-id="49e36-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="49e36-121">Disconnettere dalla rete il controller di dominio con il ruolo master schema.</span><span class="sxs-lookup"><span data-stu-id="49e36-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="49e36-122">Effettuare un backup dello stato del sistema per il controller di dominio con il master schema.</span><span class="sxs-lookup"><span data-stu-id="49e36-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="49e36-123">Estendere lo schema.</span><span class="sxs-lookup"><span data-stu-id="49e36-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="49e36-124">Quando l'estensione dello schema ha esito positivo, riconnettere il controller di dominio alla rete e verificare che la replica sia attiva e funzionante.</span><span class="sxs-lookup"><span data-stu-id="49e36-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="49e36-125">Nell'improbabile eventualità di un errore di estensione dello schema, ripristinare lo stato del sistema del controller di dominio e di Active Directory utilizzando il backup dello stato del sistema eseguito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="49e36-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="49e36-126">Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovare i file nel computer in cui è stata eseguita la Distribuzione guidata, nella directory Utenti dell'utente di Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="49e36-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="49e36-127">Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="49e36-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

