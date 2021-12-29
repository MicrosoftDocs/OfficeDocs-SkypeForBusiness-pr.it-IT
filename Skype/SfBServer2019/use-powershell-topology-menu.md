---
title: Usare PowerShell per le attività del menu Topologia
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 'Riepilogo: Skype for Business Server pannello di controllo al menu Mapping cmdlet per topologia.'
ms.openlocfilehash: da5374863d7b9e7c8217802ce98e10cfdab92e54
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626227"
---
# <a name="topology"></a>Topologia

In questo articolo viene descritto come ottenere risultati simili a quelli della voce **di** menu Topologia nel Pannello di controllo legacy utilizzando i cmdlet.

In questo articolo vengono descritti i sottomenu seguenti:

- [Topologia](#topology)
  - [Stato](#status)
  - [Applicazione server](#server-application)
  - [URL semplice](#simple-url)
  - [Applicazione attendibile](#trusted-application)

## <a name="status"></a>Stato

**Il** sottomenu STATUS consente agli amministratori di gestire i computer nella topologia.

Prendere in considerazione le varie attività che un utente può eseguire su **STATUS** e i cmdlet Skype for Business a cui tali attività sono mappate.

---

> **Scenario 1:** elencare tutti i computer e il relativo stato

   ![Elenca computer e stato](./media/topology-status-1.png)

   ***Cmdlet***

   [Get-CsPool](/powershell/module/skype/get-cspool)

   ***Esempio***

   ```powershell
    Get-CsPool
   ```

   ***Cmdlet***

   [Get-CsComputer](/powershell/module/skype/get-cscomputer)

   ***Esempio***

   ```powershell
    Get-CsComputer
   ```

   ***Cmdlet***

   [Get-CsManagementStoreReplicationStatus](/powershell/module/skype/get-csmanagementstorereplicationstatus)

   ***Esempio***

   ```powershell
   Get-CsManagementStoreReplicationStatus
   ```

---

## <a name="server-application"></a>Applicazione server

Le applicazioni server fanno riferimento ai singoli programmi eseguiti in Skype for Business Server. **Il sottomenu SERVER APPLICATION** consente agli amministratori di restituire informazioni su una o tutte le applicazioni in esecuzione come parte di Skype for Business Server.

Prendere in considerazione le varie attività che un utente può eseguire in **SERVER APPLICATION** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le applicazioni server

   ![Applicazione server di elenco](./media/server-application-1.png)

***Cmdlet***

[Get-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Esempio***

```powershell
 Get-CsServerApplication
```

---

> **Scenario 2:** abilitare/disabilitare o selezionare critico/ deselezionare critico un'applicazione server

   ![Modifica applicazione server](./media/server-application-2.png)

***Cmdlet***

[Set-CsServerApplication](/powershell/module/skype/get-csserverapplication)

***Esempio***

```powershell
 Set-CsServerApplication -Identity "Registrar:atl-cs-001.litwareinc.com/ExumRouting" -Enabled $True
```

---

## <a name="simple-url"></a>URL semplice

Gli URL semplici semplificano la partecipazione degli utenti a riunioni e conferenze e facilitano l'accesso degli amministratori al Pannello di controllo di Skype for Business Server.Il sottomenu **URL SEMPLICE** consente all'amministratore di visualizzarle.

Prendiamo in considerazione le varie attività che un utente può eseguire su **SIMPLE URL** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le configurazioni degli URL semplici

   ![URL semplice elenco](./media/simple-url-1.png)

***Cmdlet***

[Get-CsSimpleUrlConfiguration](/powershell/module/skype/get-cssimpleurlconfiguration)

***Esempio***

```powershell
 Get-CsSimpleUrlConfiguration | Select-Object -ExpandProperty SimpleUrl
```

---

## <a name="trusted-application"></a>Applicazione attendibile

Un'applicazione attendibile è un'applicazione sviluppata da terze parti a cui viene assegnato lo stato attendibile per l'esecuzione come parte di Skype for Business Server ma che non è una parte incorporata del prodotto. Il **sottomenu APPLICAZIONE** ATTENDIBILE consente all'amministratore di visualizzarli.

Prendere in considerazione le varie attività che un utente può eseguire su **TRUSTED APPLICATION** e i cmdlet Skype for Business a cui tali attività sono mappate.

---
> **Scenario 1:** elencare tutte le applicazioni attendibili

   ![Elenco applicazioni attendibili](./media/trusted-application-1.png)

***Cmdlet***

[Get-CsTrustedApplication](/powershell/module/skype/get-cstrustedapplication)

***Esempio***

```powershell
 Get-CsTrustedApplication
```

---
