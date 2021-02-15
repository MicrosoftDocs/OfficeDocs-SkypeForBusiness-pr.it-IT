---
title: Configurare un servizio informazioni percorso secondario in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configurare un database SLS (Secondary Location Source) per il servizio E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830646"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="dadff-103">Configurare un servizio informazioni percorso secondario in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dadff-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="dadff-104">Configurare un database SLS (Secondary Location Source) per il servizio E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="dadff-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="dadff-105">Skype for Business Server offre un'interfaccia del servizio Web che è possibile utilizzare per puntare il servizio informazioni percorso a un database SLS (Secondary Location Source).</span><span class="sxs-lookup"><span data-stu-id="dadff-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="dadff-106">L'interfaccia del servizio Web che si connette al database SLS deve essere conforme al file WSDL del servizio informazioni percorso.</span><span class="sxs-lookup"><span data-stu-id="dadff-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="dadff-107">Se sono configurati sia un database delle località che un database delle località secondario, il servizio informazioni percorso esegue innanzitutto una query sul database delle località e, se non viene trovata alcuna corrispondenza, invia la richiesta di posizione dal client al database SLS.</span><span class="sxs-lookup"><span data-stu-id="dadff-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="dadff-108">Se il percorso esiste nel servizio SLS, il servizio informazioni percorso invia la posizione al client.</span><span class="sxs-lookup"><span data-stu-id="dadff-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="dadff-109">Per configurare un database delle località secondario</span><span class="sxs-lookup"><span data-stu-id="dadff-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="dadff-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="dadff-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="dadff-111">Eseguire il cmdlet seguente per configurare l'URL per il percorso del database delle località secondario.</span><span class="sxs-lookup"><span data-stu-id="dadff-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="dadff-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dadff-112">See also</span></span>

[<span data-ttu-id="dadff-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="dadff-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

