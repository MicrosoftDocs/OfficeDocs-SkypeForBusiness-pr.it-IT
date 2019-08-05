---
title: Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Quando si passa da un account utente a un server Skype for Business Server 2019, vengono spostate le informazioni seguenti con l'account utente seguente:"
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191147"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="e0bd2-103">Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="e0bd2-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="e0bd2-104">Quando un account utente viene spostato in un server di Skype for Business Server 2019, le informazioni seguenti vengono spostate con l'account utente seguente:</span><span class="sxs-lookup"><span data-stu-id="e0bd2-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="e0bd2-105">**Riunioni già programmate dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="e0bd2-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="e0bd2-106">Questo include lo spostamento delle directory di conferenza e dei dati di conferenza.</span><span class="sxs-lookup"><span data-stu-id="e0bd2-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="e0bd2-107">**Pin (Personal Identification Number) dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="e0bd2-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="e0bd2-108">Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="e0bd2-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="e0bd2-109">Le informazioni dell'account utente seguenti non vengono spostati nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="e0bd2-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="e0bd2-110">**Contenuto della riunione**.</span><span class="sxs-lookup"><span data-stu-id="e0bd2-110">**Meeting content**.</span></span> <span data-ttu-id="e0bd2-111">Per trasferire il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati del sondaggio, usa il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e0bd2-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

