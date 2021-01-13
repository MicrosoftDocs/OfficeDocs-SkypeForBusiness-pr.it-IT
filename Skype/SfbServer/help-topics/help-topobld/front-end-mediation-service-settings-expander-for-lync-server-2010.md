---
title: Espansione delle impostazioni del servizio Front End Mediation per Lync Server 2010
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
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'In questa finestra di dialogo è possibile modificare le proprietà delle impostazioni di Gateway PSTN Mediation Server. È possibile definire le impostazioni seguenti:'
ms.openlocfilehash: ad6aab0ce528db01621b1d43a62624d96649e66a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807056"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="7378d-104">Espansione delle impostazioni del servizio Front End Mediation per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7378d-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="7378d-105">In questa finestra di dialogo è possibile modificare le proprietà delle impostazioni di **Gateway PSTN Mediation Server**.</span><span class="sxs-lookup"><span data-stu-id="7378d-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="7378d-106">È possibile definire le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7378d-106">You define the following settings:</span></span>
  
- <span data-ttu-id="7378d-107">Selezionare il **Mediation Server collocato abilitato** se si desidera collocare il Mediation Server con il front end server o i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="7378d-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="7378d-108">**Porte di attesa**: consente di definire le porte che il Mediation server ascolterà.</span><span class="sxs-lookup"><span data-stu-id="7378d-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="7378d-109">È possibile definire una porta per **TLS** (Transport Layer Security) o **TCP** (Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="7378d-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="7378d-110">Per rendere disponibile la voce della porta relativa a TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="7378d-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7378d-111">Consultare la documentazione e le impostazioni di configurazione del gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi.</span><span class="sxs-lookup"><span data-stu-id="7378d-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="7378d-112">TLS è un protocollo più sicuro, utilizzando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="7378d-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="7378d-113">Non tutti i gateway PSTN supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="7378d-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="7378d-114">Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.</span><span class="sxs-lookup"><span data-stu-id="7378d-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="7378d-p105">Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il Mediation Server. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.</span><span class="sxs-lookup"><span data-stu-id="7378d-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="7378d-118">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="7378d-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="7378d-119">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7378d-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="7378d-120">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="7378d-120">**Help** Displays this help screen.</span></span>
  

