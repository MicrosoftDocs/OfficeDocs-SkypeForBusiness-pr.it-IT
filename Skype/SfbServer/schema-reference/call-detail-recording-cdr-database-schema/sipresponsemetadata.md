---
title: Tabella SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable contiene un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici. Questi codici vengono generati in risposta agli eventi che interessano i dispositivi SIP e le sessioni di comunicazione SIP; ad esempio, il codice di risposta 403 viene generato quando un dispositivo SIP effettua una richiesta, ma il server rifiuta di onorare la richiesta.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194740"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="9738b-104">Tabella SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="9738b-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="9738b-105">SIPResponseMetaDataTable contiene un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici.</span><span class="sxs-lookup"><span data-stu-id="9738b-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="9738b-106">Questi codici vengono generati in risposta agli eventi che interessano i dispositivi SIP e le sessioni di comunicazione SIP; ad esempio, il codice di risposta 403 viene generato quando un dispositivo SIP effettua una richiesta, ma il server rifiuta di onorare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="9738b-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="9738b-107">Questa tabella è stata introdotta in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9738b-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="9738b-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="9738b-108">**Column**</span></span>|<span data-ttu-id="9738b-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="9738b-109">**Data Type**</span></span>|<span data-ttu-id="9738b-110">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="9738b-110">**Key/Index**</span></span>|<span data-ttu-id="9738b-111">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="9738b-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9738b-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="9738b-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="9738b-113">int</span><span class="sxs-lookup"><span data-stu-id="9738b-113">int</span></span>  <br/> |<span data-ttu-id="9738b-114">Principale</span><span class="sxs-lookup"><span data-stu-id="9738b-114">Primary</span></span>  <br/> |<span data-ttu-id="9738b-115">Valore numerico che rappresenta il codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="9738b-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="9738b-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="9738b-116">**Class**</span></span> <br/> |<span data-ttu-id="9738b-117">int</span><span class="sxs-lookup"><span data-stu-id="9738b-117">int</span></span>  <br/> || <span data-ttu-id="9738b-118">Classificazione generale per il codice di risposta.</span><span class="sxs-lookup"><span data-stu-id="9738b-118">General classification for the response code.</span></span> <span data-ttu-id="9738b-119">Le classificazioni includono:</span><span class="sxs-lookup"><span data-stu-id="9738b-119">Classifications include:</span></span> <br/>  <span data-ttu-id="9738b-120">1-risposte informative</span><span class="sxs-lookup"><span data-stu-id="9738b-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="9738b-121">2-risposte di successo</span><span class="sxs-lookup"><span data-stu-id="9738b-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="9738b-122">3-risposte di Reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="9738b-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="9738b-123">4-risposte di errore client</span><span class="sxs-lookup"><span data-stu-id="9738b-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="9738b-124">5--risposte di errore del server</span><span class="sxs-lookup"><span data-stu-id="9738b-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="9738b-125">6-risposta di errore globale</span><span class="sxs-lookup"><span data-stu-id="9738b-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="9738b-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="9738b-126">**Description**</span></span> <br/> |<span data-ttu-id="9738b-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9738b-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="9738b-128">Descrizione del codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="9738b-128">Description of the SIP response code.</span></span> <span data-ttu-id="9738b-129">Ad esempio, il codice di risposta 181 ha la seguente descrizione:</span><span class="sxs-lookup"><span data-stu-id="9738b-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="9738b-130">Chiamata inoltrata</span><span class="sxs-lookup"><span data-stu-id="9738b-130">Call Is Being Forwarded</span></span>  <br/> |
   

