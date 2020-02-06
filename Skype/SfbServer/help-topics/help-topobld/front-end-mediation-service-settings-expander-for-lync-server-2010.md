---
title: Espansione delle impostazioni del servizio Mediation Front End per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'È possibile modificare le proprietà delle impostazioni del gateway PSTN di Mediation Server in questa finestra di dialogo. Si definiscono le impostazioni seguenti:'
ms.openlocfilehash: dfe3defeb7cdce787321a401ca2a5450ee6b4ab8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819878"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="af353-104">Espansione delle impostazioni del servizio Mediation Front End per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="af353-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="af353-105">È possibile modificare le proprietà delle impostazioni del **gateway PSTN di Mediation Server** in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="af353-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="af353-106">Si definiscono le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af353-106">You define the following settings:</span></span>
  
- <span data-ttu-id="af353-107">Selezionare il **Mediation Server collocato abilitato** se si vuole collocare il Mediation Server con questo server front-end o i pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="af353-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="af353-108">**Porte in ascolto**: definire le porte che il server di mediazione ascolterà.</span><span class="sxs-lookup"><span data-stu-id="af353-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="af353-109">Puoi definire una porta per **TLS** o Transport Layer Security o **TCP**o Transport Control Protocol.</span><span class="sxs-lookup"><span data-stu-id="af353-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="af353-110">Per rendere disponibile la voce di porta per TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="af353-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="af353-111">Fare riferimento alla documentazione e alle impostazioni di configurazione per il gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi.</span><span class="sxs-lookup"><span data-stu-id="af353-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="af353-112">TLS è un protocollo più sicuro, usando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="af353-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="af353-113">Non tutti i gateway PSTN supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="af353-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="af353-114">Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.</span><span class="sxs-lookup"><span data-stu-id="af353-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="af353-p105">Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il servizio Mediation. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.</span><span class="sxs-lookup"><span data-stu-id="af353-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="af353-118">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="af353-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="af353-119">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="af353-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="af353-120">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="af353-120">**Help** Displays this help screen.</span></span>
  

