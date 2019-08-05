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
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194817"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="48245-103">Tabella finestre di dialogo in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="48245-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="48245-104">La tabella Dialogs è una tabella di supporto in cui sono archiviate le informazioni su DialogIDs per le sessioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="48245-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="48245-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="48245-105">**Column**</span></span>|<span data-ttu-id="48245-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="48245-106">**Data Type**</span></span>|<span data-ttu-id="48245-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="48245-107">**Key/Index**</span></span>|<span data-ttu-id="48245-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="48245-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48245-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="48245-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="48245-110">DateTime</span><span class="sxs-lookup"><span data-stu-id="48245-110">datetime</span></span>  <br/> |<span data-ttu-id="48245-111">Principale</span><span class="sxs-lookup"><span data-stu-id="48245-111">Primary</span></span>  <br/> |<span data-ttu-id="48245-112">Ora della richiesta di sessione; usato in combinazione con SessionIDSeq per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="48245-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="48245-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="48245-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="48245-114">int</span><span class="sxs-lookup"><span data-stu-id="48245-114">int</span></span>  <br/> |<span data-ttu-id="48245-115">Principale</span><span class="sxs-lookup"><span data-stu-id="48245-115">Primary</span></span>  <br/> |<span data-ttu-id="48245-116">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="48245-116">ID number to identify the session.</span></span> <span data-ttu-id="48245-117">Usato in combinazione con SessionIDTime per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="48245-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="48245-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="48245-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="48245-119">int</span><span class="sxs-lookup"><span data-stu-id="48245-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="48245-120">Checksum della ExternalID.</span><span class="sxs-lookup"><span data-stu-id="48245-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="48245-121">Questo campo viene usato per aumentare la velocità delle ricerche di database.</span><span class="sxs-lookup"><span data-stu-id="48245-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="48245-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="48245-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="48245-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="48245-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="48245-124">ID finestra di dialogo SIP, archiviato come binario.</span><span class="sxs-lookup"><span data-stu-id="48245-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="48245-125">Il formato del file binario è:</span><span class="sxs-lookup"><span data-stu-id="48245-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="48245-126">finestra di dialogo; da-tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="48245-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="48245-127">Questi dati possono essere convertiti in formato testo usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="48245-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

