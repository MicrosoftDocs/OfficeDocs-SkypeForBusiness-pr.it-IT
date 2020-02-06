---
title: Modifiche allo schema in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Prima di distribuire e gestire Skype for Business Server, è necessario preparare i servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Skype for Business Server.
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815484"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="0b708-104">Modifiche allo schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0b708-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="0b708-105">Prima di distribuire e gestire Skype for Business Server, è necessario preparare i servizi di dominio Active Directory estendendo lo schema.</span><span class="sxs-lookup"><span data-stu-id="0b708-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="0b708-106">Le estensioni dello schema aggiungono le classi e gli attributi richiesti da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="0b708-107">Se si esegue l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015, non vengono apportate modifiche allo schema e pertanto questo articolo non si applica.</span><span class="sxs-lookup"><span data-stu-id="0b708-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="0b708-108">Skype for Business Server richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti.</span><span class="sxs-lookup"><span data-stu-id="0b708-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="0b708-109">Inoltre, molte informazioni di configurazione per Skype for Business Server sono archiviate nell'archivio di gestione centrale anziché in servizi di dominio Active Directory come nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0b708-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="0b708-110">Le informazioni seguenti sono ancora archiviate in servizi di dominio Active Directory in Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0b708-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="0b708-111">**Estensioni dello schema**:</span><span class="sxs-lookup"><span data-stu-id="0b708-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="0b708-112">Estensioni degli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="0b708-112">User object extensions</span></span>
    
  - <span data-ttu-id="0b708-113">Estensioni per le classi per mantenere la compatibilità con le versioni precedenti supportate di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="0b708-114">**Dati** (archiviati in Skype for Business Server Extended schema e nelle classi dello schema esistenti):</span><span class="sxs-lookup"><span data-stu-id="0b708-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="0b708-115">URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="0b708-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="0b708-116">Oggetti contatto per applicazioni come Response Group e operatore di conferenza</span><span class="sxs-lookup"><span data-stu-id="0b708-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="0b708-117">Un puntatore all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="0b708-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="0b708-118">Account di autenticazione Kerberos (un oggetto computer facoltativo)</span><span class="sxs-lookup"><span data-stu-id="0b708-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="0b708-119">Questo argomento descrive le modifiche allo schema di Active Directory richieste da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="0b708-120">Non descrive le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="0b708-121">Per un elenco delle classi e delle relative descrizioni, vedere [classi di schema e descrizioni in Skype for Business Server](schema-classes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="0b708-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="0b708-122">Per un elenco degli attributi e delle relative descrizioni, vedere [attributi e descrizioni dello schema in Skype for Business Server](schema-attributes-and-descriptions.md).</span><span class="sxs-lookup"><span data-stu-id="0b708-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="0b708-123">Per un elenco di classi con gli attributi che possono contenere, Vedi [attributi dello schema per classe in Skype for Business Server](schema-attributes-by-class.md).</span><span class="sxs-lookup"><span data-stu-id="0b708-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="0b708-124">Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="0b708-125">Nuovi attributi di Active Directory</span><span class="sxs-lookup"><span data-stu-id="0b708-125">New Active Directory Attributes</span></span>

<span data-ttu-id="0b708-126">La tabella seguente descrive gli attributi di Active Directory aggiunti da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="0b708-127">**Attributi aggiunti da Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="0b708-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="0b708-128">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="0b708-128">**Attribute**</span></span>|<span data-ttu-id="0b708-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0b708-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0b708-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0b708-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="0b708-131">Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente.</span><span class="sxs-lookup"><span data-stu-id="0b708-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="0b708-132">I criteri di blocco mantengono gli elementi della cassetta postale per l'utente per la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="0b708-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="0b708-133">Questo attributo è condiviso con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="0b708-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="0b708-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="0b708-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="0b708-135">Questo è l'ID del gruppo di routing SIP.</span><span class="sxs-lookup"><span data-stu-id="0b708-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="0b708-136">Gli utenti nello stesso gruppo registreranno lo stesso server front-end.</span><span class="sxs-lookup"><span data-stu-id="0b708-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="0b708-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="0b708-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="0b708-138">Questo attributo viene usato per archiviare il backend di SQL Server con mirroring usato dal pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="0b708-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="0b708-139">Classi di Active Directory modificate</span><span class="sxs-lookup"><span data-stu-id="0b708-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="0b708-140">La tabella seguente descrive le classi Active Directory modificate da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b708-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="0b708-141">**Classi modificate da Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="0b708-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="0b708-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="0b708-142">**Class**</span></span>|<span data-ttu-id="0b708-143">**Modificare**</span><span class="sxs-lookup"><span data-stu-id="0b708-143">**Change**</span></span>|<span data-ttu-id="0b708-144">**Classe o attributo**</span><span class="sxs-lookup"><span data-stu-id="0b708-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b708-145">Utente</span><span class="sxs-lookup"><span data-stu-id="0b708-145">User</span></span>  <br/> |<span data-ttu-id="0b708-146">Aggiungi: mayContain</span><span class="sxs-lookup"><span data-stu-id="0b708-146">add: mayContain</span></span>  <br/> <span data-ttu-id="0b708-147">Aggiungi: mayContain</span><span class="sxs-lookup"><span data-stu-id="0b708-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="0b708-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0b708-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="0b708-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="0b708-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="0b708-150">Contatto</span><span class="sxs-lookup"><span data-stu-id="0b708-150">Contact</span></span>  <br/> |<span data-ttu-id="0b708-151">Aggiungi: mayContain</span><span class="sxs-lookup"><span data-stu-id="0b708-151">add: mayContain</span></span>  <br/> <span data-ttu-id="0b708-152">Aggiungi: mayContain</span><span class="sxs-lookup"><span data-stu-id="0b708-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="0b708-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0b708-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="0b708-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="0b708-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="0b708-155">Destinatario della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="0b708-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="0b708-156">Aggiungi: mayContain</span><span class="sxs-lookup"><span data-stu-id="0b708-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="0b708-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0b708-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="0b708-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="0b708-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="0b708-159">Aggiungi: mayContain</span><span class="sxs-lookup"><span data-stu-id="0b708-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="0b708-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="0b708-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

