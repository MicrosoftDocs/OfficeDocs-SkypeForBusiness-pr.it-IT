---
title: Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Abilitare il bypass multimediale per ignorare sempre il Mediation Server in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 23d3100e355d100e3dea1932639d70f9290e7ea4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804216"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="69c74-103">Configurare il bypass multimediale in Skype for Business Server per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="69c74-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="69c74-104">Abilitare il bypass multimediale per ignorare sempre il Mediation Server in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="69c74-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="69c74-105">Se si utilizzano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che si disponga di una buona connettività tra gli endpoint di Skype for business e qualsiasi peer per il quale è stato configurato il bypass multimediale sulla connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="69c74-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="69c74-106">Se non si dispone di una buona connettività tra gli endpoint di Skype for business e tutti i peer al Mediation Server di cui sono state abilitate le rispettive connessioni trunk per il bypass multimediale, è necessario configurare le impostazioni di bypass multimediale globale per l'utilizzo delle informazioni sul sito e sulla regione quando si utilizza il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="69c74-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="69c74-107">Ciò consente di specificare in modo più preciso quando il contenuto multimediale deve ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="69c74-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="69c74-108">A tale scopo, eseguire la procedura descritta in [Configure Media Bypass Global Settings in Skype for Business Server per utilizzare le informazioni sui siti e le aree](use-site-and-region-information.md) geografiche e [associare invece una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="69c74-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="69c74-109">Per abilitare il bypass multimediale globalmente in modo che il Mediation Server venga ignorato sempre</span><span class="sxs-lookup"><span data-stu-id="69c74-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="69c74-110">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="69c74-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="69c74-111">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="69c74-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="69c74-112">Fare doppio clic sulla configurazione **Globale** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="69c74-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="69c74-113">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.</span><span class="sxs-lookup"><span data-stu-id="69c74-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="69c74-114">Fare clic su **Ignora sempre**.</span><span class="sxs-lookup"><span data-stu-id="69c74-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="69c74-115">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="69c74-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="69c74-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69c74-116">See also</span></span>

[<span data-ttu-id="69c74-117">Pianificare il bypass multimediale in Skype for business</span><span class="sxs-lookup"><span data-stu-id="69c74-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="69c74-118">Distribuire il bypass multimediale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="69c74-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

