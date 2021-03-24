---
title: Configurare l'elenco contatti smart nei client Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 'Riepilogo: informazioni su come attivare la funzionalità Elenco contatti smart nel client Skype for Business.'
ms.openlocfilehash: 1f049493d591cd561b87611f8a34f9176ace165a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095800"
---
# <a name="configure-smart-contacts-list-in-skype-for-business-clients"></a><span data-ttu-id="92d08-103">Configurare l'elenco contatti smart nei client Skype for Business</span><span class="sxs-lookup"><span data-stu-id="92d08-103">Configure Smart contacts list in Skype for Business clients</span></span>

<span data-ttu-id="92d08-104">**Riepilogo:** Scopri come attivare la funzionalità Elenco contatti smart nel client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="92d08-104">**Summary:** Learn how to turn on the Smart contacts list feature in the Skype for Business client.</span></span>

<span data-ttu-id="92d08-105">La funzionalità Elenco contatti smart consente la popolamento automatico degli elenchi di contatti per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="92d08-105">The Smart contacts list feature allows automatic population of contact lists for your end users.</span></span> <span data-ttu-id="92d08-106">Al primo utilizzo di Skype for Business, gli utenti visualizzano automaticamente il manager e altre persone nel team.</span><span class="sxs-lookup"><span data-stu-id="92d08-106">Upon first using Skype for Business, your users will automatically see their manager and other people on their team.</span></span> <span data-ttu-id="92d08-107">Questa funzionalità è attivata per impostazione predefinita per gli utenti di Microsoft 365 e Office 365, ma è necessario abilitare esplicitamente questa funzionalità per gli utenti locali configurando l'impostazione dei criteri client.</span><span class="sxs-lookup"><span data-stu-id="92d08-107">This feature is turned on by default for Microsoft 365 and Office 365 users, but you must explicitly enable this feature for your on-premises users by configuring the client policy setting.</span></span>

<span data-ttu-id="92d08-108">Quando si configura questa funzionalità, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="92d08-108">Keep the following in mind when configuring this feature:</span></span>

- <span data-ttu-id="92d08-109">Gli utenti, fino a 13, vengono aggiunti automaticamente all'elenco Contatti smart nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="92d08-109">Users, up to 13, are automatically added to the Smart contacts list in the following order:</span></span>

  1. <span data-ttu-id="92d08-110">Manager</span><span class="sxs-lookup"><span data-stu-id="92d08-110">Manager</span></span>

  2. <span data-ttu-id="92d08-111">Indirizza in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="92d08-111">Directs in alphabetical order</span></span>

  3. <span data-ttu-id="92d08-112">Peer in ordine alfabetico</span><span class="sxs-lookup"><span data-stu-id="92d08-112">Peers in alphabetical order</span></span>

- <span data-ttu-id="92d08-113">La prima volta che un utente accede, viene creato un nuovo gruppo denominato My Group.</span><span class="sxs-lookup"><span data-stu-id="92d08-113">The first time a user logs in, a new group, named My Group, is created.</span></span> <span data-ttu-id="92d08-114">Il gruppo viene popolato automaticamente con le persone nella relazione di gruppo AD dell'utente in base all'alias utente popolato nel campo Manager.</span><span class="sxs-lookup"><span data-stu-id="92d08-114">The group is automatically populated with people in the user's AD group relationship based on the user alias populated in the Manager field.</span></span> <span data-ttu-id="92d08-115">Tieni presente che le modifiche apportate all'appartenenza al gruppo ad Active Directory non causano aggiornamenti a My Group dopo che è stato inizialmente popolato.</span><span class="sxs-lookup"><span data-stu-id="92d08-115">Note that changes to the AD group membership do not cause updates to My Group after it is initially populated.</span></span> <span data-ttu-id="92d08-116">Se un utente elimina un contatto o un gruppo, né il contatto né il gruppo vengono ri-creati.</span><span class="sxs-lookup"><span data-stu-id="92d08-116">If a user deletes a contact or the group, neither the contact nor the group are re-created.</span></span> 

- <span data-ttu-id="92d08-117">Se il tagging automatico è attivato, i contatti nell'elenco verranno contrassegnati per le modifiche alla presenza.</span><span class="sxs-lookup"><span data-stu-id="92d08-117">If auto tagging is turned on, contacts in the list will be tagged for presence changes.</span></span> <span data-ttu-id="92d08-118">Il tagging automatico è attivato per impostazione predefinita, ma puoi scegliere di disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="92d08-118">Auto tagging is turned on by default, but you can choose to turn it off.</span></span> 

- <span data-ttu-id="92d08-119">Tutti i nuovi utenti del gruppo verranno informati che sono stati aggiunti all'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="92d08-119">All new users in the group will be informed that they have been added to the contacts list.</span></span> <span data-ttu-id="92d08-120">Gli utenti possono aggiungere manualmente nuovi membri al proprio gruppo personale o ad altri gruppi di loro scelta.</span><span class="sxs-lookup"><span data-stu-id="92d08-120">Users can manually add new members to their My Group or to other groups of their choosing.</span></span>

- <span data-ttu-id="92d08-121">Questa funzionalità è valida solo per gli utenti che a tale scopo esere connessi per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="92d08-121">This feature works only for users who are signing in for the first time.</span></span> <span data-ttu-id="92d08-122">Se un utente ha eseguito in precedenza l'accesso da qualsiasi dispositivo, ad esempio qualsiasi dispositivo mobile o Mac, la funzionalità non è abilitata per tale utente.</span><span class="sxs-lookup"><span data-stu-id="92d08-122">If a user has previously signed in from any device--including, for example, any mobile device or a Mac--the feature is not enabled for that user.</span></span>

## <a name="configure-smart-contacts-list"></a><span data-ttu-id="92d08-123">Configurare l'elenco contatti intelligente</span><span class="sxs-lookup"><span data-stu-id="92d08-123">Configure Smart contacts list</span></span>

<span data-ttu-id="92d08-124">Per abilitare la funzionalità Elenco contatti smart per gli utenti, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="92d08-124">To enable the Smart contacts list feature for your users, you will need to perform the following steps:</span></span> 

- <span data-ttu-id="92d08-125">Creare una nuova voce CsClientPolicy e aggiungerla al criterio client globale.</span><span class="sxs-lookup"><span data-stu-id="92d08-125">Create a new CsClientPolicy entry and add it to the global client policy.</span></span> 

- <span data-ttu-id="92d08-126">Verificare che la ricerca nella Rubrica sia configurata solo per la ricerca Sul Web.</span><span class="sxs-lookup"><span data-stu-id="92d08-126">Make sure that Address Book Search is configured for Web Search only.</span></span>

### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a><span data-ttu-id="92d08-127">Creare una voce di criterio per abilitare l'elenco contatti smart</span><span class="sxs-lookup"><span data-stu-id="92d08-127">Create a policy entry to enable Smart contacts list</span></span>

<span data-ttu-id="92d08-128">Per creare una voce di criterio per abilitare la funzionalità Elenco contatti smart, utilizzare il cmdlet [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) con l'opzione EnableClientAutoPopulateWithTeam come segue:</span><span class="sxs-lookup"><span data-stu-id="92d08-128">To create a policy entry to enable the Smart contacts list feature, use the [New-CsClientPolicyEntry](/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet with the EnableClientAutoPopulateWithTeam option as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

<span data-ttu-id="92d08-129">Successivamente, utilizzare il cmdlet [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) per scrivere le modifiche al criterio globale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="92d08-129">Next, use the [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet to write the changes to the global policy as follows:</span></span>

```powershell
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="92d08-130">Facoltativamente, puoi creare un criterio per disattivare il tagging automatico come segue:</span><span class="sxs-lookup"><span data-stu-id="92d08-130">You can optionally create a policy to turn off auto tagging as follows:</span></span>

```powershell
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

<span data-ttu-id="92d08-131">È inoltre necessario impostare il parametro AddressBookAvailability per il criterio corrispondente su WebSearchOnly.</span><span class="sxs-lookup"><span data-stu-id="92d08-131">You must also set the AddressBookAvailability parameter for the corresponding policy to WebSearchOnly.</span></span> <span data-ttu-id="92d08-132">Per ulteriori informazioni, vedere [Set-CsClientPolicy.](/powershell/module/skype/set-csclientpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="92d08-132">For more information, see [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span> 

### <a name="troubleshoot"></a><span data-ttu-id="92d08-133">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="92d08-133">Troubleshoot</span></span>

<span data-ttu-id="92d08-134">Se l'elenco contatti smart non funziona come previsto, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="92d08-134">If Smart contacts list is not functioning as expected, check the following:</span></span>

- <span data-ttu-id="92d08-135">Convalidare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="92d08-135">Validate the configuration.</span></span> 

- <span data-ttu-id="92d08-136">Verificare che le informazioni sull'organizzazione di Active Directory sono popolate.</span><span class="sxs-lookup"><span data-stu-id="92d08-136">Confirm that the AD organization information is populated.</span></span>

- <span data-ttu-id="92d08-137">Raccogliere i log del client Skype for Business su un nuovo utente per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="92d08-137">Collect Skype for Business client logs on a new user for further analysis.</span></span>

- <span data-ttu-id="92d08-138">Verificare che nell'interfaccia utente del client Skype for Business non sia visualizzato un messaggio che indica che non è in grado di connettersi alla Rubrica.</span><span class="sxs-lookup"><span data-stu-id="92d08-138">Confirm that the Skype for Business client UI is not displaying a message that it cannot connect to the Address Book.</span></span> <span data-ttu-id="92d08-139">Per verificare la connettività della Rubrica, eseguire una ricerca per un utente nella barra di ricerca del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="92d08-139">To confirm Address Book connectivity, perform a search for a user in the Skype for Business client search bar.</span></span>

- <span data-ttu-id="92d08-140">I problemi di replica di Servizi di dominio Active Directory potrebbero causare i contatti irrisolti quando un utente accede per la prima volta a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="92d08-140">AD DS replication issues could cause contacts to be unresolved when a user first signs in to Skype for Business.</span></span>