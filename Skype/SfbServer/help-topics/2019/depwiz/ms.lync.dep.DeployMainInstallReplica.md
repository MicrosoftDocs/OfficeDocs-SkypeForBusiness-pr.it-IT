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
description: Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server, è necessario innanzitutto installare SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale (CMS) di Skype for Business Server.
ms.openlocfilehash: dcaf00e0bd14daecb6d2859bf40463265a3d6bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833806"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="ce754-104">Installare l'archivio di configurazione locale</span><span class="sxs-lookup"><span data-stu-id="ce754-104">Install Local Configuration Store</span></span>

<span data-ttu-id="ce754-105">Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server, è necessario innanzitutto installare SQL Server locale che ospiterà l'archivio di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="ce754-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="ce754-106">L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale (CMS) di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ce754-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="ce754-107">È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="ce754-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="ce754-108">Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="ce754-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="ce754-109">Il documento di definizione del generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ce754-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="ce754-110">Per esportare il documento di definizione del generatore di topologie e renderlo disponibile ai server perimetrali, vedere l'argomento[esportare la topologia e copiarla su supporto esterno per l'installazione perimetrale](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span><span class="sxs-lookup"><span data-stu-id="ce754-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="ce754-111">Per avviare l'installazione, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce754-111">To begin the installation:</span></span>

1. <span data-ttu-id="ce754-112">Nella pagina Skype for Business Server fare clic su **Esegui** accanto a **passaggio 1: installazione dell'archivio di configurazione locale**.</span><span class="sxs-lookup"><span data-stu-id="ce754-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="ce754-113">Nella pagina **Configurazione server locale** verificare che l'opzione **Recupera configurazione automaticamente dall'archivio di gestione centrale** sia selezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ce754-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="ce754-114">Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ce754-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="ce754-115">L'installazione di SQL Server locale può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="ce754-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="ce754-116">Durante l'installazione di SQL Server non verranno visualizzati gli aggiornamenti relativi allo stato di avanzamento nella schermata di riepilogo delle installazioni.</span><span class="sxs-lookup"><span data-stu-id="ce754-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="ce754-117">Se si desidera monitorare lo stato dell'installazione, utilizzare Gestione attività per guardare il programma di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ce754-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


