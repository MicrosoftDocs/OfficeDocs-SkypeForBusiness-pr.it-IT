---
title: Ulteriori informazioni sulla riga ID chiamante e la chiamata a nome entità
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Informazioni sui motivi per cui si desidera aggiungere un utente autorizzato può apportare modifiche all'account quando si utilizza la procedura guidata nuovo ordine di porta numero locale.
ms.openlocfilehash: deb4320617d1840f2a237776ed0c4dc584fc2964
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="b85a1-103">Ulteriori informazioni sulla riga ID chiamante e la chiamata a nome entità</span><span class="sxs-lookup"><span data-stu-id="b85a1-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="b85a1-104">CallerID, come in genere denominato, effettivamente costituito da due parti personali per l'utente delle informazioni:</span><span class="sxs-lookup"><span data-stu-id="b85a1-104">CallerID, as it typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="b85a1-105">Un numero di telefono (in genere definito come CLID o chiamate linea ID)</span><span class="sxs-lookup"><span data-stu-id="b85a1-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="b85a1-106">Nome di terze parti (denominato in genere CNAM) che può corrispondere al massimo 15 caratteri la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b85a1-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="b85a1-107">Quando viene effettuata una chiamata, il CLID (numero di telefono) viene instradato al gestore di destinazione (anche noto come vettore terminazione).</span><span class="sxs-lookup"><span data-stu-id="b85a1-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as terminating carrier).</span></span> <span data-ttu-id="b85a1-108">Info CNAM per la chiamata può o non può essere inoltrata con la chiamata dipende dalle paese è implementato come CNAM (se affatto).</span><span class="sxs-lookup"><span data-stu-id="b85a1-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="b85a1-109">L'affidabilità del recapito CNAM con la chiamata varia a seconda del paese e gestori telefonici che gestiscono le chiamate come un intermediario e/o un operatore di telefonia terminazione.</span><span class="sxs-lookup"><span data-stu-id="b85a1-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="b85a1-110">Trasmissione CLID & CNAM è responsabilità del gestore telefonico di terminazione nella misura in cui il gestore telefonico terminazione deve supportare le funzionalità CLID & CNAM e su come fornire record aggiornati di entrambi i valori.</span><span class="sxs-lookup"><span data-stu-id="b85a1-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records of both values.</span></span> <span data-ttu-id="b85a1-111">Microsoft fornisce in modo affidabile i valori CLID quando le chiamate di origine, ma tali valori potrebbero non essere conservati dopo il passaggio attraverso un intermediario gestore o gestore terminazione.</span><span class="sxs-lookup"><span data-stu-id="b85a1-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="b85a1-112">Purtroppo, nel caso in cui il valore CLID viene modificato, omesso o per portante intermedia o terminazione troncato, Microsoft non ha poche attività su il ricorso di risolvere questi problemi della rete telefonica pubblica.</span><span class="sxs-lookup"><span data-stu-id="b85a1-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="b85a1-113">Incongruenze nella CNAM possono essere causate da ritardi nel gestori telefonici intermediate o terminazione aggiornamento info CNAM nei database rilevanti, ad esempio Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="b85a1-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases such as the United States.</span></span> <span data-ttu-id="b85a1-114">Nei paesi in cui è presente alcun database rilevanti per CNAM, consigliate singolo vettore anche possono causare problemi con le informazioni CNAM in arrivo quando viene spostato con la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b85a1-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="b85a1-115">Microsoft attualmente non supporta origine CNAM informazioni nei paesi eccezione degli Stati Uniti."</span><span class="sxs-lookup"><span data-stu-id="b85a1-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="b85a1-116">See also</span><span class="sxs-lookup"><span data-stu-id="b85a1-116">Related topics</span></span>


