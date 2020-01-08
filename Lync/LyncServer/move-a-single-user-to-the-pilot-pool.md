---
title: Trasferire un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9ee58a49afaa9c1e57689b6a3a87fac1a6a4502
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="03021-102">Trasferire un singolo utente nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="03021-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03021-103">_**Argomento Ultima modifica:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="03021-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="03021-104">È possibile trasferire un utente dal pool di Lync Server 2010 al pool di piloti di Lync Server 2013 usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="03021-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="03021-105">Nell'esempio seguente, nella colonna del pool di registrazione, **pool01.contoso.NET** è il pool di Lync Server 2010 e tutti e sei questi utenti sono connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="03021-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="03021-106">Usare le procedure seguenti per trasferire un utente nel pool di Lync Server 2013 tramite il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="03021-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="03021-107">Per trasferire un utente tramite il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03021-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="03021-108">**Elenco di utenti nel pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="03021-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="03021-109">![Pannello di controllo di Lync Server,](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Pannello di controllo") della finestra di dialogo spostati utente</span><span class="sxs-lookup"><span data-stu-id="03021-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="03021-110">Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="03021-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="03021-111">Aprire il **Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="03021-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="03021-112">Fare clic su **utenti**, fare clic su Cerca e quindi su **trova**.</span><span class="sxs-lookup"><span data-stu-id="03021-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="03021-113">Selezionare un utente che si vuole trasferire nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03021-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="03021-114">In questo esempio si sposterà l'utente Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="03021-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="03021-115">Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="03021-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="03021-116">Nell'elenco a discesa selezionare il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03021-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="03021-117">Fare clic su **azione** e quindi su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="03021-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="03021-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="03021-118">Click **OK**.</span></span>
    
    <span data-ttu-id="03021-119">![Trasferire utenti, finestra di dialogo pool di registrar di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ", finestra di dialogo pool Registrar di destinazione")</span><span class="sxs-lookup"><span data-stu-id="03021-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="03021-120">Verificare che la colonna del **pool di registrar** per l'utente contenga ora il pool di Lync Server 2013, che indica che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="03021-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="03021-121">Per trasferire un utente tramite Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="03021-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="03021-122">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="03021-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="03021-123">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="03021-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="03021-124">Nella riga di comando, quindi, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="03021-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="03021-125">L'identità **RegistrarPool** punta ora sul pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03021-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="03021-126">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="03021-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="03021-127">![Output del cmdlet Get-CsUser con]l'output del filtro di identità(images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "dal cmdlet Get-CsUser con il filtro delle identità")</span><span class="sxs-lookup"><span data-stu-id="03021-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03021-128">Per informazioni dettagliate sul cmdlet <STRONG>Get-CsUser</STRONG> , eseguire: <STRONG>Get-Help Get-CsUser-detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="03021-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

