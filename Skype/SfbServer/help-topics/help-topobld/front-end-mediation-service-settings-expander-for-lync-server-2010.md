---
title: Expander per le impostazioni del servizio di mediazione front end per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'È possibile modificare le proprietà delle impostazioni del gateway PSTN di Mediation Server in questa finestra di dialogo. Si definiscono le impostazioni seguenti:'
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189911"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="b7dc3-104">Expander per le impostazioni del servizio di mediazione front end per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b7dc3-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="b7dc3-105">È possibile modificare le proprietà delle impostazioni del **gateway PSTN di Mediation Server** in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="b7dc3-106">Si definiscono le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7dc3-106">You define the following settings:</span></span>
  
- <span data-ttu-id="b7dc3-107">Selezionare il **Mediation Server collocato abilitato** se si vuole collocare il Mediation Server con questo server front-end o i pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="b7dc3-108">**Porte in ascolto**: definire le porte che il server di mediazione ascolterà.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="b7dc3-109">Puoi definire una porta per **TLS** o Transport Layer Security o **TCP**o Transport Control Protocol.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="b7dc3-110">Per rendere disponibile la voce di porta per TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b7dc3-111">Fare riferimento alla documentazione e alle impostazioni di configurazione per il gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="b7dc3-112">TLS è un protocollo più sicuro, usando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="b7dc3-113">Non tutti i gateway PSTN supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="b7dc3-114">Elenco dei **Trunk**, ovvero dei trunk SIP (Session Initiation Protocol), **Gateway**, ovvero gateway PSTN o IP-PBX, e **Siti**, ovvero siti configurati per i trunk e i gateway, attualmente associati ed esistenti.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="b7dc3-p105">Selezionare un trunk, un gateway e un sito e fare clic su **Rendi predefinito** per impostare la selezione come predefinita per il servizio Mediation. Selezionare l'impostazione predefinita corrente e fare clic su **Annulla predefinito** per rimuovere la selezione come impostazione predefinita corrente. Selezionare quindi una nuova impostazione predefinita e fare clic su **Rendi predefinito**.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="b7dc3-118">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b7dc3-119">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b7dc3-120">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="b7dc3-120">**Help** Displays this help screen.</span></span>
  

