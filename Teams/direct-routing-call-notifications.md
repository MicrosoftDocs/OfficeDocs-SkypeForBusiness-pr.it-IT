---
title: Routing diretto del sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: Notifica delle chiamate di routing diretto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 07efe11d304107a5a8606a07f5d1c2a7a130bc0b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "37639380"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="2eaaf-103">Gestire le notifiche delle chiamate</span><span class="sxs-lookup"><span data-stu-id="2eaaf-103">Manage call notifications</span></span>

<span data-ttu-id="2eaaf-104">Questo articolo descrive come gestire le notifiche delle chiamate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2eaaf-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="2eaaf-105">È possibile configurare gli endpoint delle chiamate sia in team che in un PBX (Private Branch Exchange) di terze parti o in SBC (Session Border Controller).</span><span class="sxs-lookup"><span data-stu-id="2eaaf-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="2eaaf-106">Questa operazione è utile, ad esempio, se si vuole inviare una chiamata ai telefoni mobili e da tavolo di un utente contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2eaaf-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="2eaaf-107">Nel diagramma seguente l'utente Irena ha due endpoint:</span><span class="sxs-lookup"><span data-stu-id="2eaaf-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="2eaaf-108">Un endpoint Teams</span><span class="sxs-lookup"><span data-stu-id="2eaaf-108">A Teams endpoint</span></span>
- <span data-ttu-id="2eaaf-109">Un telefono SIP connesso a un SBC di terze parti</span><span class="sxs-lookup"><span data-stu-id="2eaaf-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="2eaaf-110">Quando arriva una chiamata, l'SBC biforca la chiamata tra il routing diretto del sistema telefonico e lo SBC di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2eaaf-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagramma che Mostra gli endpoint di Team biforcati](media/direct-routing-call-notification-1.png)

<span data-ttu-id="2eaaf-112">Se la chiamata viene accettata in fork 2 (da parte di SBC di terze parti), i team generano una notifica "chiamata persa".</span><span class="sxs-lookup"><span data-stu-id="2eaaf-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="2eaaf-113">È possibile impedire la notifica "chiamata persa" configurando il SBC per l'invio di un annullamento su fork 1 come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2eaaf-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="2eaaf-114">MOTIVO: SIP; causa = 200; testo "chiamata completata altrove"</span><span class="sxs-lookup"><span data-stu-id="2eaaf-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="2eaaf-115">Tieni presente che la chiamata non verrà registrata nei record dettagli chiamata di Microsoft Phone System come chiamata corretta.</span><span class="sxs-lookup"><span data-stu-id="2eaaf-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="2eaaf-116">La chiamata verrà registrata come "tentativo" con il codice SIP finale "487", il sottocodice finale Microsoft "540200" e la frase finale del codice SIP "chiamata completata altrove".</span><span class="sxs-lookup"><span data-stu-id="2eaaf-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="2eaaf-117">Per visualizzare i record dettagli chiamata, visitare il portale di amministrazione di teams, le analisi e i report, i report sull'utilizzo e selezionare l'uso di PSNT.</span><span class="sxs-lookup"><span data-stu-id="2eaaf-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSNT Usage.)</span></span>


<span data-ttu-id="2eaaf-118">Il diagramma seguente illustra la scala SIP per il fork 1, spiega il flusso delle chiamate e il motivo previsto nel messaggio di annullamento.</span><span class="sxs-lookup"><span data-stu-id="2eaaf-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagramma che Mostra gli endpoint di Team biforcati](media/direct-routing-call-notification-2.png)
