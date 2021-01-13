---
title: Verificare la replica della partizione dello schema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: "Per verificare la corretta replica dell'estensione dello schema nella foresta di servizi di dominio Active Directory, eseguire le operazioni seguenti:"
ms.openlocfilehash: db30087e6b996b70fe97e3249c1bf2eaa97a694c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800546"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="72c66-103">Verificare la replica della partizione dello schema</span><span class="sxs-lookup"><span data-stu-id="72c66-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="72c66-104">Per verificare la corretta replica dell'estensione dello schema nella foresta di servizi di dominio Active Directory, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="72c66-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="72c66-105">Accedere a un controller di dominio (diverso dal controller di dominio che contiene il ruolo master schema) nella foresta di servizi di dominio Active Directory, in cui sono state applicate le estensioni dello schema come membri del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="72c66-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="72c66-106">Aprire ADSI Edit: fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione**, quindi **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="72c66-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="72c66-107">In alternativa, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **adsiedit.msc** per avviare ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="72c66-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="72c66-108">Nell'albero di Microsoft Management Console (MMC), se non è già selezionato, fare clic su ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="72c66-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="72c66-109">Scegliere **Connetti a** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="72c66-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="72c66-110">Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="72c66-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="72c66-p101">Nel contenitore Schema individuare la voce CN=ms-RTC-SIP-SchemaVersion. Se questo oggetto è presente e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non è presente o i valori degli attributi **rangeUpper** e **rangeLower** sono diversi da quelli specificati, lo schema non è stato modificato né replicato.</span><span class="sxs-lookup"><span data-stu-id="72c66-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="72c66-114">Se dalla verifica della replica dello schema ancora non risulta un esito positivo, attendere circa 15 minuti e quindi ripetere la verifica.</span><span class="sxs-lookup"><span data-stu-id="72c66-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="72c66-115">La replica di Active Directory si basa su un modello di coerenza sciolto e può verificarsi una latenza di replica, in base a un numero di fattori nel server e nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="72c66-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

