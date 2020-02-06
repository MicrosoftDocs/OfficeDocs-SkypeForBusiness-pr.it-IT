---
title: Espansione delle impostazioni del registrar per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'Si modificano le impostazioni per la resilienza e si configurano le proprietà seguenti:'
ms.openlocfilehash: adc3d3f0be42d542583cf269a7acf83d98df8dd7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819338"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="a2ecb-103">Espansione delle impostazioni del registrar per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a2ecb-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="a2ecb-104">Si modificano le impostazioni per la **resilienza** e si configurano le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2ecb-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="a2ecb-105">Selezionare **pool di registrar di backup associato** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="a2ecb-106">Facoltativamente, selezionare la casella **di controllo failover automatico e failback per la voce** .</span><span class="sxs-lookup"><span data-stu-id="a2ecb-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="a2ecb-107">Configurare l' **intervallo di rilevamento errori vocali (sec)** e l' **intervallo di failback vocale (sec)**.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="a2ecb-108">Per impostazione predefinita, gli intervalli sono 120 secondi per il rilevamento dell'errore vocale e 240 secondi per il failback vocale.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="a2ecb-109">Il numero di secondi definiti per gli intervalli di failover e failback deve essere testato con attenzione per verificare che la resilienza funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="a2ecb-110">L'impostazione dell'intervallo su basso (ovvero meno di 120 secondi) o il failover e il failback impostati troppo da vicino può causare il failover effettivo e il failback non funzionano come previsto.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="a2ecb-111">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="a2ecb-112">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="a2ecb-113">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="a2ecb-113">**Help** Displays this help screen.</span></span>
  

