---
title: Espansione delle impostazioni del servizio di registrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
ROBOTS: NOINDEX, NOFOLLOW
description: La resilienza garantisce l'elevata disponibilità e il ripristino di emergenza per il pool di registrar. Fornendo un registrar di backup in caso di errore del registrar principale, il registrar di backup può subentrare per il registrar non riuscito, consentendo agli utenti di accedere e comunicare. Gli utenti possono potenzialmente provare funzionalità ridotte, a seconda dei sistemi non riusciti con il registrar principale.
ms.openlocfilehash: 122124140c93afb3ce58b1d9423839f3e21dbcad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188024"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="38784-105">Espansione delle impostazioni del servizio di registrazione</span><span class="sxs-lookup"><span data-stu-id="38784-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="38784-106">La resilienza garantisce l'elevata disponibilità e il ripristino di emergenza per il pool di registrar.</span><span class="sxs-lookup"><span data-stu-id="38784-106">Resiliency provides high availability and disaster recovery for the Registrar pool.</span></span> <span data-ttu-id="38784-107">Fornendo un registrar di backup in caso di errore del registrar principale, il registrar di backup può subentrare per il registrar non riuscito, consentendo agli utenti di accedere e comunicare.</span><span class="sxs-lookup"><span data-stu-id="38784-107">By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate.</span></span> <span data-ttu-id="38784-108">Gli utenti possono potenzialmente provare funzionalità ridotte, a seconda dei sistemi non riusciti con il registrar principale.</span><span class="sxs-lookup"><span data-stu-id="38784-108">Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="38784-109">Nella sezione **resilienza** della finestra di dialogo **modifica proprietà** relativa a Survivable Branch Appliance o Survivable Branch Server è possibile modificare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38784-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="38784-110">**Servizio utente associato e pool Registrar di backup** Nell'elenco a discesa selezionare il pool di front end Enterprise Edition o il server front end Standard Edition che funge da registrar per il Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="38784-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="38784-111">**Abilitare il failover e il failback** Selezionare questa impostazione per consentire il rilevamento automatico di un registrar non riuscito e la determinazione automatica che il registrar principale è il backup e pronto per riprendere il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="38784-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="38784-112">**Intervallo di rilevamento errori (sec)** Digitare il numero di secondi che deve trascorrere prima che venga determinato che il registrar principale non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="38784-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="38784-113">Il valore predefinito è 120 secondi.</span><span class="sxs-lookup"><span data-stu-id="38784-113">The default value is 120 seconds.</span></span> <span data-ttu-id="38784-114">Questo campo è obbligatorio se si seleziona **Abilita failover e failback**.</span><span class="sxs-lookup"><span data-stu-id="38784-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="38784-115">**Intervallo di rilevamento del fallback (sec)** Digitare il numero di secondi che deve trascorrere prima che venga determinato il backup del registrar principale.</span><span class="sxs-lookup"><span data-stu-id="38784-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="38784-116">Il valore predefinito è 240 secondi.</span><span class="sxs-lookup"><span data-stu-id="38784-116">The default value is 240 seconds.</span></span> <span data-ttu-id="38784-117">Questo campo è obbligatorio se si seleziona **Abilita failover e fallback**.</span><span class="sxs-lookup"><span data-stu-id="38784-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="38784-118">Quando si definisce l'intervallo di rilevamento degli errori e l'intervallo di rilevamento del fallback, prestare attenzione a non immettere un intervallo che provocherà il failover e il fallback se il registrar non risponde per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="38784-118">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="38784-119">È possibile che il registrar principale non possa rispondere per brevi periodi di tempo in base al caricamento del pool o dei server.</span><span class="sxs-lookup"><span data-stu-id="38784-119">It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

