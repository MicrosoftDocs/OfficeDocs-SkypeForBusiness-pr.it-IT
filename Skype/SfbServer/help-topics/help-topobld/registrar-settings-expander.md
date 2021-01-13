---
title: Espansione delle impostazioni del servizio di registrazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RegistrarSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c7486ab3-61fd-45c6-9edc-a15535f273ff
description: La resilienza offre disponibilità elevata e ripristino di emergenza per il pool di registrazione. Dato che è disponibile un servizio di registrazione di backup in caso di errore del servizio di registrazione principale, quello di backup può subentrare al posto di quello in errore, permettendo agli utenti di accedere e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda dei sistemi che hanno avuto problemi con il servizio di registrazione principale.
ms.openlocfilehash: 8ab5fc804b6fad1f049e70477d7c16cb35111f79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818296"
---
# <a name="registrar-settings-expander"></a><span data-ttu-id="bdd50-105">Espansione delle impostazioni del servizio di registrazione</span><span class="sxs-lookup"><span data-stu-id="bdd50-105">Registrar Settings Expander</span></span>
 
<span data-ttu-id="bdd50-p102">La resilienza offre disponibilità elevata e ripristino di emergenza per il pool di registrazione. Dato che è disponibile un servizio di registrazione di backup in caso di errore del servizio di registrazione principale, quello di backup può subentrare al posto di quello in errore, permettendo agli utenti di accedere e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda dei sistemi che hanno avuto problemi con il servizio di registrazione principale.</span><span class="sxs-lookup"><span data-stu-id="bdd50-p102">Resiliency provides high availability and disaster recovery for the Registrar pool. By providing a backup Registrar in the event of failure of the primary Registrar, the backup Registrar can take over for the failed Registrar, allowing users to log on and communicate. Users can potentially experience reduced functionality, depending on which systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="bdd50-109">Nella sezione **Resilienza** della finestra di dialogo **Modifica proprietà** per il Survivable Branch Appliance o il Survivable Branch Server è possibile modificare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="bdd50-109">In the **Resiliency** section of the **Edit Properties** dialog box for your Survivable Branch Appliance or Survivable Branch Server, you can change the following settings:</span></span>
  
- <span data-ttu-id="bdd50-110">**Pool di registrazione di backup e servizi utente associati** Nell'elenco a discesa selezionare il pool Enterprise Edition front end o Standard Edition Front End Server che deve fungere da registrar di backup per Survivable Branch Appliance o Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="bdd50-110">**Associated User service and backup Registrar pool** In the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that is to act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
- <span data-ttu-id="bdd50-111">**Abilitare il failover e il failback** Selezionare questa impostazione per consentire il rilevamento automatico di un registrar non riuscito e la determinazione automatica che il servizio di registrazione principale sia di nuovo attivo e pronto per riprendere il processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="bdd50-111">**Enable Failover and Failback** Select this setting to allow for the automatic detection of a failed Registrar and the automatic determination that the primary Registrar is back up and ready to resume the Registrar process.</span></span>
    
- <span data-ttu-id="bdd50-112">**Intervallo di rilevamento errori (sec)** Digitare il numero di secondi che devono trascorrere prima che venga stabilito che il servizio di registrazione primario ha avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="bdd50-112">**Failure detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar has failed.</span></span> <span data-ttu-id="bdd50-113">Il valore predefinito è 120 secondi.</span><span class="sxs-lookup"><span data-stu-id="bdd50-113">The default value is 120 seconds.</span></span> <span data-ttu-id="bdd50-114">È necessario specificare un valore in questo campo se si seleziona **Abilita failover e failback**.</span><span class="sxs-lookup"><span data-stu-id="bdd50-114">This field is required if you select **Enable Failover and Failback**.</span></span>
    
- <span data-ttu-id="bdd50-115">**Intervallo di rilevamento del fallback (sec)** Digitare il numero di secondi che devono trascorrere prima che venga stabilito che è stato eseguito il backup del servizio di registrazione principale.</span><span class="sxs-lookup"><span data-stu-id="bdd50-115">**Fallback detection interval (sec)** Type the number of seconds that should elapse before it is determined that the primary Registrar is backed up.</span></span> <span data-ttu-id="bdd50-116">Il valore predefinito è 240 secondi.</span><span class="sxs-lookup"><span data-stu-id="bdd50-116">The default value is 240 seconds.</span></span> <span data-ttu-id="bdd50-117">È necessario specificare un valore in questo campo se si seleziona **Abilita failover e failback**.</span><span class="sxs-lookup"><span data-stu-id="bdd50-117">This field is required if you select **Enable Failover and Fallback**.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="bdd50-p105">Quando si definiscono l'intervallo di rilevamento degli errori e l'intervallo di failback, fare attenzione a non immettere un intervallo che possa provocare il failover e il failback se il servizio di registrazione non risponde per un breve periodo di tempo. È infatti possibile che il servizio di registrazione principale non risponda per brevi periodi a causa del caricamento del pool o dei server.</span><span class="sxs-lookup"><span data-stu-id="bdd50-p105">When you define the failure detection interval and the fallback detection interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time. It is possible that the primary Registrar may not respond for short periods of time based on the loading of the pool or servers.</span></span> 
  

