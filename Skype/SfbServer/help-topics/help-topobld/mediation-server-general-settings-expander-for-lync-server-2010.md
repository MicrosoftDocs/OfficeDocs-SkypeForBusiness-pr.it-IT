---
title: Espansione delle impostazioni generali di Mediation Server per Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Modificare le proprietà dei server di mediazione in questa finestra di dialogo. Lungo il lato sinistro è presente un set di collegamenti rapidi che consente di eseguire le impostazioni per le impostazioni generali, le impostazioni hop successivo e le impostazioni del gateway PSTN. In ogni sezione sono disponibili le impostazioni seguenti:'
ms.openlocfilehash: d439698bf0e383f9c89fb749ef4cedc7ae253997
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684549"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="eff91-105">Espansione delle impostazioni generali di Mediation Server per Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="eff91-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="eff91-106">Modificare le proprietà dei server di mediazione in questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="eff91-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="eff91-107">Lungo il lato sinistro è presente un set di collegamenti rapidi che consente di eseguire le impostazioni per le impostazioni generali, le impostazioni hop successivo e le impostazioni del gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="eff91-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="eff91-108">In ogni sezione sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="eff91-108">In each section are the following settings:</span></span>

 <span data-ttu-id="eff91-109">**Generale**:</span><span class="sxs-lookup"><span data-stu-id="eff91-109">**General**:</span></span>

- <span data-ttu-id="eff91-110">**FQDN**: si modifica il nome di dominio completo del Mediation Server</span><span class="sxs-lookup"><span data-stu-id="eff91-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="eff91-111">**Associazioni**: selezionare la casella di controllo **Associa pool Edge (per componenti multimediali)** e selezionare un server perimetrale o un pool di Edge per il Mediation Server da usare come percorso multimediale per l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="eff91-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="eff91-112">**Hop successivo**:</span><span class="sxs-lookup"><span data-stu-id="eff91-112">**Next hop**:</span></span>

- <span data-ttu-id="eff91-113">**Selezione hop successivo**: selezionare da un elenco il front end server o il pool Front end da usare come percorso per il server di mediazione da usare per comunicare con la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="eff91-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="eff91-114">**Gateway PSTN**:</span><span class="sxs-lookup"><span data-stu-id="eff91-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="eff91-115">**Gateway PSTN di Mediation Server**:</span><span class="sxs-lookup"><span data-stu-id="eff91-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="eff91-116">**Porte in ascolto**: definire le porte che il server di mediazione ascolterà.</span><span class="sxs-lookup"><span data-stu-id="eff91-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="eff91-117">Puoi definire una porta per **TLS** o Transport Layer Security o **TCP**o Transport Control Protocol.</span><span class="sxs-lookup"><span data-stu-id="eff91-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="eff91-118">Per rendere disponibile la voce di porta per TCP, è necessario selezionare la casella di controllo **Abilita porta TCP**.</span><span class="sxs-lookup"><span data-stu-id="eff91-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eff91-119">Fare riferimento alla documentazione e alle impostazioni di configurazione per il gateway PSTN (Public Switched Telephone Network) per determinare se è necessario abilitare e definire i valori di porta TLS, TCP o entrambi.</span><span class="sxs-lookup"><span data-stu-id="eff91-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="eff91-120">TLS è un protocollo più sicuro, usando i certificati per crittografare il traffico tra il Mediation Server e il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="eff91-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="eff91-121">Non tutti i gateway PSTN supportano TLS.</span><span class="sxs-lookup"><span data-stu-id="eff91-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="eff91-122">Un elenco di trunk SIP e i gateway definiti e configurati per la distribuzione sono elencati.</span><span class="sxs-lookup"><span data-stu-id="eff91-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="eff91-123">Se non sono presenti voci, non ci sono trunk SIP o gateway PSTN configurati per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="eff91-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="eff91-124">Si definiscono e si configurano trunk e gateway in **componenti condivisi** in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="eff91-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="eff91-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eff91-125">See also</span></span>

[<span data-ttu-id="eff91-126">Panoramica del trunking SIP</span><span class="sxs-lookup"><span data-stu-id="eff91-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="eff91-127">Opzioni di distribuzione del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="eff91-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
