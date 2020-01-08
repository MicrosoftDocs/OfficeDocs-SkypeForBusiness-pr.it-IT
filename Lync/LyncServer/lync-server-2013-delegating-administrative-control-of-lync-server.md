---
title: 'Lync Server 2013: Delega del controllo amministrativo di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2acecec7a4b6543bb5dd22720af7a3f9aab62137
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="a4a01-102">Delega del controllo amministrativo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4a01-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4a01-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a4a01-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a4a01-104">In Lync Server 2013 le attività amministrative vengono delegate agli utenti tramite la nuova funzionalità controllo di accesso basato sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="a4a01-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="a4a01-105">Quando si installa Lync Server, viene creato un numero di ruoli RBAC.</span><span class="sxs-lookup"><span data-stu-id="a4a01-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="a4a01-106">Questi ruoli corrispondono ai gruppi di sicurezza universale in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4a01-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="a4a01-107">Ad esempio, il ruolo RBAC CsHelpDesk corrisponde al gruppo CsHelpDesk trovato nel contenitore utenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4a01-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="a4a01-108">Ogni ruolo RBAC è inoltre associato a un set di cmdlet di Windows PowerShell per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4a01-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="a4a01-109">Questi cmdlet rappresentano le attività che possono essere eseguite dagli utenti a cui è stato assegnato il ruolo RBAC specificato.</span><span class="sxs-lookup"><span data-stu-id="a4a01-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="a4a01-110">Ad esempio, al ruolo CsHelpDesk sono stati assegnati i cmdlet Lock-CsClientPin e UnlockCsClientPin.</span><span class="sxs-lookup"><span data-stu-id="a4a01-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="a4a01-111">Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk possono bloccare e sbloccare i numeri di PIN degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a4a01-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="a4a01-112">Tuttavia, al ruolo CsHelpDesk non è stato assegnato il cmdlet New-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="a4a01-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="a4a01-113">Ciò significa che gli utenti a cui è stato assegnato il ruolo CsHelpDesk non possono creare nuovi criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="a4a01-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="a4a01-114">Visualizzazione delle informazioni sui ruoli RBAC</span><span class="sxs-lookup"><span data-stu-id="a4a01-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="a4a01-115">È possibile recuperare le informazioni di base sui ruoli RBAC eseguendo il comando seguente all'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="a4a01-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="a4a01-116">Tieni presente che l'identità del ruolo RBAC (ad esempio CsVoiceAdministrator) ha un mapping diretto a un gruppo di sicurezza trovato nel contenitore utenti in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4a01-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="a4a01-117">Per visualizzare un elenco dei cmdlet assegnati a un ruolo, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a4a01-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="a4a01-118">Assegnazione di un ruolo RBAC a un utente</span><span class="sxs-lookup"><span data-stu-id="a4a01-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="a4a01-119">Per assegnare un ruolo RBAC a un utente, è necessario aggiungere l'utente al gruppo di sicurezza Active Directory appropriato.</span><span class="sxs-lookup"><span data-stu-id="a4a01-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="a4a01-120">Ad esempio, per assegnare il ruolo CsLocationAdministrator a un utente, è necessario aggiungere l'utente al gruppo CsLocationAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a4a01-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="a4a01-121">Questa operazione può essere eseguita eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a4a01-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="a4a01-122">**Per assegnare un utente a un gruppo di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="a4a01-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="a4a01-123">Utilizzando un account che disponga delle autorizzazioni per modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati utenti e computer di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4a01-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="a4a01-124">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a4a01-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="a4a01-125">In utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore **utenti** .</span><span class="sxs-lookup"><span data-stu-id="a4a01-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="a4a01-126">Fare clic con il pulsante destro del mouse sul gruppo di sicurezza **CsLocationAdministrator**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a4a01-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="a4a01-127">Nella scheda **membri** della finestra di dialogo **Proprietà** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a4a01-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="a4a01-128">Nella finestra di dialogo **Seleziona utenti, computer, contatti o gruppi** Digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo, ad esempio **Ken**, nella casella **immettere i nomi degli oggetti da selezionare** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4a01-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="a4a01-129">Nella finestra di dialogo **Proprietà** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4a01-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="a4a01-130">Per verificare che il ruolo RBAC sia stato assegnato, usare il cmdlet [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) , passando il cmdlet sAMAccountName (nome accesso Active Directory) dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a4a01-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="a4a01-131">Ad esempio, Esegui questo comando dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="a4a01-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

