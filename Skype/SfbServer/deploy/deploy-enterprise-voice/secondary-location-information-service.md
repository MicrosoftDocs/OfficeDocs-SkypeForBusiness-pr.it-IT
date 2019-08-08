---
title: Configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurare un database di origine della posizione secondaria (SLS) per E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240400"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="c1e6b-103">Configurare un servizio di informazioni sulla posizione secondaria in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c1e6b-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="c1e6b-104">Configurare un database di origine della posizione secondaria (SLS) per E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c1e6b-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c1e6b-105">Skype for Business Server offre un'interfaccia di servizio Web che può essere usata per puntare il servizio informazioni sulla posizione in un database di origine della posizione secondaria (SLS).</span><span class="sxs-lookup"><span data-stu-id="c1e6b-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="c1e6b-106">L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al WSDL del servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="c1e6b-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="c1e6b-107">Se sono configurati sia il database della posizione che il database della posizione secondaria, il servizio informazioni sulla posizione esegue prima di tutto il database della posizione e, se non viene trovata alcuna corrispondenza, Invia la richiesta di posizione dal client al database SLS.</span><span class="sxs-lookup"><span data-stu-id="c1e6b-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="c1e6b-108">Se la posizione esiste nella SLS, il servizio informazioni sulla posizione restituirà la posizione al client.</span><span class="sxs-lookup"><span data-stu-id="c1e6b-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="c1e6b-109">Per configurare un database di posizione secondario</span><span class="sxs-lookup"><span data-stu-id="c1e6b-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="c1e6b-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c1e6b-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c1e6b-111">Eseguire il cmdlet seguente per configurare l'URL per la posizione del database della posizione secondaria.</span><span class="sxs-lookup"><span data-stu-id="c1e6b-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="c1e6b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1e6b-112">See also</span></span>

[<span data-ttu-id="c1e6b-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c1e6b-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

