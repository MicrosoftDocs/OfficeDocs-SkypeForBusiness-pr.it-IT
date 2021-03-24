---
title: Installare l'archivio di configurazione locale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione di un nuovo server dei ruoli di Skype for Business Server, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale (CMS) di Skype for Business Server.
ms.openlocfilehash: 78492f8ce913d8f73336ae4f6cdf06fd340ed5f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095980"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="a028e-104">Installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="a028e-104">Install Local Configuration Store</span></span>

<span data-ttu-id="a028e-105">Per iniziare l'installazione di un nuovo server dei ruoli di Skype for Business Server, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="a028e-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="a028e-106">L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale (CMS) di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a028e-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="a028e-107">È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a028e-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="a028e-108">Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a028e-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="a028e-109">Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a028e-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="a028e-110">Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span><span class="sxs-lookup"><span data-stu-id="a028e-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="a028e-111">Per avviare l'installazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a028e-111">To begin the installation:</span></span>

1. <span data-ttu-id="a028e-112">Nella pagina Skype for Business Server, accanto a **Passaggio 1: Installare l'archivio di configurazione locale,** fare clic su **Esegui.**</span><span class="sxs-lookup"><span data-stu-id="a028e-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="a028e-113">Nella pagina **Configurazione server** locale verificare  che l'opzione Recupera configurazione automaticamente dall'archivio di gestione centrale sia selezionata e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a028e-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="a028e-114">Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a028e-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="a028e-115">L'installazione del SQL Server locale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="a028e-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="a028e-116">Gli aggiornamenti non verranno visualizzati nella schermata di riepilogo dell'installazione durante SQL Server'installazione.</span><span class="sxs-lookup"><span data-stu-id="a028e-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="a028e-117">Se si desidera monitorare lo stato dell'installazione, utilizzare Task Manager per controllare l'SQL Server installazione.</span><span class="sxs-lookup"><span data-stu-id="a028e-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>