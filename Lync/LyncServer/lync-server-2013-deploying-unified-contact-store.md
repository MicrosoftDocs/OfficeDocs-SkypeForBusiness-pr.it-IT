---
title: "Lync Server 2013: distribuzione dell'archivio contatti unificato"
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
ms.openlocfilehash: a94d19026d2df00caf8079914d8b93bd70a87f6d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522853"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="ac8d8-102">Distribuzione dell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac8d8-102">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac8d8-103">_**Ultimo argomento modificato:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="ac8d8-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="ac8d8-104">L'abilitazione dell'archivio contatti unificato in Lync Server 2013 non richiede impostazioni di topologia.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="ac8d8-105">I requisiti per l'abilitazione dell'archivio contatti unificato per gli utenti sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac8d8-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="ac8d8-106">I criteri dell'archivio contatto unificati sono abilitati (abilitati per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="ac8d8-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="ac8d8-107">Gli utenti accedono con Lync 2013 almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="ac8d8-108">Dopo la migrazione dei contatti di un utente, che si verifica automaticamente quando un utente esegue l'accesso con Lync 2013, l'utente può accedere e gestire i propri contatti di Lync da Lync 2013, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="ac8d8-109">Non è necessario che l'utente sia connesso a Lync per gestire i propri contatti da Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ac8d8-110">Se un utente esegue l'accesso da Lync 2010 dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non è in grado di gestire (ovvero, aggiungere, eliminare, spostare, contrassegnare, UNTAG o modificare) tali contatti.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac8d8-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="ac8d8-111">In This Section</span></span>

  - [<span data-ttu-id="ac8d8-112">Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac8d8-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="ac8d8-113">Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac8d8-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="ac8d8-114">Eseguire il rollback degli utenti migrati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac8d8-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

