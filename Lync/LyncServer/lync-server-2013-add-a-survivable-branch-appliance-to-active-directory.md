---
title: 'Lync Server 2013: Aggiungere un Survivable Branch Appliance ad Active Directory'
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="da40e-102">Aggiungere un Survivable Branch Appliance ad Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da40e-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da40e-103">_**Argomento Ultima modifica:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="da40e-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="da40e-104">Se si prevede di distribuire un Survivable Branch Appliance, è necessario aggiungere il Survivable Branch Appliance a servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="da40e-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="da40e-105">Eseguire questa procedura nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="da40e-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="da40e-106">Eseguire questa procedura solo se si sta distribuendo un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="da40e-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="da40e-107">Non eseguire questa operazione se si sta distribuendo un Survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="da40e-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="da40e-108">Per aggiungere un Survivable Branch Appliance a servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="da40e-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="da40e-109">Accedere a un server membro come membro del gruppo amministratori aziendali.</span><span class="sxs-lookup"><span data-stu-id="da40e-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="da40e-110">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="da40e-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="da40e-111">Nel menu **azioni** fare clic su **nuovo** e quindi su **computer**.</span><span class="sxs-lookup"><span data-stu-id="da40e-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="da40e-112">Nella finestra di dialogo **nuovo oggetto-computer** Digitare un nome per l'oggetto computer Survivable Branch Appliance, ad esempio BranchOffice1, e quindi fare clic su **Cambia**.</span><span class="sxs-lookup"><span data-stu-id="da40e-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="da40e-113">Nella finestra di dialogo **Seleziona utente o gruppo** aggiungere il gruppo RTCUniversalSBATechnicians e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="da40e-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da40e-114">Un membro del gruppo RTCUniversalSBATechnicians nel sito della filiale aggiungerà questo dispositivo al dominio in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="da40e-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="da40e-115">Fare clic su **OK** per salvare l'oggetto computer Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="da40e-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="da40e-116">Fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Modifica ADSI**.</span><span class="sxs-lookup"><span data-stu-id="da40e-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="da40e-117">In **Modifica ADSI**fare clic con il pulsante destro del mouse sull'oggetto computer creato nei passaggi precedenti e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="da40e-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="da40e-118">Nell'elenco attributo fare clic su **servicePrincipalName**e quindi su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="da40e-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="da40e-119">Nel campo **valore da aggiungere** \<digitare FQDN\> host/SBA in cui \<l'FQDN di\> SBA è il nome di dominio completo (FQDN) dell'appliance Survivable Branch.</span><span class="sxs-lookup"><span data-stu-id="da40e-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="da40e-120">Ad esempio, digita **host/BranchOffice1. contoso. com**.</span><span class="sxs-lookup"><span data-stu-id="da40e-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="da40e-121">Fare clic su **OK** per salvare l'impostazione dell'attributo **servicePrincipalName** e quindi fare clic su **OK** per salvare le proprietà dell'oggetto computer.</span><span class="sxs-lookup"><span data-stu-id="da40e-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="da40e-122">In **utenti e computer di Active Directory**fare clic con il pulsante destro del mouse su **utenti**, scegliere **nuovo**e quindi fare clic su **utente**.</span><span class="sxs-lookup"><span data-stu-id="da40e-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="da40e-123">Immettere le informazioni nella procedura guidata per creare un account utente di dominio per un tecnico Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="da40e-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="da40e-124">In **utenti e computer di Active Directory**fare clic su **utenti**, fare clic con il pulsante destro del mouse sull'oggetto utente e quindi scegliere **Aggiungi a un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="da40e-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="da40e-125">In **immettere i nomi degli oggetti da selezionare**digitare **RTCUniversalSBATechnicians**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="da40e-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="da40e-126">Ripetere i passaggi 12-15 per ogni tecnico del sito filiale.</span><span class="sxs-lookup"><span data-stu-id="da40e-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="da40e-127">**Passaggio successivo**: [aggiungere siti di succursale alla topologia in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="da40e-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

