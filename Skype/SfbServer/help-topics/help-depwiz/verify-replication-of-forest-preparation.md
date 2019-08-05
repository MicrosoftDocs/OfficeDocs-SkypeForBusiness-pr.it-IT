---
title: Verificare la replica della preparazione della foresta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Per verificare che la replica del catalogo globale e la creazione di oggetti durante la preparazione della foresta abbiano avuto esito positivo, eseguire le operazioni seguenti:'
ms.openlocfilehash: ae6d068521f7b2e6038d05545da16be11c51cf18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191459"
---
# <a name="verify-replication-of-forest-preparation"></a>Verificare la replica della preparazione della foresta
 
Per verificare che la replica del catalogo globale e la creazione di oggetti durante la preparazione della foresta abbiano avuto esito positivo, eseguire le operazioni seguenti:
  
1. In un controller di dominio (preferibilmente in un sito remoto dagli altri controller di dominio), nella foresta in cui è stata eseguita la preparazione della foresta, aprire **utenti e computer di Active Directory**.
    
2. In **utenti e computer di Active Directory**espandere il nome di dominio della foresta o di un dominio figlio.
    
3. Fare clic sul contenitore **utenti** nel riquadro sinistro e cercare il gruppo universale CsAdministrator nel riquadro destro. Se è presente CsAdministrator (tra otto altri nuovi gruppi universali che iniziano con CS), la replica della preparazione della foresta è stata completata.
    
4. Se il gruppo o i gruppi non sono ancora presenti, è possibile forzare la replica o attendere 15 minuti e aggiornare il riquadro laterale destro. Quando i gruppi sono presenti, la replica viene completata.
    
> [!TIP]
> Se si vogliono rivedere i file di log creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di log si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

