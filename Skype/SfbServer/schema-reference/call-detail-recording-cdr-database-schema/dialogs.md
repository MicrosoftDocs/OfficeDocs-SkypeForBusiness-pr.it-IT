---
title: Tabella finestre di dialogo in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815274"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2e11a-103">Tabella finestre di dialogo in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2e11a-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2e11a-104">La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="2e11a-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="2e11a-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2e11a-105">**Column**</span></span>|<span data-ttu-id="2e11a-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2e11a-106">**Data Type**</span></span>|<span data-ttu-id="2e11a-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2e11a-107">**Key/Index**</span></span>|<span data-ttu-id="2e11a-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2e11a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e11a-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2e11a-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2e11a-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="2e11a-110">datetime</span></span>  <br/> |<span data-ttu-id="2e11a-111">Principale</span><span class="sxs-lookup"><span data-stu-id="2e11a-111">Primary</span></span>  <br/> |<span data-ttu-id="2e11a-112">Ora della richiesta di sessione; usato in combinazione con SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="2e11a-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2e11a-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2e11a-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2e11a-114">int</span><span class="sxs-lookup"><span data-stu-id="2e11a-114">int</span></span>  <br/> |<span data-ttu-id="2e11a-115">Principale</span><span class="sxs-lookup"><span data-stu-id="2e11a-115">Primary</span></span>  <br/> |<span data-ttu-id="2e11a-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="2e11a-116">ID number to identify the session.</span></span> <span data-ttu-id="2e11a-117">Usato in combinazione con SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="2e11a-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2e11a-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="2e11a-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="2e11a-119">int</span><span class="sxs-lookup"><span data-stu-id="2e11a-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="2e11a-120">Checksum della ExternalID.</span><span class="sxs-lookup"><span data-stu-id="2e11a-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="2e11a-121">Questo campo viene usato per aumentare la velocità delle ricerche di database.</span><span class="sxs-lookup"><span data-stu-id="2e11a-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="2e11a-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="2e11a-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="2e11a-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="2e11a-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="2e11a-124">ID finestra di dialogo SIP, archiviato come binario.</span><span class="sxs-lookup"><span data-stu-id="2e11a-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="2e11a-125">Il formato del file binario è:</span><span class="sxs-lookup"><span data-stu-id="2e11a-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="2e11a-126">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="2e11a-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="2e11a-127">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2e11a-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

