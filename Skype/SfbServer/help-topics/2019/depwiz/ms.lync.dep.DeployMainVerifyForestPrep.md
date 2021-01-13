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
# <a name="verify-replication-of-forest-preparation"></a>Verificare la replica della preparazione della foresta
 
Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:
  
1. In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.
    
2. In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.
    
3. Fare clic sul contenitore **utenti** nel riquadro sinistro e cercare il gruppo universale CsAdministrator nel riquadro a destra. Se CsAdministrator (tra otto nuovi gruppi universali che iniziano con CS) è presente, la replica della preparazione della foresta ha avuto esito positivo.
    
4. Se il gruppo o i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare la visualizzazione del riquadro destro. La replica è completata quando i gruppi risultano presenti.
    
> [!TIP]
> Se si desidera esaminare i file di registro creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di registro sono disponibili in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

