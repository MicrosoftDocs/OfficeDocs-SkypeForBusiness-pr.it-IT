---
title: Spostare un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile spostare un utente dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell. Nell'esempio riportato di seguito, nella colonna pool di registrazione, pool01.contoso.net è il pool legacy e tutti e sei gli utenti sono connessi al pool. Utilizzare le procedure seguenti per spostare un utente nel pool di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752508"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="56b24-105">Spostare un singolo utente nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="56b24-105">Move a single user to the pilot pool</span></span>

<span data-ttu-id="56b24-106">È possibile spostare un utente dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="56b24-106">You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span> <span data-ttu-id="56b24-107">Nell'esempio riportato di seguito, nella colonna **pool di registrazione** , **pool01.contoso.NET** è il pool legacy e tutti e sei gli utenti sono connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="56b24-107">In the example below, in the **Registrar pool** column, **pool01.contoso.net** is the legacy pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="56b24-108">Utilizzare le procedure seguenti per spostare un utente nel pool di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="56b24-108">Use the following procedures to move a user to your Skype for Business Server 2019 pool using Skype for Business Server 2019 Control Panel and Skype for Business Server Management Shell.</span></span> 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="56b24-109">Per spostare un utente utilizzando il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="56b24-109">To move a user by using the Skype for Business Server 2019 Control Panel</span></span>
  
1. <span data-ttu-id="56b24-110">Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="56b24-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="56b24-111">Aprire il **Pannello di controllo di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="56b24-111">Open **Skype for Business Server Control Panel**.</span></span>
    
3. <span data-ttu-id="56b24-112">Fare clic su **utenti**, fare clic su **Cerca**e quindi su **trova**.</span><span class="sxs-lookup"><span data-stu-id="56b24-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
4. <span data-ttu-id="56b24-113">Selezionare un utente che si desidera spostare nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56b24-113">Select a user that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="56b24-114">In questo esempio, sposteremo l'utente Sara Davis.</span><span class="sxs-lookup"><span data-stu-id="56b24-114">In this example, we will move user Sara Davis.</span></span>
    
5. <span data-ttu-id="56b24-115">Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="56b24-115">On the **Action** menu, select **Move selected users to pool**.</span></span>
    
6. <span data-ttu-id="56b24-116">Nell'elenco a discesa selezionare il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56b24-116">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
7. <span data-ttu-id="56b24-117">Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**.</span><span class="sxs-lookup"><span data-stu-id="56b24-117">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="56b24-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="56b24-118">Click **OK**.</span></span>
  
8. <span data-ttu-id="56b24-119">Verificare che la colonna **pool di registrazione** per l'utente contenga ora il pool di Skype for Business Server 2019, che indica che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="56b24-119">Verify that the **Registrar pool** column for the user now contains the Skype for Business Server 2019 pool, which indicates that the user has been successfully moved.</span></span> 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="56b24-120">Per spostare un utente tramite la shell di gestione di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="56b24-120">To move a user by using the Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="56b24-121">Aprire la shell di gestione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="56b24-121">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="56b24-122">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="56b24-122">At the command line, type the following:</span></span> 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. <span data-ttu-id="56b24-123">Nella riga di comando, digitare quindi quanto segue:</span><span class="sxs-lookup"><span data-stu-id="56b24-123">Next, at the command line, type the following:</span></span> 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. <span data-ttu-id="56b24-124">L'identità di **RegistrarPool** punta ora al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56b24-124">The **RegistrarPool** identity now points to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="56b24-125">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="56b24-125">The presence of this identity confirms that the user has been successfully moved.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="56b24-126">Per informazioni dettagliate sul cmdlet **Get-CsUser** , eseguire: **Get-Help Get-CsUser-detailed**</span><span class="sxs-lookup"><span data-stu-id="56b24-126">For details about the **Get-CsUser** cmdlet, run: **Get-Help Get-CsUser -Detailed**</span></span>
  

