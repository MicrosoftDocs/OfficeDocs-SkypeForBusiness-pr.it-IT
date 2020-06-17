---
title: Impedire le sessioni per i servizi
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile utilizzare il pannello di controllo Installa legacy per impedire nuove sessioni per tutti i servizi legacy in esecuzione in un computer specifico o per impedire nuove sessioni per uno specifico servizio legacy.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752288"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="3e68f-103">Impedire le sessioni per i servizi</span><span class="sxs-lookup"><span data-stu-id="3e68f-103">Prevent sessions for services</span></span>

<span data-ttu-id="3e68f-104">È possibile utilizzare il pannello di controllo Installa legacy per impedire nuove sessioni per tutti i servizi legacy in esecuzione in un computer specifico o per impedire nuove sessioni per uno specifico servizio legacy.</span><span class="sxs-lookup"><span data-stu-id="3e68f-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="3e68f-105">Per impedire nuove sessioni per i servizi in un computer</span><span class="sxs-lookup"><span data-stu-id="3e68f-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="3e68f-106">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3e68f-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="3e68f-107">Aprire il pannello di controllo di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3e68f-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="3e68f-108">Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="3e68f-109">Nella pagina **Stato** ordinare l'elenco oppure cercare nell'elenco il computer in cui sono in esecuzione i servizi per cui si desidera impedire nuove sessioni, quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="3e68f-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="3e68f-110">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="3e68f-111">Fare clic su **Impedisci nuove sessioni per tutti i servizi**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="3e68f-112">Per impedire nuove sessioni per uno specifico servizio</span><span class="sxs-lookup"><span data-stu-id="3e68f-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="3e68f-113">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3e68f-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="3e68f-114">Aprire il pannello di controllo di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3e68f-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="3e68f-115">Sulla barra di spostamento sinistra fare clic su **Topologia** e quindi su **Stato**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="3e68f-116">Nella pagina **Stato** ordinare o scorrere l'elenco per trovare il computer in cui è in esecuzione il servizio che si desidera avviare o arrestare e quindi fare clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="3e68f-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="3e68f-117">Fare clic su **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="3e68f-118">Ordinare l'elenco dei servizi, se necessario, quindi fare clic sul servizio per cui si desidera impedire nuove sessioni.</span><span class="sxs-lookup"><span data-stu-id="3e68f-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="3e68f-119">Fare clic su **Azione**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="3e68f-120">Fare clic su **Impedisci nuove sessioni per il servizio**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="3e68f-121">Fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3e68f-121">Click **Close**.</span></span>
    

