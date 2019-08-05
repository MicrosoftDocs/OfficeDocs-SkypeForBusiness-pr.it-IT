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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194748"
---
# <a name="roles-table"></a><span data-ttu-id="61081-103">Tabella Roles</span><span class="sxs-lookup"><span data-stu-id="61081-103">Roles table</span></span>
 
<span data-ttu-id="61081-104">La tabella Roles è una tabella statica in cui è archiviato l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.</span><span class="sxs-lookup"><span data-stu-id="61081-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="61081-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="61081-105">**Column**</span></span>|<span data-ttu-id="61081-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="61081-106">**Data Type**</span></span>|<span data-ttu-id="61081-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="61081-107">**Key/Index**</span></span>|<span data-ttu-id="61081-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="61081-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61081-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="61081-109">**RoleId**</span></span> <br/> |<span data-ttu-id="61081-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="61081-110">tinyint</span></span>  <br/> |<span data-ttu-id="61081-111">Principale</span><span class="sxs-lookup"><span data-stu-id="61081-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="61081-112">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="61081-112">**Role**</span></span> <br/> |<span data-ttu-id="61081-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="61081-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="61081-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="61081-114">Allowed values:</span></span> <br/>  <span data-ttu-id="61081-115">0-sconosciuto</span><span class="sxs-lookup"><span data-stu-id="61081-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="61081-116">1-relatore</span><span class="sxs-lookup"><span data-stu-id="61081-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="61081-117">2-partecipante</span><span class="sxs-lookup"><span data-stu-id="61081-117">2 - Attendee</span></span> <br/> |
   

