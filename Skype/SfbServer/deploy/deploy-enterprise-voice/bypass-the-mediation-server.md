---
title: Configurare il bypass multimediale in Skype for Business Server per aggirare sempre il Mediation Server
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Abilitare il bypass multimediale per aggirare sempre il Mediation Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: dfffda1130fc1fb119e6cbf5d9b12af766b9c038
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234035"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1dccb-103">Configurare il bypass multimediale in Skype for Business Server per aggirare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="1dccb-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="1dccb-104">Abilitare il bypass multimediale per aggirare sempre il Mediation Server in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="1dccb-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="1dccb-105">Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presume che si disponga di una buona connettività tra endpoint Skype for business e qualsiasi peer per il quale è stato configurato il bypass multimediale nella connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="1dccb-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="1dccb-106">Se non si dispone di una buona connettività tra endpoint Skype for business e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni di bypass multimediale globale per l'uso delle informazioni sul sito e sulle aree geografiche Quando si usa il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1dccb-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="1dccb-107">In questo modo è possibile determinare un maggiore controllo quando l'elemento multimediale ignora il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1dccb-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="1dccb-108">Per eseguire questa operazione, usare la procedura descritta in [configurare le impostazioni globali di bypass multimediale in Skype for Business Server per usare le informazioni sul sito e le aree](use-site-and-region-information.md) geografiche e [associare invece una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="1dccb-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1dccb-109">Per abilitare il bypass multimediale a livello globale per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="1dccb-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="1dccb-110">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1dccb-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1dccb-111">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="1dccb-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1dccb-112">Fare doppio clic sulla configurazione **globale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1dccb-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="1dccb-113">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="1dccb-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="1dccb-114">Fare clic su **Ignora sempre**.</span><span class="sxs-lookup"><span data-stu-id="1dccb-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="1dccb-115">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1dccb-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1dccb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dccb-116">See also</span></span>

[<span data-ttu-id="1dccb-117">Pianificare il bypass multimediale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="1dccb-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="1dccb-118">Distribuire il bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1dccb-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

