---
title: Procedure consigliate per il server Chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fceea7401a6d5442738a0cc64e9a2bafbfd83827
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500143"
---
# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="ce8f5-102">Procedure consigliate per il server Chat persistente</span><span class="sxs-lookup"><span data-stu-id="ce8f5-102">Persistent Chat Server best practices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce8f5-103">_**Ultimo argomento modificato:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ce8f5-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ce8f5-104">Quando si creano le categorie e le chat room permanenti e si progetta l'ambito e l'appartenenza, i suggerimenti seguenti possono essere utili per la pianificazione:</span><span class="sxs-lookup"><span data-stu-id="ce8f5-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="ce8f5-105">Se l'azienda non richiede un ethical wall, non restringere l'ambito nell'albero delle categorie.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="ce8f5-106">Inserire tutti gli utenti nell'ambito di una categoria e creare tutte le chat room della categoria.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="ce8f5-107">Successivamente, utilizzare solo gli elenchi di appartenenze per concedere o limitare l'accesso a ogni chat room.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="ce8f5-108">Nella maggior parte dei casi, è necessario consentire agli utenti di creare nuove chat room in modo che le discussioni sui nuovi argomenti possano essere avviate in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="ce8f5-109">A tale scopo, è possibile fare in modo che l'elenco dei **creatori** corrisponda a quello dell'elenco **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="ce8f5-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="ce8f5-110">Tuttavia, se si desidera consentire solo a un team di supporto centrale o a utenti designati di creare sale, rendere l'elenco dei **creatori** come il sottoinsieme appropriato.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="ce8f5-111">Fornire a ogni chat room un nome completo e un riepilogo della descrizione che descrive la posizione adatta all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="ce8f5-112">Poiché gli utenti non possono visualizzare il nome della categoria quando usano la chat room, non è possibile fare affidamento sul nome della categoria per consentire agli utenti di determinare il forum di discussione previsto per la chat room.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="ce8f5-113">Se si dispone di determinate convenzioni di denominazione o altri controlli di accesso o convalide da implementare, potrebbe essere necessario disporre di un flusso di lavoro personalizzato per la creazione di una sala.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="ce8f5-114">La configurazione di chat persistente consente di personalizzare **RoomManagementUrl** in un elemento host.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="ce8f5-115">Ad esempio, quando gli utenti fanno clic su **Crea una chat room** nel client Lync, possono essere reindirizzati alla soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="ce8f5-116">Creare una serie di componenti aggiuntivi utili per migliorare l'esperienza nelle chat room introducendo altri dati business nelle chat room.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="ce8f5-117">Gli amministratori devono registrare i componenti aggiuntivi che si desidera consentire nel sistema.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="ce8f5-118">I responsabili e i creatori della chat room possono scegliere tra l'elenco dei componenti aggiuntivi consentiti per quelli più rilevanti per le rispettive sale.</span><span class="sxs-lookup"><span data-stu-id="ce8f5-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="ce8f5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce8f5-119">See Also</span></span>


[<span data-ttu-id="ce8f5-120">Gestione di categorie, chat room e componenti aggiuntivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce8f5-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

