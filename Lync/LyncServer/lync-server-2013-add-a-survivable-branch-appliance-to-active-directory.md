---
title: 'Lync Server 2013: aggiungere un Survivable Branch Appliance ad Active Directory'
description: 'Lync Server 2013: aggiungere un Survivable Branch Appliance ad Active Directory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd06332679be0819cf3002f344a62a7ce1d5a9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567892"
---
# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="5a4ff-103">Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a4ff-103">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a4ff-104">_**Ultimo argomento modificato:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="5a4ff-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="5a4ff-105">Se si prevede di distribuire un Survivable Branch Appliance, è necessario aggiungere il Survivable Branch Appliance ai servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-105">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="5a4ff-106">Eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-106">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5a4ff-107">Eseguire questa procedura solo se si sta distribuendo un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-107">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="5a4ff-108">Non eseguirlo se si sta distribuendo un Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-108">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="5a4ff-109">Per aggiungere un Survivable Branch Appliance a Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="5a4ff-109">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="5a4ff-110">Eseguire l'accesso a un server membro come membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-110">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="5a4ff-111">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **Utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-111">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="5a4ff-112">Scegliere **Nuovo** dal menu **Azioni** e quindi fare clic su **Computer**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-112">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="5a4ff-113">Nella finestra di dialogo **nuovo oggetto-computer** Digitare un nome per l'oggetto computer Survivable Branch Appliance (ad esempio, BranchOffice1), quindi fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-113">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="5a4ff-114">Nella finestra di dialogo **Seleziona utente o gruppo** aggiungere il gruppo RTCUniversalSBATechnicians e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-114">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5a4ff-115">Un membro del gruppo RTCUniversalSBATechnicians nel sito di succursale aggiungerà successivamente questo dispositivo al dominio.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-115">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="5a4ff-116">Fare clic su **OK** per salvare l'oggetto computer Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-116">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="5a4ff-117">Fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-117">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="5a4ff-118">In **ADSI Edit** fare clic con il pulsante destro del mouse sull'oggetto computer creato nei passaggi precedenti e quindi scegliere **Properties**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-118">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="5a4ff-119">Nell'elenco degli attributi fare clic su **servicePrincipalName** e quindi su **Edit**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-119">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="5a4ff-120">Nel campo **valore da aggiungere** digitare host/ \<SBA FQDN\> dove \<SBA FQDN\> è il nome di dominio completo (FQDN) del Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-120">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="5a4ff-121">Digitare ad esempio **HOST/BranchOffice1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-121">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="5a4ff-122">Fare clic su **OK** per salvare l'impostazione dell'attributo **servicePrincipalName** e quindi su **OK** per salvare le proprietà dell'oggetto computer.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-122">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="5a4ff-123">In **Utenti e computer di Active Directory** fare clic con il pulsante destro del mouse su **Utenti**, scegliere **Nuovo** e quindi fare clic su **Utente**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-123">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="5a4ff-124">Immettere le informazioni nella procedura guidata per creare un account utente di dominio per un Survivable Branch Appliance tecnico.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-124">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="5a4ff-125">In **Utenti e computer di Active Directory** fare clic su **Utenti**, fare clic con il pulsante destro del mouse sull'oggetto utente e quindi scegliere **Aggiungi a un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-125">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="5a4ff-126">In **Immettere i nomi degli oggetti da selezionare** digitare **RTCUniversalSBATechnicians** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-126">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="5a4ff-127">Ripetere i passaggi 12-15 per ogni tecnico del sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="5a4ff-127">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="5a4ff-128">**Passaggio successivo**: [aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="5a4ff-128">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

