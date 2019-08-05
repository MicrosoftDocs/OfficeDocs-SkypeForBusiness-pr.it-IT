---
title: Estensioni, classi e attributi dello schema di Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Questa sezione di riferimento include le informazioni seguenti:'
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194872"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="0f5b4-103">Estensioni, classi e attributi dello schema di Active Directory</span><span class="sxs-lookup"><span data-stu-id="0f5b4-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="0f5b4-104">Questa sezione di riferimento include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f5b4-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="0f5b4-105">Estensioni dello schema di Active Directory nuove o modificate per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="0f5b4-106">Lo schema Active Directory contiene definizioni formali di tutte le classi di oggetti che possono essere create in una foresta di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f5b4-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="0f5b4-107">Lo schema contiene anche definizioni formali di ogni attributo che può esistere in un oggetto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f5b4-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="0f5b4-108">Il catalogo globale di Active Directory contiene le repliche di tutti gli oggetti per la foresta, insieme a un sottoinsieme degli attributi per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="0f5b4-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="0f5b4-109">Questa sezione descrive le classi e gli attributi nuovi o modificati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0f5b4-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="0f5b4-110">Tutte le classi usate da Skype for Business Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="0f5b4-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="0f5b4-111">Tutti gli attributi usati da Skype for Business Server, con una descrizione di ogni</span><span class="sxs-lookup"><span data-stu-id="0f5b4-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="0f5b4-112">Elenco delle classi usate da Skype for Business Server, con gli attributi che ognuno di essi può contenere</span><span class="sxs-lookup"><span data-stu-id="0f5b4-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="0f5b4-113">Impostazioni globali e oggetti, oltre ai gruppi di servizi e di amministrazione universali creati durante la preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="0f5b4-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="0f5b4-114">Voci di controllo di accesso (ACE) create nella radice del dominio e contenitori predefiniti durante la preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="0f5b4-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="0f5b4-115">Le modifiche apportate in un'unità organizzativa di Active Directory dal cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="0f5b4-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="0f5b4-116">Le modifiche apportate in un'unità organizzativa di Active Directory dal cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="0f5b4-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="0f5b4-117">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0f5b4-117">In This Section</span></span>

- [<span data-ttu-id="0f5b4-118">Modifiche allo schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="0f5b4-119">Classi e descrizioni dello schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="0f5b4-120">Attributi e descrizioni dello schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="0f5b4-121">Attributi dello schema per classe in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="0f5b4-122">Modifiche apportate dalla preparazione della foresta in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="0f5b4-123">Modifiche apportate dalla preparazione del dominio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="0f5b4-124">Modifiche apportate da Grant-CsSetupPermission in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="0f5b4-125">Modifiche apportate da Grant-CsOUPermission in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0f5b4-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

