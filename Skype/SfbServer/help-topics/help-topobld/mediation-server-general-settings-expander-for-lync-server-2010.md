---
title: Espansione delle impostazioni di Mediation Server per Lync Server 2010
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
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'In questa finestra di dialogo è possibile modificare le proprietà dei Mediation Server. Sul lato sinistro è presente un insieme di collegamenti rapidi che consentono di accedere alle impostazioni delle sezioni Generale, Hop successivo e Gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:'
ms.openlocfilehash: 6c8c238ce7d89db53f3b92a0f513c080976a3bab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114192"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="74ad1-105">Espansione delle impostazioni di Mediation Server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="74ad1-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="74ad1-106">In questa finestra di dialogo è possibile modificare le proprietà dei Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="74ad1-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="74ad1-107">Sul lato sinistro è presente un insieme di collegamenti rapidi che consentono di accedere alle impostazioni delle sezioni Generale, Hop successivo e Gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="74ad1-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="74ad1-108">In ogni sezione sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74ad1-108">In each section are the following settings:</span></span>

 <span data-ttu-id="74ad1-109">**Generale**:</span><span class="sxs-lookup"><span data-stu-id="74ad1-109">**General**:</span></span>

- <span data-ttu-id="74ad1-110">**FQDN**: modificare il nome di dominio completo del Mediation Server</span><span class="sxs-lookup"><span data-stu-id="74ad1-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="74ad1-111">**Associazioni**: selezionare la casella di controllo Associa pool di server perimetrali (per i componenti **multimediali)** e selezionare un server perimetrale o un pool di server perimetrali per il Mediation Server da utilizzare come percorso multimediale per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="74ad1-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="74ad1-112">**Hop successivo**:</span><span class="sxs-lookup"><span data-stu-id="74ad1-112">**Next hop**:</span></span>

- <span data-ttu-id="74ad1-113">**Selezione hop successivo:** selezionare da un elenco il Front End Server o il pool Front End da utilizzare come percorso per il Mediation Server da utilizzare per comunicare con la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="74ad1-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="74ad1-114">**Gateway PSTN**:</span><span class="sxs-lookup"><span data-stu-id="74ad1-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="74ad1-115">**Gateway PSTN Mediation Server**:</span><span class="sxs-lookup"><span data-stu-id="74ad1-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="74ad1-116">**Porte di attesa:** definire le porte su cui il Mediation Server sarà in ascolto.</span><span class="sxs-lookup"><span data-stu-id="74ad1-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="74ad1-117">È possibile definire una porta per **TLS** (Transport Layer Security) o **TCP** (Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="74ad1-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="74ad1-118">Per rendere disponibile la voce della porta relativa a TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="74ad1-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="74ad1-119">Consultare la documentazione e le impostazioni di configurazione del gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi.</span><span class="sxs-lookup"><span data-stu-id="74ad1-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="74ad1-120">TLS è un protocollo più sicuro, che utilizza certificati per crittografare il traffico tra Mediation Server e il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="74ad1-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="74ad1-121">Non tutti i gateway PSTN supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="74ad1-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="74ad1-122">Di seguito sono elencati i trunk SIP e i gateway definiti e configurati per la distribuzione corrente.</span><span class="sxs-lookup"><span data-stu-id="74ad1-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="74ad1-123">Se non è presente alcuna voce, significa che non ci sono trunk SIP o gateway PSTN configurati per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="74ad1-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="74ad1-124">È possibile definire e configurare trunk e gateway in **Componenti condivisi** in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="74ad1-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="74ad1-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74ad1-125">See also</span></span>

[<span data-ttu-id="74ad1-126">Panoramica del trunking SIP</span><span class="sxs-lookup"><span data-stu-id="74ad1-126">Overview of SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[<span data-ttu-id="74ad1-127">Opzioni di distribuzione del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="74ad1-127">PSTN Gateway Deployment Options</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)