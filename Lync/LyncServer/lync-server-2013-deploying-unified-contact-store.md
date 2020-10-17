---
title: "Lync Server 2013: distribuzione dell'archivio contatti unificato"
description: "Lync Server 2013: distribuzione dell'archivio contatti unificato."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 056792d2e4ea66699b276d0d571e83c8a0256483
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557752"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="6ec93-103">Distribuzione dell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ec93-103">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ec93-104">_**Ultimo argomento modificato:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="6ec93-104">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="6ec93-105">L'abilitazione dell'archivio contatti unificato in Lync Server 2013 non richiede impostazioni di topologia.</span><span class="sxs-lookup"><span data-stu-id="6ec93-105">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="6ec93-106">I requisiti per l'abilitazione dell'archivio contatti unificato per gli utenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ec93-106">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="6ec93-107">I criteri dell'archivio contatto unificati sono abilitati (abilitati per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="6ec93-107">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="6ec93-108">Gli utenti accedono con Lync 2013 almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="6ec93-108">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="6ec93-109">Dopo la migrazione dei contatti di un utente, che si verifica automaticamente quando un utente esegue l'accesso con Lync 2013, l'utente può accedere e gestire i propri contatti di Lync da Lync 2013, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="6ec93-109">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="6ec93-110">Non è necessario che l'utente sia connesso a Lync per gestire i propri contatti da Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="6ec93-110">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ec93-111">Se un utente esegue l'accesso da Lync 2010 dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non è in grado di gestire (ovvero, aggiungere, eliminare, spostare, contrassegnare, UNTAG o modificare) tali contatti.</span><span class="sxs-lookup"><span data-stu-id="6ec93-111">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6ec93-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="6ec93-112">In This Section</span></span>

  - [<span data-ttu-id="6ec93-113">Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ec93-113">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="6ec93-114">Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ec93-114">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="6ec93-115">Eseguire il rollback degli utenti migrati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ec93-115">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

