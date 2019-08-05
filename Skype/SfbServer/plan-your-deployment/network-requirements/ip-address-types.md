---
title: Configurare i tipi di indirizzi IP in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Riepilogo: esaminare le considerazioni di tipo indirizzo IP seguenti prima di implementare Skype for Business Server.'
ms.openlocfilehash: 21e6254255766874872a342a2316dc8cddd5f9d2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194913"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="1d40a-103">Configurare i tipi di indirizzi IP in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1d40a-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="1d40a-104">**Riepilogo:** Esaminare le considerazioni di tipo indirizzo IP seguenti prima di implementare Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1d40a-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="1d40a-105">I tipi di indirizzo IP vengono distribuiti usando le impostazioni della topologia configurate in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="1d40a-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="1d40a-106">Questa sezione descrive come distribuire i tipi di indirizzo IP in server front-end, Mediation Server e Edge Server.</span><span class="sxs-lookup"><span data-stu-id="1d40a-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="1d40a-107">Distribuire i tipi di indirizzi IP in un Front End Server</span><span class="sxs-lookup"><span data-stu-id="1d40a-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="1d40a-108">Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un server front-end.</span><span class="sxs-lookup"><span data-stu-id="1d40a-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="1d40a-109">Per distribuire i tipi di indirizzo IP in un server front-end</span><span class="sxs-lookup"><span data-stu-id="1d40a-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="1d40a-110">In **pool Enterprise Edition front-end**fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-110">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="1d40a-111">In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="1d40a-111">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="1d40a-112">Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="1d40a-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="1d40a-113">Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="1d40a-114">**Finestra di dialogo Modifica proprietà per il pool del server front-end**</span><span class="sxs-lookup"><span data-stu-id="1d40a-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="1d40a-115">**Usare tutti gli indirizzi IP**configurati.</span><span class="sxs-lookup"><span data-stu-id="1d40a-115">**Use all configured IP addresses**.</span></span> <span data-ttu-id="1d40a-116">Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="1d40a-116">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1d40a-117">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="1d40a-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="1d40a-118">**Limitare l'utilizzo del servizio agli indirizzi IP selezionati**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-118">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="1d40a-119">Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="1d40a-119">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="1d40a-120">Se si seleziona questa opzione, è necessario immettere un valore per l' **indirizzo IP principale**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-120">If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="1d40a-121">**Indirizzo IP principale**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-121">**Primary IP address**.</span></span> <span data-ttu-id="1d40a-122">Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="1d40a-122">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="1d40a-123">L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.</span><span class="sxs-lookup"><span data-stu-id="1d40a-123">The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="1d40a-124">**Indirizzo IP PSTN**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-124">**PSTN IP address**.</span></span> <span data-ttu-id="1d40a-125">Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="1d40a-125">Define a PSTN IP address when a Mediation Server is collocated on the Front End Server.</span></span> <span data-ttu-id="1d40a-126">Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1d40a-126">This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="1d40a-127">L'installazione di schede di interfaccia di rete aggiuntive (NIC) per supportare la configurazione degli indirizzi IP PSTN (o per qualsiasi altro motivo) nei server front-end non è supportata.</span><span class="sxs-lookup"><span data-stu-id="1d40a-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="1d40a-128">Per altre informazioni sulle configurazioni di NIC supportate per Skype for Business Server, vedere [piattaforme hardware server per Lync server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="1d40a-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="1d40a-129">Distribuire i tipi di indirizzi IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="1d40a-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="1d40a-130">Usando generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzo IP in un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1d40a-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="1d40a-131">Per distribuire i tipi di indirizzo IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="1d40a-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="1d40a-132">In Generatore di topologia, in **pool**di mediazione, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="1d40a-133">In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="1d40a-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="1d40a-134">Nella finestra di dialogo **modifica proprietà** selezionare il tipo di indirizzo IP che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="1d40a-134">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="1d40a-135">Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="1d40a-135">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="1d40a-136">**Finestra di dialogo Modifica proprietà per il pool di Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="1d40a-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="1d40a-137">**Usare tutti gli indirizzi IP**configurati.</span><span class="sxs-lookup"><span data-stu-id="1d40a-137">**Use all configured IP addresses**.</span></span> <span data-ttu-id="1d40a-138">Selezionare questa opzione se si vuole consentire l'uso di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="1d40a-138">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d40a-139">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="1d40a-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="1d40a-140">**Limitare l'utilizzo del servizio agli indirizzi IP selezionati**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-140">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="1d40a-141">Selezionare questa opzione per specificare un indirizzo specifico da usare nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="1d40a-141">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="1d40a-142">Se si seleziona questa opzione, è necessario immettere un valore per l'indirizzo IP principale.</span><span class="sxs-lookup"><span data-stu-id="1d40a-142">If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="1d40a-143">**Indirizzo IP principale**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-143">**Primary IP address**.</span></span> <span data-ttu-id="1d40a-144">Immettere un indirizzo IP che il server userà per tutte le comunicazioni eccetto PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="1d40a-144">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="1d40a-145">L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo di selezione.</span><span class="sxs-lookup"><span data-stu-id="1d40a-145">The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="1d40a-146">**Indirizzo IP PSTN**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-146">**PSTN IP address**.</span></span> <span data-ttu-id="1d40a-147">Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="1d40a-147">Define a PSTN IP address when a Mediation Server is collocated on the Front End Server.</span></span> <span data-ttu-id="1d40a-148">Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="1d40a-148">This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="1d40a-149">Supportiamo solo due schede di rete su server di mediazione *dedicati* .</span><span class="sxs-lookup"><span data-stu-id="1d40a-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="1d40a-150">Se il ruolo di mediazione sServer è collocato sul front-end, le schede di rete doppie non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="1d40a-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="1d40a-151">Per altre informazioni sulle configurazioni di NIC supportate per Skype for Business Server 2015, vedere [hardware per Skype for Business server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="1d40a-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="1d40a-152">Per altre informazioni sulle configurazioni di NIC supportate per Skype for Business Server 2019, vedere [hardware per Skype for Business server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="1d40a-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="1d40a-153">Distribuire i tipi di indirizzi IP in un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="1d40a-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="1d40a-154">Con generatore di topologie eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="1d40a-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="1d40a-155">Per distribuire i tipi di indirizzo IP in un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="1d40a-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="1d40a-156">In Generatore di topologie, in **pool di bordi**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1d40a-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="1d40a-157">In alternativa, selezionare il server e quindi fare clic su **modifica proprietà** dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="1d40a-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="1d40a-158">Nella finestra **modifica proprietà** selezionare la configurazione dell'indirizzo IP che si vuole supportare.</span><span class="sxs-lookup"><span data-stu-id="1d40a-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="1d40a-159">Per ogni tipo di indirizzo selezionato, è necessario specificare indirizzi interni ed esterni appropriati.</span><span class="sxs-lookup"><span data-stu-id="1d40a-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
