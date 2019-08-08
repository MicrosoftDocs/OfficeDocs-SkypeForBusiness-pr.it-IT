---
title: Trasferire più utenti nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: È possibile trasferire più utenti dal pool legacy al pool pilota di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.
ms.openlocfilehash: 6c6f61287cfc75b7500317d62de4ea846af1abd3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244820"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a><span data-ttu-id="7939c-103">Trasferire più utenti nel pool pilota</span><span class="sxs-lookup"><span data-stu-id="7939c-103">Move multiple users to the pilot pool</span></span>

<span data-ttu-id="7939c-104">È possibile trasferire più utenti dal pool legacy al pool pilota di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7939c-104">You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.</span></span>

 <span data-ttu-id="7939c-105">**In questo articolo**</span><span class="sxs-lookup"><span data-stu-id="7939c-105">**In this article**</span></span>
  
[<span data-ttu-id="7939c-106">Per trasferire più utenti tramite il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7939c-106">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection0)
  
[<span data-ttu-id="7939c-107">Per trasferire più utenti usando Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="7939c-107">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection1)
  
[<span data-ttu-id="7939c-108">Per trasferire tutti gli utenti contemporaneamente usando Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="7939c-108">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="7939c-109">Per trasferire più utenti tramite il pannello di controllo di Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7939c-109">To move multiple users by using the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="7939c-110"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7939c-110"></span></span>

1. <span data-ttu-id="7939c-111">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7939c-111">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="7939c-112">Fare clic su **utenti**, fare clic su **Cerca**e quindi su **trova**.</span><span class="sxs-lookup"><span data-stu-id="7939c-112">Click **Users**, click **Search**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="7939c-113">Selezionare due utenti che si desidera trasferire nel pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7939c-113">Select two users that you want to move to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="7939c-114">In questo esempio verranno spostati gli utenti Chen Yang e Claus Hansen.</span><span class="sxs-lookup"><span data-stu-id="7939c-114">In this example, we will move users Chen Yang and Claus Hansen.</span></span>
    
     ![Spostamento di utenti nel pool di registrazione specifico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. <span data-ttu-id="7939c-116">Nel menu **azione** selezionare Trasferisci **utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="7939c-116">From the **Action** menu, select **Move selected users to pool**.</span></span>
    
5. <span data-ttu-id="7939c-117">Nell'elenco a discesa selezionare il pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7939c-117">From the drop-down list, select the Skype for Business Server 2019 pool.</span></span>
    
6. <span data-ttu-id="7939c-118">Fare clic su **azione**e quindi su **Trasferisci utenti selezionati in pool**.</span><span class="sxs-lookup"><span data-stu-id="7939c-118">Click **Action**, and then click **Move selected users to pool**.</span></span> <span data-ttu-id="7939c-119">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7939c-119">Click **OK**.</span></span>
    
     ![Finestra di dialogo per lo spostamento di utenti nel pool di registrazione di destinazione](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. <span data-ttu-id="7939c-121">Verificare che la colonna del **pool** di registrar per gli utenti contenga ora il pool di Skype for Business Server 2019, che indica che gli utenti sono stati spostati correttamente.</span><span class="sxs-lookup"><span data-stu-id="7939c-121">Verify that the **Registrar pool** column for the users now contains the Skype for Business Server 2019 pool, which indicates that the users have been successfully moved.</span></span> 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="7939c-122">Per trasferire più utenti usando Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="7939c-122">To move multiple users by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="7939c-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7939c-123"></span></span>

1. <span data-ttu-id="7939c-124">Aprire Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7939c-124">Open the Skype for Business Server 2019 Management Shell.</span></span> 
    
2. <span data-ttu-id="7939c-125">Nella riga di comando digitare le opzioni seguenti e sostituire **User1** e **User2** con nomi utente specifici da trasferire e sostituire **pool_FQDN** con il nome del pool di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7939c-125">At the command line, type the following and replace **User1** and **User2** with specific user names you want to move, and replace **pool_FQDN** with the name of the destination pool.</span></span> <span data-ttu-id="7939c-126">In questo esempio verranno spostati gli utenti Hao Chen e Katie Jordan.</span><span class="sxs-lookup"><span data-stu-id="7939c-126">In this example we will move users Hao Chen and Katie Jordan.</span></span> 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Esempio di cmdlet Get-CsUser di PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. <span data-ttu-id="7939c-128">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7939c-128">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. <span data-ttu-id="7939c-129">L'identità del **pool di registrazione** deve ora puntare al pool specificato come **pool_FQDN** nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="7939c-129">The **Registrar Pool** identity should now point to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="7939c-130">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7939c-130">The presence of this identity confirms that the user has been successfully moved.</span></span> <span data-ttu-id="7939c-131">Ripetere il passaggio per verificare che **User2** sia stato spostato.</span><span class="sxs-lookup"><span data-stu-id="7939c-131">Repeat step to verify that **User2** has been moved.</span></span> 
    
     ![Output del cmdlet Get-UsUser-Identity di PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="7939c-133">Per trasferire tutti gli utenti contemporaneamente usando Skype for Business Server 2019 Management Shell</span><span class="sxs-lookup"><span data-stu-id="7939c-133">To move all users at the same time by using the Skype for Business Server 2019 Management Shell</span></span>
<span data-ttu-id="7939c-134"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7939c-134"></span></span>

<span data-ttu-id="7939c-135">In questo esempio tutti gli utenti sono stati restituiti al pool legacy (pool01.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="7939c-135">In this example, all users have been returned to the legacy pool (pool01.contoso.net).</span></span> <span data-ttu-id="7939c-136">Usando Skype for Business Server 2019 Management Shell, sposteremo tutti gli utenti contemporaneamente al pool Skype for Business Server 2019 (pool02.contoso.net).</span><span class="sxs-lookup"><span data-stu-id="7939c-136">Using the Skype for Business Server 2019 Management Shell, we will move all users at the same time to the Skype for Business Server 2019 pool (pool02.contoso.net).</span></span>
  
1. <span data-ttu-id="7939c-137">Aprire Skype for Business Server 2019 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7939c-137">Open the Skype for Business Server 2019 Management Shell.</span></span>
    
2. <span data-ttu-id="7939c-138">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7939c-138">At the command line, type the following:</span></span> 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet di PowerShell e risultati in Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. <span data-ttu-id="7939c-140">Eseguire **Get-CsUser** per uno degli utenti pilota.</span><span class="sxs-lookup"><span data-stu-id="7939c-140">Run **Get-CsUser** for one of the pilot users.</span></span> 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. <span data-ttu-id="7939c-141">L'identità del **pool** di registrar per ogni utente ora punta al pool specificato come **pool_FQDN** nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="7939c-141">The **Registrar Pool** identity for each user now points to the pool you specified as **pool_FQDN** in the previous step.</span></span> <span data-ttu-id="7939c-142">La presenza di questa identità conferma che l'utente è stato spostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7939c-142">The presence of this identity confirms that the user has been successfully moved.</span></span> 
    
5. <span data-ttu-id="7939c-143">Inoltre, è possibile visualizzare l'elenco degli utenti nel pannello di controllo di Skype for Business Server 2019 e verificare che il valore del pool di registrazione punti ora al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7939c-143">Additionally, we can view the list of users in the Skype for Business Server 2019 Control Panel and verify that the Registrar Pool value now points to the Skype for Business Server 2019 pool.</span></span>
    
     ![Elenco utenti del pannello di controllo di Skype for Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

