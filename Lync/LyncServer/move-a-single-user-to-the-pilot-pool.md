---
title: Spostare un singolo utente nel pool pilota
description: Spostare un singolo utente nel pool pilota.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f7396ed2d92c7015f01ff6cd6e90fd3998219d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574732"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="cfe3c-103">Spostare un singolo utente nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="cfe3c-103">Move a single user to the pilot pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfe3c-104">_**Ultimo argomento modificato:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="cfe3c-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="cfe3c-105">È possibile spostare un utente dal pool Lync Server 2010 al pool pilota di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-105">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="cfe3c-106">Nell'esempio riportato di seguito, nella colonna pool di registrazione, **pool01.contoso.NET** è il pool Lync Server 2010 e tutti e sei gli utenti sono connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-106">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="cfe3c-107">Utilizzare le procedure seguenti per spostare un utente nel pool di Lync Server 2013 utilizzando il pannello di controllo di Lync Server 2013 e Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-107">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="cfe3c-108">Per spostare un utente utilizzando il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfe3c-108">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="cfe3c-109">**Elenco di utenti nel Pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="cfe3c-109">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="cfe3c-110">![Pannello di controllo di Lync Server, finestra di dialogo Sposta utente](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Pannello di controllo di Lync Server, finestra di dialogo Sposta utente")</span><span class="sxs-lookup"><span data-stu-id="cfe3c-110">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="cfe3c-111">Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-111">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="cfe3c-112">Aprire il **Pannello di controllo di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-112">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="cfe3c-113">Fare clic su **Utenti**, su Cerca e quindi su **Trova**.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-113">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="cfe3c-114">Selezionare un utente che si desidera spostare nel pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-114">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="cfe3c-115">In questo esempio, sposteremo l'utente Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-115">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="cfe3c-116">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-116">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="cfe3c-117">Nell'elenco a discesa selezionare il pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-117">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="cfe3c-118">Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-118">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="cfe3c-119">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-119">Click **OK**.</span></span>
    
    <span data-ttu-id="cfe3c-120">![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Finestra di dialogo Sposta utenti, pool di registrazione di destinazione")</span><span class="sxs-lookup"><span data-stu-id="cfe3c-120">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="cfe3c-121">Verificare che la colonna **pool di registrazione** per l'utente contenga ora il pool Lync Server 2013, che indica che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-121">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="cfe3c-122">Per spostare un utente utilizzando Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="cfe3c-122">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="cfe3c-123">Aprire Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-123">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="cfe3c-124">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cfe3c-124">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="cfe3c-125">Nella riga di comando, digitare quindi quanto segue:</span><span class="sxs-lookup"><span data-stu-id="cfe3c-125">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="cfe3c-126">L'identità di **RegistrarPool** punta ora al pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-126">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="cfe3c-127">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cfe3c-127">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="cfe3c-128">![Output da Get-CsUser cmdlet con filtro identità](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output da Get-CsUser cmdlet con filtro identità")</span><span class="sxs-lookup"><span data-stu-id="cfe3c-128">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cfe3c-129">Per avere informazioni dettagliate sul cmdlet <STRONG>Get-CsUser</STRONG>, eseguire: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span><span class="sxs-lookup"><span data-stu-id="cfe3c-129">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

