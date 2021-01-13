---
title: Tabella SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809926"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="295c3-104">Tabella SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="295c3-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="295c3-p102">Nella tabella SIPResponseMetaDataTable è contenuto un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice. Questi codici vengono generati in risposta a eventi che influiscono sui dispositivi SIP e sulle sessioni di comunicazioni SIP. Il codice di risposta 403 ad esempio viene generato quando un dispositivo SIP invia una richiesta, che però non viene soddisfatta dal server.</span><span class="sxs-lookup"><span data-stu-id="295c3-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="295c3-107">Questa tabella è stata introdotta in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="295c3-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="295c3-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="295c3-108">**Column**</span></span>|<span data-ttu-id="295c3-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="295c3-109">**Data Type**</span></span>|<span data-ttu-id="295c3-110">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="295c3-110">**Key/Index**</span></span>|<span data-ttu-id="295c3-111">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="295c3-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="295c3-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="295c3-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="295c3-113">int</span><span class="sxs-lookup"><span data-stu-id="295c3-113">int</span></span>  <br/> |<span data-ttu-id="295c3-114">Principale</span><span class="sxs-lookup"><span data-stu-id="295c3-114">Primary</span></span>  <br/> |<span data-ttu-id="295c3-115">Valore numerico che rappresenta il codice di risposta SIP.</span><span class="sxs-lookup"><span data-stu-id="295c3-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="295c3-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="295c3-116">**Class**</span></span> <br/> |<span data-ttu-id="295c3-117">int</span><span class="sxs-lookup"><span data-stu-id="295c3-117">int</span></span>  <br/> || <span data-ttu-id="295c3-p103">Classifica generale del codice di risposta. Sono incluse le classifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="295c3-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="295c3-120">1-risposte informative</span><span class="sxs-lookup"><span data-stu-id="295c3-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="295c3-121">2-risposte con esito positivo</span><span class="sxs-lookup"><span data-stu-id="295c3-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="295c3-122">3-risposte di Reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="295c3-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="295c3-123">4-risposte di errore client</span><span class="sxs-lookup"><span data-stu-id="295c3-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="295c3-124">5-risposte di errore del server</span><span class="sxs-lookup"><span data-stu-id="295c3-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="295c3-125">6-risposta di errore globale</span><span class="sxs-lookup"><span data-stu-id="295c3-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="295c3-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="295c3-126">**Description**</span></span> <br/> |<span data-ttu-id="295c3-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="295c3-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="295c3-p104">Descrizione del codice di risposta SIP. Il codice di risposta 181 ad esempio è associato alla descrizione seguente:</span><span class="sxs-lookup"><span data-stu-id="295c3-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="295c3-130">Call Is Being Forwarded</span><span class="sxs-lookup"><span data-stu-id="295c3-130">Call Is Being Forwarded</span></span>  <br/> |
   

