---
title: Impedire nuove connessioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188549"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a><span data-ttu-id="1b285-102">Prevenzione di nuove connessioni a Skype for Business Server per la manutenzione del server</span><span class="sxs-lookup"><span data-stu-id="1b285-102">Preventing new connections to Skype for Business Server for server maintenance</span></span>


<span data-ttu-id="1b285-103">Skype for Business Server consente di prendere un server offline (ad esempio, per applicare aggiornamenti software o hardware) senza perdita di servizio agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1b285-103">Skype for Business Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="1b285-104">Quando si specifica l'opzione per impedire le nuove connessioni o le chiamate a un server in un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione.</span><span class="sxs-lookup"><span data-stu-id="1b285-104">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="1b285-105">Queste nuove connessioni e chiamate vengono instradate tramite altri server nel pool.</span><span class="sxs-lookup"><span data-stu-id="1b285-105">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="1b285-106">Un server che impedisce le nuove connessioni consente di continuare le sessioni sulle connessioni esistenti finché non terminano naturalmente.</span><span class="sxs-lookup"><span data-stu-id="1b285-106">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="1b285-107">Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere preso offline.</span><span class="sxs-lookup"><span data-stu-id="1b285-107">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="1b285-108">Quando si impediscono nuove connessioni a un server front-end, alcune caratteristiche e servizi di Skype for Business Server si basano sul bilanciamento del carico DNS per verificare che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="1b285-108">When you prevent new connections to a Front End Server, some Skype for Business Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="1b285-109">Se non si usa il bilanciamento del carico DNS sul pool, le connessioni tramite questi servizi potrebbero non essere reindirizzate ad altri server durante il periodo in cui il server impedisce le nuove connessioni e quindi quando il server viene disconnesso alcune sessioni e le chiamate possono essere interrotti.</span><span class="sxs-lookup"><span data-stu-id="1b285-109">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="1b285-110">Le caratteristiche che si basano sul bilanciamento del carico DNS per verificare che questa opzione funzioni correttamente sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b285-110">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="1b285-111">Operatore</span><span class="sxs-lookup"><span data-stu-id="1b285-111">Attendant</span></span>

  - <span data-ttu-id="1b285-112">Applicazione per l'annuncio di conferenza</span><span class="sxs-lookup"><span data-stu-id="1b285-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="1b285-113">Response Group Application</span><span class="sxs-lookup"><span data-stu-id="1b285-113">Response Group application</span></span>

  - <span data-ttu-id="1b285-114">Applicazione annuncio</span><span class="sxs-lookup"><span data-stu-id="1b285-114">Announcement application</span></span>

  - <span data-ttu-id="1b285-115">Applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="1b285-115">Call Park application</span></span>

<span data-ttu-id="1b285-116">Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [requisiti di bilanciamento del carico](../../plan-your-deployment/network-requirements/load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="1b285-116">For details about DNS load balancing, see [Load balancing requirements](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span>

<span data-ttu-id="1b285-117">Oltre a impedire nuove connessioni per tutti i servizi in un server che gestisce Skype for Business Server, puoi anche evitare nuove connessioni per i singoli servizi di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1b285-117">In addition to preventing new connections for all services on a server running Skype for Business Server, you can also prevent new connections for individual Skype for Business Server services.</span></span> <span data-ttu-id="1b285-118">Ad esempio, questo metodo è utile in una situazione in cui è necessario applicare un aggiornamento di Skype for Business Server che non richiede l'arresto dell'intero server.</span><span class="sxs-lookup"><span data-stu-id="1b285-118">For example, this method is useful in a situation where you need to apply a Skype for Business Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="1b285-119">Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio mentre viene raggruppato e visualizzato nell'elenco di servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="1b285-119">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="1b285-120">Ad esempio, il servizio front-end di Skype for Business Server e l'agente di raccolta dati per il monitoraggio sono servizi distinti per Skype for Business Server, ma nell'elenco dei servizi Windows vengono consolidati e visualizzati come front-end di Skype for Business Server servizio.</span><span class="sxs-lookup"><span data-stu-id="1b285-120">For example, the Skype for Business Server Front-End service and the data collection agent for Monitoring are separate Skype for Business Server services, but in the Windows services list they are consolidated and shown as the Skype for Business Server Front End service.</span></span> <span data-ttu-id="1b285-121">Puoi impedire le nuove connessioni per il servizio front-end di Skype for Business Server, ma non puoi impedire le nuove connessioni per questi due singoli servizi Skype for Business Server separatamente.</span><span class="sxs-lookup"><span data-stu-id="1b285-121">You can prevent new connections for the Skype for Business Server Front End service, but you cannot prevent new connections for these two individual underlying Skype for Business Server services separately.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b285-122">Quando si imposta un server per impedire nuove connessioni e quindi riavviare il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="1b285-122">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="1b285-123">Per evitare questo problema, imposta il server solo per sospendere e riprendere manualmente, prima di riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="1b285-123">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a><span data-ttu-id="1b285-124">Per evitare nuove connessioni a Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1b285-124">To prevent new connections to Skype for Business Server</span></span>

1.  <span data-ttu-id="1b285-125">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="1b285-125">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="1b285-126">Aprire la console snap-in Servizi: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="1b285-126">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="1b285-127">Nell'elenco fare doppio clic sul servizio Windows Skype for Business Server a cui si vogliono impedire le nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="1b285-127">In the list, double-click the Skype for Business Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="1b285-128">Nella finestra di dialogo Proprietà, in **stato del servizio: avviato**, \*\*\*\* fare clic su Sospendi.</span><span class="sxs-lookup"><span data-stu-id="1b285-128">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="1b285-129">Facoltativamente, ma consigliato, accanto a **tipo di avvio**, fare clic su **manuale**.</span><span class="sxs-lookup"><span data-stu-id="1b285-129">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1b285-130">Quando si imposta un server per impedire nuove connessioni e quindi riavviare il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio.</span><span class="sxs-lookup"><span data-stu-id="1b285-130">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="1b285-131">Per evitare questo problema, imposta il server solo per sospendere e riprendere manualmente, prima di riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="1b285-131">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>
