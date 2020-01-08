---
title: "Lync Server 2013: Distribuzione dell'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94f4c52eb3adda31f32de410f139154788fa37e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="3e4a0-102">Distribuzione dell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e4a0-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e4a0-103">_**Argomento Ultima modifica:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="3e4a0-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="3e4a0-104">L'abilitazione dell'archivio contatti unificato in Lync Server 2013 non richiede le impostazioni della topologia.</span><span class="sxs-lookup"><span data-stu-id="3e4a0-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="3e4a0-105">L'abilitazione dell'archivio contatti unificato per gli utenti richiede le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="3e4a0-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="3e4a0-106">Il criterio archivio contatti unificato è abilitato (il valore predefinito è abilitato).</span><span class="sxs-lookup"><span data-stu-id="3e4a0-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="3e4a0-107">Gli utenti accedono a Lync 2013 almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="3e4a0-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="3e4a0-108">Dopo la migrazione dei contatti di un utente, che avviene automaticamente quando un utente accede con Lync 2013, l'utente può accedere e gestire i contatti di Lync da Lync 2013, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3e4a0-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="3e4a0-109">Non è necessario che l'utente abbia effettuato l'accesso a Lync per gestire i propri contatti da Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="3e4a0-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e4a0-110">Se un utente accede da Lync 2010 dopo la migrazione, i contatti e i gruppi sono disponibili e aggiornati, ma l'utente non può gestire (ovvero aggiungere, eliminare, trasferire, contrassegnare, UNTAG o modificare) i contatti.</span><span class="sxs-lookup"><span data-stu-id="3e4a0-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e4a0-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3e4a0-111">In This Section</span></span>

  - [<span data-ttu-id="3e4a0-112">Abilitare gli utenti per l'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e4a0-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="3e4a0-113">Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e4a0-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="3e4a0-114">Eseguire il rollback degli utenti migrati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e4a0-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

