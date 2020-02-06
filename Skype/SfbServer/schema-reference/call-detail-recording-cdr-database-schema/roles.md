---
title: Tabella Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814934"
---
# <a name="roles-table"></a><span data-ttu-id="84f56-103">Tabella Roles</span><span class="sxs-lookup"><span data-stu-id="84f56-103">Roles table</span></span>
 
<span data-ttu-id="84f56-104">La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.</span><span class="sxs-lookup"><span data-stu-id="84f56-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="84f56-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="84f56-105">**Column**</span></span>|<span data-ttu-id="84f56-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="84f56-106">**Data Type**</span></span>|<span data-ttu-id="84f56-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="84f56-107">**Key/Index**</span></span>|<span data-ttu-id="84f56-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="84f56-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84f56-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="84f56-109">**RoleId**</span></span> <br/> |<span data-ttu-id="84f56-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="84f56-110">tinyint</span></span>  <br/> |<span data-ttu-id="84f56-111">Principale</span><span class="sxs-lookup"><span data-stu-id="84f56-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="84f56-112">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="84f56-112">**Role**</span></span> <br/> |<span data-ttu-id="84f56-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="84f56-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="84f56-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="84f56-114">Allowed values:</span></span> <br/>  <span data-ttu-id="84f56-115">0-sconosciuto</span><span class="sxs-lookup"><span data-stu-id="84f56-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="84f56-116">1-relatore</span><span class="sxs-lookup"><span data-stu-id="84f56-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="84f56-117">2-partecipante</span><span class="sxs-lookup"><span data-stu-id="84f56-117">2 - Attendee</span></span> <br/> |
   

