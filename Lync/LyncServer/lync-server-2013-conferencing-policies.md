---
title: 'Lync Server 2013: criteri di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ea3f562f06c0f228e7275481c288c4a3e107d56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="97ddb-102">Criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ddb-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97ddb-103">_**Ultimo argomento modificato:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="97ddb-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="97ddb-p101">Il criterio di conferenza definisce le caratteristiche e le funzionalità disponibili agli utenti durante una conferenza, detta anche riunione. Le impostazioni di tale criterio riguardano una vasta gamma di opzioni di pianificazione e partecipazione, dalla possibilità di includere contenuto audio e video IP in una riunione al numero massimo di persone che possono partecipare. Gli amministratori possono utilizzare il criterio di conferenza per gestire la sicurezza, la larghezza di banda e gli aspetti legali delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="97ddb-p101">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting). Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="97ddb-p102">È possibile definire un criterio di conferenza su tre livelli: ambito globale, ambito sito e ambito utente. Le impostazioni si applicano a un utente specifico partendo dall'ambito più ristretto fino all'ambito più ampio. Se si assegna un criterio utente a un utente, tali impostazioni hanno la priorità. Se non si assegna un criterio utente, si applicano le impostazioni sito. Se non si applica alcun criterio utente o sito, le impostazioni predefinite vengono fornite dal criterio globale.</span><span class="sxs-lookup"><span data-stu-id="97ddb-p102">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a user policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="97ddb-p103">Poiché esiste un criterio globale per impostazione predefinita, non è possibile crearne uno nuovo. Non è possibile inoltre eliminare il criterio globale esistente, ma è possibile modificarlo per personalizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="97ddb-p103">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97ddb-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="97ddb-114">In This Section</span></span>

  - [<span data-ttu-id="97ddb-115">Visualizzare le informazioni sui criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ddb-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="97ddb-116">Creare o modificare criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ddb-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="97ddb-117">Eliminare un criterio di conferenza esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ddb-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="97ddb-118">Informazioni di riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97ddb-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

