---
title: Verificare la replica della preparazione della foresta
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:'
ms.openlocfilehash: 31164e51cd3de60ce25313f726fc9c7ba086f299
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738542"
---
# <a name="verify-replication-of-forest-preparation"></a>Verificare la replica della preparazione della foresta
 
Per verificare che sia stata eseguita la replica del catalogo globale e la creazione degli oggetti durante la preparazione della foresta, eseguire le operazioni seguenti:
  
1. In un controller di dominio, preferibilmente in un sito remoto degli altri controller di dominio, aprire **Utenti e computer di Active Directory** nella foresta in cui è stata eseguita la relativa preparazione.
    
2. In **Utenti e computer di Active Directory** espandere il nome di dominio della foresta o di un dominio figlio.
    
3. Fare clic **sul** contenitore Utenti nel riquadro sinistro e cercare il gruppo universale CsAdministrator nel riquadro a destra. Se CsAdministrator (tra gli altri otto nuovi gruppi universali che iniziano con Cs), la replica della preparazione della foresta ha avuto esito positivo.
    
4. Se il gruppo o i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare la visualizzazione del riquadro destro. La replica è completata quando i gruppi risultano presenti.
    
> [!TIP]
> Se si desidera esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

