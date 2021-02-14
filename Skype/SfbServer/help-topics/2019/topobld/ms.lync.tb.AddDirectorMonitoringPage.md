---
title: Aggiungere il monitoraggio del Director
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorMonitoringPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a9009434-3771-475f-8314-c104f2716a29
ROBOTS: NOINDEX, NOFOLLOW
description: "È possibile definire l'archivio SQL Server per il monitoraggio configurando queste proprietà:"
ms.openlocfilehash: 324acca0ed3fef57e74a069dccb60f8c79a0060a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807796"
---
# <a name="add-director-monitoring"></a><span data-ttu-id="28c6f-103">Aggiungere il monitoraggio del Director</span><span class="sxs-lookup"><span data-stu-id="28c6f-103">Add Director Monitoring</span></span>
 
<span data-ttu-id="28c6f-104">È possibile **definire l'archivio SQL Server per il monitoraggio** configurando queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="28c6f-104">You can **Define the Monitoring SQL Server store** by configuring the following properties:</span></span>
  
- <span data-ttu-id="28c6f-105">**Monitoraggio SQL Server archivio:** selezionare un SQL Server di dominio completo (FQDN) e, facoltativamente, un'istanza SQL Server denominata) dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="28c6f-105">**Monitoring SQL Server store**: Select a SQL Server fully qualified domain name (FQDN) (and, optionally, a named SQL Server instance) from the list.</span></span>
    
    <span data-ttu-id="28c6f-106">Fare **clic su** Nuovo per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="28c6f-106">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the Monitoring Server store.</span></span>
    
- <span data-ttu-id="28c6f-107">Selezionare la **casella SQL Server il mirroring dell'archivio** se si desidera aggiungere il mirroring del database per il Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="28c6f-107">Select the **Enable SQL Server store mirroring** check box if you want to add database mirroring for the Monitoring Server.</span></span>
    
    <span data-ttu-id="28c6f-108">Selezionare un mirror archivio nell'elenco **Mirror archivio SQL Server monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="28c6f-108">Select an existing **Monitoring SQL Server store mirror** from the list.</span></span>
    
    <span data-ttu-id="28c6f-109">Fare **clic su** Nuovo per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio mirror.</span><span class="sxs-lookup"><span data-stu-id="28c6f-109">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirror store.</span></span>
    
- <span data-ttu-id="28c6f-110">Se è stata selezionata l'opzione **Abilita mirroring** SQL Server store, facoltativamente selezionare Usa controllo del mirroring SQL Server per abilitare il **failover** automatico per selezionare un archivio di controllo del mirroring SQL Server nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="28c6f-110">If you selected **Enable SQL Server store mirroring**, optionally select **Use SQL Server mirroring witness to enable automatic failover** to select a SQL Server mirroring witness store from the list.</span></span>
    
    <span data-ttu-id="28c6f-111">Fare **clic su Nuovo** per creare una nuova SQL Server FQDN e facoltativamente un nome di istanza per l'archivio di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="28c6f-111">Click **New** to create a new SQL Server FQDN definition, and optionally, an instance name for the mirroring witness store.</span></span>
    
<span data-ttu-id="28c6f-112">Fare clic su **Indietro** per tornare alla finestra di dialogo per la definizione del pool precedente.</span><span class="sxs-lookup"><span data-stu-id="28c6f-112">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="28c6f-113">Fare clic su **Avanti** dopo avere specificato le opzioni per questa finestra di dialogo per continuare con la configurazione.</span><span class="sxs-lookup"><span data-stu-id="28c6f-113">Click **Next** after you have finished entering the options for this dialog to proceed with the configuration.</span></span>
  
<span data-ttu-id="28c6f-114">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="28c6f-114">Click **Cancel** to discard all changes and end the wizard.</span></span>
  
<span data-ttu-id="28c6f-115">Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="28c6f-115">Click **Help** to access context-sensitive help, such as this page.</span></span>
  

