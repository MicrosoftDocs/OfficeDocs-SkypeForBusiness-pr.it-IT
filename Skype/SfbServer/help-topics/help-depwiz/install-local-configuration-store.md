---
title: Installare un archivio di configurazione locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server 2015, è necessario prima di tutto installare il server SQL locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura di Skype for Business Server Central Management store (CMS). È necessario essere connessi al server in cui si sta eseguendo il passaggio Installa archivio di configurazione locale come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione del generatore di topologia verrà letto dal documento di definizione esportato anziché dall'Central Management store. Per esportare il documento di definizione del generatore di topologia e renderlo disponibile per gli Edge Server, vedere l'argomento esportare la topologia e copiarla in elementi multimediali esterni per l'installazione di Edge.
ms.openlocfilehash: c3da29e6c9630b22e7ae947f9b23ab5dbeebd13c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195242"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="e5f0a-108">Installare un archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="e5f0a-108">Install Local Configuration Store</span></span>

<span data-ttu-id="e5f0a-109">Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server 2015, è necessario prima di tutto installare il server SQL locale che ospiterà l'archivio di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="e5f0a-110">L'archivio di configurazione locale fungerà da replica di sola lettura di Skype for Business Server Central Management store (CMS).</span><span class="sxs-lookup"><span data-stu-id="e5f0a-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="e5f0a-111">È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e5f0a-112">Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="e5f0a-113">Il documento di definizione del generatore di topologia verrà letto dal documento di definizione esportato anziché dall'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="e5f0a-114">Per esportare il documento di definizione del generatore di topologia e renderlo disponibile per gli Edge Server, vedere l'argomento [esportare la topologia e copiarla in elementi multimediali esterni per l'installazione di Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="e5f0a-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="e5f0a-115">Per avviare l'installazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5f0a-115">To begin the installation:</span></span>

1. <span data-ttu-id="e5f0a-116">Nella pagina Skype for Business Server 2015, accanto a **Step1: install Local Configuration Store**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="e5f0a-117">Nella pagina **Configurazione server locale** verificare che l'opzione **Recupera configurazione automaticamente da Archivio di gestione centrale** sia selezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="e5f0a-118">Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f0a-119">L'installazione di SQL Server locale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="e5f0a-120">Durante l'installazione di SQL Server, gli aggiornamenti sullo stato di avanzamento non verranno visualizzati nella schermata Riepilogo installazioni.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="e5f0a-121">Se si vuole monitorare lo stato di avanzamento dell'installazione, usare Gestione attività per guardare la configurazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5f0a-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


