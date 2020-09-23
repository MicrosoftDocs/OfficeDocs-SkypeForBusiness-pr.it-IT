---
title: Espansione delle impostazioni del servizio di registrazione per Lync Server per la versione 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17dcd75c-bd9a-407e-af9b-c61cb1201c07
description: 'È possibile modificare le impostazioni della sezione Resilienza e configurare le proprietà seguenti:'
ms.openlocfilehash: 4271203bf9f737034796cc3b74c95836480df521
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217177"
---
# <a name="registrar-settings-expander-for-lync-server-for-2010"></a><span data-ttu-id="8f9cb-103">Espansione delle impostazioni del servizio di registrazione per Lync Server per la versione 2010</span><span class="sxs-lookup"><span data-stu-id="8f9cb-103">Registrar Settings Expander for Lync Server for 2010</span></span>
 
<span data-ttu-id="8f9cb-104">È possibile modificare le impostazioni relative alla **Resilienza** e configurare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f9cb-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>
  
- <span data-ttu-id="8f9cb-105">Selezionare **Pool di registrazione di backup associato** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-105">Select **Associated backup Registrar pool** from the list.</span></span>
    
    <span data-ttu-id="8f9cb-106">Se lo si desidera, selezionare la casella di controllo **Failover e failback automatico per VolP**.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>
    
    <span data-ttu-id="8f9cb-p101">Configurare le opzioni **Intervallo rilevamento errori VolP (sec)** e **Intervallo failback VolP (sec)**. Per impostazione predefinita, gli intervalli sono di 120 secondi per il rilevamento errori VolP e di 240 secondi per il failback VolP.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8f9cb-p102">Il numero di secondi definito per gli intervalli di failover e failback deve essere testato attentamente per assicurare che la resilienza funzioni nel modo previsto. L'impostazione di un intervallo troppo basso, ovvero inferiore a 120 secondi, o l'impostazione di valori di failover e failback troppo vicini potrebbe compromettere il funzionamento del failover e del failback.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span> 
  
  <span data-ttu-id="8f9cb-111">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-111">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="8f9cb-112">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-112">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="8f9cb-113">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="8f9cb-113">**Help** Displays this help screen.</span></span>
  

