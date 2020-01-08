---
title: 'Lync Server 2013: criteri di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60b521c69b821dacfe8bd569a6300b4c21e0287
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="d7851-102">Criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7851-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7851-103">_**Argomento Ultima modifica:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="d7851-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="d7851-104">I criteri di conferenza definiscono le caratteristiche e le funzionalità disponibili per gli utenti durante una conferenza (nota anche come riunione).</span><span class="sxs-lookup"><span data-stu-id="d7851-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="d7851-105">Le impostazioni dei criteri di conferenza includono una vasta gamma di opzioni di pianificazione e partecipazione, che vanno dal fatto che una riunione possa includere l'audio e il video IP al numero massimo di persone che possono partecipare.</span><span class="sxs-lookup"><span data-stu-id="d7851-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="d7851-106">Gli amministratori possono usare i criteri di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="d7851-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="d7851-107">È possibile definire i criteri di conferenza su tre livelli: ambito globale, ambito del sito e ambito utente.</span><span class="sxs-lookup"><span data-stu-id="d7851-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="d7851-108">Le impostazioni si applicano a un utente specifico dall'ambito più stretto all'ambito più ampio.</span><span class="sxs-lookup"><span data-stu-id="d7851-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="d7851-109">Se si assegna un criterio utente a un utente, queste impostazioni hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="d7851-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="d7851-110">Se non si assegna un criterio utente, le impostazioni del sito si applicano.</span><span class="sxs-lookup"><span data-stu-id="d7851-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="d7851-111">Se non si applicano criteri per l'utente o il sito, i criteri globali forniscono le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="d7851-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="d7851-112">Un criterio globale esiste per impostazione predefinita, quindi non è possibile creare un nuovo criterio globale.</span><span class="sxs-lookup"><span data-stu-id="d7851-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="d7851-113">Non è inoltre possibile eliminare i criteri globali esistenti, ma è possibile modificare i criteri globali esistenti per personalizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="d7851-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7851-114">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d7851-114">In This Section</span></span>

  - [<span data-ttu-id="d7851-115">Visualizzare le informazioni sui criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7851-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="d7851-116">Creare o modificare criteri per i servizi di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7851-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="d7851-117">Eliminare un criterio di conferenza esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7851-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="d7851-118">Informazioni di riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7851-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

