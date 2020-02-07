---
title: Problemi noti per i criteri di conservazione in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Elenco corrente dei problemi noti per i criteri di conservazione di Microsoft teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838206"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="eb199-103">Problemi noti per i criteri di conservazione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb199-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="eb199-104">Non è ancora supportata la configurazione per la conservazione dei messaggi del canale privato.</span><span class="sxs-lookup"><span data-stu-id="eb199-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="eb199-105">È supportata la conservazione dei file condivisi nei canali privati.</span><span class="sxs-lookup"><span data-stu-id="eb199-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="eb199-106">Di seguito sono riportati i problemi noti per i criteri di conservazione in team che vengono rilevati e analizzati.</span><span class="sxs-lookup"><span data-stu-id="eb199-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="eb199-107">In Scegli teams nella riga location messages Channel teams è possibile che i gruppi di Office 365 non siano anche teams.</span><span class="sxs-lookup"><span data-stu-id="eb199-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="eb199-108">Questa operazione verrà affrontata in futuro.</span><span class="sxs-lookup"><span data-stu-id="eb199-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="eb199-109">In Scegli utenti nella riga posizione chat teams è possibile che vengano visualizzati utenti guest e non-Mailbox.</span><span class="sxs-lookup"><span data-stu-id="eb199-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="eb199-110">I criteri di conservazione non sono pensati per essere impostati per gli utenti e stiamo lavorando per rimuoverli dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="eb199-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="eb199-111">Il programma ELC (Exchange Life Cycle Assistant) viene eseguito giornalmente, ma ha uno SLA di 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="eb199-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="eb199-112">Di conseguenza, è possibile che, se si dispone di un criterio di conservazione di teams per eliminare gli elementi precedenti a 60 giorni, questi elementi potrebbero essere mantenuti per un massimo di 67 giorni.</span><span class="sxs-lookup"><span data-stu-id="eb199-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="eb199-113">Non si tratta di una nuova situazione: segue il modello Exchange.</span><span class="sxs-lookup"><span data-stu-id="eb199-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="eb199-114">Naturalmente, nella maggior parte dei casi, non ci sono ritardi.</span><span class="sxs-lookup"><span data-stu-id="eb199-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="eb199-116">Punto decisionale</span><span class="sxs-lookup"><span data-stu-id="eb199-116">Decision point</span></span>         |<span data-ttu-id="eb199-117">Quali caratteristiche di sicurezza e conformità richiedono l'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="eb199-117">What security and compliance features does your organization require?</span></span> <span data-ttu-id="eb199-118">L'organizzazione ha le licenze necessarie per soddisfare i requisiti aziendali per la sicurezza e la conformità?</span><span class="sxs-lookup"><span data-stu-id="eb199-118">Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Icona che rappresenta i passaggi successivi](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="eb199-120">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="eb199-120">Next steps</span></span>         |<span data-ttu-id="eb199-121">Documentare le caratteristiche di sicurezza e conformità richieste.</span><span class="sxs-lookup"><span data-stu-id="eb199-121">Document your required security and compliance features.</span></span>         |
