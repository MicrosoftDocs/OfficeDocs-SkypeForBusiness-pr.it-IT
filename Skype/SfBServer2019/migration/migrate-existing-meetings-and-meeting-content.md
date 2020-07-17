---
title: Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "Quando un account utente viene spostato da un server Skype for Business Server 2019, le informazioni seguenti vengono spostate con l'account utente seguente:"
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752688"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="08126-103">Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="08126-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="08126-104">Quando un account utente viene spostato in un server Skype for Business Server 2019, le informazioni seguenti vengono spostate con l'account utente seguente:</span><span class="sxs-lookup"><span data-stu-id="08126-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="08126-105">**Le riunioni già pianificate dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="08126-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="08126-106">Vengono spostate anche le directory e i dati delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="08126-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="08126-107">**Codice PIN (Personal Identification Number) dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="08126-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="08126-108">Il PIN corrente dell'utente continua a funzionare fino alla scadenza o l'utente richiede un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="08126-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="08126-109">Le seguenti informazioni sull'account utente non vengono spostate nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="08126-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="08126-110">**Contenuto delle riunioni**.</span><span class="sxs-lookup"><span data-stu-id="08126-110">**Meeting content**.</span></span> <span data-ttu-id="08126-111">Per spostare il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati di polling, utilizzare il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="08126-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

