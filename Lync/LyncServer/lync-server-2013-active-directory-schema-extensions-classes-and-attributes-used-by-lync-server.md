---
title: 'Lync Server 2013: Estensioni dello schema, classi e attributi di Active Directory utilizzati da Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc883c1c85acbe41bec6a25467e50800c036996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="9f845-102">Estensioni dello schema, classi e attributi di Active Directory utilizzati da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f845-103">_**Argomento Ultima modifica:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="9f845-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="9f845-104">Questa sezione di riferimento include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f845-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="9f845-105">Estensioni dello schema di Active Directory nuove o modificate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="9f845-106">Lo schema Active Directory contiene definizioni formali di tutte le classi di oggetti che possono essere create in una foresta di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f845-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="9f845-107">Lo schema contiene anche definizioni formali di ogni attributo che può esistere in un oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f845-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="9f845-108">Il catalogo globale di Active Directory contiene le repliche di tutti gli oggetti per la foresta, insieme a un sottoinsieme degli attributi per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="9f845-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="9f845-109">Questa sezione descrive le classi e gli attributi nuovi o modificati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9f845-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="9f845-110">Tutte le classi usate da Lync Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="9f845-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="9f845-111">Tutti gli attributi usati da Lync Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="9f845-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="9f845-112">Elenco delle classi usate da Lync Server, con gli attributi che ognuno di essi può contenere</span><span class="sxs-lookup"><span data-stu-id="9f845-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="9f845-113">Impostazioni globali e oggetti, oltre ai gruppi di servizi e di amministrazione universali creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="9f845-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="9f845-114">Voci di controllo di accesso (ACE) create nella radice del dominio e contenitori predefiniti durante la preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="9f845-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="9f845-115">Le modifiche apportate in un'unità organizzativa di Active Directory dal cmdlet Grant\_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="9f845-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="9f845-116">Le modifiche apportate in un'unità organizzativa di Active Directory\_dal cmdlet Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="9f845-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9f845-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9f845-117">In This Section</span></span>

  - [<span data-ttu-id="9f845-118">Modifiche allo schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="9f845-119">Classi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="9f845-120">Attributi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="9f845-121">Attributi dello schema per classe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="9f845-122">Modifiche apportate dalla preparazione della foresta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="9f845-123">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="9f845-124">Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="9f845-125">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f845-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

