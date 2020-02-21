---
title: 'Lync Server 2013: configurazione delle conferenze telefoniche con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 990f22cc08d25d8b78263f4594d8345be5b29c5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="a95a3-102">Configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a95a3-103">_**Ultimo argomento modificato:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="a95a3-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="a95a3-104">In questa sezione viene illustrata la configurazione delle conferenze telefoniche con accesso esterno di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a95a3-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a95a3-105">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="a95a3-105">In This Section</span></span>

  - [<span data-ttu-id="a95a3-106">Prerequisiti e autorizzazioni per la configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="a95a3-107">Elenco di controllo di distribuzione per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="a95a3-108">Configurare i dial plan per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="a95a3-109">Assicurarsi che i dial plan Lync Server 2013 abbiano assegnato aree geografiche</span><span class="sxs-lookup"><span data-stu-id="a95a3-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="a95a3-110">Optional Verificare le impostazioni del criterio PIN in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="a95a3-111">Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="a95a3-112">Configurare i numeri di accesso per le conferenze telefoniche con chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="a95a3-113">Optional Verificare le impostazioni delle conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="a95a3-114">Optional Modificare il mapping dei tasti per i comandi DTMF in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="a95a3-115">Optional Abilitare e disabilitare gli annunci di partecipazione alla conferenza e di uscita in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="a95a3-116">Optional Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="a95a3-117">Distribuire il componente aggiuntivo per riunioni online per Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="a95a3-118">Configurare le impostazioni degli account utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="a95a3-119">Consigliato Creare directory conferenze</span><span class="sxs-lookup"><span data-stu-id="a95a3-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="a95a3-120">Optional Accogliere gli utenti per le conferenze telefoniche con accesso esterno in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="a95a3-121">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="a95a3-121">Related Sections</span></span>

[<span data-ttu-id="a95a3-122">Distribuzione di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a95a3-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

