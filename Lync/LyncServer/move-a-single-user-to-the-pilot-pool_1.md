---
title: Trasferire un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cb89fde2a62858c3bd9a402207f4b23fd51643
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="b43e8-102">Trasferire un singolo utente nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="b43e8-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b43e8-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b43e8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b43e8-104">È possibile trasferire un utente dal pool di Office Communications Server 2007 R2 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b43e8-104">You can move a user from your Office Communications Server 2007 R2 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="b43e8-105">Nell'esempio seguente, nella colonna del pool di registrazione, \*\* \<Office Communications Server\> \*\* è il pool di Office Communications Server 2007 R2 e tutti e sei gli utenti sono connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="b43e8-105">In the example below, in the Registrar pool column, **\<Office Communications Server\>** is the Office Communications Server 2007 R2 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="b43e8-106">Usare le procedure seguenti per trasferire un utente nel pool di Lync Server 2013 tramite il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b43e8-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<span data-ttu-id="b43e8-107">![Ricerca di utenti OCS nel Pannello di controllo di Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Ricerca di utenti OCS nel Pannello di controllo di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="b43e8-107">![Search for OCS users in Lync Server Control Panel](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="b43e8-108">Per trasferire un utente tramite il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b43e8-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="b43e8-109">Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b43e8-109">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="b43e8-110">Aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b43e8-110">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b43e8-111">Fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="b43e8-111">Click **Users**.</span></span>

4.  <span data-ttu-id="b43e8-112">Nella scheda **ricerca utente** fare clic sul pulsante **Cerca** .</span><span class="sxs-lookup"><span data-stu-id="b43e8-112">From the **User Search** tab, click the **Search** button.</span></span>

5.  <span data-ttu-id="b43e8-113">Fare quindi clic su **Aggiungi filtro**.</span><span class="sxs-lookup"><span data-stu-id="b43e8-113">Next, click **Add Filter**.</span></span>

6.  <span data-ttu-id="b43e8-114">Creare un filtro in cui l' **utente di Office Communications Server** è uguale a **vero**.</span><span class="sxs-lookup"><span data-stu-id="b43e8-114">Create a filter where **Office Communications Server user** is equal to **True**.</span></span>

7.  <span data-ttu-id="b43e8-115">Fare clic su **trova** per cercare gli utenti legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b43e8-115">Click **Find** to search for legacy Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="b43e8-116">![Ricerca di utenti OCS nel Pannello di controllo di Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Ricerca di utenti OCS nel Pannello di controllo di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="b43e8-116">![Search for OCS users in Lync Server Control Panel](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Search for OCS users in Lync Server Control Panel")</span></span>  

8.  <span data-ttu-id="b43e8-117">Selezionare un utente che si vuole trasferire nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b43e8-117">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="b43e8-118">In questo esempio si sposterà l'utente Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="b43e8-118">In this example, we will move user Sara Davis.</span></span>

9.  <span data-ttu-id="b43e8-119">Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="b43e8-119">On the **Action** menu, select **Move selected users to pool**.</span></span>

10. <span data-ttu-id="b43e8-120">Nell'elenco a discesa selezionare il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b43e8-120">From the drop-down list, select the Lync Server 2013 pool.</span></span>

11. <span data-ttu-id="b43e8-121">Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="b43e8-121">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="b43e8-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b43e8-122">Click **OK**.</span></span>
    
    <span data-ttu-id="b43e8-123">![Impostazione del pool di destinazione nella finestra di dialogo Sposta utenti](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Impostazione del pool di destinazione nella finestra di dialogo Sposta utenti")</span><span class="sxs-lookup"><span data-stu-id="b43e8-123">![Setting the Destination pool in Move Users dialog](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Setting the Destination pool in Move Users dialog")</span></span>  

12. <span data-ttu-id="b43e8-124">Verificare che la colonna del **pool di registrar** per l'utente contenga ora il pool di Lync Server 2013, che indica che l'utente è stato spostato correttamente</span><span class="sxs-lookup"><span data-stu-id="b43e8-124">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="b43e8-125">Per trasferire un utente tramite Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="b43e8-125">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="b43e8-126">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b43e8-126">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b43e8-127">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b43e8-127">At the command line, type the following:</span></span>
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="b43e8-128">Nella riga di comando, quindi, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b43e8-128">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="b43e8-129">L'identità **RegistrarPool** punta ora sul pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b43e8-129">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="b43e8-130">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="b43e8-130">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="b43e8-131">![Output del cmdlet Get-CsUser con filtro Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output del cmdlet Get-CsUser con filtro Identity")</span><span class="sxs-lookup"><span data-stu-id="b43e8-131">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b43e8-132">Per informazioni dettagliate sul cmdlet <STRONG>Get-CsUser</STRONG> , eseguire: <STRONG>Get-Help Get-CsUser-detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="b43e8-132">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

