---
title: Tabella ClientVersions in Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813316"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="90178-104">Tabella ClientVersions in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="90178-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="90178-p102">La tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei diversi tipi di client e delle versioni che hanno partecipato alle sessioni registrate nel database. Ogni record della tabella rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="90178-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="90178-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="90178-107">**Column**</span></span>|<span data-ttu-id="90178-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="90178-108">**Data Type**</span></span>|<span data-ttu-id="90178-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="90178-109">**Key/Index**</span></span>|<span data-ttu-id="90178-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="90178-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90178-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="90178-111">**VersionId**</span></span> <br/> |<span data-ttu-id="90178-112">**int**</span><span class="sxs-lookup"><span data-stu-id="90178-112">**int**</span></span> <br/> |<span data-ttu-id="90178-113">Principale</span><span class="sxs-lookup"><span data-stu-id="90178-113">Primary</span></span>  <br/> |<span data-ttu-id="90178-114">Numero univoco che identifica il tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="90178-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="90178-115">**Versione**</span><span class="sxs-lookup"><span data-stu-id="90178-115">**Version**</span></span> <br/> |<span data-ttu-id="90178-116">**nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="90178-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="90178-117">Nome della versione.</span><span class="sxs-lookup"><span data-stu-id="90178-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="90178-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="90178-118">**ClientType**</span></span> <br/> |<span data-ttu-id="90178-119">int</span><span class="sxs-lookup"><span data-stu-id="90178-119">int</span></span>  <br/> ||<span data-ttu-id="90178-120">Specifica il tipo di client usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="90178-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="90178-121">Per ulteriori informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="90178-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="90178-122">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90178-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

