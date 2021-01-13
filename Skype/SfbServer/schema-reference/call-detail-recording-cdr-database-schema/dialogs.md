---
title: Tabella Dialogs in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni relative a DialogIDs per le sessioni peer-to-peer.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816046"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2f6b3-103">Tabella Dialogs in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f6b3-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2f6b3-104">La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni relative a DialogIDs per le sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="2f6b3-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-105">**Column**</span></span>|<span data-ttu-id="2f6b3-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-106">**Data Type**</span></span>|<span data-ttu-id="2f6b3-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-107">**Key/Index**</span></span>|<span data-ttu-id="2f6b3-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f6b3-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2f6b3-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2f6b3-110">datetime</span></span>  <br/> |<span data-ttu-id="2f6b3-111">Principale</span><span class="sxs-lookup"><span data-stu-id="2f6b3-111">Primary</span></span>  <br/> |<span data-ttu-id="2f6b3-112">Ora della richiesta di sessione; utilizzato insieme a SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2f6b3-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2f6b3-114">int</span><span class="sxs-lookup"><span data-stu-id="2f6b3-114">int</span></span>  <br/> |<span data-ttu-id="2f6b3-115">Principale</span><span class="sxs-lookup"><span data-stu-id="2f6b3-115">Primary</span></span>  <br/> |<span data-ttu-id="2f6b3-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-116">ID number to identify the session.</span></span> <span data-ttu-id="2f6b3-117">Utilizzato insieme a SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2f6b3-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="2f6b3-119">int</span><span class="sxs-lookup"><span data-stu-id="2f6b3-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="2f6b3-120">Checksum del ExternalID.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="2f6b3-121">Questo campo viene utilizzato per aumentare la velocità delle ricerche di database.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="2f6b3-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="2f6b3-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="2f6b3-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="2f6b3-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="2f6b3-124">ID finestra di dialogo SIP, memorizzato come binario.</span><span class="sxs-lookup"><span data-stu-id="2f6b3-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="2f6b3-125">Il formato del file binario è:</span><span class="sxs-lookup"><span data-stu-id="2f6b3-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="2f6b3-126">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="2f6b3-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="2f6b3-127">Questi dati possono essere convertiti in formato testo utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2f6b3-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

