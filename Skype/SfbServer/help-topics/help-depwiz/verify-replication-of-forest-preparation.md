---
title: Verificare la replica della preparazione della foresta
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:'
ms.openlocfilehash: 304513bbae1e27224172c3efc638825c22a1f2d8f6ce2b4d83085d6b0b38a226
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347032"
---
# <a name="verify-replication-of-forest-preparation"></a>Verificare la replica della preparazione della foresta
 
Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:
  
1. In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.
    
2. In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.
    
3. Fare clic **sul** contenitore Utenti nel riquadro sinistro e cercare il gruppo universale CsAdministrator nel riquadro a destra. Se CsAdministrator (tra gli altri otto nuovi gruppi universali che iniziano con Cs), la replica della preparazione della foresta ha avuto esito positivo.
    
4. Se il gruppo o i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare la visualizzazione del riquadro destro. La replica è completata quando i gruppi risultano presenti.
    
> [!TIP]
> Se si desidera esaminare i file di registro creati dalla Distribuzione guidata Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

