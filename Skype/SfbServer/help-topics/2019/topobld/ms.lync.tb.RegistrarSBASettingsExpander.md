---
title: Espansione delle impostazioni SBA del servizio di registrazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSBASettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 68ea1fc0-9cd1-4e0a-995e-b53845493477
ROBOTS: NOINDEX, NOFOLLOW
description: 'È possibile modificare le impostazioni della sezione Resilienza e configurare le proprietà seguenti:'
ms.openlocfilehash: 277f1b78db9a756ea3a31bcae060d59ab3e69bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822126"
---
# <a name="registrar-sba-settings-expander"></a><span data-ttu-id="0aad7-103">Espansione delle impostazioni SBA del servizio di registrazione</span><span class="sxs-lookup"><span data-stu-id="0aad7-103">Registrar SBA Settings Expander</span></span>

<span data-ttu-id="0aad7-104">È possibile modificare le impostazioni della sezione **Resilienza** e configurare le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="0aad7-104">You edit the settings for **Resiliency** and configure the following properties:</span></span>

- <span data-ttu-id="0aad7-105">Selezionare **Pool di registrazione di backup e servizi utente associati** nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0aad7-105">Select **Associated User service and backup Registrar pool** from the list.</span></span>

    <span data-ttu-id="0aad7-106">Facoltativamente, selezionare la casella di controllo **Failover e failback automatico per VolP**.</span><span class="sxs-lookup"><span data-stu-id="0aad7-106">Optionally, select the **Automatic failover and failback for Voice** check box.</span></span>

    <span data-ttu-id="0aad7-p101">Configurare le opzioni **Intervallo rilevamento errori VolP (sec)** e **Intervallo failback VolP (sec)**. Per impostazione predefinita, gli intervalli sono di 120 secondi per il rilevamento errori VolP e di 240 secondi per il failback VolP.</span><span class="sxs-lookup"><span data-stu-id="0aad7-p101">Configure the **Voice failure detection interval (sec)** and the **Voice failback interval (sec)**. By default, the intervals are 120 seconds for Voice failure detection and 240 seconds for Voice failback.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="0aad7-p102">Il numero di secondi definito per gli intervalli di failover e failback deve essere testato attentamente per assicurare che la resilienza funzioni nel modo previsto. L'impostazione di un intervallo troppo basso, ovvero inferiore a 120 secondi, o l'impostazione di valori di failover e failback troppo vicini potrebbe compromettere il funzionamento del failover e del failback.</span><span class="sxs-lookup"><span data-stu-id="0aad7-p102">The number of seconds that you define for the failover and failback intervals should be carefully tested to ensure that the resiliency works as expected. Setting the interval to low (that is, less than 120 seconds) or the failover and failback set too closely may result in the actual failover and failback not working as expected.</span></span>

  <span data-ttu-id="0aad7-111">**OK** Accetta le modifiche apportate nella finestra di dialogo e ne esegue il commit.</span><span class="sxs-lookup"><span data-stu-id="0aad7-111">**OK** Accepts and commits changes to the dialog.</span></span>

  <span data-ttu-id="0aad7-112">**Annulla** Rimuove le modifiche e chiude la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0aad7-112">**Cancel** Discards changes and closes the dialog.</span></span>

  <span data-ttu-id="0aad7-113">**?** Visualizza questa schermata della Guida.</span><span class="sxs-lookup"><span data-stu-id="0aad7-113">**Help** Displays this help screen.</span></span>

## <a name="see-also"></a><span data-ttu-id="0aad7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0aad7-114">See also</span></span>

[<span data-ttu-id="0aad7-115">Pianificazione della resilienza di VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="0aad7-115">Planning for Enterprise Voice Resiliency</span></span>](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)
