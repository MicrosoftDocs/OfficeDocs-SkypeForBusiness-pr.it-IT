---
title: 'Lync Server 2013: estensioni dello schema, classi e attributi di Active Directory utilizzati da Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cf2b157dcd039f11d38ef56d6da07a6921e1c9c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521593"
---
# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="85bb9-102">Estensioni, classi e attributi dello schema di Active Directory utilizzati da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85bb9-103">_**Ultimo argomento modificato:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="85bb9-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="85bb9-104">In questa sezione di riferimento sono incluse le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85bb9-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="85bb9-105">Estensioni dello schema di Active Directory nuove o modificate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="85bb9-106">Lo schema di Active Directory contiene le definizioni formali di ogni classe di oggetti che è possibile creare in una foresta di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85bb9-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="85bb9-107">Lo schema include inoltre le definizioni formali di ogni attributo che è possibile definire per un oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="85bb9-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="85bb9-108">Il catalogo globale di Active Directory contiene le repliche di tutti gli oggetti relativi alla foresta, insieme a un sottoinsieme degli attributi relativi a ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="85bb9-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="85bb9-109">In questa sezione vengono descritte le classi e gli attributi nuovi o modificati in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="85bb9-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="85bb9-110">Tutte le classi utilizzate da Lync Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="85bb9-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="85bb9-111">Tutti gli attributi utilizzati da Lync Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="85bb9-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="85bb9-112">Un elenco delle classi utilizzate da Lync Server, con gli attributi ognuno dei quali può contenere</span><span class="sxs-lookup"><span data-stu-id="85bb9-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="85bb9-113">Impostazioni globali e oggetti, nonché i gruppi amministrativi e di servizi universali creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="85bb9-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="85bb9-114">Voci di controllo di accesso create nella radice del dominio e contenitori predefiniti utilizzati durante la preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="85bb9-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="85bb9-115">Modifiche apportate in un'unità organizzativa (OU) di Active Directory dal \_ cmdlet Grant CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="85bb9-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="85bb9-116">Modifiche apportate in un'unità organizzativa di Active Directory dal \_ cmdlet Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="85bb9-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="85bb9-117">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="85bb9-117">In This Section</span></span>

  - [<span data-ttu-id="85bb9-118">Modifiche dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="85bb9-119">Classi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="85bb9-120">Attributi e descrizioni dello schema in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="85bb9-121">Attributi dello schema per classe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="85bb9-122">Modifiche apportate dalla preparazione della foresta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="85bb9-123">Modifiche apportate dalla preparazione del dominio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="85bb9-124">Modifiche apportate da Grant-CsSetupPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="85bb9-125">Modifiche apportate da Grant-CsOUPermission in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85bb9-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

