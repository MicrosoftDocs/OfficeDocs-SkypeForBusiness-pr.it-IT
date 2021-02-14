---
title: Installare l'archivio di configurazione locale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Per iniziare l'installazione di un nuovo server dei ruoli di Skype for Business Server 2015, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale di Skype for Business Server. È necessario essere connessi al server in cui si sta eseguendo il passaggio Installa archivio di configurazione locale come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale. Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827146"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="a1c80-108">Installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="a1c80-108">Install Local Configuration Store</span></span>

<span data-ttu-id="a1c80-109">Per iniziare l'installazione di un nuovo server dei ruoli di Skype for Business Server 2015, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="a1c80-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="a1c80-110">L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a1c80-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="a1c80-111">È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a1c80-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="a1c80-112">Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="a1c80-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="a1c80-113">Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="a1c80-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="a1c80-114">Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento [Export Your Topology and Copy It to External Media for Edge Installation.](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)</span><span class="sxs-lookup"><span data-stu-id="a1c80-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="a1c80-115">Per avviare l'installazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1c80-115">To begin the installation:</span></span>

1. <span data-ttu-id="a1c80-116">Nella pagina Skype for Business Server 2015, accanto a **Passaggio 1: Installare l'archivio** di configurazione locale, fare clic su **Esegui.**</span><span class="sxs-lookup"><span data-stu-id="a1c80-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="a1c80-117">Nella pagina **Configurazione server** locale verificare  che l'opzione Recupera configurazione automaticamente dall'archivio di gestione centrale sia selezionata e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a1c80-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="a1c80-118">Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a1c80-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="a1c80-119">L'installazione del SQL Server locale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="a1c80-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="a1c80-120">Gli aggiornamenti sullo stato non verranno visualizzati nella schermata di riepilogo dell'SQL Server durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a1c80-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="a1c80-121">Se si desidera monitorare l'avanzamento dell'installazione, utilizzare Gestione attività per controllare l'SQL Server configurazione.</span><span class="sxs-lookup"><span data-stu-id="a1c80-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


