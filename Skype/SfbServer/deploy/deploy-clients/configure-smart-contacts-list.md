---
title: Configurare l'elenco contatti intelligenti nei client Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Riepilogo: informazioni su come attivare la caratteristica elenco contatti Smart nel client Skype for business.'
ms.openlocfilehash: 0deb90293ddf4f1a6627eb4bff86d7d8eb0ae5c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190472"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="a5add-103">Configurare l'elenco contatti intelligenti nei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="a5add-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="a5add-104">**Riepilogo:** Informazioni su come attivare la caratteristica elenco contatti intelligenti nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="a5add-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="a5add-105">La caratteristica elenco contatti intelligenti consente la popolazione automatica degli elenchi di contatti per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="a5add-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="a5add-106">Al primo utilizzo di Skype for business, gli utenti vedranno automaticamente il loro manager e altre persone nel loro team.</span><span class="sxs-lookup"><span data-stu-id="a5add-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="a5add-107">Questa caratteristica è attivata per impostazione predefinita per gli utenti di Office 365, ma è necessario abilitare esplicitamente questa caratteristica per gli utenti locali configurando l'impostazione del criterio client.</span><span class="sxs-lookup"><span data-stu-id="a5add-107">This feature is turned on by default for Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="a5add-108">Quando si configura questa funzionalità, tieni presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a5add-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="a5add-109">Gli utenti, fino a 13, vengono aggiunti automaticamente all'elenco contatti intelligenti nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="a5add-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="a5add-110">Manager</span><span class="sxs-lookup"><span data-stu-id="a5add-110">Manager</span></span>

  2. <span data-ttu-id="a5add-111">Dirige in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="a5add-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="a5add-112">Peer in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="a5add-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="a5add-113">La prima volta che si accede a un utente, viene creato un nuovo gruppo denominato gruppo personale.</span><span class="sxs-lookup"><span data-stu-id="a5add-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="a5add-114">Il gruppo viene popolato automaticamente con persone nella relazione del gruppo di annunci dell'utente in base all'alias utente compilato nel campo Manager.</span><span class="sxs-lookup"><span data-stu-id="a5add-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="a5add-115">Tieni presente che le modifiche apportate all'appartenenza al gruppo di annunci non causano aggiornamenti al gruppo dopo che è stato inizialmente compilato.</span><span class="sxs-lookup"><span data-stu-id="a5add-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="a5add-116">Se un utente elimina un contatto o il gruppo, non vengono ricreati né il contatto né il gruppo.</span><span class="sxs-lookup"><span data-stu-id="a5add-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="a5add-117">Se il contrassegno automatico è attivato, i contatti nell'elenco verranno contrassegnati per le modifiche alla presenza.</span><span class="sxs-lookup"><span data-stu-id="a5add-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="a5add-118">La codifica automatica è attivata per impostazione predefinita, ma puoi scegliere di disattivarla.</span><span class="sxs-lookup"><span data-stu-id="a5add-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="a5add-119">Tutti i nuovi utenti del gruppo verranno informati che sono stati aggiunti all'elenco contatti.</span><span class="sxs-lookup"><span data-stu-id="a5add-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="a5add-120">Gli utenti possono aggiungere manualmente nuovi membri al gruppo personale o ad altri gruppi di loro scelta.</span><span class="sxs-lookup"><span data-stu-id="a5add-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="a5add-121">Questa funzionalità funziona solo per gli utenti che accedono per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="a5add-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="a5add-122">Se un utente ha già eseguito l'accesso da qualsiasi dispositivo, ad esempio un dispositivo mobile o un Mac, la funzionalità non è abilitata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a5add-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="a5add-123">Configurare l'elenco contatti intelligenti</span><span class="sxs-lookup"><span data-stu-id="a5add-123">Configure Smart contacts list</span></span>

<span data-ttu-id="a5add-124">Per abilitare la caratteristica elenco contatti Smart per gli utenti, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a5add-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="a5add-125">Creare una nuova voce di CsClientPolicy e aggiungerla al criterio client globale.</span><span class="sxs-lookup"><span data-stu-id="a5add-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="a5add-126">Verificare che la ricerca della rubrica sia configurata solo per la ricerca Web.</span><span class="sxs-lookup"><span data-stu-id="a5add-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="a5add-127">Creare una voce di criteri per abilitare l'elenco contatti intelligenti</span><span class="sxs-lookup"><span data-stu-id="a5add-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="a5add-128">Per creare una voce di criteri per abilitare la caratteristica elenco contatti intelligenti, usare il cmdlet [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con l'opzione EnableClientAutoPopulateWithTeam come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a5add-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="a5add-129">Utilizzare quindi il cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) per scrivere le modifiche apportate al criterio globale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a5add-129">Next, use the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="a5add-130">È possibile creare facoltativamente un criterio per disattivare la codifica automatica come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a5add-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="a5add-131">Devi anche impostare il parametro AddressBookAvailability per il criterio corrispondente in WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="a5add-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="a5add-132">Per altre informazioni, vedere [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a5add-132">For more information, see [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="a5add-133">Risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="a5add-133">Troubleshoot</span></span>

<span data-ttu-id="a5add-134">Se l'elenco contatti intelligenti non funziona come previsto, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a5add-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="a5add-135">Convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="a5add-135">Validate the configuration.</span></span> 

- <span data-ttu-id="a5add-136">Verificare che le informazioni sull'organizzazione degli annunci vengano popolate.</span><span class="sxs-lookup"><span data-stu-id="a5add-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="a5add-137">Raccogliere i registri client Skype for business su un nuovo utente per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="a5add-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="a5add-138">Verificare che l'interfaccia utente del client Skype for business non visualizzi un messaggio che non riesce a connettersi alla Rubrica.</span><span class="sxs-lookup"><span data-stu-id="a5add-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="a5add-139">Per confermare la connettività della Rubrica, eseguire una ricerca per un utente nella barra di ricerca del client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="a5add-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="a5add-140">I problemi di replica di servizi di dominio Active Directory possono causare la risoluzione dei contatti quando un utente accede prima a Skype for business.</span><span class="sxs-lookup"><span data-stu-id="a5add-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>


