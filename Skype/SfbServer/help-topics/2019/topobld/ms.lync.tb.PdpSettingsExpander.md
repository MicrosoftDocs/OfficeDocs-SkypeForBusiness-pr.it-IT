---
title: Espansione delle impostazioni del servizio Controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.
ms.openlocfilehash: e05d4b480472289560c3d1f517e725fadf7288bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829916"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="e06d5-104">Espansione delle impostazioni del servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="e06d5-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="e06d5-p102">Il servizio Controllo di ammissione di chiamata (CAC) è una rete di aree, siti e subnet che consentono di applicare restrizioni relative alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo avere configurato la rete per tale servizio, è necessario abilitare il servizio per applicare le limitazioni della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="e06d5-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e06d5-107">È inoltre possibile utilizzare il Pannello di controllo o i cmdlet di Management Shell per abilitare il servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e06d5-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="e06d5-108">Nella sezione **Impostazione controllo di ammissione di chiamata** della finestra di dialogo **Modifica proprietà** per il sito è possibile modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e06d5-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="e06d5-109">**Abilitazione del controllo di ammissione di chiamata** Selezionare questa impostazione per abilitare il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e06d5-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="e06d5-110">Deselezionare questa impostazione per disabilitare tale servizio per l'intera rete.</span><span class="sxs-lookup"><span data-stu-id="e06d5-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="e06d5-111">Per poter abilitare il controllo di ammissione di chiamata, è necessario avere configurato la rete per il servizio.</span><span class="sxs-lookup"><span data-stu-id="e06d5-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="e06d5-112">Per informazioni dettagliate, vedere [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e06d5-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="e06d5-113">**Pool Front End per l'esecuzione del servizio Controllo di ammissione di chiamata** Se è stato abilitato il servizio Controllo di ammissione di chiamata, è possibile modificare il pool che lo esegue.</span><span class="sxs-lookup"><span data-stu-id="e06d5-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="e06d5-114">A tale scopo, selezionare il pool desiderato nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="e06d5-114">Select the pool from the drop-down list.</span></span>
    

