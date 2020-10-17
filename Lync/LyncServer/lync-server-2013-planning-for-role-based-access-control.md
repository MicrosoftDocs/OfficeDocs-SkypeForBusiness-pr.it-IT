---
title: 'Lync Server 2013: pianificazione del controllo di accesso basato sui ruoli'
description: 'Lync Server 2013: pianificazione del controllo di accesso basato sui ruoli.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971b3353694a1cdd53d88452717e6a9a360c6870
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549242"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="03eb9-103">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03eb9-103">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03eb9-104">_**Ultimo argomento modificato:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="03eb9-104">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="03eb9-105">Per consentire di delegare le attività amministrative mantenendo gli standard elevati per la sicurezza, Lync Server 2013 offre il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="03eb9-105">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="03eb9-106">Grazie a questa funzionalità, il privilegio amministrativo viene concesso assegnando gli utenti a ruoli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="03eb9-106">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="03eb9-107">Lync Server 2013 include un set completo di ruoli amministrativi incorporati e consente inoltre di creare nuovi ruoli e di specificare un elenco personalizzato di cmdlet per ogni nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-107">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="03eb9-108">Rende inoltre possibile l'aggiunta di script di cmdlet alle attività consentite sia dei ruoli RBAC predefiniti che di quelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="03eb9-108">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="03eb9-109">Migliore sicurezza dei server e centralizzazione</span><span class="sxs-lookup"><span data-stu-id="03eb9-109">Better Server Security and Centralization</span></span>

<span data-ttu-id="03eb9-110">Con RBAC, l'accesso e l'autorizzazione si basano proprio sul ruolo Lync Server di un utente.</span><span class="sxs-lookup"><span data-stu-id="03eb9-110">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="03eb9-111">In questo modo si dispone di un più ampio margine per applicare il metodo di sicurezza basato sul principio dei privilegi minimi, che concede agli amministratori e agli utenti solo i diritti necessari per le attività che devono svolgere.</span><span class="sxs-lookup"><span data-stu-id="03eb9-111">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="03eb9-112">Le restrizioni RBAC funzionano solo per gli amministratori che operano in remoto, utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="03eb9-112">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="03eb9-113">Un utente che si trova in un server su cui è in esecuzione Lync Server non è limitato da RBAC.</span><span class="sxs-lookup"><span data-stu-id="03eb9-113">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="03eb9-114">Pertanto, la sicurezza fisica del server Lync è importante per preservare le restrizioni RBAC.</span><span class="sxs-lookup"><span data-stu-id="03eb9-114">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="03eb9-115">Ruoli e ambito</span><span class="sxs-lookup"><span data-stu-id="03eb9-115">Roles and Scope</span></span>

<span data-ttu-id="03eb9-p104">Nel controllo di accesso basato sui ruoli un *ruolo* è abilitato all'uso di un elenco di cmdlet, progettati in modo da essere utilizzati da un determinato tipo di amministratore o tecnico. Un *ambito* è un insieme di oggetti sui cui possono operare i cmdlet definiti in un ruolo. Gli oggetti su cui ha effetto l'ambito possono essere account utente (raggruppati per unità organizzativa) o server (raggruppati per sito).</span><span class="sxs-lookup"><span data-stu-id="03eb9-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="03eb9-119">Nella tabella seguente sono elencati i ruoli predefiniti in Lync Server e viene fornita una panoramica generale dei tipi di attività che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="03eb9-119">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="03eb9-120">La quarta colonna Visualizza il ruolo di Microsoft Exchange Server analogo per ogni ruolo di Lync Server, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="03eb9-120">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="03eb9-121">Ruoli amministrativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="03eb9-121">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03eb9-122">Ruolo</span><span class="sxs-lookup"><span data-stu-id="03eb9-122">Role</span></span></th>
<th><span data-ttu-id="03eb9-123">Attività consentite</span><span class="sxs-lookup"><span data-stu-id="03eb9-123">Tasks allowed</span></span></th>
<th><span data-ttu-id="03eb9-124">Gruppo Active Directory sottostante</span><span class="sxs-lookup"><span data-stu-id="03eb9-124">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="03eb9-125">Equivalente di Exchange</span><span class="sxs-lookup"><span data-stu-id="03eb9-125">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03eb9-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-p106">Può eseguire tutte le attività amministrative e modificare tutte le impostazioni, tra cui la creazione di ruoli e l'assegnazione di utenti ai ruoli. Può espandere una distribuzione aggiungendo nuovi siti, pool e servizi.</span><span class="sxs-lookup"><span data-stu-id="03eb9-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-129">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-129">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-130">Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="03eb9-130">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eb9-131">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-131">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-132">Consente di abilitare e disabilitare gli utenti per Lync Server, spostare gli utenti e assegnare criteri esistenti agli utenti.</span><span class="sxs-lookup"><span data-stu-id="03eb9-132">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="03eb9-133">Non può modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="03eb9-133">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-134">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-134">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-135">Mail Recipients</span><span class="sxs-lookup"><span data-stu-id="03eb9-135">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eb9-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-136">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-137">Può creare, configurare e gestire le impostazioni e i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="03eb9-137">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-138">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-138">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-139">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="03eb9-139">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eb9-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-140">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-p108">Può gestire e monitorare server e servizi, nonché risolvere i relativi errori. Può impedire nuove connessioni ai server, arrestare e avviare servizi e applicare aggiornamenti software. Non può apportare modifiche con impatto sulla configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="03eb9-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-144">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-144">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-145">Server Management</span><span class="sxs-lookup"><span data-stu-id="03eb9-145">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eb9-146">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-146">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-147">Può visualizzare la distribuzione, incluse le informazioni su utenti e server, in modo da monitorare l'integrità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="03eb9-147">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-148">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-148">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-149">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="03eb9-149">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eb9-150">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="03eb9-150">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="03eb9-p109">Può visualizzare la distribuzione, tra cui le proprietà e i criteri utente, e può eseguire specifiche attività di risoluzione dei problemi. Non può modificare le proprietà o i criteri utente, la configurazione dei server o i servizi.</span><span class="sxs-lookup"><span data-stu-id="03eb9-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-154">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="03eb9-154">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="03eb9-155">HelpDesk</span><span class="sxs-lookup"><span data-stu-id="03eb9-155">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eb9-156">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-156">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-157">Può modificare la configurazione e i criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="03eb9-157">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-158">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-158">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-159">Gestione conservazione, Conservazione legale</span><span class="sxs-lookup"><span data-stu-id="03eb9-159">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eb9-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-160">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-161">Può gestire la configurazione dell'applicazione Response Group in un sito.</span><span class="sxs-lookup"><span data-stu-id="03eb9-161">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-162">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-162">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-163">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="03eb9-163">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eb9-164">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-164">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-p110">Livello minimo di diritti per la gestione di Enhanced 9-1-1 (E9-1-1), incluse la creazione di posizioni E9-1-1 e di identificatori di rete e l'associazione tra questi elementi. Questo ruolo viene sempre assegnato con un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="03eb9-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-167">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-167">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-168">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="03eb9-168">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03eb9-169">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="03eb9-169">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="03eb9-170">Può gestire Response Group specifici.</span><span class="sxs-lookup"><span data-stu-id="03eb9-170">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-171">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="03eb9-171">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="03eb9-172">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="03eb9-172">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03eb9-173">Ruolo CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-173">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-174">Può gestire la funzionalità di chat persistente e specifiche chat Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="03eb9-174">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="03eb9-175">Ruolo CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="03eb9-175">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="03eb9-176">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="03eb9-176">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="03eb9-177">Tutti i ruoli predefiniti spediti in Lync Server hanno un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="03eb9-177">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="03eb9-178">Per applicare il principio dei privilegi minimi, è consigliabile non assegnare utenti a ruoli con ambito globale se amministreranno solo un insieme limitato di server o utenti.</span><span class="sxs-lookup"><span data-stu-id="03eb9-178">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="03eb9-179">A tale scopo, è possibile creare ruoli basati su ruoli esistenti, ma con un ambito molto più limitato.</span><span class="sxs-lookup"><span data-stu-id="03eb9-179">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="03eb9-180">Creazione di un ruolo con ambito</span><span class="sxs-lookup"><span data-stu-id="03eb9-180">Creating a Scoped Role</span></span>

<span data-ttu-id="03eb9-181">Quando si crea un ruolo con ambito limitato, ovvero un ruolo con ambito, si specifica l'ambito insieme al ruolo esistente sui cui si basa e al gruppo Active Directory a cui assegnare il ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-181">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="03eb9-182">Il gruppo Active Directory specificato deve essere già creato.</span><span class="sxs-lookup"><span data-stu-id="03eb9-182">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="03eb9-183">Il cmdlet seguente è un esempio di creazione di un ruolo che dispone dei privilegi di uno dei ruoli amministrativi, ma con ambito limitato.</span><span class="sxs-lookup"><span data-stu-id="03eb9-183">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="03eb9-184">Viene creato un nuovo ruolo denominato `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="03eb9-184">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="03eb9-185">Il nuovo ruolo ha le capacità del ruolo CsServerAdministrator predefinito, ma solo per i server del sito Site01.</span><span class="sxs-lookup"><span data-stu-id="03eb9-185">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="03eb9-186">Per il funzionamento di questo cmdlet, è necessario che il sito Site01 sia già stato definito e che sia già presente un gruppo di sicurezza universale denominato `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="03eb9-186">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="03eb9-187">Dopo l'esecuzione di questo cmdlet, tutti gli utenti membri del `Site01 Server Administrators` gruppo disporranno dei privilegi di amministratore del server per i server di Site01.</span><span class="sxs-lookup"><span data-stu-id="03eb9-187">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="03eb9-188">Inoltre, tutti gli utenti che successivamente sono stati aggiunti a questo gruppo di protezione universale ottengono anche i privilegi di questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-188">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="03eb9-189">Si noti che sia il ruolo stesso che il gruppo di sicurezza universale a cui viene assegnato sono chiamati `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="03eb9-189">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="03eb9-190">Nell'esempio seguente si applicano limiti all'ambito utente anziché all'ambito server.</span><span class="sxs-lookup"><span data-stu-id="03eb9-190">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="03eb9-191">Consente di creare un `Sales Users Administrator` ruolo per amministrare gli account utente nell'unità organizzativa Sales.</span><span class="sxs-lookup"><span data-stu-id="03eb9-191">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="03eb9-192">Per il funzionamento del cmdlet, è necessario che il gruppo di sicurezza universale di SalesUsersAdministrator sia già stato creato.</span><span class="sxs-lookup"><span data-stu-id="03eb9-192">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="03eb9-193">Creazione di un nuovo ruolo</span><span class="sxs-lookup"><span data-stu-id="03eb9-193">Creating a New Role</span></span>

<span data-ttu-id="03eb9-p115">Per creare un ruolo che disponga di accesso a un insieme di cmdlet non inclusi in uno dei ruoli predefiniti oppure a un insieme di script o moduli, usare di nuovo uno dei ruoli predefiniti come modello. Si noti che gli script e i moduli che i ruoli sono in grado di eseguire devono essere memorizzati nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="03eb9-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="03eb9-196">Il percorso del modulo di Lync, che per impostazione predefinita è C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ modules \\ Lync</span><span class="sxs-lookup"><span data-stu-id="03eb9-196">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="03eb9-197">Il percorso dello script utente, che per impostazione predefinita è C: \\ Program Files \\ Common Files \\ Microsoft Lync Server 2013 \\ AdminScripts</span><span class="sxs-lookup"><span data-stu-id="03eb9-197">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="03eb9-198">Per creare un nuovo ruolo, utilizzare il cmdlet **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="03eb9-198">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="03eb9-199">Prima di eseguire **New-CsAdminRole**, è innanzitutto necessario creare il gruppo di protezione universale sottostante che verrà associato a questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-199">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="03eb9-200">I cmdlet seguenti possono essere usati come esempio di creazione di un nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-200">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="03eb9-201">Si crea un nuovo tipo di ruolo denominato `MyHelpDeskScriptRole` .</span><span class="sxs-lookup"><span data-stu-id="03eb9-201">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="03eb9-202">Il nuovo ruolo ha le capacità del ruolo CsHelpDesk predefinito e può anche eseguire le funzioni in uno script denominato "testscript".</span><span class="sxs-lookup"><span data-stu-id="03eb9-202">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="03eb9-203">Affinché questo cmdlet funzioni, è necessario che sia stato creato per la prima volta il gruppo di protezione universale MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="03eb9-203">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="03eb9-204">Dopo aver eseguito il cmdlet, è possibile assegnare gli utenti direttamente a questo ruolo (in tal caso avranno ambito globale) o creare un ruolo con ambito basato su questo ruolo, come spiegato nella sezione precedente del presente documento, intitolata Creazione di un ruolo con ambito.</span><span class="sxs-lookup"><span data-stu-id="03eb9-204">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="03eb9-205">Assegnazione di ruoli agli utenti</span><span class="sxs-lookup"><span data-stu-id="03eb9-205">Assigning Roles to Users</span></span>

<span data-ttu-id="03eb9-206">Ogni ruolo di Lync Server è associato a un gruppo di protezione universale di Active Directory sottostante.</span><span class="sxs-lookup"><span data-stu-id="03eb9-206">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="03eb9-207">Tutti gli utenti che vengono aggiunti al gruppo sottostante acquisiscono le capacità di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-207">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="03eb9-208">Negli esempi nelle sezioni precedenti è stato creato un nuovo ruolo e assegnato un gruppo di sicurezza universale esistente al nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-208">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="03eb9-209">Per assegnare un ruolo esistente a uno o più utenti, aggiungere gli utenti desiderati al gruppo associato al ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-209">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="03eb9-210">È possibile aggiungere entrambi i singoli utenti e i gruppi di protezione universale a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="03eb9-210">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="03eb9-211">Ad esempio, il ruolo **CsAdministrator** viene concesso automaticamente al gruppo di protezione universale **Administrators di CS** in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03eb9-211">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="03eb9-212">Questo gruppo di sicurezza universale viene creato in Active Directory quando si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="03eb9-212">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="03eb9-213">Per concedere questo privilegio a un utente o a un gruppo, è sufficiente aggiungerlo al gruppo **CS Administrators**.</span><span class="sxs-lookup"><span data-stu-id="03eb9-213">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="03eb9-214">È possibile assegnare a un utente più ruoli di controllo di accesso basato sui ruoli aggiungendo l'utente ai gruppi Active Directory sottostanti che corrispondono a ogni ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-214">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="03eb9-215">Si noti che quando si crea un ruolo, gli utenti che vengono aggiunti successivamente al gruppo Active Directory sottostante acquisiscono le capacità di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-215">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="03eb9-216">Modifica delle capacità di un ruolo</span><span class="sxs-lookup"><span data-stu-id="03eb9-216">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="03eb9-p121">È possibile modificare l'elenco di cmdlet e script che un ruolo può eseguire, nonché modificare sia i cmdlet che gli script che i ruoli personalizzati possono eseguire, ma solo gli script dei ruoli predefiniti. Ogni cmdlet digitato può aggiungere, rimuovere o sostituire cmdlet o script.</span><span class="sxs-lookup"><span data-stu-id="03eb9-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="03eb9-220">Per modificare un ruolo, usare il cmdlet **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="03eb9-220">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="03eb9-221">Il cmdlet seguente consente di rimuovere uno script dal ruolo.</span><span class="sxs-lookup"><span data-stu-id="03eb9-221">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="03eb9-222">Pianificazione del controllo di accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="03eb9-222">Planning for RBAC</span></span>

<span data-ttu-id="03eb9-223">Per ogni persona a cui deve essere assegnato qualsiasi tipo di diritti amministrativi per la distribuzione di Lync Server, prendere in considerazione le attività da eseguire, quindi assegnarle ai ruoli con i privilegi minimi e l'ambito necessari per il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="03eb9-223">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="03eb9-224">Se necessario, è possibile utilizzare il cmdlet **Set-CsAdminRole** per creare un nuovo ruolo con i soli cmdlet richiesti per le attività di questo utente.</span><span class="sxs-lookup"><span data-stu-id="03eb9-224">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="03eb9-p124">Gli utenti con ruolo CsAdministrator possono creare tutti i tipi di ruoli, inclusi quelli basati su CsAdministrator, e assegnare utenti a tali ruoli. La procedura consigliata prevede l'assegnazione del ruolo CsAdministrator a un insieme limitato di utenti trusted.</span><span class="sxs-lookup"><span data-stu-id="03eb9-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

