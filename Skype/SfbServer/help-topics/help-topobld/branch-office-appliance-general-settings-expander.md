---
title: Espansione delle impostazioni generali di Survivable Office Appliance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 'Per modificare le impostazioni di un Survivable Branch Appliance o Survivable Branch Server esistente, sono disponibili le sezioni seguenti:'
ms.openlocfilehash: 95f842e72066f7ef19c474b10f7293f05c83cd67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833206"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="cc53d-103">Espansione delle impostazioni generali di Branch Office Appliance</span><span class="sxs-lookup"><span data-stu-id="cc53d-103">Branch Office Appliance General Settings Expander</span></span>

<span data-ttu-id="cc53d-104">Per modificare le impostazioni di un Survivable Branch Appliance o Survivable Branch Server esistente, sono disponibili le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc53d-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>

- <span data-ttu-id="cc53d-105">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="cc53d-105">General settings</span></span>

- <span data-ttu-id="cc53d-106">Impostazioni di resilienza</span><span class="sxs-lookup"><span data-stu-id="cc53d-106">Resiliency settings</span></span>

- <span data-ttu-id="cc53d-107">Impostazioni del Mediation Server</span><span class="sxs-lookup"><span data-stu-id="cc53d-107">Mediation Server settings</span></span>



<span data-ttu-id="cc53d-108">Per un Survivable Branch Appliance o un Survivable Branch Server, sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc53d-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>

## <a name="general-settings"></a><span data-ttu-id="cc53d-109">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="cc53d-109">General settings</span></span>

<span data-ttu-id="cc53d-p101">Nome di dominio completo (FQDN) del Survivable Branch Appliance o Survivable Branch Server. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="cc53d-p101">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>

<span data-ttu-id="cc53d-p102">È possibile selezionare **Usa tutti gli indirizzi IP configurati** o **Limita utilizzo servizio a indirizzi IP selezionati**. Se si seleziona **Limita utilizzo servizio a indirizzi IP selezionati**, sarà necessario definire l'indirizzo IP primario che verrà usato dal server per tutte le comunicazioni, tranne per il gateway PSTN (Public Switched Telephone Network). Sarà necessario definire un indirizzo IP separato per l'utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="cc53d-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>

<span data-ttu-id="cc53d-116">In **Associazioni** è possibile modificare o specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cc53d-116">In **Associations**, you can edit or specify the following:</span></span>

- <span data-ttu-id="cc53d-117">Associa server di archiviazione consente di scegliere di associare un server di archiviazione al Survivable Branch Appliance o al Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="cc53d-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cc53d-118">È possibile eseguire la selezione da un server di archiviazione già definito  selezionandolo nell'elenco a discesa oppure fare clic su Nuovo per specificare un nuovo server di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc53d-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cc53d-119">Prima della pubblicazione della nuova topologia definita, il server specificato deve esistere ed essere aggiunto al dominio.</span><span class="sxs-lookup"><span data-stu-id="cc53d-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span>

- <span data-ttu-id="cc53d-120">Associa Monitoring Server consente di scegliere di associare un Monitoring Server al Survivable Branch Appliance o al Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="cc53d-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cc53d-121">È possibile scegliere da un Monitoring Server già definito selezionandolo nell'elenco a discesa oppure fare clic su **Nuovo** per specificare un nuovo Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="cc53d-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>

- <span data-ttu-id="cc53d-122">Associa pool di server perimetrali consente di scegliere di associare un server perimetrale o un pool di server perimetrali al Survivable Branch Appliance o al Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="cc53d-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cc53d-123">È possibile usare un server perimetrale o un pool di server perimetrali già definito selezionandolo nell'elenco a discesa oppure specificare un nuovo server perimetrale o un nuovo pool di server perimetrali facendo clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="cc53d-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>

## <a name="resiliency"></a><span data-ttu-id="cc53d-124">Resilienza</span><span class="sxs-lookup"><span data-stu-id="cc53d-124">Resiliency</span></span>

<span data-ttu-id="cc53d-p106">La resilienza garantisce una disponibilità elevata per il pool di registrazione. Fornendo una funzione di registrazione di backup, in caso di malfunzionamento della funzione di registrazione principale, quella di backup può subentrare, consentendo agli utenti di connettersi e comunicare. Gli utenti possono riscontrare funzionalità ridotte, a seconda di quali sistemi hanno avuto problemi con la funzione di registrazione principale.</span><span class="sxs-lookup"><span data-stu-id="cc53d-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>

<span data-ttu-id="cc53d-128">Nell'elenco a discesa selezionare il pool Enterprise Edition Front End o il Front End Server Standard Edition che fungerà da funzione di registrazione di backup per il Survivable Branch Appliance o il Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="cc53d-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="cc53d-129">È inoltre possibile scegliere di impostare intervalli di tempo per il failover e il failback.</span><span class="sxs-lookup"><span data-stu-id="cc53d-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="cc53d-130">Abilitando le impostazioni per tali intervalli (specificati in secondi), viene rilevata automaticamente la presenza di una funzione di registrazione con problemi ed è previsto un periodo di tempo per determinare automaticamente se la funzione di registrazione principale sia di nuovo attiva e pronta per riacquisire il controllo del processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cc53d-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc53d-131">Nel definire l'intervallo di rilevamento degli errori e l'intervallo di failback, prestare attenzione a non immettere un intervallo che possa dare luogo al failover e al failback se la funzione di registrazione non risponde per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="cc53d-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="cc53d-132">È infatti possibile che la funzione di registrazione principale non risponda per brevi periodi a causa del caricamento del pool o dei server.</span><span class="sxs-lookup"><span data-stu-id="cc53d-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="cc53d-133">I valori predefiniti per un Survivable Branch Appliance o un Survivable Branch Server in un sito in un pool o Standard Edition Front End Server sono 120 secondi per il failover e 240 secondi per il fallback.</span><span class="sxs-lookup"><span data-stu-id="cc53d-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span>

## <a name="mediation-server"></a><span data-ttu-id="cc53d-134">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="cc53d-134">Mediation Server</span></span>

<span data-ttu-id="cc53d-135">Per **Mediation Server** è possibile specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cc53d-135">For **Mediation Server** you can specify the following:</span></span>

<span data-ttu-id="cc53d-136">La casella di controllo **Mediation Server nella stessa posizione abilitato** non è disponibile per un Survivable Branch Appliance o un Survivable Branch Server perché il Mediation Server è collocato.</span><span class="sxs-lookup"><span data-stu-id="cc53d-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>

<span data-ttu-id="cc53d-p109">Definire la porta di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.</span><span class="sxs-lookup"><span data-stu-id="cc53d-p109">You define the listening port on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="cc53d-p110">Definire gateway PSTN associati al Mediation Server collocato. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server. Se i gateway non sono stati definiti ma sono disponibili per la definizione, sarà possibile selezionare **Nuovo**. Sarà inoltre possibile rimuovere i gateway già configurati per il Mediation Server. A tale scopo, selezionare il gateway e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="cc53d-p110">You define PSTN gateways that are associated with the collocated Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you have not defined any gateways, but you have them available to define, you can select **New**. You can also remove gateways that are already configured for this Mediation Server. Select the gateway, and then click **Remove**.</span></span>

<span data-ttu-id="cc53d-p111">Se a un Mediation Server è associato più di un gateway, il primo gateway associato sarà quello predefinito. Se è necessario scegliere un altro gateway come predefinito, selezionare il gateway desiderato e fare clic su **Rendi predefinito**.</span><span class="sxs-lookup"><span data-stu-id="cc53d-p111">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway. If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc53d-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc53d-149">See also</span></span>

<span data-ttu-id="cc53d-150">Per informazioni dettagliate sulla definizione e sulla configurazione delle impostazioni per il Survivable Branch Appliance o il Survivable Branch Server, vedere [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc53d-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](https://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>


