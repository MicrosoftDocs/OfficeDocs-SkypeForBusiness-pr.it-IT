---
title: Espansione delle impostazioni del servizio Controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.
ms.openlocfilehash: 4df5a9f5be761e1e039a259d0abf4a38d51170df
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218787"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="127de-104">Espansione delle impostazioni del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="127de-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="127de-p102">Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="127de-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="127de-107">È inoltre possibile utilizzare il pannello di controllo o i cmdlet di Management Shell per abilitare il servizio di gestione delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="127de-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="127de-108">Nella sezione **Impostazione controllo di ammissione di chiamata** della finestra di dialogo **Modifica proprietà** per il sito è possibile modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="127de-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="127de-109">**Abilitazione del controllo di ammissione di chiamata** Selezionare questa impostazione per abilitare il servizio di controllo di ammissione.</span><span class="sxs-lookup"><span data-stu-id="127de-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="127de-110">Deselezionare questa impostazione per disabilitare tale servizio per l'intera rete.</span><span class="sxs-lookup"><span data-stu-id="127de-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="127de-111">Per poter abilitare il controllo di ammissione di chiamata, è necessario avere configurato la rete per il servizio.</span><span class="sxs-lookup"><span data-stu-id="127de-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="127de-112">Per informazioni dettagliate, vedere [deploy Call Admission Control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="127de-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="127de-113">**Pool Front end per eseguire il controllo di ammissione di chiamata** Se è stato abilitato il servizio di controllo di ammissione, è possibile modificare il pool che lo esegue.</span><span class="sxs-lookup"><span data-stu-id="127de-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="127de-114">A tale scopo, selezionare il pool desiderato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="127de-114">Select the pool from the drop-down list.</span></span>
    

