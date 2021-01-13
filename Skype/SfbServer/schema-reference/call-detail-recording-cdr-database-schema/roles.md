---
title: Tabella Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: La tabella Roles è una tabella statica in cui viene archiviato l'elenco di possibili ruoli per conferenze, ad esempio partecipante e relatore.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809976"
---
# <a name="roles-table"></a><span data-ttu-id="fb0f1-103">Tabella Roles</span><span class="sxs-lookup"><span data-stu-id="fb0f1-103">Roles table</span></span>
 
<span data-ttu-id="fb0f1-104">La tabella Roles è una tabella statica in cui viene archiviato l'elenco di possibili ruoli per conferenze, ad esempio partecipante e relatore.</span><span class="sxs-lookup"><span data-stu-id="fb0f1-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="fb0f1-105">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="fb0f1-105">**Column**</span></span>|<span data-ttu-id="fb0f1-106">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="fb0f1-106">**Data Type**</span></span>|<span data-ttu-id="fb0f1-107">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="fb0f1-107">**Key/Index**</span></span>|<span data-ttu-id="fb0f1-108">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="fb0f1-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fb0f1-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="fb0f1-109">**RoleId**</span></span> <br/> |<span data-ttu-id="fb0f1-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="fb0f1-110">tinyint</span></span>  <br/> |<span data-ttu-id="fb0f1-111">Principale</span><span class="sxs-lookup"><span data-stu-id="fb0f1-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="fb0f1-112">**Ruolo**</span><span class="sxs-lookup"><span data-stu-id="fb0f1-112">**Role**</span></span> <br/> |<span data-ttu-id="fb0f1-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fb0f1-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fb0f1-114">Valori consentiti:</span><span class="sxs-lookup"><span data-stu-id="fb0f1-114">Allowed values:</span></span> <br/>  <span data-ttu-id="fb0f1-115">0 - Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="fb0f1-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="fb0f1-116">1 - Relatore</span><span class="sxs-lookup"><span data-stu-id="fb0f1-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="fb0f1-117">2 - Partecipante</span><span class="sxs-lookup"><span data-stu-id="fb0f1-117">2 - Attendee</span></span> <br/> |
   

