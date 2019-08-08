---
title: Impedire sessioni per i servizi
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: È possibile usare il pannello di controllo installazioni legacy per impedire la nuova sessione per tutti i servizi legacy in uso in un computer specifico o per impedire la nuova sessione di un servizio legacy specifico.
ms.openlocfilehash: 978c97bd7f610e6b40d467b80f5df8483b6d370f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244577"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="adf73-103">Impedire sessioni per i servizi</span><span class="sxs-lookup"><span data-stu-id="adf73-103">Prevent sessions for services</span></span>

<span data-ttu-id="adf73-104">È possibile usare il pannello di controllo installazioni legacy per impedire la nuova sessione per tutti i servizi legacy in uso in un computer specifico o per impedire la nuova sessione di un servizio legacy specifico.</span><span class="sxs-lookup"><span data-stu-id="adf73-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="adf73-105">Per evitare nuove sessioni per i servizi in un computer</span><span class="sxs-lookup"><span data-stu-id="adf73-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="adf73-106">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="adf73-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="adf73-107">Aprire il pannello di controllo di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="adf73-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="adf73-108">Nella barra di spostamento sinistra fare clic \*\*\*\* su topologia e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="adf73-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="adf73-109">Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui sono in esecuzione i servizi per cui si vogliono impedire le nuove sessioni e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="adf73-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="adf73-110">Fare clic su **azione**.</span><span class="sxs-lookup"><span data-stu-id="adf73-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="adf73-111">Fare clic su **Impedisci nuove sessioni per tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="adf73-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="adf73-112">Per impedire nuove sessioni per un servizio specifico</span><span class="sxs-lookup"><span data-stu-id="adf73-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="adf73-113">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. 2019.</span><span class="sxs-lookup"><span data-stu-id="adf73-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="adf73-114">Aprire il pannello di controllo di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="adf73-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="adf73-115">Nella barra di spostamento sinistra fare clic \*\*\*\* su topologia e quindi su **stato**.</span><span class="sxs-lookup"><span data-stu-id="adf73-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="adf73-116">Nella pagina **stato** ordinare o cercare l'elenco in base alle esigenze per trovare il computer in cui è in esecuzione il servizio che si vuole avviare o arrestare e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="adf73-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="adf73-117">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="adf73-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="adf73-118">Ordinare l'elenco dei servizi, se necessario, e fare clic sul servizio per cui si vogliono impedire le nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="adf73-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="adf73-119">Fare clic su **azione**.</span><span class="sxs-lookup"><span data-stu-id="adf73-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="adf73-120">Fare clic su **Impedisci nuove sessioni per il servizio**.</span><span class="sxs-lookup"><span data-stu-id="adf73-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="adf73-121">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="adf73-121">Click **Close**.</span></span>
    

