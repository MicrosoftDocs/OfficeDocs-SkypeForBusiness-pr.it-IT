---
title: Modifiche allo schema in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Prima di distribuire e utilizzare Skype for Business Server, è necessario preparare Servizi di dominio Active Directory estendendo lo schema. Le estensioni dello schema aggiungono le classi e gli attributi necessari per Skype for Business Server.
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813576"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="2c89d-104">Modifiche allo schema in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2c89d-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="2c89d-105">Prima di distribuire e utilizzare Skype for Business Server, è necessario preparare Servizi di dominio Active Directory estendendo lo schema.</span><span class="sxs-lookup"><span data-stu-id="2c89d-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="2c89d-106">Le estensioni dello schema aggiungono le classi e gli attributi necessari per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="2c89d-107">Se si esegue l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015, non vengono apportate modifiche allo schema e pertanto questo articolo non è applicabile.</span><span class="sxs-lookup"><span data-stu-id="2c89d-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="2c89d-108">Skype for Business Server richiede diverse nuove classi e attributi e modifica alcune classi e attributi esistenti.</span><span class="sxs-lookup"><span data-stu-id="2c89d-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="2c89d-109">Inoltre, molte informazioni di configurazione per Skype for Business Server vengono archiviate nell'archivio di gestione centrale anziché in Servizi di dominio Active Directory come nelle versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2c89d-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="2c89d-110">Le informazioni seguenti sono ancora archiviate in Servizi di dominio Active Directory in Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2c89d-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="2c89d-111">**Estensioni dello schema**:</span><span class="sxs-lookup"><span data-stu-id="2c89d-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="2c89d-112">Estensioni degli oggetti utente</span><span class="sxs-lookup"><span data-stu-id="2c89d-112">User object extensions</span></span>
    
  - <span data-ttu-id="2c89d-113">Estensioni per le classi per mantenere la compatibilità con le versioni precedenti supportate di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="2c89d-114">**Dati** (archiviati nello schema esteso di Skype for Business Server e nelle classi dello schema esistenti):</span><span class="sxs-lookup"><span data-stu-id="2c89d-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="2c89d-115">URI (Uniform Resource Identifier) SIP dell'utente e altre impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="2c89d-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="2c89d-116">Oggetti contatto per applicazioni quali Response Group e Operatore Conferenza</span><span class="sxs-lookup"><span data-stu-id="2c89d-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="2c89d-117">Puntatore all'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="2c89d-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="2c89d-118">Account di autenticazione Kerberos (un oggetto computer facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2c89d-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="2c89d-119">In questo argomento vengono descritte le modifiche allo schema di Active Directory richieste da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="2c89d-120">Non vengono descritte le modifiche allo schema introdotte dalle versioni precedenti di Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="2c89d-121">Per un elenco delle classi e delle relative descrizioni, vedi Le classi e le descrizioni dello [schema in Skype for Business Server.](schema-classes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="2c89d-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="2c89d-122">Per un elenco degli attributi e delle relative descrizioni, vedere Attributi e descrizioni dello [schema in Skype for Business Server.](schema-attributes-and-descriptions.md)</span><span class="sxs-lookup"><span data-stu-id="2c89d-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="2c89d-123">Per un elenco delle classi con gli attributi che possono contenere, vedere [Attributi dello schema per classe in Skype for Business Server.](schema-attributes-by-class.md)</span><span class="sxs-lookup"><span data-stu-id="2c89d-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="2c89d-124">Il prefisso msRTCSIP identifica le classi e gli attributi specifici di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="2c89d-125">Nuovi attributi di Active Directory</span><span class="sxs-lookup"><span data-stu-id="2c89d-125">New Active Directory Attributes</span></span>

<span data-ttu-id="2c89d-126">Nella tabella seguente vengono descritti gli attributi di Active Directory aggiunti da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="2c89d-127">**Attributi aggiunti da Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="2c89d-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="2c89d-128">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="2c89d-128">**Attribute**</span></span>|<span data-ttu-id="2c89d-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2c89d-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2c89d-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="2c89d-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="2c89d-131">Questo attributo multivalore contiene gli identificatori per i criteri di blocco applicabili all'utente.</span><span class="sxs-lookup"><span data-stu-id="2c89d-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="2c89d-132">I criteri di blocco mantengono gli elementi della cassetta postale per l'utente per tutta la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="2c89d-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="2c89d-133">Questo attributo è condiviso con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2c89d-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="2c89d-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2c89d-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="2c89d-135">Questo è l'ID del gruppo di routing SIP.</span><span class="sxs-lookup"><span data-stu-id="2c89d-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="2c89d-136">Gli utenti dello stesso gruppo verranno registrati nello stesso Front End Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="2c89d-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="2c89d-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="2c89d-138">Questo attributo viene utilizzato per archiviare il SQL Server back-end con mirroring utilizzato dal pool Front End.</span><span class="sxs-lookup"><span data-stu-id="2c89d-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="2c89d-139">Classi di Active Directory modificate</span><span class="sxs-lookup"><span data-stu-id="2c89d-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="2c89d-140">Nella tabella seguente vengono descritte le classi di Active Directory modificate da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2c89d-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="2c89d-141">**Classi modificate da Skype for Business Server**</span><span class="sxs-lookup"><span data-stu-id="2c89d-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="2c89d-142">**Classe**</span><span class="sxs-lookup"><span data-stu-id="2c89d-142">**Class**</span></span>|<span data-ttu-id="2c89d-143">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="2c89d-143">**Change**</span></span>|<span data-ttu-id="2c89d-144">**Classe o attributo**</span><span class="sxs-lookup"><span data-stu-id="2c89d-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c89d-145">Utente</span><span class="sxs-lookup"><span data-stu-id="2c89d-145">User</span></span>  <br/> |<span data-ttu-id="2c89d-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="2c89d-146">add: mayContain</span></span>  <br/> <span data-ttu-id="2c89d-147">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="2c89d-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="2c89d-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2c89d-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="2c89d-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2c89d-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="2c89d-150">Contatto</span><span class="sxs-lookup"><span data-stu-id="2c89d-150">Contact</span></span>  <br/> |<span data-ttu-id="2c89d-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="2c89d-151">add: mayContain</span></span>  <br/> <span data-ttu-id="2c89d-152">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="2c89d-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="2c89d-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="2c89d-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="2c89d-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="2c89d-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="2c89d-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="2c89d-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="2c89d-156">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="2c89d-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="2c89d-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="2c89d-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="2c89d-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="2c89d-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="2c89d-159">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="2c89d-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="2c89d-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="2c89d-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

