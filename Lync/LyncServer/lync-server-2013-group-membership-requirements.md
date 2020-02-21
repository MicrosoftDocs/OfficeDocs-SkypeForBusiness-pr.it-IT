---
title: 'Lync Server 2013: requisiti di appartenenza ai gruppi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8726d471b1db95aa67cca58a77452d9faa43df4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="dca90-102">Requisiti di appartenenza ai gruppi per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dca90-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dca90-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="dca90-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="dca90-104">Nella tabella seguente viene riepilogato il gruppo o i gruppi a cui appartiene una persona per poter eseguire correttamente l'installazione, la gestione e la risoluzione dei problemi di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dca90-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dca90-105">File eseguibile di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dca90-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="dca90-106">Appartenenze ai gruppi richieste</span><span class="sxs-lookup"><span data-stu-id="dca90-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dca90-107"><strong>Setup. exe</strong> : eseguibile che avvia l'installazione degli strumenti di amministrazione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dca90-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="dca90-108">Membro del gruppo Administrators locale nel computer da cui viene eseguito il file.</span><span class="sxs-lookup"><span data-stu-id="dca90-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="dca90-109">Membro del gruppo Domain Users per leggere le informazioni in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dca90-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="dca90-110">Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI richiesti nel computer locale richiede privilegi che consentano la lettura e scrittura di risorse del computer locale protette, come le directory Programmi e l'hive Local Machine del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="dca90-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="dca90-111">È inoltre possibile delegare le autorizzazioni per l'installazione a utenti o gruppi a cui non si desidera concedere l'appartenenza al gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="dca90-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="dca90-112">Per informazioni dettagliate, vedere <A href="lync-server-2013-granting-setup-permissions.md">concessione di autorizzazioni di installazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dca90-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dca90-113"><strong>Deploy.exe</strong> – Chiamato da setup.exe, deploy.exe è responsabile per la distribuzione dei componenti software per i ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="dca90-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="dca90-114">Membro del gruppo Administrators locale nel computer da cui viene eseguito il file.</span><span class="sxs-lookup"><span data-stu-id="dca90-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="dca90-115">Membro del gruppo Domain Users per la lettura delle informazioni in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dca90-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="dca90-116">Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI richiesti nel computer locale richiede privilegi che consentano la lettura e scrittura di risorse del computer locale protette, come le directory Programmi e l'hive Local Machine del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="dca90-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="dca90-117">L'appartenenza al gruppo di RtcUniversalReadOnlyAdmins è necessaria per leggere l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="dca90-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="dca90-118">Se si esegue il sistema operativo Windows Vista o Windows 7, viene richiesto dal controllo dell'account utente di procedere con l'installazione.</span><span class="sxs-lookup"><span data-stu-id="dca90-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="dca90-119">Se si è connessi con un account utente standard, sarà necessario che qualcuno membro del gruppo Administrators locale fornisca le credenziali quando viene richiesto di specificare un account che dispone delle autorizzazioni per l'installazione del software.</span><span class="sxs-lookup"><span data-stu-id="dca90-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dca90-120"><strong>Bootstrapper.exe</strong> – Chiamato da setup.exe, bootstrapper.exe è responsabile della distribuzione e configurazione dei ruoli del server.</span><span class="sxs-lookup"><span data-stu-id="dca90-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="dca90-p105">Membro del gruppo Administrators locale nel computer da cui viene eseguito il file. Membro del gruppo RTCUniversalServerAdmins per l'esecuzione di Bootstrapper.exe. Membro del gruppo Utenti di dominio per la lettura di informazioni in AD DS. Questo livello di autorizzazione è necessario perché l'installazione automatica dei pacchetti MSI richiesti nel computer locale richiede privilegi che consentano la lettura e scrittura di risorse del computer locale protette, come le directory Programmi e l'hive Local Machine del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="dca90-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dca90-125"><strong>TopologyBuilder</strong> : interfaccia utente basata su procedura guidata per creare, visualizzare, modificare e convalidare le topologie di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dca90-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="dca90-126">Membro del gruppo Administrators locale nel computer da cui viene eseguito il file per visualizzare la topologia.</span><span class="sxs-lookup"><span data-stu-id="dca90-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="dca90-127">Membro del gruppo RTCUniversalServerAdmins per modificare le impostazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dca90-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="dca90-128">Membro del gruppo RTCUniversalServerAdmins e del gruppo Domain Admins oppure membro del gruppo RTCUniversalServerAdmins (solo se al gruppo sono state concesse le autorizzazioni per la delega dell'installazione) per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="dca90-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="dca90-129">Per informazioni dettagliate sulla delega delle autorizzazioni di installazione per consentire ai membri del gruppo RTCUniversalServerAdmins di pubblicare la topologia senza essere membri del gruppo Domain Admins, vedere <a href="lync-server-2013-granting-setup-permissions.md">concessione di autorizzazioni di installazione in Lync Server 2013</a> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dca90-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dca90-130"><strong>AdminUIHost</strong> -interfaccia utente grafica basata sul Web per la gestione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dca90-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="dca90-131">Membro del gruppo CsAdministrator o di un altro ruolo di controllo di accesso basato sui ruoli a cui viene assegnata la specifica attività amministrativa.</span><span class="sxs-lookup"><span data-stu-id="dca90-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="dca90-132">Il pannello di controllo di Lync Server 2013 implementa le modifiche di configurazione eseguendo i cmdlet di Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dca90-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="dca90-133">Per un elenco di ruoli predefiniti e per i quali è consentito l'esecuzione dei membri cmdlet, vedere <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="dca90-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dca90-134"><strong>PowerShell. exe con lo</strong> strumento di amministrazione della riga di comando di lync Server 2013 con cmdlet specifici per la gestione di lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dca90-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="dca90-135">Membro del gruppo CsAdministrator o di un altro ruolo di controllo di accesso basato sui ruoli a cui viene assegnato il cmdlet specifico.</span><span class="sxs-lookup"><span data-stu-id="dca90-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="dca90-136">Per un elenco di ruoli predefiniti e per i quali è consentito l'esecuzione dei membri cmdlet, vedere <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in Lync Server 2013</a> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="dca90-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="dca90-137">Oppure membro di uno o più dei gruppi seguenti, a seconda del cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dca90-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="dca90-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="dca90-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="dca90-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="dca90-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="dca90-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="dca90-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

