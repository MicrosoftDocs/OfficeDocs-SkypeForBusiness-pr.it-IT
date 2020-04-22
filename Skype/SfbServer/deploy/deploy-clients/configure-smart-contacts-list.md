---
title: Configurare l'elenco dei contatti intelligenti nei client Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Riepilogo: informazioni su come abilitare la funzionalità elenco contatti Smart nel client Skype for business.'
ms.openlocfilehash: d99008cde28b834f77a2935ffd7882162aa05e95
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776691"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="aeee3-103">Configurare l'elenco dei contatti intelligenti nei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="aeee3-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="aeee3-104">**Riepilogo:** Informazioni su come abilitare la funzionalità elenco contatti Smart nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="aeee3-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="aeee3-105">La funzionalità elenco contatti avanzati consente la popolamento automatico degli elenchi di contatti per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="aeee3-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="aeee3-106">Al primo utilizzo di Skype for business, gli utenti visualizzeranno automaticamente il Manager e altre persone del team.</span><span class="sxs-lookup"><span data-stu-id="aeee3-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="aeee3-107">Questa funzionalità è attivata per impostazione predefinita per gli utenti di Microsoft 365 e Office 365, ma è necessario abilitare esplicitamente questa funzionalità per gli utenti locali configurando l'impostazione dei criteri client.</span><span class="sxs-lookup"><span data-stu-id="aeee3-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="aeee3-108">Quando si configura questa funzionalità, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="aeee3-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="aeee3-109">Gli utenti, fino a 13, vengono aggiunti automaticamente all'elenco dei contatti Smart nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="aeee3-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="aeee3-110">Manager</span><span class="sxs-lookup"><span data-stu-id="aeee3-110">Manager</span></span>

  2. <span data-ttu-id="aeee3-111">Indirizza in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="aeee3-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="aeee3-112">Peer in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="aeee3-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="aeee3-113">La prima volta che un utente esegue l'accesso, viene creato un nuovo gruppo denominato My Group.</span><span class="sxs-lookup"><span data-stu-id="aeee3-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="aeee3-114">Il gruppo viene popolato automaticamente con persone nella relazione del gruppo di annunci dell'utente in base all'alias utente popolato nel campo Manager.</span><span class="sxs-lookup"><span data-stu-id="aeee3-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="aeee3-115">Si noti che le modifiche apportate all'appartenenza a un gruppo di annunci non causano aggiornamenti al gruppo dopo che è stata inizialmente popolata.</span><span class="sxs-lookup"><span data-stu-id="aeee3-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="aeee3-116">Se un utente elimina un contatto o un gruppo, il contatto o il gruppo non vengono ricreati.</span><span class="sxs-lookup"><span data-stu-id="aeee3-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="aeee3-117">Se l'opzione di tagging automatico è attivata, i contatti nell'elenco verranno contrassegnati per le modifiche alla presenza.</span><span class="sxs-lookup"><span data-stu-id="aeee3-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="aeee3-118">La codifica automatica è attivata per impostazione predefinita, ma è possibile scegliere di disattivarla.</span><span class="sxs-lookup"><span data-stu-id="aeee3-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="aeee3-119">Tutti i nuovi utenti del gruppo verranno informati che sono stati aggiunti all'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="aeee3-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="aeee3-120">Gli utenti possono aggiungere manualmente nuovi membri al proprio gruppo personale o ad altri gruppi di loro scelta.</span><span class="sxs-lookup"><span data-stu-id="aeee3-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="aeee3-121">Questa funzionalità è compatibile solo per gli utenti che accedono per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="aeee3-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="aeee3-122">Se un utente ha precedentemente eseguito l'accesso da qualsiasi dispositivo, ad esempio un dispositivo mobile o un Mac, la caratteristica non è abilitata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="aeee3-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="aeee3-123">Configurare l'elenco dei contatti intelligenti</span><span class="sxs-lookup"><span data-stu-id="aeee3-123">Configure Smart contacts list</span></span>

<span data-ttu-id="aeee3-124">Per abilitare la funzionalità elenco contatti Smart per gli utenti, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeee3-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="aeee3-125">Creare una nuova voce di CsClientPolicy e aggiungerla al criterio client globale.</span><span class="sxs-lookup"><span data-stu-id="aeee3-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="aeee3-126">Verificare che la ricerca rubrica sia configurata solo per la ricerca Web.</span><span class="sxs-lookup"><span data-stu-id="aeee3-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="aeee3-127">Creare una voce di criteri per abilitare l'elenco dei contatti intelligenti</span><span class="sxs-lookup"><span data-stu-id="aeee3-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="aeee3-128">Per creare una voce di criteri per abilitare la funzionalità elenco Smart contacts, utilizzare il cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con l'opzione EnableClientAutoPopulateWithTeam, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="aeee3-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="aeee3-129">Successivamente, utilizzare il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) per scrivere le modifiche apportate ai criteri globali, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="aeee3-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="aeee3-130">Facoltativamente, è possibile creare un criterio per disattivare il tagging automatico come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="aeee3-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="aeee3-131">È inoltre necessario impostare il parametro AddressBookAvailability per il criterio corrispondente su WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="aeee3-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="aeee3-132">Per ulteriori informazioni, vedere [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aeee3-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="aeee3-133">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="aeee3-133">Troubleshoot</span></span>

<span data-ttu-id="aeee3-134">Se l'elenco dei contatti avanzati non funziona come previsto, controllare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="aeee3-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="aeee3-135">Convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="aeee3-135">Validate the configuration.</span></span> 

- <span data-ttu-id="aeee3-136">Verificare che le informazioni dell'organizzazione di Active Directory siano popolate.</span><span class="sxs-lookup"><span data-stu-id="aeee3-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="aeee3-137">Raccolta di registri client Skype for business su un nuovo utente per ulteriori analisi.</span><span class="sxs-lookup"><span data-stu-id="aeee3-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="aeee3-138">Verificare che l'interfaccia utente del client Skype for business non visualizzi un messaggio che non sia in grado di connettersi alla Rubrica.</span><span class="sxs-lookup"><span data-stu-id="aeee3-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="aeee3-139">Per confermare la connettività della Rubrica, eseguire una ricerca per un utente nella barra di ricerca del client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="aeee3-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="aeee3-140">I problemi di replica di servizi di dominio Active Directory potrebbero causare la risoluzione dei contatti quando un utente accede per la prima volta a Skype for business.</span><span class="sxs-lookup"><span data-stu-id="aeee3-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


