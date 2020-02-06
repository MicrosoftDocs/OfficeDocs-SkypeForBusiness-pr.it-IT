---
title: Tabella ClientVersions in Skype for Business Server 2015
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La Tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei vari tipi di client e versioni che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta una versione client.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815404"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0d770-104">Tabella ClientVersions in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d770-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0d770-105">La Tabella ClientVersions è una tabella di supporto in cui è archiviato un elenco dei vari tipi di client e versioni che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="0d770-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0d770-106">Ogni record nella tabella rappresenta una versione client.</span><span class="sxs-lookup"><span data-stu-id="0d770-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="0d770-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0d770-107">**Column**</span></span>|<span data-ttu-id="0d770-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="0d770-108">**Data Type**</span></span>|<span data-ttu-id="0d770-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="0d770-109">**Key/Index**</span></span>|<span data-ttu-id="0d770-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="0d770-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0d770-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="0d770-111">**VersionId**</span></span> <br/> |<span data-ttu-id="0d770-112">**int**</span><span class="sxs-lookup"><span data-stu-id="0d770-112">**int**</span></span> <br/> |<span data-ttu-id="0d770-113">Principale</span><span class="sxs-lookup"><span data-stu-id="0d770-113">Primary</span></span>  <br/> |<span data-ttu-id="0d770-114">Numero univoco che identifica questo tipo di client e la versione.</span><span class="sxs-lookup"><span data-stu-id="0d770-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="0d770-115">**Versione**</span><span class="sxs-lookup"><span data-stu-id="0d770-115">**Version**</span></span> <br/> |<span data-ttu-id="0d770-116">**nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="0d770-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="0d770-117">Nome versione.</span><span class="sxs-lookup"><span data-stu-id="0d770-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="0d770-118">**TipoClient**</span><span class="sxs-lookup"><span data-stu-id="0d770-118">**ClientType**</span></span> <br/> |<span data-ttu-id="0d770-119">int</span><span class="sxs-lookup"><span data-stu-id="0d770-119">int</span></span>  <br/> ||<span data-ttu-id="0d770-120">Specifica il tipo di client usato nella sessione.</span><span class="sxs-lookup"><span data-stu-id="0d770-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="0d770-121">Per altre informazioni, vedere la [Tabella UserAgentDef](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="0d770-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="0d770-122">Questo campo è stato introdotto in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d770-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

