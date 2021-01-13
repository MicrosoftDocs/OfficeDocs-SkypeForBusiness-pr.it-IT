---
title: Verificare la replica della preparazione della foresta
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:'
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801596"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="d66de-103">Verificare la replica della preparazione della foresta</span><span class="sxs-lookup"><span data-stu-id="d66de-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="d66de-104">Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d66de-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="d66de-105">In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.</span><span class="sxs-lookup"><span data-stu-id="d66de-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="d66de-106">In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.</span><span class="sxs-lookup"><span data-stu-id="d66de-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="d66de-107">Fare clic sul contenitore **utenti** nel riquadro sinistro e cercare il gruppo universale CsAdministrator nel riquadro a destra.</span><span class="sxs-lookup"><span data-stu-id="d66de-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="d66de-108">Se CsAdministrator (tra otto nuovi gruppi universali che iniziano con CS) è presente, la replica della preparazione della foresta ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d66de-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="d66de-p102">Se il gruppo o i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare la visualizzazione del riquadro destro. La replica è completata quando i gruppi risultano presenti.</span><span class="sxs-lookup"><span data-stu-id="d66de-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="d66de-111">Se si desidera esaminare i file di registro creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di servizi di dominio Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="d66de-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="d66de-112">Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di registro sono disponibili in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="d66de-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

