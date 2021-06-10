---
title: Instradamento diretto di Sistema telefonico
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
f1.keywords:
- NOCSH
description: Notifica di chiamata instradamento diretto
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341802"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="1089a-103">Gestire le notifiche di chiamata</span><span class="sxs-lookup"><span data-stu-id="1089a-103">Manage call notifications</span></span>

<span data-ttu-id="1089a-104">Questo articolo descrive come gestire le notifiche di chiamata per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1089a-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="1089a-105">È possibile configurare gli endpoint di chiamata sia per Teams che per un pbx (Private Branch Exchange) o SBC (Session Border Controller) di terze parti.</span><span class="sxs-lookup"><span data-stu-id="1089a-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="1089a-106">Questa opzione è utile, ad esempio, se si vuole inviare una chiamata contemporaneamente ai telefoni cellulari e da tavolo di un utente.</span><span class="sxs-lookup"><span data-stu-id="1089a-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="1089a-107">Nel diagramma seguente l'utente Irena ha due endpoint:</span><span class="sxs-lookup"><span data-stu-id="1089a-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="1089a-108">Un endpoint Teams</span><span class="sxs-lookup"><span data-stu-id="1089a-108">A Teams endpoint</span></span>
- <span data-ttu-id="1089a-109">Un telefono SIP connesso a un SBC di terze parti</span><span class="sxs-lookup"><span data-stu-id="1089a-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="1089a-110">Quando arriva una chiamata, la SBC la forierà tra Sistema telefonico Direct Routing e SBC di terze parti.</span><span class="sxs-lookup"><span data-stu-id="1089a-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![Diagramma che mostra gli endpoint Teams forked](media/direct-routing-call-notification-1.png)

<span data-ttu-id="1089a-112">Se la chiamata viene accettata su Fork 2 (da parte di SBC di terze parti), Teams genererà una notifica "Chiamata persa".</span><span class="sxs-lookup"><span data-stu-id="1089a-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="1089a-113">È possibile impedire la notifica "Chiamata persa" configurando SBC in modo che invii un messaggio Annulla al fork 1 come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1089a-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="1089a-114">MOTIVO: SIP; causa=200;testo"Chiamata completata altrove"</span><span class="sxs-lookup"><span data-stu-id="1089a-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="1089a-115">Si noti che la chiamata non verrà registrata nei record dei dettagli della chiamata di Telefono Microsoft sistema come chiamata riuscita.</span><span class="sxs-lookup"><span data-stu-id="1089a-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="1089a-116">La chiamata verrà registrata come "Tentativo" con codice SIP finale "487", sottocodice finale Microsoft "540200" e frase del codice SIP finale "Chiamata completata altrove".</span><span class="sxs-lookup"><span data-stu-id="1089a-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="1089a-117">Per visualizzare i record dei dettagli delle chiamate, passare al portale di amministrazione di Teams, Analisi e report, Report utilizzo e selezionare Utilizzo PSTN.</span><span class="sxs-lookup"><span data-stu-id="1089a-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="1089a-118">Il diagramma seguente illustra la scala SIP per fork 1, spiega il flusso delle chiamate e il motivo previsto nel messaggio Annulla.</span><span class="sxs-lookup"><span data-stu-id="1089a-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![Diagramma che mostra gli endpoint Teams forked](media/direct-routing-call-notification-2.png)
