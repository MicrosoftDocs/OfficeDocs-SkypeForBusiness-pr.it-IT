---
title: Configurare i tipi di indirizzi IP in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: "Riepilogo: esaminare le considerazioni relative al tipo di indirizzo IP di seguito prima dell'implementazione di Skype for Business Server."
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825257"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="50eb4-103">Configurare i tipi di indirizzi IP in Skype for business</span><span class="sxs-lookup"><span data-stu-id="50eb4-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="50eb4-104">**Riepilogo:** Esaminare le considerazioni relative al tipo di indirizzo IP seguenti prima di implementare Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="50eb4-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="50eb4-105">È possibile distribuire i tipi di indirizzi IP utilizzando le impostazioni di topologia configurate in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="50eb4-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="50eb4-106">In questa sezione viene descritto come distribuire i tipi di indirizzi IP nei Front End Server, Mediation Server e server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="50eb4-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="50eb4-107">Distribuire i tipi di indirizzi IP in un front end server</span><span class="sxs-lookup"><span data-stu-id="50eb4-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="50eb4-108">Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un front end server.</span><span class="sxs-lookup"><span data-stu-id="50eb4-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="50eb4-109">Per distribuire i tipi di indirizzi IP in un Front End Server</span><span class="sxs-lookup"><span data-stu-id="50eb4-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="50eb4-p102">In **Pool Enterprise Edition Front End** fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **Modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="50eb4-112">Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="50eb4-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="50eb4-113">Per una configurazione a doppio stack, selezionare **Abilita IPv4** e **Abilita IPv6**.</span><span class="sxs-lookup"><span data-stu-id="50eb4-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="50eb4-114">**Finestra di dialogo Modifica proprietà per il pool Front End Server**</span><span class="sxs-lookup"><span data-stu-id="50eb4-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="50eb4-p104">**Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="50eb4-117">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="50eb4-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="50eb4-p105">**Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un determinato indirizzo da utilizzare nel nuovo server. Se si seleziona questa opzione, sarà necessario immettere un valore per **Indirizzo IP primario**.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="50eb4-p106">**Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, tranne quelle su rete PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="50eb4-p107">**Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel Front End Server. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="50eb4-127">L'installazione di altre schede di interfaccia di rete (NIC) per supportare la configurazione degli indirizzi IP PSTN (o per qualsiasi altro motivo) nei front end server non è supportata.</span><span class="sxs-lookup"><span data-stu-id="50eb4-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="50eb4-128">Per ulteriori informazioni sulle configurazioni di NIC supportate per Skype for Business Server, vedere [server hardware Platforms for Lync server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="50eb4-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="50eb4-129">Distribuire i tipi di indirizzi IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="50eb4-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="50eb4-130">Utilizzando Generatore di topologie, eseguire i passaggi descritti nella procedura seguente per distribuire i tipi di indirizzi IP in un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="50eb4-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="50eb4-131">Per distribuire i tipi di indirizzi IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="50eb4-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="50eb4-132">In Generatore di topologie fare clic con il pulsante destro del mouse sul server all'interno di un pool in **pool di Mediation** e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="50eb4-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="50eb4-133">In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="50eb4-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="50eb4-p110">Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione con dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="50eb4-136">**Finestra di dialogo Modifica proprietà per il pool Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="50eb4-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="50eb4-p111">**Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="50eb4-139">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="50eb4-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="50eb4-p112">**Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da utilizzare nel nuovo server. Se si seleziona questa opzione è necessario immettere un valore per Indirizzo IP primario.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="50eb4-p113">**Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, ad eccezione di PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="50eb4-p114">**Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel Front End Server. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="50eb4-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="50eb4-149">Sono supportate solo due schede di rete su Mediation Server *dedicati* .</span><span class="sxs-lookup"><span data-stu-id="50eb4-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="50eb4-150">Se il ruolo Mediation sServer è collocato nel front-end, le schede di rete dual non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="50eb4-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="50eb4-151">Per ulteriori informazioni sulle configurazioni di NIC supportate per Skype for Business Server 2015, vedere [hardware for Skype for Business server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="50eb4-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="50eb4-152">Per ulteriori informazioni sulle configurazioni di NIC supportate per Skype for Business Server 2019, vedere [hardware for Skype for Business server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="50eb4-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="50eb4-153">Distribuire i tipi di indirizzi IP in un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="50eb4-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="50eb4-154">Utilizzando Generatore di topologie, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50eb4-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="50eb4-155">Per distribuire tipi di indirizzo IP su un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="50eb4-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="50eb4-156">In Generatore di topologie, in pool di server **perimetrali**, fare clic con il pulsante destro del mouse su di esso in un pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="50eb4-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="50eb4-157">(Alternativamente, selezionare il server e fare clic su **Modifica proprietà** dal menu **Azione**.)</span><span class="sxs-lookup"><span data-stu-id="50eb4-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="50eb4-158">Nella finestra **Modifica proprietà**, selezionare la configurazione dell'indirizzo IP che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="50eb4-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="50eb4-159">Per ciascun tipo di indirizzo selezionato, è necessario fornire gli indirizzi interni e esterni appropriati.</span><span class="sxs-lookup"><span data-stu-id="50eb4-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
