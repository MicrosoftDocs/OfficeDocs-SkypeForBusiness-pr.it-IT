---
title: Trasferire un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: È possibile trasferire un utente dal pool legacy al pool pilota di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell. Nell'esempio seguente, nella colonna del pool di registrazione, pool01.contoso.net è il pool legacy e tutti e sei di questi utenti sono connessi al pool. Usare le procedure seguenti per trasferire un utente nel pool di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell.
ms.openlocfilehash: 23ce56f8bcf759aeeaa9e9a9b64820958c656c6a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195003"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="22b14-105">Trasferire un singolo utente nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="22b14-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="22b14-106">È possibile trasferire un utente dal pool legacy al pool pilota di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="22b14-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="22b14-107">Nell'esempio seguente, nella colonna del **pool di registrazione** , **pool01.contoso.NET** è il pool legacy e tutti e sei di questi utenti sono connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="22b14-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="22b14-108">Usare le procedure seguenti per trasferire un utente nel pool di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="22b14-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="22b14-109">Per trasferire un utente usando il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="22b14-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="22b14-110">Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="22b14-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="22b14-111">Aprire il **Pannello di controllo di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="22b14-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="22b14-112">Fare clic su **utenti**, fare clic su **Cerca**e quindi su **trova**.</span><span class="sxs-lookup"><span data-stu-id="22b14-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="22b14-113">Selezionare un utente che si vuole trasferire nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22b14-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="22b14-114">In questo esempio si sposterà l'utente Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="22b14-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="22b14-115">Nel menu **azione** selezionare Trasferisci **utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="22b14-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="22b14-116">Nell'elenco a discesa selezionare il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22b14-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="22b14-117">Fare clic su **azione**e quindi su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="22b14-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="22b14-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="22b14-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="22b14-119">Verificare che la colonna del **pool** di registrar per l'utente contenga ora il pool di Skype for Business Server 2019, che indica che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="22b14-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="22b14-120">Per trasferire un utente usando Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="22b14-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="22b14-121">Aprire Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="22b14-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="22b14-122">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="22b14-122">At the command line, type the following:</span></span> 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="22b14-123">Nella riga di comando, quindi, digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="22b14-123">Next, at the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="22b14-124">L'identità **RegistrarPool** punta ora sul pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22b14-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="22b14-125">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="22b14-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="22b14-126">Per informazioni dettagliate sul cmdlet **Get-CsUser** , eseguire: **Get-Help Get-CsUser-** detailed</span><span class="sxs-lookup"><span data-stu-id="22b14-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

