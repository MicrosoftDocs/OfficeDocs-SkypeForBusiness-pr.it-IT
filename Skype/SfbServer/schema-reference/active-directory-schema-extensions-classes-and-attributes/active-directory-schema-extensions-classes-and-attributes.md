---
title: Estensioni dello schema, classi e attributi di Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'In questa sezione di riferimento sono incluse le informazioni seguenti:'
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831936"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="5be01-103">Estensioni dello schema, classi e attributi di Active Directory</span><span class="sxs-lookup"><span data-stu-id="5be01-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="5be01-104">In questa sezione di riferimento sono incluse le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5be01-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="5be01-105">Estensioni dello schema di Active Directory nuove o modificate per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="5be01-106">Lo schema di Active Directory contiene le definizioni formali di ogni classe di oggetti che è possibile creare in una foresta di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5be01-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="5be01-107">Lo schema include inoltre le definizioni formali di ogni attributo che è possibile definire per un oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5be01-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="5be01-108">Il catalogo globale di Active Directory contiene le repliche di tutti gli oggetti relativi alla foresta, insieme a un sottoinsieme degli attributi relativi a ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="5be01-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="5be01-109">In questa sezione vengono descritte le classi e gli attributi nuovi o modificati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5be01-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="5be01-110">Tutte le classi utilizzate da Skype for Business Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="5be01-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="5be01-111">Tutti gli attributi utilizzati da Skype for Business Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="5be01-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="5be01-112">Un elenco delle classi utilizzate da Skype for Business Server, con gli attributi ognuno dei quali può contenere</span><span class="sxs-lookup"><span data-stu-id="5be01-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="5be01-113">Impostazioni globali e oggetti, nonché i gruppi amministrativi e di servizi universali creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="5be01-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="5be01-114">Voci di controllo di accesso create nella radice del dominio e contenitori predefiniti utilizzati durante la preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="5be01-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="5be01-115">Le modifiche apportate in un'unità organizzativa (OU) di Active Directory dal cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="5be01-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="5be01-116">Le modifiche apportate in un'unità organizzativa di Active Directory dal cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="5be01-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="5be01-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5be01-117">In This Section</span></span>

- [<span data-ttu-id="5be01-118">Modifiche dello schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="5be01-119">Classi e descrizioni dello schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="5be01-120">Attributi e descrizioni dello schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="5be01-121">Attributi dello schema per classe in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="5be01-122">Modifiche apportate dalla preparazione della foresta in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="5be01-123">Modifiche apportate dalla preparazione del dominio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="5be01-124">Modifiche apportate da Grant-CsSetupPermission in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="5be01-125">Modifiche apportate da Grant-CsOUPermission in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be01-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

