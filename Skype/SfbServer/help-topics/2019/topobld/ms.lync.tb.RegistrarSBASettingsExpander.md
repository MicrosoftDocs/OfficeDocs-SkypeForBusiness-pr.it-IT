---
title: Espansione delle impostazioni del registrar SBA
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'Si modificano le impostazioni per la resilienza e si configurano le proprietà seguenti:'
ms.openlocfilehash: 4297f70acfbf695d8dcfdcdb58a09d8f608add71
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701641"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="99fa8-103">Espansione delle impostazioni del registrar SBA</span><span class="sxs-lookup"><span data-stu-id="99fa8-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="99fa8-104">Si modificano le impostazioni per la **resilienza** e si configurano le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="99fa8-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="99fa8-105">Selezionare **servizio utente associato e pool di registrar di backup** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="99fa8-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="99fa8-106">Facoltativamente, selezionare la casella **di controllo failover automatico e failback per la voce** .</span><span class="sxs-lookup"><span data-stu-id="99fa8-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="99fa8-107">Configurare l' **intervallo di rilevamento errori vocali (sec)** e l' **intervallo di failback vocale (sec)**.</span><span class="sxs-lookup"><span data-stu-id="99fa8-107">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**.</span></span> <span data-ttu-id="99fa8-108">Per impostazione predefinita, gli intervalli sono 120 secondi per il rilevamento dell'errore vocale e 240 secondi per il failback vocale.</span><span class="sxs-lookup"><span data-stu-id="99fa8-108">By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="99fa8-109">Il numero di secondi definiti per gli intervalli di failover e failback deve essere testato con attenzione per verificare che la resilienza funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="99fa8-109">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected.</span></span> <span data-ttu-id="99fa8-110">L'impostazione dell'intervallo su basso (ovvero meno di 120 secondi) o il failover e il failback impostati troppo da vicino può causare il failover effettivo e il failback non funzionano come previsto.</span><span class="sxs-lookup"><span data-stu-id="99fa8-110">Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="99fa8-111">**OK** Consente di accettare e salvare le modifiche nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="99fa8-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="99fa8-112">**Annulla** Consente di eliminare le modifiche e di chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="99fa8-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="99fa8-113">**Guida** Consente di visualizzare questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="99fa8-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="99fa8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99fa8-114">See also</span></span>

[<span data-ttu-id="99fa8-115">Pianificazione della resilienza di Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="99fa8-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
