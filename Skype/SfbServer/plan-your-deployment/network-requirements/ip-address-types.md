---
title: Configurare i tipi di indirizzi IP in Skype for Business
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
description: 'Riepilogo: esaminare le considerazioni sul tipo di indirizzo IP riportate di seguito prima di implementare Skype for Business Server.'
ms.openlocfilehash: ba10dd223e7e099d27e31bddce478603f50e49a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101252"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="786b1-103">Configurare i tipi di indirizzi IP in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="786b1-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="786b1-104">**Riepilogo:** Prima di implementare Skype for Business Server, leggere le considerazioni sul tipo di indirizzo IP riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="786b1-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="786b1-105">I tipi di indirizzi IP vengono distribuiti utilizzando le impostazioni della topologia configurate in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="786b1-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="786b1-106">In questa sezione viene descritto come distribuire tipi di indirizzi IP in Front End Server, Mediation Server e server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="786b1-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="786b1-107">Distribuire tipi di indirizzi IP in un Front End Server</span><span class="sxs-lookup"><span data-stu-id="786b1-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="786b1-108">Utilizzando Generatore di topologie, eseguire i passaggi della procedura seguente per distribuire i tipi di indirizzi IP in un Front End Server.</span><span class="sxs-lookup"><span data-stu-id="786b1-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="786b1-109">Per distribuire i tipi di indirizzi IP in un Front End Server</span><span class="sxs-lookup"><span data-stu-id="786b1-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="786b1-p102">In **Pool Enterprise Edition Front End** fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **Modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="786b1-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="786b1-112">Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="786b1-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="786b1-113">Per una configurazione dual stack, selezionare **Abilita IPv4** e **Abilita IPv6.**</span><span class="sxs-lookup"><span data-stu-id="786b1-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="786b1-114">**Finestra di dialogo Modifica proprietà per il pool Front End Server**</span><span class="sxs-lookup"><span data-stu-id="786b1-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="786b1-p104">**Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="786b1-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="786b1-117">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="786b1-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="786b1-p105">**Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un determinato indirizzo da utilizzare nel nuovo server. Se si seleziona questa opzione, sarà necessario immettere un valore per **Indirizzo IP primario**.</span><span class="sxs-lookup"><span data-stu-id="786b1-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="786b1-p106">**Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, tranne quelle su rete PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="786b1-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="786b1-p107">**Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel Front End Server. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="786b1-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="786b1-127">L'installazione di schede di interfaccia di rete aggiuntive (NIC) per supportare la configurazione degli indirizzi IP PSTN (o per qualsiasi altro motivo) nei Front End Server non è supportata.</span><span class="sxs-lookup"><span data-stu-id="786b1-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="786b1-128">Per ulteriori informazioni sulle configurazioni NIC supportate per Skype for Business Server, vedere [Server hardware platforms for Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)</span><span class="sxs-lookup"><span data-stu-id="786b1-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="786b1-129">Distribuire tipi di indirizzi IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="786b1-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="786b1-130">Utilizzando Generatore di topologie, eseguire i passaggi della procedura seguente per distribuire i tipi di indirizzi IP in un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="786b1-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="786b1-131">Per distribuire i tipi di indirizzi IP in un Mediation Server</span><span class="sxs-lookup"><span data-stu-id="786b1-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="786b1-132">In Generatore di topologie, in **Pool Mediation Server,** fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi **scegliere Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="786b1-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="786b1-133">In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="786b1-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="786b1-p110">Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione con dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="786b1-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="786b1-136">**Finestra di dialogo Modifica proprietà per il pool Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="786b1-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="786b1-p111">**Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="786b1-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="786b1-139">Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="786b1-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="786b1-p112">**Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da utilizzare nel nuovo server. Se si seleziona questa opzione è necessario immettere un valore per Indirizzo IP primario.</span><span class="sxs-lookup"><span data-stu-id="786b1-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="786b1-p113">**Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, ad eccezione di PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="786b1-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="786b1-p114">**Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel Front End Server. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.</span><span class="sxs-lookup"><span data-stu-id="786b1-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="786b1-149">Sono supportate solo due schede di rete *su* Mediation Server dedicati.</span><span class="sxs-lookup"><span data-stu-id="786b1-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="786b1-150">Se il ruolo Mediation Sserver è collocato nel Front End, le schede di rete doppie non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="786b1-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="786b1-151">Per ulteriori informazioni sulle configurazioni NIC supportate per Skype for Business Server 2015, vedere [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="786b1-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="786b1-152">Per ulteriori informazioni sulle configurazioni NIC supportate per Skype for Business Server 2019, vedere [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="786b1-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="786b1-153">Distribuire tipi di indirizzi IP in un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="786b1-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="786b1-154">Utilizzando Generatore di topologie, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="786b1-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="786b1-155">Per distribuire tipi di indirizzo IP su un server perimetrale</span><span class="sxs-lookup"><span data-stu-id="786b1-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="786b1-156">In Generatore di topologie, in Pool di server perimetrali, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi **scegliere Modifica proprietà**. </span><span class="sxs-lookup"><span data-stu-id="786b1-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="786b1-157">(Alternativamente, selezionare il server e fare clic su **Modifica proprietà** dal menu **Azione**.)</span><span class="sxs-lookup"><span data-stu-id="786b1-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="786b1-158">Nella finestra **Modifica proprietà**, selezionare la configurazione dell'indirizzo IP che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="786b1-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="786b1-159">Per ciascun tipo di indirizzo selezionato, è necessario fornire gli indirizzi interni e esterni appropriati.</span><span class="sxs-lookup"><span data-stu-id="786b1-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>