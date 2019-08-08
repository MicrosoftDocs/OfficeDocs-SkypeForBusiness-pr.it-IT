---
title: Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Quando si passa da un account utente a un server Skype for Business Server 2019, vengono spostate le informazioni seguenti con l'account utente seguente:"
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238512"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="dc045-103">Eseguire la migrazione di riunioni e contenuto delle riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="dc045-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="dc045-104">Quando un account utente viene spostato in un server di Skype for Business Server 2019, le informazioni seguenti vengono spostate con l'account utente seguente:</span><span class="sxs-lookup"><span data-stu-id="dc045-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="dc045-105">**Riunioni già programmate dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="dc045-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="dc045-106">Questo include lo spostamento delle directory di conferenza e dei dati di conferenza.</span><span class="sxs-lookup"><span data-stu-id="dc045-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="dc045-107">**Pin (Personal Identification Number) dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="dc045-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="dc045-108">Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="dc045-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="dc045-109">Le informazioni dell'account utente seguenti non vengono spostati nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="dc045-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="dc045-110">**Contenuto della riunione**.</span><span class="sxs-lookup"><span data-stu-id="dc045-110">**Meeting content**.</span></span> <span data-ttu-id="dc045-111">Per trasferire il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati del sondaggio, usa il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="dc045-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

