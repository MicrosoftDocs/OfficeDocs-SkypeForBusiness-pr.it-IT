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
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per il servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.
ms.openlocfilehash: 345668c61697dfa90e9e511d98ac82e6468440cc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684859"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="24cd3-104">Espansione delle impostazioni del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="24cd3-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="24cd3-p102">Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per il servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="24cd3-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="24cd3-107">È inoltre possibile utilizzare il pannello di controllo o i cmdlet di Management Shell per abilitare il servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="24cd3-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="24cd3-108">Nella sezione **Impostazione controllo di ammissione di chiamata** della finestra di dialogo **Modifica proprietà** per il sito è possibile modificare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="24cd3-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="24cd3-109">**Abilitare il controllo di ammissione alle chiamate** Selezionare questa impostazione per abilitare CAC.</span><span class="sxs-lookup"><span data-stu-id="24cd3-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="24cd3-110">Deselezionare questa impostazione per disabilitare il servizio per l'intera rete.</span><span class="sxs-lookup"><span data-stu-id="24cd3-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="24cd3-111">Per poter abilitare il servizio Controllo di ammissione di chiamata, è necessario avere configurato la rete per il servizio.</span><span class="sxs-lookup"><span data-stu-id="24cd3-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="24cd3-112">Per informazioni dettagliate, vedere [distribuire il controllo di ammissione alle chiamate in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="24cd3-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="24cd3-113">**Pool Front-end per l'esecuzione del controllo di ammissione alle chiamate** Se è stato abilitato CAC, è possibile modificare il pool che lo esegue.</span><span class="sxs-lookup"><span data-stu-id="24cd3-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="24cd3-114">Selezionare il pool nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="24cd3-114">Select the pool from the drop-down list.</span></span>
    

