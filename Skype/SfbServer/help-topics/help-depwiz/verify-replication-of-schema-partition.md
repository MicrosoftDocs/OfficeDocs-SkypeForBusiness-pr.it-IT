---
title: Verificare la replica della partizione dello schema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: "Per verificare che l'estensione dello schema sia stata replicata correttamente nella foresta dei servizi di dominio Active Directory, eseguire le operazioni seguenti:"
ms.openlocfilehash: 0b90f61849e66e78c49d7d00783133198bab6b54
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687319"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="97ec4-103">Verificare la replica della partizione dello schema</span><span class="sxs-lookup"><span data-stu-id="97ec4-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="97ec4-104">Per verificare che l'estensione dello schema sia stata replicata correttamente nella foresta dei servizi di dominio Active Directory, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="97ec4-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="97ec4-105">Accedere a un controller di dominio (ad eccezione del controller di dominio che contiene il ruolo di master schema) nella foresta di servizi di dominio Active Directory in cui sono state applicate le estensioni dello schema come membro del gruppo amministratori aziendali.</span><span class="sxs-lookup"><span data-stu-id="97ec4-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="97ec4-106">Aprire ADSI Edit: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Modifica ADSI**.</span><span class="sxs-lookup"><span data-stu-id="97ec4-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="97ec4-107">In alternativa, fare clic sul pulsante **Start**e quindi su **Esegui**, digitare **ADSIEdit. msc** per avviare ADSI Edit.</span><span class="sxs-lookup"><span data-stu-id="97ec4-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="97ec4-108">Nell'albero di Microsoft Management Console (MMC), se non è già selezionato, fare clic su Modifica ADSI.</span><span class="sxs-lookup"><span data-stu-id="97ec4-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="97ec4-109">Nel menu **azione** fare clic su **Connetti a**.</span><span class="sxs-lookup"><span data-stu-id="97ec4-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="97ec4-110">Nella finestra di dialogo **impostazioni di connessione** in **selezionare un contesto di denominazione ben noto**Selezionare **schema**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="97ec4-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="97ec4-111">In contenitore schema cercare CN = ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="97ec4-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="97ec4-112">Se l'oggetto esiste e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **RangeLower** è 3, lo schema è stato aggiornato e replicato correttamente.</span><span class="sxs-lookup"><span data-stu-id="97ec4-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="97ec4-113">Se l'oggetto non esiste o se i valori degli attributi **rangeUpper** e **RangeLower** non sono specificati, lo schema non è stato modificato o non è stato replicato.</span><span class="sxs-lookup"><span data-stu-id="97ec4-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="97ec4-114">Se il controllo della replica dello schema non mostra ancora una replica corretta, attendere circa 15 minuti e quindi eseguire di nuovo il controllo.</span><span class="sxs-lookup"><span data-stu-id="97ec4-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="97ec4-115">La replica di Active Directory si basa su un modello di coerenza allentato e si può verificare la latenza della replica, in base a diversi fattori nel server e nell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="97ec4-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

