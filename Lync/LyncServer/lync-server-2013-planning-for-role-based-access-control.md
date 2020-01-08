---
title: 'Lync Server 2013: Pianificazione del controllo di accesso basato sui ruoli'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="c8414-102">Pianificazione del controllo di accesso basato sui ruoli in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8414-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8414-103">_**Argomento Ultima modifica:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="c8414-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="c8414-104">Per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza, Lync Server 2013 offre il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="c8414-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="c8414-105">Con RBAC, il privilegio amministrativo viene concesso assegnando agli utenti ruoli amministrativi.</span><span class="sxs-lookup"><span data-stu-id="c8414-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="c8414-106">Lync Server 2013 include un set completo di ruoli amministrativi predefiniti e consente inoltre di creare nuovi ruoli e specificare un elenco personalizzato di cmdlet per ogni nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="c8414-107">È inoltre possibile aggiungere script di cmdlet alle attività consentite sia dei ruoli predefiniti che di quelli RBAC.</span><span class="sxs-lookup"><span data-stu-id="c8414-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="c8414-108">Migliorare la sicurezza e la centralizzazione del server</span><span class="sxs-lookup"><span data-stu-id="c8414-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="c8414-109">Con RBAC, Access e Authorization si basano proprio sul ruolo del server Lync dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c8414-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="c8414-110">In questo modo, è possibile usare la procedura di sicurezza "privilegi minimi", concedendo solo agli amministratori e agli utenti i diritti necessari per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c8414-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8414-111">Le restrizioni RBAC funzionano solo per gli amministratori che lavorano in remoto, usando il pannello di controllo di Lync Server o Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8414-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="c8414-112">Un utente che si siede in un server su cui è in uso Lync Server non è limitato da RBAC.</span><span class="sxs-lookup"><span data-stu-id="c8414-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="c8414-113">Di conseguenza, la sicurezza fisica del server Lync è importante per preservare le restrizioni RBAC.</span><span class="sxs-lookup"><span data-stu-id="c8414-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="c8414-114">Ruoli e ambito</span><span class="sxs-lookup"><span data-stu-id="c8414-114">Roles and Scope</span></span>

<span data-ttu-id="c8414-115">In RBAC viene abilitato un *ruolo* per l'uso di un elenco di cmdlet, progettato per essere utile per un determinato tipo di amministratore o tecnico.</span><span class="sxs-lookup"><span data-stu-id="c8414-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="c8414-116">Un *ambito* è il set di oggetti su cui possono operare i cmdlet definiti in un ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="c8414-117">Gli oggetti a cui viene applicato l'ambito possono essere account utente (raggruppati per unità organizzativa) o server (raggruppati per sito).</span><span class="sxs-lookup"><span data-stu-id="c8414-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="c8414-118">La tabella seguente elenca i ruoli predefiniti in Lync Server e offre una panoramica generale dei tipi di attività che ognuno può eseguire.</span><span class="sxs-lookup"><span data-stu-id="c8414-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="c8414-119">La quarta colonna Mostra il ruolo di Microsoft Exchange Server simile per ogni ruolo di Lync Server, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="c8414-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="c8414-120">Ruoli amministrativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="c8414-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8414-121">Ruolo</span><span class="sxs-lookup"><span data-stu-id="c8414-121">Role</span></span></th>
<th><span data-ttu-id="c8414-122">Attività consentite</span><span class="sxs-lookup"><span data-stu-id="c8414-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="c8414-123">Gruppo Active Directory sottostante</span><span class="sxs-lookup"><span data-stu-id="c8414-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="c8414-124">Equivalente di Exchange</span><span class="sxs-lookup"><span data-stu-id="c8414-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8414-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-126">Può eseguire tutte le attività amministrative e modificare tutte le impostazioni, tra cui la creazione di ruoli e l'assegnazione di utenti ai ruoli.</span><span class="sxs-lookup"><span data-stu-id="c8414-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="c8414-127">Può espandere una distribuzione aggiungendo nuovi siti, pool e servizi.</span><span class="sxs-lookup"><span data-stu-id="c8414-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="c8414-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-129">Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c8414-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8414-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-131">Può abilitare e disabilitare gli utenti per Lync Server, trasferire gli utenti e assegnare i criteri esistenti agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c8414-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="c8414-132">Non è possibile modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="c8414-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="c8414-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-134">Destinatari della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c8414-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8414-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-136">Può creare, configurare e gestire le impostazioni e i criteri relativi alla voce.</span><span class="sxs-lookup"><span data-stu-id="c8414-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="c8414-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-138">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c8414-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8414-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-140">Può gestire, monitorare e risolvere i problemi di server e servizi.</span><span class="sxs-lookup"><span data-stu-id="c8414-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="c8414-141">Può impedire le nuove connessioni ai server, arrestare e avviare i servizi e applicare gli aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="c8414-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="c8414-142">Non è possibile apportare modifiche con l'impatto della configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="c8414-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="c8414-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-144">Gestione server</span><span class="sxs-lookup"><span data-stu-id="c8414-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8414-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-146">Può visualizzare la distribuzione, incluse le informazioni sull'utente e sul server, per monitorare l'integrità della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8414-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="c8414-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-148">Gestione dell'organizzazione di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c8414-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8414-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="c8414-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="c8414-150">Può visualizzare la distribuzione, incluse le proprietà e i criteri dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c8414-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="c8414-151">Può eseguire attività specifiche per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="c8414-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="c8414-152">Non è possibile modificare le proprietà o i criteri degli utenti, la configurazione del server o i servizi.</span><span class="sxs-lookup"><span data-stu-id="c8414-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="c8414-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="c8414-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="c8414-154">Help desk</span><span class="sxs-lookup"><span data-stu-id="c8414-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8414-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-156">Può modificare la configurazione e i criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c8414-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="c8414-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-158">Gestione della conservazione, blocco legale</span><span class="sxs-lookup"><span data-stu-id="c8414-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8414-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-160">Può gestire la configurazione dell'applicazione Response Group all'interno di un sito.</span><span class="sxs-lookup"><span data-stu-id="c8414-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="c8414-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-162">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c8414-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8414-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-164">Livello di diritti più basso per la gestione avanzata di 9-1-1 (E9-1-1), tra cui la creazione di percorsi E9-1-1 e gli identificatori di rete e l'associazione tra loro.</span><span class="sxs-lookup"><span data-stu-id="c8414-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="c8414-165">Questo ruolo viene sempre assegnato con un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="c8414-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="c8414-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-167">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c8414-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8414-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="c8414-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="c8414-169">Può gestire gruppi di risposta specifici.</span><span class="sxs-lookup"><span data-stu-id="c8414-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="c8414-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="c8414-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="c8414-171">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c8414-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8414-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-173">Può gestire la funzionalità chat persistente e le chat room persistenti specifiche.</span><span class="sxs-lookup"><span data-stu-id="c8414-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="c8414-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="c8414-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c8414-175">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c8414-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c8414-176">Tutti i ruoli predefiniti spediti in Lync Server hanno un ambito globale.</span><span class="sxs-lookup"><span data-stu-id="c8414-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="c8414-177">Per seguire le procedure per i privilegi minimi, non è consigliabile assegnare utenti ai ruoli con ambito globale se si vuole amministrare solo un set limitato di server o utenti.</span><span class="sxs-lookup"><span data-stu-id="c8414-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="c8414-178">A questo scopo, puoi creare ruoli basati su un ruolo esistente, ma con un ambito più limitato.</span><span class="sxs-lookup"><span data-stu-id="c8414-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="c8414-179">Creazione di un ruolo con ambito</span><span class="sxs-lookup"><span data-stu-id="c8414-179">Creating a Scoped Role</span></span>

<span data-ttu-id="c8414-180">Quando si crea un ruolo con un ambito limitato (un ruolo con ambito), si specifica l'ambito, insieme al ruolo esistente su cui è basato e al gruppo Active Directory a cui assegnare il ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="c8414-181">Il gruppo di Active Directory specificato deve essere già creato.</span><span class="sxs-lookup"><span data-stu-id="c8414-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="c8414-182">Il cmdlet seguente è un esempio di creazione di un ruolo che ha i privilegi di uno dei ruoli amministrativi predefiniti, ma con un ambito limitato.</span><span class="sxs-lookup"><span data-stu-id="c8414-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="c8414-183">Viene creato un nuovo ruolo denominato `Site01 Server Administrators`.</span><span class="sxs-lookup"><span data-stu-id="c8414-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="c8414-184">Il ruolo ha le capacità del ruolo di CsServerAdministrator predefinito, ma solo per i server presenti nel sito di Site01.</span><span class="sxs-lookup"><span data-stu-id="c8414-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="c8414-185">Affinché questo cmdlet funzioni, il sito di Site01 deve essere già definito e un gruppo di sicurezza universale denominato `Site01 Server Administrators` deve esistere già.</span><span class="sxs-lookup"><span data-stu-id="c8414-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="c8414-186">Dopo l'esecuzione di questo cmdlet, tutti gli utenti membri del `Site01 Server Administrators` gruppo avranno i privilegi di amministratore del server per i server in Site01.</span><span class="sxs-lookup"><span data-stu-id="c8414-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="c8414-187">Inoltre, gli eventuali utenti aggiunti in seguito a questo gruppo di sicurezza universale acquisiscono anche i privilegi di questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="c8414-188">Tieni presente che viene chiamato `Site01 Server Administrators`sia il ruolo stesso che il gruppo di sicurezza universale a cui viene assegnato.</span><span class="sxs-lookup"><span data-stu-id="c8414-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="c8414-189">L'esempio seguente limita l'ambito utente anziché l'ambito server.</span><span class="sxs-lookup"><span data-stu-id="c8414-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="c8414-190">Crea un `Sales Users Administrator` ruolo per amministrare gli account utente nell'unità organizzativa Sales.</span><span class="sxs-lookup"><span data-stu-id="c8414-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="c8414-191">Il gruppo di sicurezza universale SalesUsersAdministrator deve essere già creato per il funzionamento del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c8414-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="c8414-192">Creazione di un nuovo ruolo</span><span class="sxs-lookup"><span data-stu-id="c8414-192">Creating a New Role</span></span>

<span data-ttu-id="c8414-193">Per creare un ruolo che abbia accesso a un set di cmdlet non in uno dei ruoli predefiniti oppure a un set di script o moduli, è possibile iniziare a usare uno dei ruoli predefiniti come modello.</span><span class="sxs-lookup"><span data-stu-id="c8414-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="c8414-194">Tieni presente che gli script e i moduli che i ruoli possono eseguire devono essere archiviati nei percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8414-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="c8414-195">Percorso modulo di Lync, che è per impostazione predefinita C\\: programmi\\file comuni\\Microsoft Lync Server 2013\\modules\\Lync</span><span class="sxs-lookup"><span data-stu-id="c8414-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="c8414-196">Il percorso di script utente, che è per impostazione predefinita\\C:\\programmi file\\comuni di Microsoft Lync\\Server 2013 AdminScripts</span><span class="sxs-lookup"><span data-stu-id="c8414-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="c8414-197">Per creare un nuovo ruolo, puoi usare il cmdlet **New-CsAdminRole** .</span><span class="sxs-lookup"><span data-stu-id="c8414-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="c8414-198">Prima di eseguire **New-CsAdminRole**, è necessario prima di tutto creare il gruppo di sicurezza universale sottostante che verrà associato a questo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="c8414-199">I cmdlet seguenti fungono da esempio di creazione di un nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="c8414-200">Crea un nuovo tipo di ruolo denominato `MyHelpDeskScriptRole`.</span><span class="sxs-lookup"><span data-stu-id="c8414-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="c8414-201">Il nuovo ruolo ha le capacità del ruolo CsHelpDesk predefinito e può inoltre eseguire le funzioni in uno script denominato "TestScript".</span><span class="sxs-lookup"><span data-stu-id="c8414-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="c8414-202">Per il funzionamento di questo cmdlet, è necessario aver creato prima il gruppo di sicurezza universale MyHelpDeskScriptRole.</span><span class="sxs-lookup"><span data-stu-id="c8414-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="c8414-203">Dopo l'esecuzione di questo cmdlet, è possibile assegnare gli utenti direttamente a questo ruolo (nel qual caso hanno ambito globale) oppure creare un ruolo con ambito basato su questo ruolo, come spiegato in creare un ruolo con ambito, in precedenza in questo documento.</span><span class="sxs-lookup"><span data-stu-id="c8414-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="c8414-204">Assegnazione di ruoli agli utenti</span><span class="sxs-lookup"><span data-stu-id="c8414-204">Assigning Roles to Users</span></span>

<span data-ttu-id="c8414-205">Ogni ruolo di Lync Server è associato a un gruppo di sicurezza universale di Active Directory sottostante.</span><span class="sxs-lookup"><span data-stu-id="c8414-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="c8414-206">Gli utenti aggiunti al gruppo sottostante acquisiscono le capacità di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="c8414-207">Gli esempi nelle sezioni precedenti hanno creato un nuovo ruolo e assegnato un gruppo di sicurezza universale esistente al nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="c8414-208">Per assegnare un ruolo esistente a uno o più utenti, aggiungere gli utenti al gruppo associato al ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="c8414-209">È possibile aggiungere entrambi i singoli utenti e i gruppi di sicurezza universale a questi gruppi.</span><span class="sxs-lookup"><span data-stu-id="c8414-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="c8414-210">Ad esempio, il ruolo **CsAdministrator** viene concesso automaticamente al gruppo **amministratori** di sicurezza universale di CS in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c8414-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="c8414-211">Questo gruppo di sicurezza universale viene creato in Active Directory quando si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8414-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="c8414-212">Per concedere a un utente o a un gruppo questo privilegio, è possibile aggiungerli semplicemente al gruppo **amministratori di CS** .</span><span class="sxs-lookup"><span data-stu-id="c8414-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="c8414-213">A un utente possono essere assegnati più ruoli RBAC per essere aggiunti ai gruppi di Active Directory sottostanti che corrispondono a ogni ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="c8414-214">Tieni presente che quando crei un ruolo, gli utenti che vengono aggiunti in seguito al gruppo Active Directory sottostante acquisiscono le capacità di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="c8414-215">Modifica delle capacità di un ruolo</span><span class="sxs-lookup"><span data-stu-id="c8414-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="c8414-216">È possibile modificare l'elenco di cmdlet e script che possono essere eseguiti da un ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="c8414-217">È possibile modificare sia i cmdlet che gli script che i ruoli personalizzati possono eseguire, ma è possibile modificare solo gli script per i ruoli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c8414-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="c8414-218">Ogni cmdlet digitato può aggiungere, rimuovere o sostituire cmdlet o script.</span><span class="sxs-lookup"><span data-stu-id="c8414-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="c8414-219">Per modificare un ruolo, usare il cmdlet **Set-CsAdminRole** .</span><span class="sxs-lookup"><span data-stu-id="c8414-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="c8414-220">Il cmdlet seguente consente di rimuovere uno script dal ruolo.</span><span class="sxs-lookup"><span data-stu-id="c8414-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="c8414-221">Pianificazione per RBAC</span><span class="sxs-lookup"><span data-stu-id="c8414-221">Planning for RBAC</span></span>

<span data-ttu-id="c8414-222">Per ogni persona a cui deve essere assegnato qualsiasi tipo di diritti amministrativi per la distribuzione di Lync Server, valutare le attività che devono eseguire, quindi assegnarle ai ruoli con i privilegi minimi e l'ambito necessari per il lavoro.</span><span class="sxs-lookup"><span data-stu-id="c8414-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="c8414-223">Se necessario, puoi usare il cmdlet **Set-CsAdminRole** per creare un nuovo ruolo con solo i cmdlet necessari per le attività di questa persona.</span><span class="sxs-lookup"><span data-stu-id="c8414-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="c8414-224">Gli utenti che hanno il ruolo CsAdministrator possono creare tutti i tipi di ruoli, inclusi i ruoli basati su CsAdministrator, e assegnarli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c8414-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="c8414-225">La procedura consigliata consiste nell'assegnare il ruolo CsAdministrator a un set molto piccolo di utenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="c8414-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

