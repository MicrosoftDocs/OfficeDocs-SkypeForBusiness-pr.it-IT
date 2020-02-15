---
title: 'Lync Server 2013: pianificazione del controllo di accesso basato sui ruoli'
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
ms.openlocfilehash: fb7a359620c7e93565c0d4ef49c813ff0966989c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="5b53e-102">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b53e-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b53e-103">_**Ultimo argomento modificato:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="5b53e-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="5b53e-104">Per consentire di delegare le attività amministrative mantenendo gli standard elevati per la sicurezza, Lync Server 2013 offre il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="5b53e-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="5b53e-105">Grazie a questa funzionalità, il privilegio amministrativo viene concesso assegnando gli utenti a ruoli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="5b53e-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="5b53e-106">Lync Server 2013 include un set completo di ruoli amministrativi incorporati e consente inoltre di creare nuovi ruoli e di specificare un elenco personalizzato di cmdlet per ogni nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="5b53e-107">Rende inoltre possibile l'aggiunta di script di cmdlet alle attività consentite sia dei ruoli RBAC predefiniti che di quelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5b53e-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="5b53e-108">Migliore sicurezza dei server e centralizzazione</span><span class="sxs-lookup"><span data-stu-id="5b53e-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="5b53e-109">Con RBAC, l'accesso e l'autorizzazione si basano proprio sul ruolo Lync Server di un utente.</span><span class="sxs-lookup"><span data-stu-id="5b53e-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="5b53e-110">In questo modo si dispone di un più ampio margine per applicare il metodo di sicurezza basato sul principio dei privilegi minimi, che concede agli amministratori e agli utenti solo i diritti necessari per le attività che devono svolgere.</span><span class="sxs-lookup"><span data-stu-id="5b53e-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5b53e-111">Le restrizioni RBAC funzionano solo per gli amministratori che operano in remoto, utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5b53e-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="5b53e-112">Un utente che si trova in un server su cui è in esecuzione Lync Server non è limitato da RBAC.</span><span class="sxs-lookup"><span data-stu-id="5b53e-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="5b53e-113">Pertanto, la sicurezza fisica del server Lync è importante per preservare le restrizioni RBAC.</span><span class="sxs-lookup"><span data-stu-id="5b53e-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="5b53e-114">Ruoli e ambito</span><span class="sxs-lookup"><span data-stu-id="5b53e-114">Roles and Scope</span></span>

<span data-ttu-id="5b53e-p104">Nel controllo di accesso basato sui ruoli un *ruolo* è abilitato all'uso di un elenco di cmdlet, progettati in modo da essere utilizzati da un determinato tipo di amministratore o tecnico. Un *ambito* è un insieme di oggetti sui cui possono operare i cmdlet definiti in un ruolo. Gli oggetti su cui ha effetto l'ambito possono essere account utente (raggruppati per unità organizzativa) o server (raggruppati per sito).</span><span class="sxs-lookup"><span data-stu-id="5b53e-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="5b53e-118">Nella tabella seguente sono elencati i ruoli predefiniti in Lync Server e viene fornita una panoramica generale dei tipi di attività che possono essere eseguite.</span><span class="sxs-lookup"><span data-stu-id="5b53e-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="5b53e-119">La quarta colonna Visualizza il ruolo di Microsoft Exchange Server analogo per ogni ruolo di Lync Server, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="5b53e-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="5b53e-120">Ruoli amministrativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="5b53e-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b53e-121">Ruolo</span><span class="sxs-lookup"><span data-stu-id="5b53e-121">Role</span></span></th>
<th><span data-ttu-id="5b53e-122">Attività consentite</span><span class="sxs-lookup"><span data-stu-id="5b53e-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="5b53e-123">Gruppo Active Directory sottostante</span><span class="sxs-lookup"><span data-stu-id="5b53e-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="5b53e-124">Equivalente di Exchange</span><span class="sxs-lookup"><span data-stu-id="5b53e-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b53e-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-p106">Può eseguire tutte le attività amministrative e modificare tutte le impostazioni, tra cui la creazione di ruoli e l'assegnazione di utenti ai ruoli. Può espandere una distribuzione aggiungendo nuovi siti, pool e servizi.</span><span class="sxs-lookup"><span data-stu-id="5b53e-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-129">Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5b53e-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b53e-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-131">Consente di abilitare e disabilitare gli utenti per Lync Server, spostare gli utenti e assegnare criteri esistenti agli utenti.</span><span class="sxs-lookup"><span data-stu-id="5b53e-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="5b53e-132">Non può modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="5b53e-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-134">Mail Recipients</span><span class="sxs-lookup"><span data-stu-id="5b53e-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b53e-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-136">Può creare, configurare e gestire le impostazioni e i criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="5b53e-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-138">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5b53e-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b53e-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-p108">Può gestire e monitorare server e servizi, nonché risolvere i relativi errori. Può impedire nuove connessioni ai server, arrestare e avviare servizi e applicare aggiornamenti software. Non può apportare modifiche con impatto sulla configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="5b53e-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-144">Server Management</span><span class="sxs-lookup"><span data-stu-id="5b53e-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b53e-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-146">Può visualizzare la distribuzione, incluse le informazioni su utenti e server, in modo da monitorare l'integrità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5b53e-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-148">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="5b53e-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b53e-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="5b53e-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="5b53e-p109">Può visualizzare la distribuzione, tra cui le proprietà e i criteri utente, e può eseguire specifiche attività di risoluzione dei problemi. Non può modificare le proprietà o i criteri utente, la configurazione dei server o i servizi.</span><span class="sxs-lookup"><span data-stu-id="5b53e-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="5b53e-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="5b53e-154">HelpDesk</span><span class="sxs-lookup"><span data-stu-id="5b53e-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b53e-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-156">Può modificare la configurazione e i criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="5b53e-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-158">Gestione conservazione, Conservazione legale</span><span class="sxs-lookup"><span data-stu-id="5b53e-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b53e-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-160">Può gestire la configurazione dell'applicazione Response Group in un sito.</span><span class="sxs-lookup"><span data-stu-id="5b53e-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-162">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5b53e-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b53e-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-p110">Livello minimo di diritti per la gestione di Enhanced 9-1-1 (E9-1-1), incluse la creazione di posizioni E9-1-1 e di identificatori di rete e l'associazione tra questi elementi. Questo ruolo viene sempre assegnato con un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="5b53e-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-167">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5b53e-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b53e-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="5b53e-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="5b53e-169">Può gestire Response Group specifici.</span><span class="sxs-lookup"><span data-stu-id="5b53e-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="5b53e-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="5b53e-171">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5b53e-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b53e-172">Ruolo CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-173">Può gestire la funzionalità di chat persistente e specifiche chat Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="5b53e-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="5b53e-174">Ruolo CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b53e-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b53e-175">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5b53e-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5b53e-176">Tutti i ruoli predefiniti spediti in Lync Server hanno un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="5b53e-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="5b53e-177">Per applicare il principio dei privilegi minimi, è consigliabile non assegnare utenti a ruoli con ambito globale se amministreranno solo un insieme limitato di server o utenti.</span><span class="sxs-lookup"><span data-stu-id="5b53e-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="5b53e-178">A tale scopo, è possibile creare ruoli basati su ruoli esistenti, ma con un ambito molto più limitato.</span><span class="sxs-lookup"><span data-stu-id="5b53e-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="5b53e-179">Creazione di un ruolo con ambito</span><span class="sxs-lookup"><span data-stu-id="5b53e-179">Creating a Scoped Role</span></span>

<span data-ttu-id="5b53e-180">Quando si crea un ruolo con ambito limitato, ovvero un ruolo con ambito, si specifica l'ambito insieme al ruolo esistente sui cui si basa e al gruppo Active Directory a cui assegnare il ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="5b53e-181">Il gruppo Active Directory specificato deve essere già creato.</span><span class="sxs-lookup"><span data-stu-id="5b53e-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="5b53e-182">Il cmdlet seguente è un esempio di creazione di un ruolo che dispone dei privilegi di uno dei ruoli amministrativi, ma con ambito limitato.</span><span class="sxs-lookup"><span data-stu-id="5b53e-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="5b53e-183">Viene creato un nuovo ruolo denominato `Site01 Server Administrators`.</span><span class="sxs-lookup"><span data-stu-id="5b53e-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="5b53e-184">Il nuovo ruolo ha le capacità del ruolo CsServerAdministrator predefinito, ma solo per i server del sito Site01.</span><span class="sxs-lookup"><span data-stu-id="5b53e-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="5b53e-185">Per il funzionamento di questo cmdlet, è necessario che il sito Site01 sia già stato definito e che sia `Site01 Server Administrators` già presente un gruppo di sicurezza universale denominato.</span><span class="sxs-lookup"><span data-stu-id="5b53e-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="5b53e-186">Dopo l'esecuzione di questo cmdlet, tutti gli utenti membri del `Site01 Server Administrators` gruppo disporranno dei privilegi di amministratore del server per i server di Site01.</span><span class="sxs-lookup"><span data-stu-id="5b53e-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="5b53e-187">Inoltre, tutti gli utenti che successivamente sono stati aggiunti a questo gruppo di protezione universale ottengono anche i privilegi di questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="5b53e-188">Si noti che sia il ruolo stesso che il gruppo di sicurezza universale a cui viene assegnato sono `Site01 Server Administrators`chiamati.</span><span class="sxs-lookup"><span data-stu-id="5b53e-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="5b53e-189">Nell'esempio seguente si applicano limiti all'ambito utente anziché all'ambito server.</span><span class="sxs-lookup"><span data-stu-id="5b53e-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="5b53e-190">Consente di creare `Sales Users Administrator` un ruolo per amministrare gli account utente nell'unità organizzativa Sales.</span><span class="sxs-lookup"><span data-stu-id="5b53e-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="5b53e-191">Per il funzionamento del cmdlet, è necessario che il gruppo di sicurezza universale di SalesUsersAdministrator sia già stato creato.</span><span class="sxs-lookup"><span data-stu-id="5b53e-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="5b53e-192">Creazione di un nuovo ruolo</span><span class="sxs-lookup"><span data-stu-id="5b53e-192">Creating a New Role</span></span>

<span data-ttu-id="5b53e-p115">Per creare un ruolo che disponga di accesso a un insieme di cmdlet non inclusi in uno dei ruoli predefiniti oppure a un insieme di script o moduli, usare di nuovo uno dei ruoli predefiniti come modello. Si noti che gli script e i moduli che i ruoli sono in grado di eseguire devono essere memorizzati nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b53e-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="5b53e-195">Il percorso del modulo di Lync, che per impostazione predefinita\\è C\\: Program\\files Common Files Microsoft\\Lync\\Server 2013 Modules Lync</span><span class="sxs-lookup"><span data-stu-id="5b53e-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="5b53e-196">Il percorso dello script utente, che per impostazione predefinita è\\C:\\Program Files\\Common Files Microsoft Lync\\Server 2013 AdminScripts</span><span class="sxs-lookup"><span data-stu-id="5b53e-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="5b53e-197">Per creare un nuovo ruolo, utilizzare il cmdlet **New-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="5b53e-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="5b53e-198">Prima di eseguire **New-CsAdminRole**, è innanzitutto necessario creare il gruppo di protezione universale sottostante che verrà associato a questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="5b53e-199">I cmdlet seguenti possono essere usati come esempio di creazione di un nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="5b53e-200">Si crea un nuovo tipo di ruolo `MyHelpDeskScriptRole`denominato.</span><span class="sxs-lookup"><span data-stu-id="5b53e-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="5b53e-201">Il nuovo ruolo ha le capacità del ruolo CsHelpDesk predefinito e può anche eseguire le funzioni in uno script denominato "testscript".</span><span class="sxs-lookup"><span data-stu-id="5b53e-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="5b53e-202">Affinché questo cmdlet funzioni, è necessario che sia stato creato per la prima volta il gruppo di protezione universale MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="5b53e-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="5b53e-203">Dopo aver eseguito il cmdlet, è possibile assegnare gli utenti direttamente a questo ruolo (in tal caso avranno ambito globale) o creare un ruolo con ambito basato su questo ruolo, come spiegato nella sezione precedente del presente documento, intitolata Creazione di un ruolo con ambito.</span><span class="sxs-lookup"><span data-stu-id="5b53e-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="5b53e-204">Assegnazione di ruoli agli utenti</span><span class="sxs-lookup"><span data-stu-id="5b53e-204">Assigning Roles to Users</span></span>

<span data-ttu-id="5b53e-205">Ogni ruolo di Lync Server è associato a un gruppo di protezione universale di Active Directory sottostante.</span><span class="sxs-lookup"><span data-stu-id="5b53e-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="5b53e-206">Tutti gli utenti che vengono aggiunti al gruppo sottostante acquisiscono le capacità di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="5b53e-207">Negli esempi nelle sezioni precedenti è stato creato un nuovo ruolo e assegnato un gruppo di sicurezza universale esistente al nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="5b53e-208">Per assegnare un ruolo esistente a uno o più utenti, aggiungere gli utenti desiderati al gruppo associato al ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="5b53e-209">È possibile aggiungere entrambi i singoli utenti e i gruppi di protezione universale a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="5b53e-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="5b53e-210">Ad esempio, il ruolo **CsAdministrator** viene concesso automaticamente al gruppo di protezione universale **Administrators di CS** in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5b53e-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="5b53e-211">Questo gruppo di sicurezza universale viene creato in Active Directory quando si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5b53e-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="5b53e-212">Per concedere questo privilegio a un utente o a un gruppo, è sufficiente aggiungerlo al gruppo **CS Administrators**.</span><span class="sxs-lookup"><span data-stu-id="5b53e-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="5b53e-213">È possibile assegnare a un utente più ruoli di controllo di accesso basato sui ruoli aggiungendo l'utente ai gruppi Active Directory sottostanti che corrispondono a ogni ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="5b53e-214">Si noti che quando si crea un ruolo, gli utenti che vengono aggiunti successivamente al gruppo Active Directory sottostante acquisiscono le capacità di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="5b53e-215">Modifica delle capacità di un ruolo</span><span class="sxs-lookup"><span data-stu-id="5b53e-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="5b53e-p121">È possibile modificare l'elenco di cmdlet e script che un ruolo può eseguire, nonché modificare sia i cmdlet che gli script che i ruoli personalizzati possono eseguire, ma solo gli script dei ruoli predefiniti. Ogni cmdlet digitato può aggiungere, rimuovere o sostituire cmdlet o script.</span><span class="sxs-lookup"><span data-stu-id="5b53e-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="5b53e-219">Per modificare un ruolo, usare il cmdlet **Set-CsAdminRole**.</span><span class="sxs-lookup"><span data-stu-id="5b53e-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="5b53e-220">Il cmdlet seguente consente di rimuovere uno script dal ruolo.</span><span class="sxs-lookup"><span data-stu-id="5b53e-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="5b53e-221">Pianificazione del controllo di accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="5b53e-221">Planning for RBAC</span></span>

<span data-ttu-id="5b53e-222">Per ogni persona a cui deve essere assegnato qualsiasi tipo di diritti amministrativi per la distribuzione di Lync Server, prendere in considerazione le attività da eseguire, quindi assegnarle ai ruoli con i privilegi minimi e l'ambito necessari per il proprio lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b53e-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="5b53e-223">Se necessario, è possibile utilizzare il cmdlet **Set-CsAdminRole** per creare un nuovo ruolo con i soli cmdlet richiesti per le attività di questo utente.</span><span class="sxs-lookup"><span data-stu-id="5b53e-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="5b53e-p124">Gli utenti con ruolo CsAdministrator possono creare tutti i tipi di ruoli, inclusi quelli basati su CsAdministrator, e assegnare utenti a tali ruoli. La procedura consigliata prevede l'assegnazione del ruolo CsAdministrator a un insieme limitato di utenti trusted.</span><span class="sxs-lookup"><span data-stu-id="5b53e-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

