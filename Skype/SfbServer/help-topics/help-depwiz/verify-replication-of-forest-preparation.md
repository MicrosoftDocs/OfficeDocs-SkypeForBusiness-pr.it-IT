---
title: Verificare la replica della preparazione della foresta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Per verificare che la replica del catalogo globale e la creazione di oggetti durante la preparazione della foresta abbiano avuto esito positivo, eseguire le operazioni seguenti:'
ms.openlocfilehash: 4f17b62fd0756019bab105df323215571557dce2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700651"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="74e7e-103">Verificare la replica della preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="74e7e-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="74e7e-104">Per verificare che la replica del catalogo globale e la creazione di oggetti durante la preparazione della foresta abbiano avuto esito positivo, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74e7e-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="74e7e-105">In un controller di dominio (preferibilmente in un sito remoto dagli altri controller di dominio), nella foresta in cui è stata eseguita la preparazione della foresta, aprire **utenti e computer di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="74e7e-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="74e7e-106">In **utenti e computer di Active Directory**espandere il nome di dominio della foresta o di un dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="74e7e-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="74e7e-107">Fare clic sul contenitore **utenti** nel riquadro sinistro e cercare il gruppo universale CsAdministrator nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="74e7e-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="74e7e-108">Se è presente CsAdministrator (tra otto altri nuovi gruppi universali che iniziano con CS), la replica della preparazione della foresta è stata completata.</span><span class="sxs-lookup"><span data-stu-id="74e7e-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="74e7e-109">Se il gruppo o i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare il riquadro laterale destro.</span><span class="sxs-lookup"><span data-stu-id="74e7e-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="74e7e-110">Quando i gruppi sono presenti, la replica viene completata.</span><span class="sxs-lookup"><span data-stu-id="74e7e-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="74e7e-111">Se si vogliono rivedere i file di log creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di servizi di dominio Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="74e7e-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="74e7e-112">Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di log si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="74e7e-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

